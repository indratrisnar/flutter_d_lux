---
title: "Config Render Point"
date: 2023-08-17T17:10:57+07:00
weight: 2
draft: false
keywords: ["d_chart", "render", "point", "combo", "scatter"]
---

Configuring the Scatter Plot Chart view

```dart
ConfigRenderPoint? configRenderPoint
```

<br>

| <div style="width:130px">Property</div> | <div style="width:140px">Data Type</div> | <div style="width:70px">Default</div> | Description                                                                                                                                                                                                                                                         |
| --------------------------------------- | ---------------------------------------- | ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| radiusPx                                | double                                   | `3.5`                                 | Plot point/symbol size                                                                                                                                                                                                                                              |
|                                         |                                          |                                       | {{< image src="radiusPx.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}                                                                                             |
| strokeWidthPx                           | double                                   | `0.0`                                 | Stroke for **Target Line** symbol or border for **Circle** and **Rect** symbols. Does not apply to the **Triangle** symbol. <br><br> The border color follows the group color, so that it is different from the fill color, you must set the **fillColor** property |
|                                         |                                          |                                       | {{< image src="strokeWidthPx.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}                                                                                        |
| symbolRender                            | [SymbolRender?](#symbolrender)           | SymbolRenderCircle()                  | Plot point/symbol shape                                                                                                                                                                                                                                             |

<br>

#### SymbolRender

Of the 4 symbols, there is a **isSolid** property of type **bool**.
If it has **true** then **fillColor** will be active. And if **false** then **fillColor** will not be active or will change the color to white.
<br>

1. SymbolRenderCircle

| true                                                                                                                                                                                   | false                                                                                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| {{< image src="SymbolRenderCircle_true.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} | {{< image src="SymbolRenderCircle_false.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |

<br>

2. SymbolRenderLine

This symbol is in the process of being monitored for use, not sure if it will be fixed. The use of this symbol has an impact on plot point positions that do not match the data.

| true                                                                                                                                                                                 | false                                                                                                                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| {{< image src="SymbolRenderLine_true.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} | {{< image src="SymbolRenderLine_false.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |

<br>

3. SymbolRenderRect

| true                                                                                                                                                                                 | false                                                                                                                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| {{< image src="SymbolRenderRect_true.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} | {{< image src="SymbolRenderRect_false.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |

<br>

4. SymbolRenderTriangle

| true                                                                                                                                                                                     | false                                                                                                                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| {{< image src="SymbolRenderTriangle_true.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} | {{< image src="SymbolRenderTriangle_false.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |

<br>
