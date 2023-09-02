---
title: "5. Asset"
date: 2023-08-17T11:00:00+07:00
lastmod: 2023-08-31T16:00:00+07:00
weight: 1
keywords: ["dart", "flutter", "bootcamp", "project", "asset"]
---

The data that will be used in the application is registered first in the **assets** identification section in `pubspec.yaml`. What is registered in pubspec is the location of the file, it can also be registered as the folder. Meanwhile, the files are directly added to the project, usually wrapped in an assets folder.

How to add files and register them in `pubspec.yaml`.

1. Click in the empty space right at the root of the project, then click new folder or click nan-> new folder. Name it assets or something like that.

{{< image src="1_1_project.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}
{{< image src="1_2_folder.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

2. Right click on the folder then select **Reveal in File Explorer**. Then it will automatically open the folder in file explorer.

{{< image src="2_reveal_file.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

3. Paste the files.

{{< image src="3_paste.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

4. Back in vscode, open `pubspec.yaml`. and register per file or register the folder. If there are sub folders then also register the sub folders. To summarize resource registration. Just list the folder that holds the file.

{{< image src="4_assets.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

5. Assets just need to be used, how to use them depends on the file type. However, to access the file, simply write the location and file name in string data form. An example is as below for image files.

{{< image src="5_usage.png" caption="" alt="alter-text" height="" width="" position="left" command="fill" option="q100" class="img-fluid" title=""  webp="false" >}}

<br>
