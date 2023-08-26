---
title: "Config Render Pie"
date: 2023-08-17T17:10:57+07:00
weight: 2
draft: false
keywords: ["d_chart", "render", "pie", "config"]
---

Mengkonfigurasi tampilan Pie

```dart
ConfigRenderPie? configRenderPie
```

<br>

| <div style="width:160px">Properti</div> | <div style="width:140px">Tipe Data</div> | <div style="width:70px">Default</div> | Deskripsi                                                                                                                                                                                                                                                                                                                                                                                |
| --------------------------------------- | ---------------------------------------- | ------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| arcLabelDecorator                       | [ArcLabelDecorator?](#arclabeldecorator) | null                                  | Mendekorasi label item pie                                                                                                                                                                                                                                                                                                                                                               |
| arcLength                               | double                                   | 2 \* pi <br><br>(pi from `dart:math`) | Total panjang busur, dalam radian. <br>2π = Full                                                                                                                                                                                                                                                                                                                                         |
|                                         |                                          |                                       | {{< image src="full.png" caption="Full" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}                                                                                                                                                                                                                  |
|                                         |                                          |                                       | {{< image src="three_quarter.png" caption="Three-Quarter" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}                                                                                                                                                                                                |
|                                         |                                          |                                       | {{< image src="half.png" caption="Half" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}                                                                                                                                                                                                                  |
|                                         |                                          |                                       | {{< image src="quarter.png" caption="Quarter" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}                                                                                                                                                                                                            |
| arcRatio                                | double?                                  | null                                  | Jika disetel, konfigurasikan arcWidth menjadi persentase radius. harus antara `0` dan `1`                                                                                                                                                                                                                                                                                                |
|                                         |                                          |                                       | {{< image src="arcRatio_0_5.png" caption="0.5" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}                                                                                                                                                                                                           |
|                                         |                                          |                                       | {{< image src="arcRatio_0_2.png" caption="0.2" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}                                                                                                                                                                                                           |
| arcWidth                                | int?                                     | null                                  | Menetapkan lebar busur dalam radius. Jika **arcRatio** disetel, nilai ini akan diabaikan.                                                                                                                                                                                                                                                                                                |
|                                         |                                          |                                       | {{< image src="arcWidth_40.png" caption="40px" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}                                                                                                                                                                                                           |
| startAngle                              | double                                   | -pi / 2                               | Sudut awal untuk irisan pai, dalam radian.<br> Sudut ditentukan dari sumbu x positif dalam ruang Cartesian.<br> Sudut awal defaultnya adalah -π/2                                                                                                                                                                                                                                        |
|                                         |                                          |                                       | {{< image src="startAngle_default.png" caption="Default" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} {{< image src="startAngle_min_pi_slice_1.png" caption="-pi / 1" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |
| strokeWidthPx                           | double                                   | `2.0`                                 | Lebar goresan pada batas busur                                                                                                                                                                                                                                                                                                                                                           |
|                                         |                                          |                                       | {{< image src="strokeWidthPx.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}                                                                                                                                                                                                             |

<br>

#### ArcLabelDecorator

| <div style="width:150px">Properti</div> | Tipe Data                                           | Default                                                                          | Deskripsi                                                           |
| --------------------------------------- | --------------------------------------------------- | -------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| insideLabelStyle                        | [LabelStyle](#labelstyle)                           | const LabelStyle(fontSize: 12, color: Colors.white)                              | Styling teks label ketika di dalam pie                              |
| outsideLabelStyle                       | [LabelStyle](#labelstyle)                           | const LabelStyle(fontSize: 12, color: Colors.white)                              | Styling teks label ketika di luar pie                               |
| labelPadding                            | int                                                 | `5`                                                                              | Ruang sebelum dan sesudah teks label                                |
| labelPosition                           | [ArcLabelPosition](#arclabelposition)               | ArcLabelPosition.auto                                                            | Mengonfigurasi tempat menempatkan label relatif terhadap busur      |
| leaderLineStyle                         | [ArcLabelLeaderLineStyle](#arclabelleaderlinestyle) | const ArcLabelLeaderLineStyle(color: Colors.black, length: 20.0, thickness: 1.0) | Memberikan style pada line label dimana letak label ada di luar pie |
| showLeaderLines                         | bool                                                | true                                                                             | Menampilkan garis label                                             |

<br>

#### LabelStyle

| Properti | Tipe Data | Default        | Deskripsi                          |
| -------- | --------- | -------------- | ---------------------------------- |
| color    | Color     | Colors.black87 | Memberikan warna pada label domain |
| fontSize | int?      | `12`           | Set ukuran label domain            |

<br>

#### ArcLabelPosition

| <div style="width:70px">Tipe</div> | Deskripsi                                                                                                                                                                                                                                                                                                                                                            |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| auto                               | Secara otomatis coba tempatkan label di dalam busur terlebih dahulu dan letakkan di luar ruang yang tersedia di luar busur lebih besar dari ruang yang tersedia di dalam busur. {{< image src="ArcLabelPosition_auto.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |
| outside                            | Selalu letakkan label di luar pie {{< image src="ArcLabelPosition_outside.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}                                                                                                                                            |
| inside                             | Selalu letakkan label di dalam pie {{< image src="ArcLabelPosition_inside.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}                                                                                                                                            |

<br>

#### ArcLabelLeaderLineStyle

Default class:

```dart
const ArcLabelLeaderLineStyle(
    color: Colors.black,
    length: 20.0,
    thickness: 1.0,
)
```

| Properti  | Tipe Data | Default    | Deskripsi                         |
| --------- | --------- | ---------- | --------------------------------- |
| color     | Color     | `required` | Memberikan warna pada garis label |
| length    | double    | `required` | Panjang garis label               |
| thickness | double    | `required` | Ketebalan garis label             |

<br>
