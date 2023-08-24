---
title: "Combo Basic Numeric"
date: 2023-08-17T17:10:57+07:00
---

{{< image src="basic_numeric.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

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
