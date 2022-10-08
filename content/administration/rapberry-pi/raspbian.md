---
title: "Raspbian"
date: 2022-10-09T01:40:26+03:00
tags: [администрирование, "Rapberry Pi"]
---

Различная информация об операционной системе Raspbian для Raspberry Pi

{{< toc >}}

[Официальная документация](https://www.raspberrypi.org/documentation/).

## Настройки

Некоторые критичные настройки делаются при помощи утилиты [raspi-config](https://www.raspberrypi.org/documentation/configuration/raspi-config.md).
Она предоставляет графический консольный интерфейс для удобной настройки.

### Включение ssh

После установки операционной системы Raspbian по-умолчанию демон ssh отключен. Чтобы его включить надо выполнить следующие действия (информация взята с [официального сайта](https://www.raspberrypi.org/documentation/remote-access/ssh/#)):

1. Запустить raspi-config в терминале: {{sudo raspi-config}}.
1. Выбрать `Interfacing Options`.
1. Выбрать `SSH`.
1. Потом `Yes`.
1. Нажать `Ok`.
1. И, наконец - `Finish`.
