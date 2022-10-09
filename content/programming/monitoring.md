---
title: "Мониторинг"
date: 2022-10-09T15:30:44+03:00
tags: [программирование, мониторинг, программы, ссылки]
---

{{< toc >}}

## Prometheus

[Сайт](https://prometheus.io)

[Официальная документация](https://prometheus.io/docs/introduction/overview). Информация по [запросам](https://prometheus.io/docs/prometheus/latest/querying/basics).

[Блог](https://www.robustperception.io/blog) создателей [Prometheus](https://prometheus.io) со всякой полезной информацией.

### Вычисление процентов загрузки CPU на основании времени использования

Информация взята из [understanding-machine-cpu-usage](https://www.robustperception.io/understanding-machine-cpu-usage) блога разработчиков [Prometheus](https://prometheus.io).

При использовании [node_exporter](https://github.com/prometheus/node_exporter):

```prometheus
100 - (avg by (instance) (irate(node_cpu_seconds_total{job="node",mode="idle"}[5m])) * 100)
```

где **node** - имя node_exporter, заданное в настройках Prometheus.

Для метрик, взятых из прочих экспортёров, где подсчитывается только время затраченное экспортером в секундах:

```prometheus
(avg by (job) (irate(process_cpu_seconds_total[5m])) * 100)
```

## Checkup

[Официальный сайт](https://sourcegraph.github.io/checkup).

Simple uptime monitoring.
Исходники на [Github](https://github.com/sourcegraph/checkup).

## Pyroscope

[Официальный сайт](https://pyroscope.io). [Github](https://github.com/pyroscope-io/pyroscope)

Online мониторинг программ на GO, Python и Ruby. В дальнейшем планируется Node и linux eBPF.
