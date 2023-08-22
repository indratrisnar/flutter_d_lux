---
title: "Measure Axis"
date: 2023-08-17T17:10:57+07:00
weight: 2
draft: false
keywords: ["d_chart", "measure", "axis", "combo"]
---

Digunakan untuk mengkustomisasi bagian measure, termasuk label dan line axis nya.

```dart
MeasureAxis? measureAxis
```

<br>

##### Properti

| Nama                | Tipe Data                              | Default              | Deskripsi                                                                                                                                                           |
| ------------------- | -------------------------------------- | -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| desiredMaxTickCount | int?                                   | null                 | Menentukan jumlah maksimum tick yang diinginkan                                                                                                                     |
| desiredMinTickCount | int?                                   | null                 | Menentukan jumlah minimum tick yang diinginkan                                                                                                                      |
| desiredTickCount    | int?                                   | null                 | Menentukan jumlah pasti tick yang diinginkan, minimal 2 sebagai posisi min & max                                                                                    |
| gapAxisToLabel      | int?                                   | `5`                  | Memberikan jarak antara label measure dengan line measure                                                                                                           |
|                     |                                        |                      | {{< image src="gap.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}  |
| labelAnchor         | [LabelAnchor](#labelanchor)            | LabelAnchor.centered | Posisi label berdasarkan garis/titik point                                                                                                                          |
| labelFormat         | [String Function(num?)?](#labelformat) | LabelStyle()         | Memberikan style pada label teks measure                                                                                                                            |
| labelStyle          | [LabelStyle](#labelstyle)              | LabelStyle()         | Memberikan style pada label teks measure                                                                                                                            |
| lineStyle           | [LineStyle](#linestyle)                | LineStyle()          | Memberikan style pada line measure                                                                                                                                  |
| showLine            | bool                                   | true                 | Menampilkan line measure                                                                                                                                            |
| thickLength         | int                                    | 3                    | Garis/titik point                                                                                                                                                   |
|                     |                                        |                      | {{< image src="tick.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |

<br>

###### LabelAnchor

| Tipe                 | Deskripsi                                                                                                                                                                                                |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| LabelAnchor.after    | Memposisikan label teks measure setelah(diatas) dari titik point                                                                                                                                         |
|                      | {{< image src="label_anchor_after.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}                        |
| LabelAnchor.before   | Memposisikan label teks measure sebelum(dibawah) dari titik point                                                                                                                                        |
|                      | {{< image src="label_anchor_before.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title="LabelAnchor.before"  webp="false" >}}     |
| LabelAnchor.centered | Memposisikan label teks measure tepat ditengah (sejajar) dengan titik point                                                                                                                              |
|                      | {{< image src="label_anchor_centered.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title="LabelAnchor.centered"  webp="false" >}} |
| LabelAnchor.inside   | Data pertama akan dijadikan **before** dan data terakhir akan dijadikan **after**, sedangkan data diantaranya akan dijadikan **centered**                                                                |
|                      | {{< image src="label_anchor_inside.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title="LabelAnchor.inside"  webp="false" >}}     |

<br>

###### LabelFormat

Karena bertipe `String Function(num?)?` maka kita bisa kustomisasi untuk menampilkan label dengan value bersumber dari parameter.
Misalkan kita ingin menampilkan value beserta satuan nya maka dapat digunakan kode seperti:

```dart
labelFormat: (measure) {
    return '${measure!.round()} kg';
},
```

{{< image src="label_format.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title="LabelAnchor.inside"  webp="false" >}}

<br>

###### LabelStyle

| Properti | Tipe Data | Default        | Deskripsi                           |
| -------- | --------- | -------------- | ----------------------------------- |
| color    | Color     | Colors.black87 | Memberikan warna pada label measure |
| fontSize | int?      | `12`           | Set ukuran label measure            |

{{< image src="label_style.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>

###### LineStyle

| Properti    | Tipe Data   | Default     | Deskripsi                          |
| ----------- | ----------- | ----------- | ---------------------------------- |
| color       | Color       | Colors.grey | Memberikan warna pada line measure |
| dashPattern | List\<int>? | null        | Set pattern untuk line measure     |
| thickness   | int?        | 1           | Set ketebalan label measure        |

{{< image src="line_style.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>
