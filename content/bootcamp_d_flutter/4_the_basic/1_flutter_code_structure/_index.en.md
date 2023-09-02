---
title: "1. Flutter Code Structure"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 1
keywords: ["dart", "flutter", "bootcamp", "basic", "structure"]
---

There are several types of coding scopes in Flutter. However, to make everything clear you need to practice and complete the material to the end.

{{< image src="1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}
{{< image src="2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

| <div style="width: 30px">No</div> | <div style="width:80px">Color</div> | Description                                                                                                                                                                                                                                            |
| :-------------------------------: | ----------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
|                 1                 | Green                               | If the placement is in a class then it can be accessed within that class and for access outside the class requires certain requirements. If it is outside the class or directly created in a file, it will become global and can be accessed anywhere. |
|                 2                 | Yellow                              | Function scope. Dart code instructions can generally be written inside a function. Each instruction always ends with a semi-colon (;).                                                                                                                 |
|                 3                 | Blue                                | UI scope, where UI code instructions which are often called widgets are applied. It usually ends with a comma (,).                                                                                                                                     |
|                 4                 | Red                                 | If you create a variable or function, it can only be accessed within that class. To be accessed outside there needs to be requirements. However, if accessed from the build() function, it can be accessed directly because it is in the same scope.   |

The main page structure in Flutter, using the Scaffold widget:

{{< image src="3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}
{{< image src="4.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

**Red**, page header uses the AppBar widget. For advanced cases, you can customize it using other widgets.

**Blue**, the body of the page uses a certain layout to arrange the widgets.
These 2 sections are the main page area by default. In certain case studies, to beautify the appearance, the appBar property is rarely used and is replaced with a custom UI.

<br>
