---
title: "Measure Axis"
date: 2023-08-17T17:10:57+07:00
weight: 2
draft: false
keywords: ["d_chart", "measure", "axis", "combo"]
---

Used to customize parts of the measure, including their labels and line axes.

```dart
MeasureAxis? measureAxis
```

<br>

#### Property

| Nama                | Data Type                              | Default              | Description                                                                                                                                                         |
| ------------------- | -------------------------------------- | -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| desiredMaxTickCount | int?                                   | null                 | Specifies the desired maximum number of ticks                                                                                                                       |
| desiredMinTickCount | int?                                   | null                 | Specifies the desired minimum number of ticks                                                                                                                       |
| desiredTickCount    | int?                                   | null                 | Determine the exact number of ticks desired, at least 2 as min & max positions                                                                                      |
| gapAxisToLabel      | int?                                   | `5`                  | Provides the distance between the label measure and the line measure                                                                                                |
|                     |                                        |                      | {{< image src="gap.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}  |
| labelAnchor         | [LabelAnchor](#labelanchor)            | LabelAnchor.centered | Label position based on tick                                                                                                                                        |
| labelFormat         | [String Function(num?)?](#labelformat) | LabelStyle()         | Styles the measure text labels                                                                                                                                      |
| labelStyle          | [LabelStyle](#labelstyle)              | LabelStyle()         | Styles the measure text labels                                                                                                                                      |
| lineStyle           | [LineStyle](#linestyle)                | LineStyle()          | Style the measure line                                                                                                                                              |
| showLine            | bool                                   | true                 | Show measure line                                                                                                                                                   |
| thickLength         | int                                    | 3                    | Length of tick                                                                                                                                                      |
|                     |                                        |                      | {{< image src="tick.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |

<br>

#### LabelAnchor

| Type                 | Description                                                                                                                                                                                              |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| LabelAnchor.after    | Positions the text label measure after(above) the tick                                                                                                                                                   |
|                      | {{< image src="label_anchor_after.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}                        |
| LabelAnchor.before   | Positions the measure text label before(below) of the tick                                                                                                                                               |
|                      | {{< image src="label_anchor_before.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title="LabelAnchor.before"  webp="false" >}}     |
| LabelAnchor.centered | Positions the measure text label right in the middle (aligned) with the tick                                                                                                                             |
|                      | {{< image src="label_anchor_centered.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title="LabelAnchor.centered"  webp="false" >}} |
| LabelAnchor.inside   | The first data will be used as **before** and the last data will be used as **after**, while the data between them will be used as **centered**                                                          |
|                      | {{< image src="label_anchor_inside.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title="LabelAnchor.inside"  webp="false" >}}     |

<br>

#### LabelFormat

Because of type `String Function(num?)?`, we can customize it to display labels with values sourced from parameters.
Suppose we want to display the value along with its units, we can use code like:

```dart
labelFormat: (measure) {
    return '${measure!.round()} kg';
},
```

{{< image src="label_format.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title="LabelAnchor.inside"  webp="false" >}}

<br>

#### LabelStyle

| Property | Data Type | Default        | Description                          |
| -------- | --------- | -------------- | ------------------------------------ |
| color    | Color     | Colors.black87 | Assigns a color to the measure label |
| fontSize | int?      | `12`           | Set size measure label               |

{{< image src="label_style.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>

#### LineStyle

| Property    | Data Type   | Default     | Description                             |
| ----------- | ----------- | ----------- | --------------------------------------- |
| color       | Color       | Colors.grey | Assigns color to the measure line       |
| dashPattern | List\<int>? | null        | Set pattern for measure line            |
| thickness   | int?        | 1           | Sets the thickness of the measure label |

{{< image src="line_style.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>
