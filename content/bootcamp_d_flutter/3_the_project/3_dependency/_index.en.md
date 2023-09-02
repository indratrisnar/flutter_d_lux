---
title: "3. Dependency (Package)"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 1
keywords:
  ["dart", "flutter", "bootcamp", "project", "dependency", "package", "library"]
---

Dependencies or better known in Flutter as packages are source code (code) bundles that are created to speed up or make things easier to do something, which is the current context in Flutter development.

There are many packages for Flutter, which are generally divided into 2 types, the first is a package for feature needs such as UI, functions, methods, the second is a package for application configuration development needs such as setting application icons, application IDs, testing, etc. Packages that require features are divided into 2 types, there are packages that are only based on Flutter framework resources and there are also plugins (taking special resources to the destination platform).

Because of this, not all packages support all platforms, but there are packages that support only a few platforms, for example support for mobile so they can only be run on devices with Android and iOS OS.

Installing packages or registering packages that will be used is saved or installed in `pubspec.yaml` in the **dependencies** section. Feature packages are placed in dependencies while development packages are configured in the **dev_dependencies** section. Flutter has a base for downloading packages, namely on the web [pub.dev] (https://pub.dev/). On the home page of each package published on pub.dev there is an installation method and examples of its use.

In the image below there is an example of the **cupertino_icons** package to access icons with the Cupertino style guide from iOS (Apple). And **flutter_lints** is related to the `analysis_options.yaml` file to detect if there are problems or errors in the dart syntax.

{{< image src="dependency.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>
