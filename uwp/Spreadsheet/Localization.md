---
layout: post
title: Localization in UWP Spreadsheet control | Syncfusion
description: Learn here all about Localization support in Syncfusion UWP Spreadsheet (SfSpreadsheet) control and more.
platform: UWP
control: SfSpreadsheet
documentation: ug
---

# Localization in UWP Spreadsheet (SfSpreadsheet)

Localization is the process of configuring the application to a specific language. SfSpreadsheet provides support to localize all the static text in a Ribbon and all dialogs to any desired language. Localization can be done by adding resource file and setting the specific culture in the application.

SfSpreadsheet allows you to set custom resource using Resw file. You can define your string values in resource file for a specific culture and set the culture in your application.

## Set Current UI Culture to the Application

To set the CultureInformation in the Application, set the `CurrentUICulture` before the InitializeComponent() method is called. 

Setting of the culture information,

{% tabs %}
{% highlight c# %}
   
public MainPage()
{
    System.Globalization.CultureInfo.CurrentUICulture = new System.Globalization.CultureInfo("ja");
    InitializeComponent();
}

{% endhighlight %}
{% endtabs %}

Now, the Application is set to the Japanese Culture info. 

## Localization using Resource file

The following steps show how to implement the localization in SfSpreadsheet,

* Create a folder and name it as ‘Resources’ in your application.
* Add the default resource[English("en-US")] file of `SfSpreadsheet` in the 'Resources' folder named as Syncfusion.SfSpreadsheet.UWP.resw.
  You can download the Resw file [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Syncfusion.SfSpreadsheet.UWP.Resources1773657760)
* Create Resw(resource) file under the 'Resources' folder and name it as Syncfusion.SfSpreadsheet.UWP.[Culture name].resw. 
  For example, Syncfusion.SfSpreadsheet.UWP.ja.resw for Japanese culture. 

![UWP SfSpreadsheet displays added resource file](localization_images/Loc_Image1.png)

* Add the resource key such as name and its corresponding localized value in Resource Designer of Syncfusion.SfSpreadsheet.UWP.ja.resw file. 
  For your reference, you can download the Japanese("ja-JP") Resw file [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Syncfusion.SfSpreadsheet.UWP.Resources.ja2068752327)

![UWP SfSpreadsheet displays resource file item list](localization_images/Loc_Image2.png)

The following screenshot shows you the localization in SfSpreadsheet,

![UWP SfSpreadsheet displays locaization applied in sheet](localization_images/Loc_Image3.png)

## Modifying the localized strings in Resource file

Users can modify the default localized strings in Resource file by adding the default [Resw](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Syncfusion.SfSpreadsheet.UWP.Resources1773657760) (resource) file of `SfSpreadsheet` in the 'Resources' folder of your application and name it as Syncfusion.SfSpreadsheet.UWP.resw.

Now, the default localized strings can be modified by changing the Name/Value pair in the Syncfusion.SfSpreadsheet.UWP.resw file.

![UWP SfSpreadsheet displays modified resource file item](localization_images/Loc_Image4.jpg)
