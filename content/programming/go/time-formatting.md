---
title: "Форматирование даты/времени"
date: 2022-10-02T14:06:07+03:00
tags: ["go", "программирование"]
---

{{< toc >}}

Информация взята [Format/parse a time or date](http://yourbasic.org/golang/format-parse-string-time-date-example)

## Простейший пример

Go, в отличие от других языков, использует свою нотацию для времени не `yyyy-MM-dd`. Go использует мнемоническую нотацию:

`Mon Jan 2 15:04:05 MST 2006`.

Её надо переписать в виде, котором надо. Проще всего это запомнить, если переписать её как `01/02 03:04:05PM ‘06 -0700`.

Например:

```go
const (
    layoutISO = "2006-01-02"
    layoutUS  = "January 2, 2006"
)
date := "1999-12-31"
t, _ := time.Parse(layoutISO, date)
fmt.Println(t)                  // 1999-12-31 00:00:00 +0000 UTC
fmt.Println(t.Format(layoutUS)) // December 31, 1999
```

Для форматировании времени применяются следующие методы из пакета [time.Time](https://golang.org/pkg/time/#Time):

* Метод [Format](https://golang.org/pkg/time/#Time.Format) для форматирования строки из времени.
* Функция [time.Parse](https://golang.org/pkg/time/#Parse) для получения даты из строки.

```go
func (t Time) Format(layout string) string
func Parse(layout, value string) (Time, error)
```

Стандартные форматы:

| Раскладка | Замечание |
| - | - |
|January 2, 2006 | Дата |
|01/02/06 | |
|Jan-02-06 | |
|15:04:05 | Время |
|3:04:05 PM | |
|Jan _2 15:04:05 | Timestamp |
|Jan _2 15:04:05.000000 | с микросекундами |
|2006-01-02T15:04:05-0700 | ISO 8601 (RFC 3339) |
|2006-01-02 | |
|15:04:05| |
|02 Jan 06 15:04 MST | RFC 822 |
|02 Jan 06 15:04 -0700 | с временной зоной |
|Mon, 02 Jan 2006 15:04:05 MST | RFC 1123 |
|Mon, 02 Jan 2006 15:04:05 -0700 | с временной зоной |

Также в пакете представлены следующие [константы](https://golang.org/pkg/time/#pkg-constants):

```txt
ANSIC       = "Mon Jan _2 15:04:05 2006"
UnixDate    = "Mon Jan _2 15:04:05 MST 2006"
RubyDate    = "Mon Jan 02 15:04:05 -0700 2006"
RFC822      = "02 Jan 06 15:04 MST"
RFC822Z     = "02 Jan 06 15:04 -0700"
RFC850      = "Monday, 02-Jan-06 15:04:05 MST"
RFC1123     = "Mon, 02 Jan 2006 15:04:05 MST"
RFC1123Z    = "Mon, 02 Jan 2006 15:04:05 -0700"
RFC3339     = "2006-01-02T15:04:05Z07:00"
RFC3339Nano = "2006-01-02T15:04:05.999999999Z07:00"
Kitchen     = "3:04PM"
// Handy time stamps.
Stamp      = "Jan _2 15:04:05"
StampMilli = "Jan _2 15:04:05.000"
StampMicro = "Jan _2 15:04:05.000000"
StampNano  = "Jan _2 15:04:05.000000000"
```

Опции форматирования:

| Тип | Опции |
| - | - |
| Год | 06 2006 |
| Месяц | 01 1 Jan January |
| День | 02 2 _2 (width two, right justified) |
| День недели | Mon Monday |
| Часы | 03 3 15 |
| Минуты | 04 4 |
| Секунды | 05 5 |
| мс мс нс | .000 .000000 .000000000 |
| мс мс нс | .999 .999999 .999999999 (trailing zeros removed) |
| am/pm | PM pm |
| Часовая зона | MST |
| Сдвиг часовой зоны | -0700 -07 -07:00 Z0700 Z07:00 |
