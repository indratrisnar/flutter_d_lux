---
title: "Bar Label"
date: 2023-08-17T17:10:57+07:00
weight: 2
draft: false
keywords: ["d_chart", "label", "bar", "combo"]
---

Customize the appearance of the labels on the bar chart

<br>

| <div style="width:180px">Property</div> | <div style="width:140px">Data Type</div>                             | <div style="width:70px">Default</div> | Description                                               |
| --------------------------------------- | -------------------------------------------------------------------- | ------------------------------------- | --------------------------------------------------------- |
| barLabelDecorator                       | [BarLabelDecorator?](#barlabeldecorator)                             | null                                  | Specifies the position of the label                       |
| [barLabelValue](#barlabelvalue)         | String Function(OrdinalGroup, OrdinalData, int?)?                    | domain value                          | To display labels, **barLabelDecorator** cannot be null   |
| insideBarLabelStyle                     | [LabelStyle](#labelstyle) Function(OrdinalGroup, OrdinalData, int?)? | null                                  | Styling the label text positioned inside the bar          |
| outsideBarLabelStyle                    | [LabelStyle](#labelstyle) Function(OrdinalGroup, OrdinalData, int?)? | null                                  | Styling the label text that is positioned outside the bar |

<br>

#### BarLabelDecorator

| <div style="width:160px">Property</div> | <div style="width:140px">Data Type</div> | <div style="width:70px">Default</div> | Description                                                                                                                                                                                                                                                                                                                                              |
| --------------------------------------- | ---------------------------------------- | ------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| barLabelPosition                        | [BarLabelPosition](#barlabelposition)    | BarLabelPosition.auto                 | Configure where to place the label relative to the bar                                                                                                                                                                                                                                                                                                   |
| labelAnchor                             | [BarLabelAnchor](#barlabelanchor)        | null                                  | The position of the label when inside the bar                                                                                                                                                                                                                                                                                                            |
| labelPadding                            | int                                      | `5`                                   | Spacing before and after the label text                                                                                                                                                                                                                                                                                                                  |
|                                         |                                          |                                       | {{< image src="labelPadding.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} {{< image src="labelPadding2.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |

<br>

#### BarLabelPosition

| <div style="width:70px">Type</div> | Description                                                                                                                                                                             |
| ---------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| auto                               | It automatically tries to place the label inside the bar first and if it doesn't fit it will be set outside the bar                                                                     |
|                                    | {{< image src="BarLabelPosition_auto.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}    |
| inside                             | Always place labels inside the bar                                                                                                                                                      |
|                                    | {{< image src="BarLabelPosition_inside.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}  |
| outside                            | Always place labels on the outside of the bar                                                                                                                                           |
|                                    | {{< image src="BarLabelPosition_outside.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |
| right                              | Places the label to the right inside the bar, and applies it to the horizontal bar. For now the horizontal bar in **Combo** cannot be used                                              |

<br>

#### BarLabelAnchor

| <div style="width:70px">Type</div> | Description                                                                                                                                                                          |
| ---------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| start                              | Positions the label at the start/bottom of the bar                                                                                                                                   |
|                                    | {{< image src="BarLabelAnchor_start.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}  |
| middle                             | Positions the label in the center of the bar                                                                                                                                         |
|                                    | {{< image src="BarLabelAnchor_middle.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |
| end                                | Positions the label at the end/top of the bar                                                                                                                                        |
|                                    | {{< image src="BarLabelAnchor_end.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}    |

<br>

#### BarLabelValue

- Displays measure value

```dart
barLabelValue: (group, ordinalData, index) {
    return ordinalData.measure.round().toString();
},
```

{{< image src="barLabelValue1.png" caption="" alt="alter-text" height="" width="" position="start" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>

- Displays measure value and domain

```dart
barLabelValue: (group, ordinalData, index) {
    String domain = ordinalData.domain;
    String measure = ordinalData.measure.round().toString();
    return '$domain: $measure kg';
},
```

{{< image src="barLabelValue2.png" caption="" alt="alter-text" height="" width="" position="start" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>

- Appears depending on conditions

```dart
barLabelValue: (group, ordinalData, index) {
    if (ordinalData.measure < 6) return '';
    String measure = ordinalData.measure.round().toString();
    return '$measure kg';
},
```

{{< image src="barLabelValue3.png" caption="" alt="alter-text" height="" width="" position="start" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>

#### LabelStyle

| Property | Data Type | Default        | Description                        |
| -------- | --------- | -------------- | ---------------------------------- |
| color    | Color     | Colors.black87 | Sets the color of the domain label |
| fontSize | int?      | `12`           | Domain label size set              |

```dart
insideBarLabelStyle: (group, ordinalData, index) {
    return const LabelStyle(
        color: Colors.white,
        fontSize: 16,
    );
},
outsideBarLabelStyle: (group, ordinalData, index) {
    return LabelStyle(
        color: group.color ?? Colors.black,
        fontSize: 20,
    );
},
```

{{< image src="LabelStyle_inside_outside.png" caption="" alt="alter-text" height="" width="" position="start" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>
