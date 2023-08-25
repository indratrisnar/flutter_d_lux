---
title: "Basic Pie Time"
date: 2023-08-17T17:10:57+07:00
---

{{< image src="basic_time.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

```dart
List<TimeData> timeDataList = [
    TimeData(
        domain: DateTime(2023, 8, 26),
        measure: 3,
        color: Colors.cyan[300],
    ),
    TimeData(
        domain: DateTime(2023, 8, 27),
        measure: 5,
        color: Colors.indigo[300],
    ),
    TimeData(
        domain: DateTime(2023, 8, 29),
        measure: 9,
        color: Colors.lime[300],
    ),
    TimeData(
        domain: DateTime(2023, 9, 1),
        measure: 6.5,
        color: Colors.teal[300],
    ),
];

AspectRatio(
    aspectRatio: 16 / 9,
    child: DChartPieT(
        data: timeDataList,
    ),
),
```

<br>
