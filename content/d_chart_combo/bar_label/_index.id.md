---
title: "Bar Label"
date: 2023-08-17T17:10:57+07:00
weight: 1
draft: false
keywords: ["d_chart", "label", "bar", "combo"]
---

Mengkustomisasi tampilan label di bar chart

<br>

| <div style="width:180px">Properti</div> | <div style="width:140px">Tipe Data</div>                             | <div style="width:70px">Default</div> | Deskripsi                                                       |
| --------------------------------------- | -------------------------------------------------------------------- | ------------------------------------- | --------------------------------------------------------------- |
| barLabelDecorator                       | [BarLabelDecorator?](#barlabeldecorator)                             | null                                  | Menentukan letak posisi label                                   |
| [barLabelValue](#barlabelvalue)         | String Function(OrdinalGroup, OrdinalData, int?)?                    | domain value                          | Untuk menampilkan label, **barLabelDecorator** tidak boleh null |
| insideBarLabelStyle                     | [LabelStyle](#labelstyle) Function(OrdinalGroup, OrdinalData, int?)? | null                                  | Styling teks label yang posisinya di dalam bar                  |
| outsideBarLabelStyle                    | [LabelStyle](#labelstyle) Function(OrdinalGroup, OrdinalData, int?)? | null                                  | Styling teks label yang posisinya di luar bar                   |

<br>

#### BarLabelDecorator

| <div style="width:160px">Properti</div> | <div style="width:140px">Tipe Data</div> | <div style="width:70px">Default</div> | Deskripsi                                                                                                                                                                                                                                                                                                                                                |
| --------------------------------------- | ---------------------------------------- | ------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| barLabelPosition                        | [BarLabelPosition](#barlabelposition)    | BarLabelPosition.auto                 | Mengonfigurasi tempat menempatkan label relatif terhadap bar                                                                                                                                                                                                                                                                                             |
| labelAnchor                             | [BarLabelAnchor](#barlabelanchor)        | null                                  | Posisi label ketika di dalam bar                                                                                                                                                                                                                                                                                                                         |
| labelPadding                            | int                                      | `5`                                   | Jarak sebelum dan sesudah teks label                                                                                                                                                                                                                                                                                                                     |
|                                         |                                          |                                       | {{< image src="labelPadding.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} {{< image src="labelPadding2.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |

<br>

#### BarLabelPosition

| <div style="width:70px">Tipe</div> | Deskripsi                                                                                                                                                                               |
| ---------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| auto                               | Secara otomatis mencoba menempatkan label di dalam bar terlebih dahulu dan jika tidak muat maka akan di set diluar bar                                                                  |
|                                    | {{< image src="BarLabelPosition_auto.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}    |
| inside                             | Selalu tempatkan label di dalam bar                                                                                                                                                     |
|                                    | {{< image src="BarLabelPosition_inside.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}  |
| outside                            | Selalu tempatkan label di luar bar                                                                                                                                                      |
|                                    | {{< image src="BarLabelPosition_outside.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |
| right                              | Menempatkan label di sebelah kanan di dalam bar, dan berlaku untuk bar horizontal. Untuk sekarang bar horizontal di **Combo** belum bisa digunakan                                      |

<br>

#### BarLabelAnchor

| <div style="width:70px">Tipe</div> | Deskripsi                                                                                                                                                                            |
| ---------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| start                              | Memposisikan label di awal/bawah bar                                                                                                                                                 |
|                                    | {{< image src="BarLabelAnchor_start.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}  |
| middle                             | Memposisikan label di tengah bar                                                                                                                                                     |
|                                    | {{< image src="BarLabelAnchor_middle.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |
| end                                | Memposisikan label di akhir/atas bar                                                                                                                                                 |
|                                    | {{< image src="BarLabelAnchor_end.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}    |

<br>

#### BarLabelValue

- Menampilkan nilai measure

```dart
barLabelValue: (group, ordinalData, index) {
    return ordinalData.measure.round().toString();
},
```

{{< image src="barLabelValue1.png" caption="" alt="alter-text" height="" width="" position="start" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>

- Menampilkan nilai measure dan domain

```dart
barLabelValue: (group, ordinalData, index) {
    String domain = ordinalData.domain;
    String measure = ordinalData.measure.round().toString();
    return '$domain: $measure kg';
},
```

{{< image src="barLabelValue2.png" caption="" alt="alter-text" height="" width="" position="start" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>

- Tampil tergantung kondisi

```dart
barLabelValue: (group, ordinalData, index) {
    if (ordinalData.measure < 6) return '';
    String measure = ordinalData.measure.round().toString();
    return '$measure kg';
},
```

{{< image src="barLabelValue3.png" caption="" alt="alter-text" height="" width="" position="start" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>

#### LabelStyle

| Properti | Tipe Data | Default        | Deskripsi                          |
| -------- | --------- | -------------- | ---------------------------------- |
| color    | Color     | Colors.black87 | Memberikan warna pada label domain |
| fontSize | int?      | `12`           | Set ukuran label domain            |

```dart
insideBarLabelStyle: (group, ordinalData, index) {
    return const LabelStyle(
        color: Colors.white,
        fontSize: 16,
    );
},
outsideBarLabelStyle: (group, ordinalData, index) {
    return LabelStyle(
        color: group.color ?? Colors.black,
        fontSize: 20,
    );
},
```

{{< image src="LabelStyle_inside_outside.png" caption="" alt="alter-text" height="" width="" position="start" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>
