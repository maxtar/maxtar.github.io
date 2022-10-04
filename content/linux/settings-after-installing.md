---
title: "Полезные установки"
date: 2022-10-05T01:47:02+03:00
tags: ["linux"]
---

{{< toc >}}

## Установка Oracle Java

Про разные способы установки написано [здесь](http://help.ubuntu.ru/wiki/java).
Чтобы установить родную Oracle Java необходимо добавить репозиторий **ppa:webupd8team/java** со скриптом установки:

```bash
sudo add-apt-repository ppa:webupd8team/java
sudo apt-get update
sudo apt-get install oracle-java8-installer
```

Во время установки потребуется принять лиценизию Oracle.

------

## Добавить переменную окружения в систему

Необходимо отредактировать файл {{/etc/profile}}.

```bash
JAVA_HOME=/usr/lib/jvm/jdk1.7.0_21
PATH=$PATH:$HOME/bin:$JAVA_HOME/bin
export JAVA_HOME
export JAVA_BIN
export PATH
```

Пользовательские программы копируются в {{/usr/local}}.

------

## Настройка GRUB

[Grub2-выбор OS по-умолчанию](http://ubuntologia.ru/blog/system/116.html)

------

## Чтобы отключить заставку при загрузке надо оставить

`GRUB_CMDLINE_LINUX_DEFAULT="quiet"`
в файле `/usr/share/grub/default/grub`.

Установка пакета разрешения зависимостей [Автоматическое разрешение зависимостей в Ubuntu](http://yahnev.ru/?p=2832)

------

### Чтобы подправить иконку в меню KDE

необходимо подправить соответствующий файл `.desktop` в `~/.local/share/applications`.

------

### Сброс мыши Microsoft после рестарта

Можно использовать утилиту [resetmsmice](https://sourceforge.net/projects/resetmsmice).

------

### Хранитель экрана

Установить следующей командой:

```bash
sudo apt install xscreensaver
```
