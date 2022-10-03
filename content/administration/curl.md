---
title: "Curl"
date: 2022-10-02T22:27:44+03:00
tags: ["администрирование"]
---

Полезная информация по работе с curl

## Использование клиентского сертификата для скачивания

```bash
curl -O https://url --cert cert.pem --key client.key --cacert ca.pem
```

## Ограничение скорости закачки

Ключ `--limit-rate <speed>`
Могут быть следующие суффиксы:

* "k", "K" - килобайты.
* "m", "M" - мегабайты.
* "g", "G" - гигабайты.

Например: 200K, 3m или 1G.

## Расширенное логирование

Для расширенного логирования необходимо добавить ключ `--trace`.
После ключа необходимо указать файл в который сохранять trace. Если вместо имени файла указать `-` то информация будет выводится в консоль.

## Вывод произвольной информации о загрузке

Для вывода произвольно информации применяется ключ `-w`.
Применяется следующим образом: `-w "Download time: %{time_total}, file size: %{size_download}, speed: %{speed_download}\n"`.
Могут использоваться следующие параметры:

| Параметр | Значение |
| - | - |
| **content_type** | the Content-Type value of the file |
| **http_code** | HTTP(S) code in the page |
| **http_connect** | HTTP code in the proxy response |
| **num_connects** | number of new connections made in the transfer |
| **num_redirects** | number of redirection operations that were made |
| **size_download** | total size of downloaded data |
| **size_header** | total size of the headers |
| **size_request** | total size of the request |
| **size_upload** | total size of uploaded data |
| **speed_download** | average download speed |
| **speed_upload** | average upload speed |
| **time_connect** | time from the start until the remote host connection was made |
| **time_namelookup** | time from the start of the command until name resolution was finished |
| **time_pretransfer** | time from the start until the file transfer was about to begin |
| **time_redirect** | time for all redirection operations |
| **time_starttransfer** | all pretransfer time plus the time needed to calculate the result |
| **time_total** | time for the complete operation (to the millisecond) |
| **url_effective** | the last URL fetched |
