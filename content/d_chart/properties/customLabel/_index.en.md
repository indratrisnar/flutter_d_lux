---
title: "customLabel"
date: 2023-08-17T17:10:57+07:00
weight: 1
draft: false
keywords: ["d_chart", "pie", "chart", "label"]
---

Currently, only for Pie Chart.

| Type                                | Default      |
| ----------------------------------- | ------------ |
| String Function(OrdinalData, int?)? | domain value |

```dart
customLabel: (ordinalData, index) {
    return '${ordinalData.domain}: ${ordinalData.measure}';
},
```

{{< image src="customLabel.png" caption="" alt="alter-text" height="" width="" position="start" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>
