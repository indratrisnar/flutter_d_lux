---
title: "dashPattern"
date: 2023-08-17T17:10:57+07:00
weight: 1
draft: false
keywords: ["d_chart", "pattern", "chart", "combo", "dash"]
---

Specific to the Line Chart type

| Type                                                 | Default |
| ---------------------------------------------------- | ------- |
| List<int> Function(OrdinalGroup, OrdinalData, int?)? | null    |

```dart
dashPattern: (group, ordinalData, index) {
    return [10, 10, 5];
},
```

{{< image src="dashPattern.png" caption="" alt="alter-text" height="" width="" position="start" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>
