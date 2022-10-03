---
title: "Настройка hibernate на linux без использования swap раздела"
date: 2022-10-03T13:28:23+03:00
tags: ["linux"]
---

Взято [отсюда](https://ubuntuhandbook.org/index.php/2021/08/enable-hibernate-ubuntu-21-10).

Для начала надо проверить поддержку спящего режима:

```bash
systemctl hibernate
```

Если выдаётся ошибка типа `Failed to hibernate system via logind: Sleep verb “hibernate” not supported”`, то, скорее всего, в BIOS включён *secure boot*. Необходимо его отключить.

Современные дистрибутивы, как правило, используют swap файл, а не swap раздел.

## Настройка файла swap

### 1. Создать файл нужного раздела

```bash
sudo dd if=/dev/zero of=/swapfile count=16384 bs=1MiB
```

где:

- **bs** - размер блока.
- **count** - размер файла в количестве размера блока.

В данном примере размер файла будет равен 16 Гигабайт.

### 2. Дать нужные разрешения

```bash
sudo chmod 600 /swapfile
```

### 3. Указываем файл как swap

```bash
sudo mkswap /swapfile
```

### 4. Активировать swap

```bash
sudo swapon /swapfile
```

### 5. Добавить запись в fstab

Или проверить, что она там уже есть.

```bash
echo '/swapfile none swap sw 0 0' | sudo tee -a /etc/fstab
```

## Находим UUID диска и offset файла подкачки

Чтобы найти раздел root выполняем команду:

```bash
df -h
```

находим на какой раздел примонтирован корневой каталог. Например:

```bash
max@max-dell:~$ df -h
Файл.система   Размер Использовано  Дост Использовано% Cмонтировано в
tmpfs            1,6G         1,8M  1,6G            1% /run
/dev/sda2        468G          33G  412G            8% /
tmpfs            7,8G          32M  7,8G            1% /dev/shm
tmpfs            5,0M         4,0K  5,0M            1% /run/lock
/dev/sda1        511M          39M  473M            8% /boot/efi
tmpfs            1,6G          60K  1,6G            1% /run/user/1000

```

Видим, что корень примонтирован к разделу `/dev/sda2`.

Находим UUID диска командой `blkid`. Например:

```bash
max@max-dell:~$ blkid
/dev/sda2: UUID="9964c46d-d6d7-43c7-b9a9-5fb5844436aa" BLOCK_SIZE="4096" TYPE="ext4" PARTUUID="2ded6755-e0f2-4e2f-94b5-2273fc31f526"

```

Сохраняем в "блокноте" значение *UUID*.

Командой `sudo filefrag -v /swapfile` находим физическое смещение swap файла на диске:

```bash
max@max-dell:~$ sudo filefrag -v /swapfile
Filesystem type is: ef53
File size of /swapfile is 17179869184 (4194304 blocks of 4096 bytes)
 ext:     logical_offset:        physical_offset: length:   expected: flags:
   0:        0..    4095:    1916928..   1921023:   4096:            
   1:     4096..    8191:    1925120..   1929215:   4096:    1921024:

```

Нужно сохранить значение **1916928** - это физическое смешение файла.

## Настраиваем восстановление из файла подкачки в параметрах ядра

```bash
sudo vim /etc/default/grub
```

В параметр *GRUB_CMDLINE_LINUX_DEFAULT* добавляем следующую строку: `resume=UUID=xxx resume_offset=xxx`, где меняем соответствующие `xxx` на ранее сохранённые UUID диска и физическое смещение.
Например:

```grub
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash resume=UUID=9964c46d-d6d7-43c7-b9a9-5fb5844436aa resume_offset=1916928"
```

Обновляем конфигурацию grub:

```bash
sudo update-grub
```

После этого должно гибернация должна заработать, если нет, смотри дальше...

## Пересоздаём файлы initramfs

Создаём или открываем файл `/etc/initramfs-tools/conf.d/resume`:

```bash
sudo vim /etc/initramfs-tools/conf.d/resume
```

Вставляем в него такую же строчку:

```txt
RESUME=UUID=9964c46d-d6d7-43c7-b9a9-5fb5844436aa resume_offset=1916928
```

После сохранения файла пересоздадим initramfs:

```bash
sudo update-initramfs -c -k all
```

## Включение пункта "Спящий режим" в меню

Открываем или создаём следующий файл:

```bash
sudo vim /etc/polkit-1/localauthority/50-local.d/com.ubuntu.enable-hibernate.pkla
```

Вставляем в него следующее содержимое:

```ini
[Re-enable hibernate by default in upower]
Identity=unix-user:*
Action=org.freedesktop.upower.hibernate
ResultActive=yes

[Re-enable hibernate by default in logind]
Identity=unix-user:*
Action=org.freedesktop.login1.hibernate;org.freedesktop.login1.handle-hibernate-key;org.freedesktop.login1;org.freedesktop.login1.hibernate-multiple-sessions;org.freedesktop.login1.hibernate-ignore-inhibit
ResultActive=yes
```

После перезагрузки или перелогинивания должен появится пункт "Спящий режим".
