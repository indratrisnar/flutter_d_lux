---
title: "3. Basic Time"
date: 2023-08-17T17:10:57+07:00
weight: 1
draft: false
keywords:
  [
    "d_chart",
    "example",
    "chart",
    "combo",
    "flutter",
    "code",
    "line",
    "bar",
    "scatter",
    "time",
    "date",
  ]
---

```dart
List<TimeData> timeList = [
  TimeData(domain: DateTime(2023, 8, 17), measure: 3),
  TimeData(domain: DateTime(2023, 8, 18), measure: 5),
  TimeData(domain: DateTime(2023, 8, 19), measure: 9),
  TimeData(domain: DateTime(2023, 9, 2), measure: 6.5),
];
```

<table>
 <tr>
    <td><div style="width:360px">

```dart
AspectRatio(
  aspectRatio: 16 / 9,
  child: DChartComboT(
    groupList: [
      TimeGroup(
        id: '1',
        chartType: ChartType.bar,
        data: timeList,
      ),
    ],
  ),
),
```

  </div></td>
  <td>
{{< image src="bar.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}
  </td>

 </tr>
 <tr>
    <td><div style="width:360px">

```dart
AspectRatio(
  aspectRatio: 16 / 9,
  child: DChartComboT(
    groupList: [
      TimeGroup(
        id: '1',
        chartType: ChartType.line,
        data: timeList,
      ),
    ],
  ),
),
```

  </div></td>
  <td>
{{< image src="line.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}
  </td>  
 </tr>

 <tr>
    <td><div style="width:360px">

```dart
AspectRatio(
  aspectRatio: 16 / 9,
  child: DChartComboT(
    groupList: [
      TimeGroup(
        id: '1',
        chartType: ChartType.scatterPlot,
        data: timeList,
      ),
    ],
  ),
),
```

  </div></td>
  <td>
{{< image src="scatterPlot.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}
  </td>
 </tr>

 </tr>
 <tr>
    <td><div style="width:360px">

```dart
AspectRatio(
  aspectRatio: 16 / 9,
  child: DChartComboT(
    groupList: [
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
    ],
  ),
),
```

  </div></td>
  <td>
{{< image src="combo.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}
  </td>
 </tr>
</table>

<br>
