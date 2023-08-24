---
title: "Bar Basic Time"
date: 2023-08-17T17:10:57+07:00
---

{{< image src="basic_time.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

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
        data: timeList,
    ),
];

AspectRatio(
    aspectRatio: 16 / 9,
    child: DChartBarT(
        groupList: timeGroup,
    ),
),
```

<br>
