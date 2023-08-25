---
title: "Basic Pie Numeric"
date: 2023-08-17T17:10:57+07:00
---

{{< image src="basic_numeric.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

```dart
List<NumericData> numericDataList = [
    NumericData(domain: 1, measure: 3, color: Colors.grey[300]),
    NumericData(domain: 2, measure: 5, color: Colors.green[300]),
    NumericData(domain: 3, measure: 9, color: Colors.orange[300]),
    NumericData(domain: 4, measure: 6.5, color: Colors.red[300]),
];

AspectRatio(
    aspectRatio: 16 / 9,
    child: DChartPieN(
        data: numericDataList,
    ),
),
```

<br>
