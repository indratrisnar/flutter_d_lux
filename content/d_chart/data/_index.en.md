---
title: "Data"
date: 2023-08-17T17:10:57+07:00
weight: 2
draft: false
keywords: ["d_chart", "data", "group", "combo", "chart"]
---

Chart data is always wrapped in a list, because data allows a lot and can be made per group.

```dart
required List<Group> groupList
```

The group depends on the [Domain-Type](/d_chart_combo/#domain-type) used. However, the property names for each type are the same, only different in the element type.

| Type    | Group        | Data        |
| ------- | ------------ | ----------- |
| Ordinal | OrdinalGroup | OrdinalData |
| Numeric | NumericGroup | NumericData |
| Time    | TimeGroup    | TimeData    |

<br>

So the chart data structure is like:

|                                                                                     Ordinal                                                                                      |                                                                                     Numeric                                                                                      |                                                                                     Time                                                                                      |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| {{< image src="ordinal_structure.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} | {{< image src="numeric_structure.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} | {{< image src="time_structure.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |

<br>

#### Group

| <div style="width:90px">Property</div> | <div style="width:90px">Type</div>                                  | <div style="width:130px">Default</div> | Description                                              |
| -------------------------------------- | ------------------------------------------------------------------- | -------------------------------------- | -------------------------------------------------------- |
| id                                     | String                                                              | `required`                             | As a keyword and group differentiator                    |
| chartType                              | [ChartType](#charttype)                                             | ChartType.line                         | Chart shape                                              |
| color                                  | [Color](https://api.flutter.dev/flutter/material/Colors-class.html) | Random                                 | This color will be applied to all data in the same group |
| data                                   | [List\<Data>](#data)                                                | `required`                             | The list of values to be set to the chart                |

<br>

#### ChartType

|                                                                                bar                                                                                 |                                                                                line                                                                                 |                                                                                scatterPlot                                                                                 |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------------------------------------------------------------------------------------: | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| {{< image src="bar.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} | {{< image src="line.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} | {{< image src="scatterPlot.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |

<br>

#### Data

| <div style="width:80px">Property</div> | <div style="width:120px">Type [O, N, T]</div>                                                                                                                                                                                                                                                                                                                                                                                                     | Description                  |
| -------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------- |
| domain                                 | [String](https://api.flutter.dev/flutter/dart-core/String-class.html?gclid=Cj0KCQjw0IGnBhDUARIsAMwFDLmE_RvrjjabaB64prUbFIECFjQ05dGIQWScgeXQ5TjkrhFqasd_RH4aAp-6EALw_wcB&gclsrc=aw.ds), [num](https://api.flutter.dev/flutter/dart-core/num-class.html), [DateTime](https://api.flutter.dev/flutter/dart-core/DateTime-class.html?gclid=Cj0KCQjw0IGnBhDUARIsAMwFDLmzGZm7dLhJaARC8A1g5-aMTxIUM7jxoJVzBRmjOTVfAIGZLrfAivoaAs9JEALw_wcB&gclsrc=aw.ds) | Applied to the domain axis   |
| measure                                | [num](https://api.flutter.dev/flutter/dart-core/num-class.html)                                                                                                                                                                                                                                                                                                                                                                                   | Applied to the measure axis  |
| other                                  | [dynamic](https://pub.dev/documentation/analyzer/latest/dart_element_type/DynamicType-class.html)                                                                                                                                                                                                                                                                                                                                                 | Additional data              |
| color                                  | [Color](https://api.flutter.dev/flutter/material/Colors-class.html)                                                                                                                                                                                                                                                                                                                                                                               | Specific to Pie Chart colors |

<br>
