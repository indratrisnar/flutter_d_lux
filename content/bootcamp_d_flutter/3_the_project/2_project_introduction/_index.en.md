---
title: "2. Project Introduction"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 1
keywords: ["dart", "flutter", "bootcamp", "project", "introduction"]
---

Before proceeding to the core material, let's first get acquainted with the Flutter project. Anything there, but a general overview. For specifics to the details of each section there is an explanation depending on the related material.

{{< image src="project_structure.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>

| <div style="width: 40px">No</div> | <div style="width:200px">Name</div> | Description                                                                                                                                                                                                         |
| :-------------------------------: | ----------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|                 1                 | .dart_tool                          | Dart SDK tool for programming needs, the version depends on the SDK installed.                                                                                                                                      |
|                 2                 | .idea                               | In general, it contains the visual studio code settings on the computer used. Other computers may have different settings.                                                                                          |
|                 3                 | android                             | Source code for implementation to the android platform. There are several features or packages that must be set specifically for certain parts of the platform, for example specifically for Android.               |
|                 4                 | ios                                 | Source code for implementation to the ios platform. There are several features or packages that must be set specifically for certain platforms, such as iOS.                                                        |
|                 5                 | lib                                 | Where all source code is stored, be it UI code, functions, classes, widgets and others. Including clean architecture implementation is also created in this lib folder.                                             |
|                 6                 | linux                               | Source code for implementation to the linux platform. There are several features or packages that must be set specifically for certain parts of the platform, for example specifically for Linux.                   |
|                 7                 | macos                               | Source code for implementation to the macOS platform. There are several features or packages that must be set specifically for certain parts of the platform, such as specifically for macOS.                       |
|                 8                 | test                                | Same as lib, but specifically for testing. Such as integration tests and unit tests.                                                                                                                                |
|                 9                 | web                                 | Source code for implementation to the web platform. There are several features or packages that must be set specifically for certain parts of the platform, for example specifically for the web.                   |
|                10                 | windows                             | Source code for implementation to the windows platform. There are several features or packages that must be set specifically for certain platforms, such as Windows.                                                |
|                11                 | .gitignore                          | Settings to handle sources that will be associated or not with git.                                                                                                                                                 |
|                12                 | .metadata                           | Information related to the project, in full there is additional information in the file.                                                                                                                            |
|                13                 | analysis_options.yaml               | Configure the analyzer to detect errors, warnings and more while coding in the workspace.                                                                                                                           |
|                14                 | pubspec.lock                        | Contains built-in flutter and external libraries/packages. This file should not be edited manually, it will result in the project not running properly or even not being able to run at all.                        |
|                15                 | pubspec.yaml                        | Contains summary project information. Place for registration of external packages. And registration of assets that will be used in the project. External packages added here will automatically enter pubspec.lock. |
|                16                 | README.md                           | Project information and documentation. Will appear on the published git home page.                                                                                                                                  |
|                17                 | <project_name>.iml                  | Module information.                                                                                                                                                                                                 |
|                18                 | build                               | The folder that contains the exported source executable, signing app, etc. It will appear if you have already run the application.                                                                                  |

<br>

What we can modify include the platforms folder, lib, test, pubspec.yaml, and README. .gitignore is optional if there are several settings when you want to push sources to Git.

If you want to upload or share projects manually without git, you can select all folders and files except **.dart_tool**, **.idea**, **build** then make the archive .zip, .rar, or the like. Or you can also do `flutter clean` first in the terminal to remove resource packages outside of project assets, then create an archive.

<br>
