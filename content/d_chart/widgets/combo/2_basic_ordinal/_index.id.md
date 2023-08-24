---
title: "Combo Basic Ordinal"
date: 2023-08-17T17:10:57+07:00
---

{{< image src="basic_ordinal.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

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
