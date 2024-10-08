# Примеры и случаи использования

## Оглавление

1. [Сценарий 1: Поиск пути на небольшой карте с препятствиями](#Сценарий-1-Поиск-пути-на-небольшой-карте-с-препятствиями)
2. [Сценарий 2: Поиск пути на большой карте с высоким уровнем препятствий](#Сценарий-2-Поиск-пути-на-большой-карте-с-высоким-уровнем-препятствий)
3. [Сценарий 3: Поиск пути при низкой вероятности появления препятствий](#Сценарий-3-Поиск-пути-при-низкой-вероятности-появления-препятствий)
4. [Сценарий 4: Динамическое изменение карты](#Сценарий-4-Динамическое-изменение-карты)

## Сценарий 1: Поиск пути на небольшой карте с препятствиями

**Описание**:
Рассмотрим ситуацию, в которой робот перемещается по карте размером `10x10` с вероятностью появления стен `wall_chance=0.2`. Начальная точка находится в левом верхнем углу, а цель — в правом нижнем углу. Робот должен найти оптимальный маршрут, обходя препятствия. Этот сценарий демонстрирует работу системы в условиях средней сложности, когда препятствий не слишком много, но и не слишком мало, что позволяет оценить базовые возможности алгоритма A\*.

```Python
mappy = generate_map(10, 10, 0.2)
```

## Сценарий 2: Поиск пути на большой карте с высоким уровнем препятствий

**Описание**:
В этом сценарии рассмотрим карту размером `50x50`, где вероятность появления стен составляет `wall_chance=0.5`. Эта ситуация моделирует сложные условия с большим количеством препятствий, что затрудняет нахождение пути. Робот должен попытаться найти маршрут, несмотря на высокий уровень препятствий. Этот сценарий демонстрирует, насколько эффективен алгоритм A\* при работе в условиях высокой сложности, когда препятствий много и вероятность их обхода уменьшается.

```Python
mappy = generate_map(50, 50, 0.5)
```

## Сценарий 3: Поиск пути при низкой вероятности появления препятствий

**Описание**:
В этом сценарии робот перемещается по карте размером `20x20` с вероятностью появления стен `wall_chance=0.1`. Это упрощенная ситуация, в которой на карте мало препятствий, что позволяет роботу найти путь с минимальным количеством поворотов. Такой сценарий подходит для тестирования алгоритма в идеальных условиях, когда препятствия почти отсутствуют, что дает представление о максимально возможной эффективности маршрута.

```Python
mappy = generate_map(20, 20, 0.1)
```

## Сценарий 4: Динамическое изменение карты

**Описание**:
В этом сценарии после генерации карты размером `30x30` с вероятностью появления стен `wall_chance=0.3` выполняется динамическое изменение карты — добавление новых препятствий или удаление существующих. Затем робот пытается найти путь в обновленных условиях. Данный сценарий демонстрирует, как система справляется с изменениями в среде, и может быть полезен для моделирования реальной динамической среды, например, когда неожиданно появляются новые объекты или препятствия.

```Python
# Генерация карты
mappy = generate_map(30, 30, 0.3)

# Добавление динамических изменений - добавляем новые стены
mappy[10:15, 10:15] = 1  # Добавляем стену в центре карты
```

[К началу](../../README.md)
