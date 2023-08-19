---
title: "Config Render Point"
date: 2023-08-17T17:10:57+07:00
weight: 1
draft: false
keywords: ["d_chart", "render", "point", "combo", "scatter"]
---

Mengkonfigurasi tampilan Scatter Plot Chart

```dart
ConfigRenderPoint? configRenderPoint
```

<br>

| <div style="width:130px">Properti</div> | <div style="width:140px">Tipe Data</div> | <div style="width:70px">Default</div> | Deskripsi                                                                                                                                                                                                                                                |
| --------------------------------------- | ---------------------------------------- | ------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| radiusPx                                | double                                   | `3.5`                                 | Ukuran plot point/simbol                                                                                                                                                                                                                                 |
|                                         |                                          |                                       | {{< image src="radiusPx.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}                                                                                  |
| strokeWidthPx                           | double                                   | `0.0`                                 | Goresan untuk simbol **Target Line** atau border untuk simbol **Circle** dan **Rect**. Tidak berlaku untuk simbol **Triangle**.<br><br> Warna border mengikuti warna grup, sehingga agar berbeda dengan warna fill maka harus set properti **fillColor** |
|                                         |                                          |                                       | {{< image src="strokeWidthPx.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}                                                                             |
| symbolRender                            | [SymbolRender?](#symbolrender)           | SymbolRenderCircle()                  | Bentuk plot point/simbol                                                                                                                                                                                                                                 |

<br>

#### SymbolRender

Dari ke-4 simbol, terdapat properti **isSolid** bertipe **bool**.
Jika berniali **true** maka **fillColor** akan aktif. Dan jika **false** maka **fillColor** tidak akan aktif atau akan merubah warnanya menjadi putih.

<br>

1. SymbolRenderCircle

| true                                                                                                                                                                                   | false                                                                                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| {{< image src="SymbolRenderCircle_true.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} | {{< image src="SymbolRenderCircle_false.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |

<br>

2. SymbolRenderLine

Simbol ini dalam proses pemantauan untuk penggunaannya, belum pasti apakah akan diperbaiki. Pengunaan simbol ini berdampak pada posisi plot point yang tidak sesuai dengan data.

| true                                                                                                                                                                                 | false                                                                                                                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| {{< image src="SymbolRenderLine_true.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} | {{< image src="SymbolRenderLine_false.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |

<br>

3. SymbolRenderRect

| true                                                                                                                                                                                 | false                                                                                                                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| {{< image src="SymbolRenderRect_true.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} | {{< image src="SymbolRenderRect_false.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |

<br>

4. SymbolRenderTriangle

| true                                                                                                                                                                                     | false                                                                                                                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| {{< image src="SymbolRenderTriangle_true.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} | {{< image src="SymbolRenderTriangle_false.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}} |

<br>
