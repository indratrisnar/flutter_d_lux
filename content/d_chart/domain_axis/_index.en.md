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

| <div style="width:150px">Name</div> | <div style="width:150px">Data Type</div> | Default              | Description                                                                                                                                                          |
| ----------------------------------- | ---------------------------------------- | -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| gapAxisToLabel                      | int?                                     | `5`                  | Provides the distance between the domain label and the line domain                                                                                                   |
|                                     |                                          |                      | {{< image src="gap.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}   |
| labelAnchor                         | [LabelAnchor](#labelanchor)              | LabelAnchor.centered | Label position based on thick                                                                                                                                        |
| labelStyle                          | [LabelStyle](#labelstyle)                | LabelStyle()         | Gives style to the domain text label                                                                                                                                 |
| lineStyle                           | [LineStyle](#linestyle)                  | LineStyle()          | Gives style to the line domain                                                                                                                                       |
| showLine                            | bool                                     | true                 | Show domain line                                                                                                                                                     |
| thickLength                         | int                                      | 3                    | Length of thick                                                                                                                                                      |
|                                     |                                          |                      | {{< image src="thick.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |
| numericViewport                     | [NumericViewport](#numericviewport)      | null                 | Limits the chart viewport                                                                                                                                            |
| ordinalViewport                     | [OrdinalViewport](#ordinalviewport)      | null                 | Limits the chart viewport                                                                                                                                            |
| timeViewport                        | [TimeViewport](#timeviewport)            | null                 | Limits the chart viewport                                                                                                                                            |

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

#### NumericViewport

```dart
NumericViewport(min, max)
```

Prerequisites: [min] <= [max]
When the chart type is bar, it is recommended to add distance before [min] and after [max]. The intent is to provide a starting and ending space.

| Parameter | Data Type | Default    | Description                             |
| --------- | --------- | ---------- | --------------------------------------- |
| min       | num       | `required` | The initial boundary of the domain axis |
| max       | num       | `required` | Domain axis end limit                   |

<table>
    
 <tr>
 <td style="text-align: center; vertical-align: middle;">null</td>
 <td><div>

```dart
NumericViewport(2, 4.5)
```

  </div></td>

 </tr>
 <tr>
 <td>
{{< image src="numericViewport_null.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}
 </td>
 <td>
 {{< image src="numericViewport.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}
 </td>

 </tr>
</table>

<br>

#### OrdinalViewport

```dart
OrdinalViewport(startingDomain, dataSize)
```

The viewport to include the number of data [dataSize] starting from the [startingDomain] value.

| Parameter      | Data Type | Default    | Description                             |
| -------------- | --------- | ---------- | --------------------------------------- |
| startingDomain | String    | `required` | The initial boundary of the domain axis |
| dataSize       | int       | `required` | The amount of data displayed            |

<table>
    
 <tr>
 <td style="text-align: center; vertical-align: middle;">null</td>
 <td><div>

```dart
OrdinalViewport('Wed', 2)
```

  </div></td>

 </tr>
 <tr>
 <td>
{{< image src="ordinalViewport_null.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}
 </td>
 <td>
 {{< image src="ordinalViewport.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}
 </td>

 </tr>
</table>

<br>

#### TimeViewport

```dart
TimeViewport(start, end)
```

A viewport for displaying charts by start and end time limits.

| Parameter | Data Type | Default    | Description                             |
| --------- | --------- | ---------- | --------------------------------------- |
| start     | DateTime  | `required` | The initial boundary of the domain axis |
| end       | DateTime  | `required` | Domain axis end limit                   |

<table>
    
 <tr>
 <td style="text-align: center; vertical-align: middle;">null</td>
 <td><div>

```dart
TimeViewport(
    DateTime(2023, 8, 27),
    DateTime(2023, 8, 30),
),
```

  </div></td>

 </tr>
 <tr>
 <td>
{{< image src="timeViewport_null.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}
 </td>
 <td>
 {{< image src="timeViewport.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}
 </td>

 </tr>
</table>

<br>
