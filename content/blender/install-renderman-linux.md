---
title: "Как установить Renderman в Ubuntu"
date: 2022-10-08T20:29:42+03:00
tags: [renderman, blender]
---

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
