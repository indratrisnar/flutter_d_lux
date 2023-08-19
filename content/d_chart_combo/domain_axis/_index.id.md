---
title: "Domain Axis"
date: 2023-08-17T17:10:57+07:00
weight: 1
draft: false
keywords: ["d_chart", "domain", "axis", "combo"]
---

Digunakan untuk mengkustomisasi bagian domain, termasuk label dan line axis nya.

```dart
DomainAxis? domainAxis
```

<br>

##### Properti

| Nama           | Tipe Data                   | Default              | Deskripsi                                                                                                                                                            |
| -------------- | --------------------------- | -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| gapAxisToLabel | int?                        | `5`                  | Memberikan jarak antara label domain dengan line domain                                                                                                              |
|                |                             |                      | {{< image src="gap.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}   |
| labelAnchor    | [LabelAnchor](#labelanchor) | LabelAnchor.centered | Posisi label berdasarkan garis/titik point                                                                                                                           |
| labelStyle     | [LabelStyle](#labelstyle)   | LabelStyle()         | Memberikan style pada label teks domain                                                                                                                              |
| lineStyle      | [LineStyle](#linestyle)     | LineStyle()          | Memberikan style pada line domain                                                                                                                                    |
| showLine       | bool                        | true                 | Menampilkan line domain                                                                                                                                              |
| thickLength    | int                         | 3                    | Garis/titik point                                                                                                                                                    |
|                |                             |                      | {{< image src="thick.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |

<br>

###### LabelAnchor

| Tipe                 | Deskripsi                                                                                                                                                                                                |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| LabelAnchor.after    | Memposisikan label teks domain setelah(sebelah kanan) dari titik point                                                                                                                                   |
|                      | {{< image src="label_anchor_after.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}                        |
| LabelAnchor.before   | Memposisikan label teks domain sebelum(sebelah kiri) dari titik point                                                                                                                                    |
|                      | {{< image src="label_anchor_before.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title="LabelAnchor.before"  webp="false" >}}     |
| LabelAnchor.centered | Memposisikan label teks domain tepat ditengah (sejajar) dengan titik point                                                                                                                               |
|                      | {{< image src="label_anchor_centered.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title="LabelAnchor.centered"  webp="false" >}} |
| LabelAnchor.inside   | Data pertama akan dijadikan **after** dan data terakhir akan dijadikan **before**, sedangkan data diantaranya akan dijadikan **centered**                                                                |
|                      | {{< image src="label_anchor_inside.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title="LabelAnchor.inside"  webp="false" >}}     |

<br>

###### LabelStyle

| Properti | Tipe Data | Default        | Deskripsi                          |
| -------- | --------- | -------------- | ---------------------------------- |
| color    | Color     | Colors.black87 | Memberikan warna pada label domain |
| fontSize | int?      | `12`           | Set ukuran label domain            |

{{< image src="label_style.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>

###### LineStyle

| Properti    | Tipe Data   | Default     | Deskripsi                         |
| ----------- | ----------- | ----------- | --------------------------------- |
| color       | Color       | Colors.grey | Memberikan warna pada line domain |
| dashPattern | List\<int>? | null        | Set pattern untuk line domain     |
| thickness   | int?        | 1           | Set ketebalan label domain        |

{{< image src="line_style.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>
