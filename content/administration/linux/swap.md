---
title: "Настройка swap"
date: 2022-10-08T20:33:35+03:00
tags: [linux, swap]
---

{{< toc >}}

## Процент, при котором информация из памяти скидывается в swap

[Информация взята отсюда](http://kubuntu.ru/node/13153)

Обычно рано или поздно у всех возникает вопрос: "Почему начинает заполнятся swap, когда у меня ещё много свободной оперативной памяти?". И вот тут нам приходит в помощь такой параметр, как `vm.swappiness`. Для начала в консоли выполним команду:

```bash
cat /proc/sys/vm/swappiness
```

По-умолчанию результат будет **60**.

Это параметр, который контролирует количество свободной памяти, при какой загруженности у нас начнётся сброс страниц в swap. Ну, а дальше простая формула: {{< katex >}}100\%-60\%=40\%{{< /katex >}}, т.е. уже при 40% загруженной ОЗУ данные начинают активно сливаться на жёсткий диск, что, как мне кажется, не есть хорошо. Чтобы сделать так, чтобы слив начался, хотя бы, при 90% занятой памяти нужно выполнить следующее.
Сначала в конфиг `/etc/sysctl.conf` добавим запись:

```bash
vm.swappiness=10
```

Затем, дабы не перезагружать комп, выполним с правами суперпользователя команду:

```bash
sysctl -p
```

Всё. На этом настройка закончена.

## Как задать нужный размер Swap-файла

Информация взята [отсюда](https://www.digitalocean.com/community/tutorials/how-to-add-swap-space-on-ubuntu-22-04).

1. Проверяем текущий файл

    ```bash
    sudo swapon --show
    ```

    Будет что-то типа этого:

    ```output
    NAME      TYPE SIZE USED PRIO
    /swapfile file   8G   2M   -2
    ```

    Также можно посмотреть следующей командой:

    ```bash
    free -h
    ```

    Вывод:

    ```output
                  total        used        free      shared  buff/cache   available
    Mem:          981Mi       122Mi       647Mi       0.0Ki       211Mi       714Mi
    Swap:         8,0Gi       2,0Mi       8,0Gi
    ```

2. Отключаем использования файла подкачки `/swapfile`

    ```bash
    sudo swapoff /swapfile 
    ```

3. Создаём файл нужного размера

    ```bash
    sudo fallocate -l 8G /swapfile
    ```

    После ключа `-l` задаём нужный размер файла подкачки.

4. Даём права только для пользователя **root**

    ```bash
    sudo chmod 600 /swapfile
    ```

    Проверяем командой `ls -lh /swapfile`. Должно быть следующее:

    ```output
    -rw------- 1 root root 8,0G авг 27 15:37 /swapfile
    ```

5. Активировать подкачки

    ```bash
    sudo mkswap /swapfile
    ```

    примерный вывод:

    ```output
    Setting up swapspace version 1, size = 8 GiB (8589934592 bytes)
    no label, UUID=6e965805-2ab9-450f-aed6-577e74089db
    ```

6. Включить подкачку

    ```bash
    sudo swapon /swapfile
    ```

    Проверяем, что всё успешно

    ```bash
    sudo swapon --show
    ```

    Должно быть как-то так:

    ```output
    NAME      TYPE SIZE USED PRIO
    /swapfile file   8G 2,8M   -2
    ```

7. Проверка, что файл подкачки активирован постоянно

    В файле `/etc/fstab` должны быть следующая строка:

    ```fstab
    /swapfile none swap sw 0 0
    ```

    Если нет - добавляем:

    ```bash
    echo '/swapfile none swap sw 0 0' | sudo tee -a /etc/fstab
    ```
