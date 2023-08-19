---
title: "Config Render Bar"
date: 2023-08-17T17:10:57+07:00
weight: 1
draft: false
keywords: ["d_chart", "render", "bar", "combo"]
---

Mengkonfigurasi tampilan Bar Chart

```dart
ConfigRenderBar? configRenderBar
```

<br>

| Properti               | Tipe Data                           | Default                 | Deskripsi                                                                                                                                                                             |
| ---------------------- | ----------------------------------- | ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| barGroupInnerPaddingPx | int                                 | `2`                     | Jarak antara grup                                                                                                                                                                     |
|                        |                                     |                         | {{< image src="barGroupInnerPaddingPx.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |
| barGroupingType        | [BarGroupingType](#bargroupingtype) | BarGroupingType.grouped | Menentukan cara beberapa rangkaian bar dirender per domain                                                                                                                            |
| fillPattern            | [FillPattern](#fillpattern)         | FillPattern.solid       | Mendefinisikan pola untuk isian warna                                                                                                                                                 |
| maxBarWidthPx          | int?                                | null                    | Lebar maksimal dari bilah bar                                                                                                                                                         |
| minBarLengthPx         | int                                 | `0`                     | Minimum bar                                                                                                                                                                           |
| radius                 | int                                 | `2`                     | Kelengkungan sudut bar                                                                                                                                                                |
|                        |                                     |                         | {{< image src="radius.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}                 |
| stackedBarPaddingPx    | int                                 | `1`                     | Jarak antara tumpukan grup bar. **barGroupingType** harus berupa BarGroupingType.stacked atau BarGroupingType.groupedStacked                                                          |
|                        |                                     |                         | {{< image src="stackedBarPaddingPx.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}    |
| strokeWidthPx          | double                              | `0.0`                   | Border bar, warna mengikuti warna grup sehingga perlu set property **fillColor** untuk memperjelas border                                                                             |
|                        |                                     |                         | {{< image src="border.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}                 |
| weightPattern          | List\<int>?                         | null                    | Masih tidak tersedia untuk digunakan, masih memantau [community_chart_flutter]()                                                                                                      |

<br>

#### BarGroupingType

| Tipe           | Deksripsi                                                                                                                                                                              |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| grouped        | merender Bar untuk setiap series yang berbagi nilai domain secara berdampingan                                                                                                         |
|                | {{< image src="barGroupingType_grouped.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |
| stacked        | merender Bar untuk setiap series yang berbagi nilai domain dalam tumpukan, diurutkan dalam urutan yang sama dengan daftar seri                                                         |
|                | {{< image src="barGroupingType_stacked.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |
| groupedStacked | Merender Bar untuk setiap series yang berbagi nilai domain dalam grup tumpukan bar. Setiap tumpukan akan berisi semua seri yang berbagi kategori seri                                  |
|                | {{< image src="barGroupingType_stacked.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |

<br>

#### FillPattern

| Tipe         | Deksripsi                                                                                             |
| ------------ | ----------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| forwardHatch | Mendefinisikan pola garis putih miring ke atas dan ke kanan di atas bar yang diisi dengan warna isian | {{< image src="fillPattern_forwardHatch.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |
| solid        | Mendefinisikan bilah bar sederhana yang diisi dengan warna isian. Ini menjadi pola default            | {{< image src="fillPattern_solid.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}        |

<br>
