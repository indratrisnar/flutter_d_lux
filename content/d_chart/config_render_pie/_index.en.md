---
title: "Config Render Pie"
date: 2023-08-17T17:10:57+07:00
weight: 2
draft: false
keywords: ["d_chart", "render", "pie", "config"]
---

Configuring the Pie view

```dart
ConfigRenderPie? configRenderPie
```

<br>

| <div style="width:160px">Property</div> | <div style="width:140px">Data Type</div> | <div style="width:70px">Default</div> | Description                                                                                                                                                                                                                                                                                                                                                                              |
| --------------------------------------- | ---------------------------------------- | ------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| arcLabelDecorator                       | [ArcLabelDecorator?](#arclabeldecorator) | null                                  | Decorating pie item labels                                                                                                                                                                                                                                                                                                                                                               |
| arcLength                               | double                                   | 2 \* pi <br><br>(pi from `dart:math`) | Total arc length, in radians. <br>2π = Full                                                                                                                                                                                                                                                                                                                                              |
|                                         |                                          |                                       | {{< image src="full.png" caption="Full" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}                                                                                                                                                                                                                  |
|                                         |                                          |                                       | {{< image src="three_quarter.png" caption="Three-Quarter" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}                                                                                                                                                                                                |
|                                         |                                          |                                       | {{< image src="half.png" caption="Half" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}                                                                                                                                                                                                                  |
|                                         |                                          |                                       | {{< image src="quarter.png" caption="Quarter" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}                                                                                                                                                                                                            |
| arcRatio                                | double?                                  | null                                  | If set, configure arcWidth to be a percentage of radius. must be between `0` and `1`                                                                                                                                                                                                                                                                                                     |
|                                         |                                          |                                       | {{< image src="arcRatio_0_5.png" caption="0.5" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}                                                                                                                                                                                                           |
|                                         |                                          |                                       | {{< image src="arcRatio_0_2.png" caption="0.2" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}                                                                                                                                                                                                           |
| arcWidth                                | int?                                     | null                                  | Sets the arc width in radius. If **arcRatio** is set, this value will be ignored.                                                                                                                                                                                                                                                                                                        |
|                                         |                                          |                                       | {{< image src="arcWidth_40.png" caption="40px" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}                                                                                                                                                                                                           |
| startAngle                              | double                                   | -pi / 2                               | The initial angle for the pie slice, in radians.<br> The angle is determined from the positive x-axis in Cartesian space.<br> The default initial angle is -π/2                                                                                                                                                                                                                          |
|                                         |                                          |                                       | {{< image src="startAngle_default.png" caption="Default" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} {{< image src="startAngle_min_pi_slice_1.png" caption="-pi / 1" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |
| strokeWidthPx                           | double                                   | `2.0`                                 | Stroke width at arc boundary                                                                                                                                                                                                                                                                                                                                                             |
|                                         |                                          |                                       | {{< image src="strokeWidthPx.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}                                                                                                                                                                                                             |

<br>

#### ArcLabelDecorator

| <div style="width:150px">Property</div> | Data Type                                           | Default                                                                          | Description                                                        |
| --------------------------------------- | --------------------------------------------------- | -------------------------------------------------------------------------------- | ------------------------------------------------------------------ |
| insideLabelStyle                        | [LabelStyle](#labelstyle)                           | const LabelStyle(fontSize: 12, color: Colors.white)                              | Styling the label text when inside the pie                         |
| outsideLabelStyle                       | [LabelStyle](#labelstyle)                           | const LabelStyle(fontSize: 12, color: Colors.white)                              | Styling the label text when outside the pie                        |
| labelPadding                            | int                                                 | `5`                                                                              | Space before and after the label text                              |
| labelPosition                           | [ArcLabelPosition](#arclabelposition)               | ArcLabelPosition.auto                                                            | Configures where to place the label relative to the arc            |
| leaderLineStyle                         | [ArcLabelLeaderLineStyle](#arclabelleaderlinestyle) | const ArcLabelLeaderLineStyle(color: Colors.black, length: 20.0, thickness: 1.0) | Gives a style to the label line where the label is outside the pie |
| showLeaderLines                         | bool                                                | true                                                                             | Displays the label line                                            |

<br>

#### LabelStyle

| Property | Data Type | Default        | Description               |
| -------- | --------- | -------------- | ------------------------- |
| color    | Color     | Colors.black87 | Color of the domain label |
| fontSize | int?      | `12`           | Domain label size         |

<br>

#### ArcLabelPosition

| <div style="width:70px">Type</div> | Description                                                                                                                                                                                                                                                                                                                                                   |
| ---------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| auto                               | Automatically try to place the labels inside the arc first and place them outside the available space outside the arc is greater than the available space inside the arc {{< image src="ArcLabelPosition_auto.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |
| outside                            | Always put a label on the outside of the pie {{< image src="ArcLabelPosition_outside.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}                                                                                                                          |
| inside                             | Always put labels on the inside of the pie {{< image src="ArcLabelPosition_inside.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}                                                                                                                             |

<br>

#### ArcLabelLeaderLineStyle

Default class:

```dart
const ArcLabelLeaderLineStyle(
    color: Colors.black,
    length: 20.0,
    thickness: 1.0,
)
```

| Property  | Data Type | Default    | Description                      |
| --------- | --------- | ---------- | -------------------------------- |
| color     | Color     | `required` | Sets the color of the label line |
| length    | double    | `required` | Label line length                |
| thickness | double    | `required` | Label line thickness             |

<br>
