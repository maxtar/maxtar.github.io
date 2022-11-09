---
title: "iptables"
date: 2022-11-08T17:01:34+03:00
tags: [linux]
---

Различные настройки iptables

{{< toc >}}

* [Полезные примеры](http://vasilisc.com/21-examples-iptables).

## MASQUERADE

```bash
iptables -t nat -A POSTROUTING -o eth0 -s 192.168.0.0/24 -j MASQUERADE
```

## Разрешить подключения к нужным портам

```bash
iptables -A INPUT -p tcp --dport 22 -j ACCEPT
```

где **22** - это порт, который надо открыть

## Все входящие запрещены

```bash
iptables -P INPUT DROP
```

{{< hint type=important title="Внимание" >}}
Для того, чтобы при этом работали локальные подключения надо добавить следующее правило:

```bash
iptables -A INPUT -i lo -j ACCEPT
```

{{< /hint >}}

## Разрешить уже установленные соединения

```bash
iptables -A INPUT -m state --state RELATED,ESTABLISHED -j ACCEPT
```

## Разрешить ping

```bash
iptables -A INPUT -p icmp --icmp-type echo-request -j ACCEPT
iptables -A OUTPUT -p icmp --icmp-type echo-reply -j ACCEPT
```

Информация взята [отсюда](https://linux-notes.org/razreshit-zablokirovat-ping-icmp-pakety-v-unix-linux).

## Сохранение настроек между запусками

Удобно использовать пакет *iptables-persistent*.

Для Debian-based дистрибутивов:

```bash
sudo apt install iptables-persistent
```

После установки автоматически будут сохранены текущие настройки в файлах:

* /etc/iptables/rules.v4
* /etc/iptables/rules.v6

В дальнейшем, в случае сохранения новых правил надо выполнить команду:

```bash
sudo iptables-save > /etc/iptables/rules.v4
```

или

```bash
sudo ip6tables-save > /etc/iptables/rules.v6
```
