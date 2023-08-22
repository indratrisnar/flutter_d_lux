---
title: "Domain Axis"
date: 2023-08-17T17:10:57+07:00
weight: 2
draft: false
keywords: ["d_chart", "domain", "axis", "combo"]
---

Used to customize domain parts, including their labels and axis lines.

```dart
DomainAxis? domainAxis
```

<br>

##### Property

| Name           | Data Type                   | Default              | Description                                                                                                                                                          |
| -------------- | --------------------------- | -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| gapAxisToLabel | int?                        | `5`                  | Provides the distance between the domain label and the line domain                                                                                                   |
|                |                             |                      | {{< image src="gap.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}   |
| labelAnchor    | [LabelAnchor](#labelanchor) | LabelAnchor.centered | Label position based on thick                                                                                                                                        |
| labelStyle     | [LabelStyle](#labelstyle)   | LabelStyle()         | Gives style to the domain text label                                                                                                                                 |
| lineStyle      | [LineStyle](#linestyle)     | LineStyle()          | Gives style to the line domain                                                                                                                                       |
| showLine       | bool                        | true                 | Show domain line                                                                                                                                                     |
| thickLength    | int                         | 3                    | Length of thick                                                                                                                                                      |
|                |                             |                      | {{< image src="thick.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |

<br>

###### LabelAnchor

| Type                 | Description                                                                                                                                                                                              |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| LabelAnchor.after    | Positions the domain text label after(right) of the thick                                                                                                                                                |
|                      | {{< image src="label_anchor_after.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}                        |
| LabelAnchor.before   | Positions the domain text label before(left) of the thick                                                                                                                                                |
|                      | {{< image src="label_anchor_before.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title="LabelAnchor.before"  webp="false" >}}     |
| LabelAnchor.centered | Position the domain text label right in the middle (aligned) with the thick                                                                                                                              |
|                      | {{< image src="label_anchor_centered.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title="LabelAnchor.centered"  webp="false" >}} |
| LabelAnchor.inside   | The first data will be used as **after** and the last data will be used as **before**, while the data in between will be used as **centered**                                                            |
|                      | {{< image src="label_anchor_inside.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title="LabelAnchor.inside"  webp="false" >}}     |

<br>

###### LabelStyle

| Property | Data Type | Default        | Description                        |
| -------- | --------- | -------------- | ---------------------------------- |
| color    | Color     | Colors.black87 | Sets the color of the domain label |
| fontSize | int?      | `12`           | Domain label size set              |

{{< image src="label_style.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>

###### LineStyle

| Property    | Data Type   | Default     | Description                           |
| ----------- | ----------- | ----------- | ------------------------------------- |
| color       | Color       | Colors.grey | Assign a color to the line domain     |
| dashPattern | List\<int>? | null        | Set pattern for line domains          |
| thickness   | int?        | 1           | Set the thickness of the domain label |

{{< image src="line_style.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>
