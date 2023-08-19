---
title: "1. Basic Ordinal"
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
    "ordinal",
  ]
---

```dart
List<OrdinalData> ordinalList = [
  OrdinalData(domain: 'Mon', measure: 3),
  OrdinalData(domain: 'Tue', measure: 5),
  OrdinalData(domain: 'Wed', measure: 9),
  OrdinalData(domain: 'Thu', measure: 6.5),
];
```

<table>
 <tr>
    <td><div style="width:360px">

```dart
AspectRatio(
  aspectRatio: 16 / 9,
  child: DChartComboO(
    groupList: [
      OrdinalGroup(
        id: '1',
        chartType: ChartType.bar,
        data: ordinalList,
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
  child: DChartComboO(
    groupList: [
      OrdinalGroup(
        id: '1',
        chartType: ChartType.line,
        data: ordinalList,
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
  child: DChartComboO(
    groupList: [
      OrdinalGroup(
        id: '1',
        chartType: ChartType.scatterPlot,
        data: ordinalList,
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
  child: DChartComboO(
    groupList: [
      OrdinalGroup(
        id: '1',
        chartType: ChartType.bar,
        data: ordinalList,
      ),
      OrdinalGroup(
        id: '1',
        chartType: ChartType.line,
        data: ordinalList,
      ),
      OrdinalGroup(
        id: '1',
        chartType: ChartType.scatterPlot,
        data: ordinalList,
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
