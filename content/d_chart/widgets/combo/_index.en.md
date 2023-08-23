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

Combo charts are divided into Ordinal, Numeric, and Time domain types. For the chart form, you can use line, bar, and scatter plot forms. All three can be combined at once or individually.

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

## Gallery

| <div style="width:30%"></div>                                                                                                                                                                                 | <div style="width:30%"></div>                                                                                                                                                                                 | <div style="width:30%"></div>                                                                                                                                                                        |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [{{< image src="basic_numeric.png" caption="Basic Numeric" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}](#1-basic-numeric) | [{{< image src="basic_ordinal.png" caption="Basic Ordinal" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}](#2-basic-ordinal) | [{{< image src="basic_time.png" caption="Basic Time" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}](#3-basic-time) |

<hr>

<br>

###### 1. Basic Numeric

[Gallery](#gallery)

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

[Gallery](#gallery)

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

[Gallery](#gallery)

```dart
List<TimeData> timeList = [
    TimeData(domain: DateTime(2023, 8, 26), measure: 3),
    TimeData(domain: DateTime(2023, 8, 27), measure: 5),
    TimeData(domain: DateTime(2023, 8, 29), measure: 9),
    TimeData(domain: DateTime(2023, 9, 1), measure: 6.5),
];
final timeGroup = [
    TimeGroup(
        id: '1',
        chartType: ChartType.bar,
        data: timeList,
    ),
    TimeGroup(
        id: '2',
        chartType: ChartType.line,
        data: timeList,
    ),
    TimeGroup(
        id: '3',
        chartType: ChartType.scatterPlot,
        data: timeList,
    ),
];

AspectRatio(
    aspectRatio: 16 / 9,
    child: DChartComboT(
        groupList: timeGroup,
    ),
),
```

<br>
