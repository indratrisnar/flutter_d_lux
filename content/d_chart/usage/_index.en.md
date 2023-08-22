---
title: "Usage"
date: 2023-08-17T17:10:57+07:00
weight: 1
---

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
