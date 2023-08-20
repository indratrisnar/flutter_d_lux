---
title: "2. Basic Numeric"
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
    "numeric",
  ]
---

```dart
List<NumericData> numericList = [
  NumericData(domain: 1, measure: 3),
  NumericData(domain: 2, measure: 5),
  NumericData(domain: 3, measure: 9),
  NumericData(domain: 4, measure: 6.5),
];
```

<table>
 <tr>
    <td><div style="width:360px">

```dart
AspectRatio(
  aspectRatio: 16 / 9,
  child: DChartComboN(
    groupList: [
      NumericGroup(
        id: '1',
        chartType: ChartType.bar,
        data: numericList,
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
  child: DChartComboN(
    groupList: [
      NumericGroup(
        id: '1',
        chartType: ChartType.line,
        data: numericList,
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
  child: DChartComboN(
    groupList: [
      NumericGroup(
        id: '1',
        chartType: ChartType.scatterPlot,
        data: numericList,
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
  child: DChartComboN(
    groupList: [
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
