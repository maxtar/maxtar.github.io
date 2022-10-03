---
title: "Общие вопросы"
date: 2022-10-01T21:24:41+03:00
---

{{< toc >}}

## Сети

[Сети для самых маленьких](https://linkmeup.ru/blog/11.html).

## Конвертация сертификата из cer формата в pem

### Сохранение клиентского ключа

```bash
openssl pkcs12 -in client_ssl.pfx -out client_ssl.pem -clcerts
```

### Сохранение корневого ключа

```bash
openssl pkcs12 -in client_ssl.pfx -out root.pem -cacerts
```

### Сохранение в один файл, который содержит и ключ и сертификат

```bash
openssl pkcs12 -in source.pfx -out dest.pem -nodes
```

### Сохранение информации в отдельные файлы

#### Сохранение частного ключа

```bash
openssl pkcs12 -in source.pfx -nocerts -out key.pem
```

#### Сохранение только сертификата

```bash
openssl pkcs12 -in source.pfx -clcerts -nokeys -out cert.pem
```

#### Удаление пароля из файла с ключом

```bash
openssl rsa -in key.pem -out client.key
```

#### Сохранение доверенных сертификатов из цепочки

```bash
openssl pkcs12 -in source.pfx -out ca.pem -cacerts -nokeys
```
