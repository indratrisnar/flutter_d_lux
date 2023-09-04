---
title: "16. Input"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 2
keywords:
  [
    "dart",
    "flutter",
    "bootcamp",
    "input",
    "textfield",
    "form",
    "radio",
    "checkbox",
    "switch",
  ]
---

Ada beberapa widget input bawaan flutter yang sering digunakan, diantaranya:

- [TextField](#1-textfield)
- [TextFormField & Form](#2-textformfield--form)
- [Radio](#3-radio)
- [CheckBox](#4-checkbox)
- [Switch](#5-switch)

<br>

#### 1. TextField

Input type widget dengan tanpa validator. Untuk akses dan modifikasi data input menggunakan TextEditingController class. Didukung property action seperti onChanged dan property styling seperti decoration.
Berikut contoh penggunaan Text Field Ketika non focus, focus, dan sudah diinput.

```dart
TextField(
  controller: edtInput,
  decoration: const InputDecoration(
    labelText: 'this is label',
    hintText: 'this is hint',
  ),
),
const SizedBox(height: 16),
TextField(
  controller: edtInput2,
  decoration: const InputDecoration(
    labelText: 'this is label',
    hintText: 'this is hint',
  ),
),
const SizedBox(height: 16),
TextField(
  controller: TextEditingController(),
  decoration: const InputDecoration(
    labelText: 'this is label',
    hintText: 'this is hint',
  ),
),
```

{{< image src="1_1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

Berikut cara get dan set data ke input.

```dart
final edtInput = TextEditingController();
final edtInput2 = TextEditingController();

ElevatedButton(
  onPressed: () {
    print(edtInput.text);
  },
  child: const Text('Get Value from input 1'),
),
const SizedBox(height: 16),
ElevatedButton(
  onPressed: () {
    edtInput2.text = 'here is new data';
  },
  child: const Text('Set Value to input 2'),
),
```

{{< image src="1_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

{{< image src="1_3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

<br>

#### 2. TextFormField & Form

Sama seperti Text Field namun dengan tambahan beberapa property seperti validator yang dikombinasikan dengan widget Form.

```dart
import 'package:flutter/material.dart';

class I2 extends StatelessWidget {
  const I2({super.key});

  @override
  Widget build(BuildContext context) {
    final edtInput = TextEditingController();
    final edtInput2 = TextEditingController();
    final formKey = GlobalKey<FormState>();
    return Scaffold(
      appBar: AppBar(
        title: const Text('Text Form Field & Form'),
        centerTitle: true,
      ),
      body: Form(
        key: formKey,
        child: ListView(
          padding: const EdgeInsets.all(16),
          children: [
            TextFormField(
              controller: edtInput,
              decoration: const InputDecoration(
                labelText: 'this is label',
                hintText: 'this is hint',
              ),
              validator: (value) {
                if (value == '') return "Don't empty"; // not valid
                return null; // valid
              },
            ),
            const SizedBox(height: 16),
            TextFormField(
              controller: edtInput2,
              decoration: const InputDecoration(
                labelText: 'this is label',
                hintText: 'this is hint',
              ),
              validator: (value) {
                if (value == '') return "Don't empty"; // not valid
                return null; // valid
              },
            ),
            const SizedBox(height: 16),
            ElevatedButton(
              onPressed: () {
                if (formKey.currentState!.validate()) {
                  print('valid');
                  print(edtInput.text);
                  print(edtInput2.text);
                } else {
                  print('not valid');
                }
              },
              child: const Text('Submit'),
            ),
          ],
        ),
      ),
    );
  }
}
```

{{< image src="2_1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}
{{< image src="2_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

Meskipun salah satu valid yaitu input1, karena Form ngebungkus 2 input (group). Maka input2 yang tidak valid mempengaruhi validitas form. Artinya semua input dengan group form yang sama harus valid semua.

{{< image src="2_3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}
{{< image src="2_4.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

Karena kedua input sudah valid, maka semua yang ada di block if dieksekusi.

<br>

#### 3. Radio

Opsi input yang hanya memilih satu dari sekian data yang disediakan. Perlu dibuat grouping untuk pengecekan bahwa hanya boleh satu yang dipilih. Implementasinya disarankan menggunakan class enum, meskipun bisa menggunakan tipe data lain. Untuk penggunaan easy namun simple bisa menggunakan salah satu package yang ada di pub.dev.

<table>
<tr>
<td><div>

```dart
String groupValueGenre = 'Male';

const Text('Genre:'),
Row(
  children: [
    Radio(
      value: 'Male',
      groupValue: groupValueGenre,
      onChanged: (value) {
        groupValueGenre = value!;
        setState(() {});
      },
    ),
    const Text('Male'),
  ],
),
Row(
  children: [
    Radio(
      value: 'Female',
      groupValue: groupValueGenre,
      onChanged: (value) {
        groupValueGenre = value!;
        setState(() {});
      },
    ),
    const Text('Female'),
  ],
),
```

</div></td>
<td>{{< image src="3_1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}</td>
</tr>

<tr>
<td><div>

```dart
enum SocialMedia { instagram, facebook, whatsapp }

SocialMedia groupValueSocialMedia = SocialMedia.instagram;

const Text('Social:'),
RadioListTile(
  value: SocialMedia.instagram,
  groupValue: groupValueSocialMedia,
  onChanged: (value) {
    groupValueSocialMedia = value!;
    setState(() {});
  },
  title: Text(SocialMedia.instagram.name),
),
RadioListTile(
  value: SocialMedia.facebook,
  groupValue: groupValueSocialMedia,
  onChanged: (value) {
    groupValueSocialMedia = value!;
    setState(() {});
  },
  title: Text(SocialMedia.facebook.name),
),
RadioListTile(
  value: SocialMedia.whatsapp,
  groupValue: groupValueSocialMedia,
  onChanged: (value) {
    groupValueSocialMedia = value!;
    setState(() {});
  },
  title: Text(SocialMedia.whatsapp.name),
),
```

</div></td>
<td>{{< image src="3_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}</td>
</tr>
</table>

<br>

#### 4. CheckBox

Opsi true and false, namun bisa di set memiliki nilai ke tiga dengan mengaktifkan tambahan property. Biasa digunakan untuk membuat persetujuan perjanjian dan lainnya. Biasa digunakan juga untuk pembuatan multiple selected. Untuk penggunaan easy namun simple bisa menggunakan salah satu package yang ada di pub.dev.

```dart
bool agree = false;

Row(
  children: [
    Checkbox(
      value: agree,
      onChanged: (value) {
        agree = value!;
        setState(() {});
      },
    ),
    const Text('Agreement'),
  ],
),
```

|                                                                                                                                                                  |                                                                                                                                                                  |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| {{< image src="4_1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} | {{< image src="4_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} |

```dart
List toopings = [
  {'name': 'cheese', 'value': false},
  {'name': 'sosis', 'value': false},
  {'name': 'sauce', 'value': false},
  {'name': 'puruluk', 'value': false},
];

const Text('Add Topping'),
...List.generate(toopings.length, (index) {
  Map item = toopings[index];
  return CheckboxListTile(
    value: item['value'],
    title: Text(item['name']),
    onChanged: (value) {
      toopings[index]['value'] = value;
      setState(() {});
    },
  );
}),
const SizedBox(height: 16),
ElevatedButton(
  onPressed: () {
    List selectedTopping = toopings
        .where((e) => e['value'] == true)
        .toList()
        .map((e) => e['name'])
        .toList();
    print('selected topping: $selectedTopping');
  },
  child: const Text('Get Selected topping'),
),
```

|                                                                                                                                                                  |                                                                                                                                                                  |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| {{< image src="4_3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} | {{< image src="4_4.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} |

<br>

#### 5. Switch

Seperti Check Box, memiliki 2 nilai yaitu true dan false. Switch sering digunakan seperti toggle button sebagai on/off atau active/inactive. Contoh penggunaannya seperti mengaktifkan reminder atau notification di settings.

```dart
import 'package:flutter/material.dart';

class I5 extends StatefulWidget {
  const I5({super.key});

  @override
  State<I5> createState() => _I5State();
}

class _I5State extends State<I5> {
  bool notification = false;
  bool reminder = true;
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text('Switch'),
        centerTitle: true,
      ),
      body: ListView(
        children: [
          ListTile(
            leading: const Icon(Icons.notifications),
            title: const Text('Notification'),
            trailing: Switch(
              value: notification,
              onChanged: (value) {
                notification = value;
                setState(() {});
              },
            ),
          ),
          ListTile(
            leading: const Icon(Icons.timer_sharp),
            title: const Text('Reminder'),
            trailing: Switch(
              value: reminder,
              onChanged: (value) {
                reminder = value;
                setState(() {});
              },
            ),
          ),
        ],
      ),
    );
  }
}
```

|                                                                                                                                                                  |                                                                                                                                                                  |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| {{< image src="5_1.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} | {{< image src="5_2.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} |
| {{< image src="5_3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} | {{< image src="5_4.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}} |

<br>
