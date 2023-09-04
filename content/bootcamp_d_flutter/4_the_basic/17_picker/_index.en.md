---
title: "17. Picker"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 2
keywords:
  [
    "dart",
    "flutter",
    "bootcamp",
    "picker",
    "date",
    "range",
    "time",
    "image",
    "file",
  ]
---

There are several input widgets built into Flutter that are often used, including:

- [Date Picker](#1-date-picker)
- [Date Range Picker](#2-date-range-picker)
- [Time Picker](#3-time-picker)
- [Image Picker](#4-image-picker)
- [File Picker](#5-file-picker)

<br>

#### 1. Date Picker

```dart
DateTime now = DateTime.now();
showDatePicker(
  context: context,
  initialDate: now,
  firstDate: DateTime(2020),
  lastDate: DateTime(now.year + 1),
).then((value) {
  print('datePicked: ${value?.toIso8601String()}');
});
```

|                                                                                                                                                                  |                                                                                                                                                                  |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| {{< image src="1_1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} | {{< image src="1_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} |

<br>

#### 2. Date Range Picker

Same as Text Field but with the addition of several properties such as a validator combined with a Form widget.

```dart
DateTime now = DateTime.now();
showDateRangePicker(
  context: context,
  firstDate: DateTime(2020),
  lastDate: DateTime(now.year + 1),
  initialDateRange: DateTimeRange(
    start: now.subtract(const Duration(days: 3)),
    end: now,
  ),
).then((value) {
  print('duration: ${value?.duration.inDays} days');
  print('start: ${value?.start.toIso8601String()}');
  print('end: ${value?.end.toIso8601String()}');
});
```

|                                                                                                                                                                  |                                                                                                                                                                  |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| {{< image src="2_1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} | {{< image src="2_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} |

<br>

#### 3. Time Picker

```dart
DateTime now = DateTime.now();
showTimePicker(
  context: context,
  initialTime: TimeOfDay.fromDateTime(now),
).then((value) {
  print('timePicked: ${value?.toString()}');
});
```

|                                                                                                                                                                  |                                                                                                                                                                  |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| {{< image src="3_1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} | {{< image src="3_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} |

{{< image src="3_3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>

#### 4. Image Picker

Add the image_picker package in pubspec.yaml. Because how to use each version may be different, please check the Doc: [image_picker | Flutter Package (pub.dev)](https://pub.dev/packages/image_picker).

{{< image src="4_1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

- setup iOS

{{< image src="4_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

- setup Android

{{< image src="4_3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

{{< image src="4_4.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

```dart
pickImage(ImageSource source) async {
  XFile? xFile = await ImagePicker().pickImage(source: source);
  if (xFile == null) {
    print('cancel pick');
    return;
  }

  print('''
Mime type: ${xFile.mimeType}
Name: ${xFile.name}
Path: ${xFile.path}
Last modified: ${(await xFile.lastModified()).toIso8601String()}
''');
}
```

| Gallery                                                                                                                                                          | Camera                                                                                                                                                           |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| {{< image src="4_5.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} | {{< image src="4_6.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} |

{{< image src="4_7.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>

#### 5. File Picker

For setups like the Image Picker above. However, here we will give an example for a custom picker, with the usual document file format. Because the way to use each version may be different, please check the Doc:[file_picker | Flutter Package (pub.dev)](https://pub.dev/packages/file_picker)

```dart
pickFile() async {
  FilePickerResult? result = await FilePicker.platform.pickFiles(
    type: FileType.custom,
    allowedExtensions: ['txt', 'pdf', 'doc', 'docx'],
  );

  if (result != null) {
    PlatformFile file = result.files.first;

    print(file.name);
    print(file.bytes);
    print(file.size);
    print(file.extension);
    print(file.path);
  } else {
    print('User canceled the picker');
  }
}
```

{{< image src="5_1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}
{{< image src="5_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>
