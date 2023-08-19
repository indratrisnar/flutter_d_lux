---
title: "fillColor"
date: 2023-08-17T17:10:57+07:00
weight: 1
draft: false
keywords: ["d_chart", "fill", "chart", "combo", "color"]
---

Set warna isian untuk chart yang memiliki bentuk isian seperti bar dan scatter.

| Tipe                                              | Default |
| ------------------------------------------------- | ------- |
| Color? Function(OrdinalGroup, OrdinalData, int?)? | null    |

```dart
fillColor: (group, ordinalData, index) {
    if (ordinalData.measure > 8) return Colors.red;
    return Colors.blue;
},
```

{{< image src="fillColor_bar.png" caption="" alt="alter-text" height="" width="" position="start" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}
{{< image src="fillColor_scatter.png" caption="" alt="alter-text" height="" width="" position="start" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>
