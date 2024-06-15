---
title: "Установка Firefox из репозитория"
date: 2022-10-03T12:59:56+03:00
tags: [linux, firefox]
---

## От самой Mozilla

[Установка .deb-пакета Firefox для основанных на Debian дистрибутивов](https://support.mozilla.org/ru/kb/ustanovka-firefox-na-linux#w_ustanovka-deb-paketa-firefox-dlia-osnovannykh-na-debian-distributivov)

Чтобы установить пакет **.deb** из репозитория APT, сделайте следующее:

1. Создайте директорию для хранения ключей репозитория APT, если её ещё нет:

    ```bash
    sudo install -d -m 0755 /etc/apt/keyrings
    ```

2. Импортируйте подписанные ключи APT-репозитория Mozilla:

    ```bash
    wget -q https://packages.mozilla.org/apt/repo-signing-key.gpg -O- | sudo tee /etc/apt/keyrings/packages.mozilla.org.asc > /dev/null
    ```

3. Отпечаток должен быть таким: `35BAA0B33E9EB396F59CA838C0BA5CE6DC6315A3`. Вы можете проверить это с помощью следующей команды:

    ```bash
    gpg -n -q --import --import-options import-show /etc/apt/keyrings/packages.mozilla.org.asc | awk '/pub/{getline; gsub(/^ +| +$/,""); if($0 == "35BAA0B33E9EB396F59CA838C0BA5CE6DC6315A3") print "\nThe key fingerprint matches ("$0").\n"; else print "\nVerification failed: the fingerprint ("$0") does not match the expected one.\n"}'
    ```

4. Далее добавьте APT-репозиторий Mozilla к списку своих исходников:

    ```bash
    echo "deb [signed-by=/etc/apt/keyrings/packages.mozilla.org.asc] https://packages.mozilla.org/apt mozilla main" | sudo tee -a /etc/apt/sources.list.d/mozilla.list > /dev/null
    ```

5. Сконфигурируйте APT, чтобы приоритизировать пакеты из репозитория Mozilla:

    ```bash
    echo '
    Package: *
    Pin: origin packages.mozilla.org
    Pin-Priority: 1000
    ' | sudo tee /etc/apt/preferences.d/mozilla
    ```

6. Обновите список пакетов и установите .deb-пакет Firefox:

    ```bash
    sudo apt-get update && sudo apt-get install firefox
    ```

### Установка других языков в Firefox с помощью .deb-файлов

```bash
sudo apt-get install firefox-l10n-ru
```

Чтобы просмотреть список доступных языковых пакетов, вы можете использовать эту команду после добавления APT-репозитория Mozilla и запуска sudo apt-get update:

```bash
apt-cache search firefox-l10n
```

## Вариант с beta-версиями

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
