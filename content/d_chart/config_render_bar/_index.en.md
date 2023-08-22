---
title: "Config Render Bar"
date: 2023-08-17T17:10:57+07:00
weight: 2
draft: false
keywords: ["d_chart", "render", "bar", "combo"]
---

Mengkonfigurasi tampilan Bar Chart

```dart
ConfigRenderBar? configRenderBar
```

<br>

| Property               | Data Type                           | Default                 | Description                                                                                                                                                                           |
| ---------------------- | ----------------------------------- | ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| barGroupInnerPaddingPx | int                                 | `2`                     | Distance between group                                                                                                                                                                |
|                        |                                     |                         | {{< image src="barGroupInnerPaddingPx.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |
| barGroupingType        | [BarGroupingType](#bargroupingtype) | BarGroupingType.grouped | Defines how multiple series bars are rendered per domain                                                                                                                              |
| fillPattern            | [FillPattern](#fillpattern)         | FillPattern.solid       | Defines a pattern for the fill color                                                                                                                                                  |
| maxBarWidthPx          | int?                                | null                    | Maximum width of the bar                                                                                                                                                              |
| minBarLengthPx         | int                                 | `0`                     | Minimum bar                                                                                                                                                                           |
| radius                 | int                                 | `2`                     | Corner top left and top right                                                                                                                                                         |
|                        |                                     |                         | {{< image src="radius.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}                 |
| stackedBarPaddingPx    | int                                 | `1`                     | Padding between bar group stack. **barGroupingType** must be BarGroupingType.stacked or BarGroupingType.groupedStacked                                                                |
|                        |                                     |                         | {{< image src="stackedBarPaddingPx.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}    |
| strokeWidthPx          | double                              | `0.0`                   | Border bar, the color follows the color of the group so you need to set the **fillColor** property to make the border clearer                                                         |
|                        |                                     |                         | {{< image src="border.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}                 |
| weightPattern          | List\<int>?                         | null                    | Still not available to use, still monitoring to [community_chart_flutter]()                                                                                                           |

<br>

###### BarGroupingType

| Type           | Description                                                                                                                                                                            |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| grouped        | Render bars for each series that shares a domain value side-by-side                                                                                                                    |
|                | {{< image src="barGroupingType_grouped.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |
| stacked        | Render bars for each series that shares a domain value in a stack, ordered in the same order as the series list                                                                        |
|                | {{< image src="barGroupingType_stacked.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |
| groupedStacked | Render bars for each series that shares a domain value in a group of bar stacks. Each stack will contain all the series that share a series category                                   |
|                | {{< image src="barGroupingType_stacked.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |

<br>

###### FillPattern

| Type         | Description                                                                                           |
| ------------ | ----------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| forwardHatch | Mendefinisikan pola garis putih miring ke atas dan ke kanan di atas bar yang diisi dengan warna isian | {{< image src="fillPattern_forwardHatch.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |
| solid        | Mendefinisikan bilah bar sederhana yang diisi dengan warna isian. Ini menjadi pola default            | {{< image src="fillPattern_solid.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}        |

<br>
