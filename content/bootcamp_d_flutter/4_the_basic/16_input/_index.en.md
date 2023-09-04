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

There are several input widgets built into Flutter that are often used, including:

- [TextField](#1-textfield)
- [TextFormField & Form](#2-textformfield--form)
- [Radio](#3-radio)
- [CheckBox](#4-checkbox)
- [Switch](#5-switch)

<br>

#### 1. TextField

Input type widget without validator. To access and modify input data use the TextEditingController class. Supported action properties such as onChanged and styling properties such as decoration.
The following is an example of using a Text Field when non-focused, focused, and already inputted.

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

Here's how to get and set data to input.

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

Same as Text Field but with the addition of several properties such as a validator combined with a Form widget.

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

Even though one of them is valid, namely input1, because the Form wraps 2 inputs (groups). So invalid inputs affect the validity of the form. This means that all input with the same form group must all be valid.

{{< image src="2_3.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}
{{< image src="2_4.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img- fluid" title="" webp="false" >}}

Because both inputs are valid, everything in the if block is executed.

<br>

#### 3. Radio

Input option that only selects one of the data provided. A grouping needs to be created to check that only one can be selected. The implementation is recommended to use the enum class, although other data types can be used. For easy but simple use, you can use one of the packages on pub.dev.

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

The options are true and false, but can be set to a third value by activating additional properties. Usually used to make agreement agreements and others. Also commonly used for making multiple selections. For easy but simple use, you can use one of the packages on pub.dev.

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

Like Check Box, it has 2 values namely true and false. Switches are often used like toggle buttons as on/off or active/inactive. Examples of its use are activating reminders or notifications in settings.

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
