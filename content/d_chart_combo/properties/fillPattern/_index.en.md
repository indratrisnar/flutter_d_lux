---
title: "fillPattern"
date: 2023-08-17T17:10:57+07:00
weight: 1
draft: false
keywords: ["d_chart", "fill", "chart", "combo", "pattern"]
---

Custom set of fill pattern, for Bar Chart type.

| Type                                                                   | Default           |
| ---------------------------------------------------------------------- | ----------------- |
| [FillPattern](#fillpattern) Function(OrdinalGroup, OrdinalData, int?)? | FillPattern.solid |

<br>

#### FillPattern

| <div style="width:120px">Type</div> | Description                                                                                            |
| ----------------------------------- | ------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| forwardHatch                        | Defines a pattern of white lines slanting up and to the right above the bar filled with the fill color | {{< image src="fillPattern_forwardHatch.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |
| solid                               | Defines a simple bar filled with a fill color. This becomes the default pattern                        | {{< image src="fillPattern_solid.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}        |

<br>

```dart
fillPattern: (group, ordinalData, index) {
    if (ordinalData.measure > 8) return FillPattern.forwarHatch;
    return FillPattern.solid;
},
```

{{< image src="fillPattern.png" caption="" alt="alter-text" height="" width="" position="start" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>
