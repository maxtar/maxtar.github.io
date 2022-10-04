---
title: "Полезные функции"
date: 2022-10-05T01:42:05#03:00
tags: ["программирование", "c#"]
---

{{< toc >}}

## Преобразование числа в IP-адрес

```c#
new System.Net.IPAddress(36546)).ToString();
```

## Преобразование IP-адреса в число в прямом порядке (BE)

```c#
{
    byte[] ipNums = ip.Split('.').Select(s => byte.Parse(s)).ToArray();
    uint res = 0;

    res = res + ipNums[0] << 8;
    res = res + ipNums[1] << 8;
    res = res + ipNums[2] << 8;
    res = res + ipNums[3];
    return res;
}
```
