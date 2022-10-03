---
title: "C#"
date: 2022-10-03T21:59:43+03:00
---

Заметки по .NET

{{< toc >}}

## Вызов асинхронного метода из синхронного

```c#
var task = Task.Run(async () => await MyAsyncFunction())
task.Wait();
var asyncFunctionResult = task.Result;
```
