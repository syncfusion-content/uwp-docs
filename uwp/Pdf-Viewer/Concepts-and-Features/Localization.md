---
layout: post
title: Localization in UWP PDF Viewer control | Syncfusion
description: Learn here all about Localization support in Syncfusion UWP PDF Viewer (SfPdfViewer) control and more.
platform: UWP
control: SfPdfViewerControl
documentation: ug
keywords: localization
---
# Localization in UWP PDF Viewer (SfPdfViewer)

Localization is the process of configuring the application to a specific language. SfPdfViewerControl provides support to localize the context menu. Localization can be done by adding resource file (Resw) and setting the specific culture in the application.

## Setting language in the app manifest file

The following steps illustrates you how to configure the app package for localization using the manifest designer

* In **Solution** **Explorer**, expand the project node of your UWP app.
* Double-click the **Package****.****appxmanifest** file. If the manifest file is already open in the XML code view, Visual Studio prompts you to close the file.
* Now specify the **Default** **language** on the **Application** tab as required to localize your app. Click on **More** **information** to know about the supported languages.

![Package manifest](Localization_images/Localization_img1.png)


* Save the app manifest file after setting the default language.

## Adding Resource file

* Create a folder with name ‘Resources’ in your application.
* Create a folder with language (“en-US”, “fr-FR”, etc.) under ‘Resources’ to hold the resource file for the respective language.
* Add default English (“en-US”) [Resw](https://www.syncfusion.com/downloads/support/directtrac/general/ze/Resources_file-384663272.zip)(resource) file of SfPdfViewerControl in the ‘en-US’ folder, named as Syncfusion.SfPdfViewerControl.UWP.Resources.resw, Syncfusion.SfColorPickers.WinRT.Resources.resw and Localization.Resources. resw respectively. For your reference, French(“fr-FR”) [Resw](https://www.syncfusion.com/downloads/support/directtrac/general/ze/Resources_file-1894054239.zip) file.

![Culture resources](Localization_images/Localization_img2.png)


* Add the resource key such as name and its corresponding localized value in Resource Designer of Syncfusion.SfPdfViewerControl.UWP.Resources.resw, Syncfusion.SfColorPickers.WinRT.Resources.resw file.

![Resource Dictionary](Localization_images/Localization_img3.png)


The following screenshot shows the localization of context menu in SfPdfViewerControl.

![Output](Localization_images/Localization_img4.png)

