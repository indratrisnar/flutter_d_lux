---
title: "Line Basic Numeric"
date: 2023-08-17T17:10:57+07:00
---

{{< image src="basic_numeric.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

```dart
List<NumericData> numericDataList = [
    NumericData(domain: 1, measure: 3),
    NumericData(domain: 2, measure: 5),
    NumericData(domain: 3, measure: 9),
    NumericData(domain: 4, measure: 6.5),
];

final numericGroupList = [
    NumericGroup(
        id: '1',
        data: numericDataList,
    ),
];

AspectRatio(
    aspectRatio: 16 / 9,
    child: DChartLineN(
        groupList: numericGroupList,
    ),
),
```

<br>
