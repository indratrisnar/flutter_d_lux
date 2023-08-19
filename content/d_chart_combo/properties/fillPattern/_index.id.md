---
title: "fillPattern"
date: 2023-08-17T17:10:57+07:00
weight: 1
draft: false
keywords: ["d_chart", "fill", "chart", "combo", "pattern"]
---

Set kustom pola isian, untuk tipe Bar Chart.

| Tipe                                                                   | Default           |
| ---------------------------------------------------------------------- | ----------------- |
| [FillPattern](#fillpattern) Function(OrdinalGroup, OrdinalData, int?)? | FillPattern.solid |

<br>

#### FillPattern

| <div style="width:120px">Tipe</div> | Deksripsi                                                                                             |
| ----------------------------------- | ----------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| forwardHatch                        | Mendefinisikan pola garis putih miring ke atas dan ke kanan di atas bar yang diisi dengan warna isian | {{< image src="fillPattern_forwardHatch.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |
| solid                               | Mendefinisikan bilah bar sederhana yang diisi dengan warna isian. Ini menjadi pola default            | {{< image src="fillPattern_solid.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}        |

<br>

```dart
fillPattern: (group, ordinalData, index) {
    if (ordinalData.measure > 8) return FillPattern.forwarHatch;
    return FillPattern.solid;
},
```

{{< image src="fillPattern.png" caption="" alt="alter-text" height="" width="" position="start" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>
