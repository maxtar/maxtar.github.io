---
title: "GdScript"
date: 2023-02-26T15:56:15+03:00
---

# Информация по языку программирования GdScript

## Простейший контроллер для управления камерой от первого лица

Этот код можно прицепить прямо к камере. В нём реализован поворот мышкой и перемещение вперёд, назад, влево, вправо.

```gdscript
extends Camera


# accumulators
var rot_x = 0 # сохраняет текущее вращение по оси X.
var rot_y = 0 # сохраняет текущее вращение по оси Y.

export var LOOKAROUND_SPEED = 0.01 # Скорости обзора.
export var MOVE_SPEED = 0.1 # Скорость перемещения.


func _physics_process(delta) -> void:
    if Input.is_action_pressed("ui_left"):
        translate_object_local(Vector3.LEFT * MOVE_SPEED)
    if Input.is_action_pressed("ui_right"):
        translate_object_local(Vector3.RIGHT * MOVE_SPEED)
    if Input.is_action_pressed("ui_up"):
        translate_object_local(Vector3(0, 0, -MOVE_SPEED))
    if Input.is_action_pressed("ui_down"):
        translate_object_local(Vector3(0, 0, MOVE_SPEED))


func _input(event) -> void:
    if event is InputEventMouseMotion and event.button_mask & 1:
        # modify accumulated mouse rotation
        rot_x += event.relative.x * LOOKAROUND_SPEED
        rot_y += event.relative.y * LOOKAROUND_SPEED
        transform.basis = Basis() # reset rotation
        rotate_object_local(Vector3(0, -1, 0), rot_x) # first rotate in Y
        rotate_object_local(Vector3(-1, 0, 0), rot_y) # then rotate in X

```

Можно взять готовый скрипт под godot 4 от [adamviola](https://github.com/adamviola/simple-free-look-camera).
