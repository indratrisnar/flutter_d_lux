---
title: "Data"
date: 2023-08-17T17:10:57+07:00
weight: 1
draft: false
keywords: ["d_chart", "data", "group", "combo", "chart"]
---

Data chart selalu dibungkus dengan list, karena data memungkinkan banyak dan bisa dibuat per-grup.

```dart
required List<Group> groupList
```

Group tergantung dari [Tipe Domain](/id/d_chart_combo/#tipe-domain) yang digunakan. Namun untuk nama properti masing-masing tipe sama saja, hanya berbeda di tipe elemen.

| Tipe    | Group        | Data        |
| ------- | ------------ | ----------- |
| Ordinal | OrdinalGroup | OrdinalData |
| Numeric | NumericGroup | NumericData |
| Time    | TimeGroup    | TimeData    |

<br>

Sehingga struktur data chart seperti:

|                                                                                     Ordinal                                                                                      |                                                                                     Numeric                                                                                      |                                                                                     Time                                                                                      |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| {{< image src="ordinal_structure.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} | {{< image src="numeric_structure.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} | {{< image src="time_structure.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |

<br>

#### Group

| <div style="width:90px">Properti</div> | <div style="width:90px">Tipe</div>                                  | <div style="width:130px">Default</div> | Deskripsi                                                    |
| -------------------------------------- | ------------------------------------------------------------------- | -------------------------------------- | ------------------------------------------------------------ |
| id                                     | String                                                              | `required`                             | Sebagai kata kunci dan pembeda grup                          |
| chartType                              | [ChartType](#charttype)                                             | ChartType.line                         | Bentuk chart                                                 |
| color                                  | [Color](https://api.flutter.dev/flutter/material/Colors-class.html) | Random                                 | Warna ini akan diterapkan untuk semua data di grup yang sama |
| data                                   | [List\<Data>](#data)                                                | `required`                             | Daftar nilai yang akan di set ke chart                       |

<br>

#### ChartType

|                                                                                bar                                                                                 |                                                                                line                                                                                 |                                                                                scatterPlot                                                                                 |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------------------------------------------------------------------------------------: | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| {{< image src="bar.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} | {{< image src="line.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} | {{< image src="scatterPlot.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |

<br>

#### Data

| <div style="width:80px">Properti</div> | <div style="width:120px">Tipe [O, N, T]</div>                                                                                                                                                                                                                                                                                                                                                                                                     | Deskripsi                     |
| -------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------- |
| domain                                 | [String](https://api.flutter.dev/flutter/dart-core/String-class.html?gclid=Cj0KCQjw0IGnBhDUARIsAMwFDLmE_RvrjjabaB64prUbFIECFjQ05dGIQWScgeXQ5TjkrhFqasd_RH4aAp-6EALw_wcB&gclsrc=aw.ds), [num](https://api.flutter.dev/flutter/dart-core/num-class.html), [DateTime](https://api.flutter.dev/flutter/dart-core/DateTime-class.html?gclid=Cj0KCQjw0IGnBhDUARIsAMwFDLmzGZm7dLhJaARC8A1g5-aMTxIUM7jxoJVzBRmjOTVfAIGZLrfAivoaAs9JEALw_wcB&gclsrc=aw.ds) | Diterapkan pada sumbu domain  |
| measure                                | [num](https://api.flutter.dev/flutter/dart-core/num-class.html)                                                                                                                                                                                                                                                                                                                                                                                   | Diterapkan pada sumbu measure |
| other                                  | [dynamic](https://pub.dev/documentation/analyzer/latest/dart_element_type/DynamicType-class.html)                                                                                                                                                                                                                                                                                                                                                 | Data tambahan                 |

<br>
