---
title: "areaColor"
date: 2023-08-17T17:10:57+07:00
weight: 1
draft: false
keywords: ["d_chart", "area", "chart", "combo", "color"]
---

**areaColor** returns the color of the area for a given data value.
If not available, then the group color will use 10% opacity by default.
<br>

This property is for charts with line type.
To activate a custom areaColor, in **ConfigRenderLine** there is **includeArea** which must be made **true**.

| Type                                              | Default |
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
