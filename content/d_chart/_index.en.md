---
title: "D Chart"
date: 2023-08-17T17:10:57+07:00
---

open in [pub.dev](https://pub.dev/packages/d_chart) or [github](https://github.com/indratrisnar/d_chart)

| No  | Type                     |     |
| :-: | ------------------------ | --- |
|  1  | [Bar]                    | -   |
|  2  | [Line]                   | -   |
|  3  | [Pie & Donut]            | -   |
|  4  | [Gauge]                  | -   |
|  5  | [Bar Custom]             | -   |
|  6  | [Time]                   | -   |
|  7  | [Scatter Plot (Point)]   | -   |
|  8  | [Single Bar]             | -   |
|  9  | [Combo](/d_chart_combo/) | -   |

<br>

#### Usage

Wrap it using a widget that has a size like:

- [AspecRatio](https://api.flutter.dev/flutter/widgets/AspectRatio-class.html)
- [SizedBox](https://api.flutter.dev/flutter/widgets/SizedBox-class.html)
- [Container](https://api.flutter.dev/flutter/widgets/Container-class.html)

```dart
AspectRatio(
    aspectRatio: 1,
    child: DChartComboO(),
),
SizedBox(
    width: 200,
    height: 100,
    child: DChartComboO(),
),
Container(
    width: 200,
    height: 100,
    child: DChartComboO(),
),
```
