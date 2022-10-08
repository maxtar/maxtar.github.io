---
title: "Разные вопросы по renderman"
date: 2022-10-08T20:29:42+03:00
tags: [renderman, blender]
---

{{< toc >}}

## Установка в ubuntu

1. Скачать установщик.
1. Преобразовать в deb формат командой

    ```bash
    alien -c renderman-installer...rpm
    ```

1. На выходе получится .deb файл. Дальше его установить как обычно:

    ```bash
    sudo dpkg -i renderman-installer...deb
    ```

1. Если в процессе не запустится установщик сервера:

    ```bash
    cd /opt/pixar/RenderMan-Installer-ncr-<version>/bin
    sudo ./RenderManInstaller
    ```

## Решение проблем с лицензией в windows

[Скачать](https://renderman.pixar.com/forum/ncrdownload.php) установщик RenderMan.

В случае, если установка производится не в каталог `c:\Program File\Pixar` могут возникнуть проблема с запуском движка RenderMan.

Если в Blender возникает ошибка `PRMan: Exited` необходимо сделать следующее. Данная ошибка возникает из-за того, что сам движок установщик всё равно ставит в `Program files`, но не копирует туда файл лицензии.

Допустим, установщик находится в каталоге `d:\pixar\RenderMan-Installer-ncr-21.2`.

Чтобы ошибка пропала, необходимо скопировать файл лицензии `pixar.license` из каталога `d:\pixar`, где находится установщик, в каталог `c:\Program File\Pixar`.
