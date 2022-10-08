---
title: "Установка проприетарных драйверов NVidia"
date: 2022-10-08T20:52:28+03:00
tags: [linux, nvidia]
---


1. Добавить [этот](https://launchpad.net/~graphics-drivers/+archive/ubuntu/ppa) репозиторий.

    ```bash
    sudo add-apt-repository ppa:graphics-drivers/ppa
    sudo apt-get update
    ```

1. Поставить родные драйверы от NVIDIA:

    ```bash
    sudo apt-get install nvidia-<actual_number>
    ```

1. Удалить свободные драйвера для NVIDIA:

    ```bash
    sudo apt-get purge nouveau
    ```

1. Перегрузиться. Проверить, что в меню настроек появились настройки NVIDIA. Открыть, проверить, что видеокарта определилась нормально.

{{< hint type=tip >}}
Если после этого blender не определил видеокарту, нужно будет доставить `nvidia-cuda-toolkit`:

```bash
sudo apt-get install nvidia-cuda-toolkit
```

После этого должно всё заработать.
{{< /hint >}}
