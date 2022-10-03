---
title: "Установка Firefox из репозитория"
date: 2022-10-03T12:59:56+03:00
tags: ["linux", "firefox"]
---

1. Удалите Firefox Snap, выполнив следующую команду в новом окне терминала:

    ```bash
    sudo snap remove firefox
    ```

2. Добавить PPA команды (Ubuntu) Mozilla в список источников программного обеспечения, выполнив следующую команду в том же окне терминала

    ```bash
    sudo add-apt-repository ppa:mozillateam/ppa
    ```

3. Изменить приоритет пакета Firefox, чтобы предпочтительнее использовать версию Firefox PPA/deb/apt. Это можно сделать с помощью [фрагмента кода из FosTips](https://fostips.com/ubuntu-21-10-two-firefox-remove-snap) (скопируйте и вставьте его целиком, а не построчно)

    ```bash
    echo '
    Package: *
    Pin: release o=LP-PPA-mozillateam
    Pin-Priority: 1001
    ' | sudo tee /etc/apt/preferences.d/mozilla-firefox
    ```

4. Поскольку вы (надеюсь) хотите, чтобы будущие обновления Firefox устанавливались автоматически, [Балинт Речей поделился в своем блоге краткой командой](https://balintreczey.hu/blog/firefox-on-ubuntu-22-04-from-deb-not-from-snap/), которая гарантирует, что это произойдет:

    ```bash
    echo 'Unattended-Upgrade::Allowed-Origins:: "LP-PPA-mozillateam:${distro_codename}";' | sudo tee /etc/apt/apt.conf.d/51unattended-upgrades-firefox
    ```

5. Наконец, установите Firefox через apt, выполнив эту команду:

    ```bash
    sudo apt install firefox
    ```
