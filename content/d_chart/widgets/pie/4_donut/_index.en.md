---
title: "Donut"
date: 2023-08-17T17:10:57+07:00
---

{{< image src="donut.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

```dart
List<OrdinalData> ordinalDataList = [
    OrdinalData(domain: 'Mon', measure: 3, color: Colors.blue[300]),
    OrdinalData(domain: 'Tue', measure: 5, color: Colors.amber[300]),
    OrdinalData(domain: 'Wed', measure: 9, color: Colors.purple[300]),
    OrdinalData(domain: 'Thu', measure: 6.5, color: Colors.pink[300]),
];

AspectRatio(
    aspectRatio: 16 / 9,
    child: DChartPieO(
        data: ordinalDataList,
        configRenderPie: const ConfigRenderPie(
            arcWidth: 30,
        ),
    ),
),
```

<br>
