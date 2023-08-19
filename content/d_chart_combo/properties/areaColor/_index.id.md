---
title: "areaColor"
date: 2023-08-17T17:10:57+07:00
weight: 1
draft: false
keywords: ["d_chart", "area", "chart", "combo", "color"]
---

**areaColor** mengembalikan warna area untuk nilai data tertentu.
Jika tidak tersedia, maka warna grup akan menggunakan opacity 10% secara default.
<br>

Properti ini untuk chart dengan tipe line.
Untuk mengaktifkan custom areaColor, pada **ConfigRenderLine** terdapat **includeArea** yang harus dijadikan **true**.

| Tipe                                              | Default |
| ------------------------------------------------- | ------- |
| Color? Function(OrdinalGroup, OrdinalData, int?)? | null    |

```dart
configRenderLine: ConfigRenderLine(
    includeArea: true,
),
areaColor: (group, ordinalData, index) {
    return Colors.green.withOpacity(0.3);
},
```

{{< image src="areaColor.png" caption="" alt="alter-text" height="" width="" position="start" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>
