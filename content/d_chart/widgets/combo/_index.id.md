---
title: "Combo Chart"
date: 2023-08-17T17:10:57+07:00
---

<style>
table th:first-of-type {
    width: 33.3%;
}
table th:nth-of-type(2) {
    width: 33.3%;
}
table th:nth-of-type(3) {
    width: 33.3%;
}
</style>

Combo chart dibagi menjadi tipe domain Ordinal, Numeric, dan Time. Untuk bentuk chart nya dapat menggunakan bentuk line, bar, dan scatter plot. Ketiganya dapat digabungkan sekaligus maupun satuan.

<hr>
<br>

## Tutorial

1. [Get Started](https://youtu.be/5WQPkJDEzAQ)
2. [Domain Axis](https://youtu.be/N1BQdYgIBNQ)
3. [Measure Axis](https://youtu.be/JXD4WSe4dYs)
4. [Bar Style](https://youtu.be/gY0lrJz-RAo)
5. [Bar Label Value](https://youtu.be/mFtGkTmJa0M)
6. [Line Style](https://youtu.be/j9Nuwl1nYck)
7. [Scatter Plot Style](https://youtu.be/N1BQdYgIBNQ)

<hr>
<br>

## Galeri

| <div style="width:30%"></div>                                                                                                                                                                                 | <div style="width:30%"></div>                                                                                                                                                                                 | <div style="width:30%"></div>                                                                                                                                                                        |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [{{< image src="basic_numeric.png" caption="Basic Numeric" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}](#1-basic-numeric) | [{{< image src="basic_ordinal.png" caption="Basic Ordinal" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}](#2-basic-ordinal) | [{{< image src="basic_time.png" caption="Basic Time" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}](#3-basic-time) |

<hr>

<br>

###### 1. Basic Numeric

[Galeri](#galeri)

```dart
List<NumericData> numericList = [
    NumericData(domain: 1, measure: 3),
    NumericData(domain: 2, measure: 5),
    NumericData(domain: 3, measure: 9),
    NumericData(domain: 4, measure: 6.5),
];
final numericGroup = [
    NumericGroup(
        id: '1',
        chartType: ChartType.bar,
        data: numericList,
    ),
    NumericGroup(
        id: '2',
        chartType: ChartType.line,
        data: numericList,
    ),
    NumericGroup(
        id: '3',
        chartType: ChartType.scatterPlot,
        data: numericList,
    ),
];
AspectRatio(
    aspectRatio: 16 / 9,
    child: DChartComboN(
        groupList: numericGroup,
    ),
),
```

<br>

###### 2. Basic Ordinal

[Galeri](#galeri)

```dart
List<OrdinalData> ordinalList = [
    OrdinalData(domain: 'Mon', measure: 3),
    OrdinalData(domain: 'Tue', measure: 5),
    OrdinalData(domain: 'Wed', measure: 9),
    OrdinalData(domain: 'Thu', measure: 6.5),
];

final ordinalGroup = [
    OrdinalGroup(
        id: '1',
        chartType: ChartType.bar,
        data: ordinalList,
    ),
    OrdinalGroup(
        id: '2',
        chartType: ChartType.line,
        data: ordinalList,
    ),
    OrdinalGroup(
        id: '3',
        chartType: ChartType.scatterPlot,
        data: ordinalList,
    ),
];

AspectRatio(
    aspectRatio: 16 / 9,
    child: DChartComboO(
        groupList: ordinalGroup,
    ),
),
```

<br>

###### 3. Basic Time

[Galeri](#galeri)

```dart
List<NumericData> numericList = [
    NumericData(domain: 1, measure: 3),
    NumericData(domain: 2, measure: 5),
    NumericData(domain: 3, measure: 9),
    NumericData(domain: 4, measure: 6.5),
];

final numericGroup = [
    NumericGroup(
        id: '1',
        chartType: ChartType.bar,
        data: numericList,
    ),
    NumericGroup(
        id: '2',
        chartType: ChartType.line,
        data: numericList,
    ),
    NumericGroup(
        id: '3',
        chartType: ChartType.scatterPlot,
        data: numericList,
    ),
];

AspectRatio(
    aspectRatio: 16 / 9,
    child: DChartComboN(
        groupList: numericGroup,
    ),
),
```

<br>
