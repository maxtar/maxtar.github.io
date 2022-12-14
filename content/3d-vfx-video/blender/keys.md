---
title: "Полезные команды и клавиатурные сокращения Blender"
date: 2022-10-05T02:17:22+03:00
tags: [blender]
---

## Выравнивание одного объекта относительно другого

**Клавиши**: `ctrl+alt+space`.

Необходимо выбрать, например, грань объекта, относительно какого нужно выравнивать, затем нажать `ctrl+alt+space`. В списке _transform orientation_ появится новая привязка.
Затем выбираем второй объект и его координаты перемещения будут рассчитываться относительно этого объекта.

------

## Сдвинуть вершины относительно координат

**Команда**: Shear.

**Клавиши**: `Shift+Ctrl+Alt+S`.

Выделяем точки, которые хотим сдвинуть линейно, как будто вращением. Нажимаем  `Shift+Ctrl+Alt+S` или ищем команду через поиск (`Space`). Выбираем ось, относительно которой поворачивать (`x` или `y`). Двигаем мышку до тех пор, пока точки не повернуться на нужный угол.

------

## "Проткнуть" грань

**Команда**: Poke.

**Клавиши**: `alt+p`

Выделяем грань, которую хотим подразделить. Нажимаем `alt+p`.

------

## Выбор связанного объекта, который является частью другого

**Клавиша**: `ctrl+L`.

Допустим в режиме редактирования к одному объекту был добавлен другой. Чтобы выделить все вершины данного объекта, нужно выделить вершину, грань, петлю данного объекта и нажать `ctrl+L`.
Также можно несколько раз нажимать просто `L`.

------

## Отделить часть объекта в качестве нового объекта

**Клавиша**: `P`.

В режиме редактирования выбрать необходимую часть объекта и нажать `P`. В открывшемся меню выбрать нужный режим (например, **by selection**).

------

## Периодическое выделение

**Клавиша**: `Ctrl+Shift+Num+`.

В режиме редактирования выбрать одну вершину, например. Потом выбрать вторую через необходимый интервал.

------

## Выделение по кратчайшему пути

**Клавиша**: `Ctrl+Click`.

Выделить одну вершину(ребро, грань). Кликнуть по второй вершине (ребру, грани). Произойдёт автоматическое выделение между двумя этими сущностями по кратчайшему пути.

------

## Создание ребра между двумя вершинами

**Клавиша**: `J`.

Выделить две вершины и нажать `J`.
