---
title: "Domain Axis"
date: 2023-08-17T17:10:57+07:00
weight: 2
draft: false
keywords: ["d_chart", "domain", "axis", "combo"]
---

Digunakan untuk mengkustomisasi bagian domain, termasuk label dan line axis nya.

```dart
DomainAxis? domainAxis
```

<br>

##### Properti

| <div style="width:150px">Nama</div> | <div style="width:150px">Tipe Data</div> | Default              | Deskripsi                                                                                                                                                            |
| ----------------------------------- | ---------------------------------------- | -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| gapAxisToLabel                      | int?                                     | `5`                  | Memberikan jarak antara label domain dengan line domain                                                                                                              |
|                                     |                                          |                      | {{< image src="gap.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}   |
| labelAnchor                         | [LabelAnchor](#labelanchor)              | LabelAnchor.centered | Posisi label berdasarkan garis/titik point                                                                                                                           |
| labelStyle                          | [LabelStyle](#labelstyle)                | LabelStyle()         | Memberikan style pada label teks domain                                                                                                                              |
| lineStyle                           | [LineStyle](#linestyle)                  | LineStyle()          | Memberikan style pada line domain                                                                                                                                    |
| showLine                            | bool                                     | true                 | Menampilkan line domain                                                                                                                                              |
| thickLength                         | int                                      | 3                    | Garis/titik point                                                                                                                                                    |
|                                     |                                          |                      | {{< image src="thick.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |
| numericViewport                     | [NumericViewport](#numericviewport)      | null                 | Membatasi area pandang chart                                                                                                                                         |
| ordinalViewport                     | [OrdinalViewport](#ordinalviewport)      | null                 | Membatasi area pandang chart                                                                                                                                         |
| timeViewport                        | [TimeViewport](#timeviewport)            | null                 | Membatasi area pandang chart                                                                                                                                         |

<br>

#### LabelAnchor

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

#### LabelStyle

| Properti | Tipe Data | Default        | Deskripsi                          |
| -------- | --------- | -------------- | ---------------------------------- |
| color    | Color     | Colors.black87 | Memberikan warna pada label domain |
| fontSize | int?      | `12`           | Set ukuran label domain            |

{{< image src="label_style.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>

#### LineStyle

| Properti    | Tipe Data   | Default     | Deskripsi                         |
| ----------- | ----------- | ----------- | --------------------------------- |
| color       | Color       | Colors.grey | Memberikan warna pada line domain |
| dashPattern | List\<int>? | null        | Set pattern untuk line domain     |
| thickness   | int?        | 1           | Set ketebalan label domain        |

{{< image src="line_style.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>

#### NumericViewport

```dart
NumericViewport(min, max)
```

Prasyarat: [min] <= [max]\
Disarankan menambahkan jarak sebelum [min] dan setelah [max]. Maksudnya untuk memberikan ruang awal dan akhir.

| Parameter | Tipe Data | Default    | Deskripsi                |
| --------- | --------- | ---------- | ------------------------ |
| min       | num       | `required` | Batas awal sumbu domain  |
| max       | num       | `required` | Batas akhir sumbu domain |

<table>
    
 <tr>
 <td style="text-align: center; vertical-align: middle;">null</td>
 <td><div>

```dart
NumericViewport(2, 4.5)
```

  </div></td>

 </tr>
 <tr>
 <td>
{{< image src="numericViewport_null.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}
 </td>
 <td>
 {{< image src="numericViewport.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}
 </td>

 </tr>
</table>

<br>

#### OrdinalViewport

```dart
OrdinalViewport(startingDomain, dataSize)
```

Area pandang untuk mencakup jumlah data [dataSize] mulai dari nilai [startingDomain].

| Parameter      | Tipe Data | Default    | Deskripsi                    |
| -------------- | --------- | ---------- | ---------------------------- |
| startingDomain | String    | `required` | Batas awal sumbu domain      |
| dataSize       | int       | `required` | Jumlah data yang ditampilkan |

<table>
    
 <tr>
 <td style="text-align: center; vertical-align: middle;">null</td>
 <td><div>

```dart
OrdinalViewport('Wed', 2)
```

  </div></td>

 </tr>
 <tr>
 <td>
{{< image src="ordinalViewport_null.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}
 </td>
 <td>
 {{< image src="ordinalViewport.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}
 </td>

 </tr>
</table>

<br>

#### TimeViewport

```dart
TimeViewport(start, end)
```

Area pandang untuk menampilkan chart berdasarkan batas waktu awal dan akhir.

| Parameter | Tipe Data | Default    | Deskripsi                |
| --------- | --------- | ---------- | ------------------------ |
| start     | DateTime  | `required` | Batas awal sumbu domain  |
| end       | DateTime  | `required` | Batas akhir sumbu domain |

<table>
    
 <tr>
 <td style="text-align: center; vertical-align: middle;">null</td>
 <td><div>

```dart
TimeViewport(
    DateTime(2023, 8, 27),
    DateTime(2023, 8, 30),
),
```

  </div></td>

 </tr>
 <tr>
 <td>
{{< image src="timeViewport_null.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}
 </td>
 <td>
 {{< image src="timeViewport.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}
 </td>

 </tr>
</table>

<br>
