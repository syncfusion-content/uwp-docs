---
layout: post
title: Localization in UWP TreeGrid control | Syncfusion
description: Learn here all about Localization support in Syncfusion UWP TreeGrid (SfTreeGrid) control and more.
platform: uwp
control: SfTreeGrid
documentation: ug
---

# Localization in UWP TreeGrid (SfTreeGrid)

Localization is the process of translating the application resources into different language for the specific cultures. You can localize the treegrid by adding resource file. Application culture can be changed by setting [CurrentUICulture](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.currentuiculture.aspx) before InitializeComponent method.

Below application culture changed to German.

{% tabs %}
{% highlight c# %}
public MainPage()
{
    System.Globalization.CultureInfo.CurrentUICulture = new System.Globalization.CultureInfo("de");
    this.InitializeComponent();
}
{% endhighlight %}
{% endtabs %}

## Localize the drag and drop window text in treegrid

To localize the treegrid, drag and drop window based on CurrentUICulture using resource files, follow the below steps.

1.Right-click on the project, select `Add` and then `NewItem`.

2.In Add New Item wizard, select the `Resource File` option and name the filename as `Syncfusion.SfGrid.UWP.Resources.&lt;culture name&gt;.resw`.

![Creating resource file](Localization_images/Localization_img1.jpeg)

3.For example, you have to give name as `Syncfusion.SfGrid.UWP.Resources.de.resw` for German culture.

4.The culture name that indicates the name of language and country.

5.Now the resource file is added.

![Added the created resource file](Localization_images/Localization_img2.jpeg)

6.Add the Name/Value pair in Resource Designer of `Syncfusion.SfGrid.UWP.Resources.de.resw` file and change its corresponding value to corresponding culture.
![Providing the resources as per culture](Localization_images/Localization_img3.jpeg)

You can get the SfTreeGrid’ s key from default resource [Syncfusion.SfGrid.UWP.Resources.resw](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Syncfusion.SfGrid.UWP.Resources-531431521.zip).

![Drag drop window of UWP treegrid with localized string](Localization_images/Localization_img4.jpeg)

You can download the sample [here](https://github.com/SyncfusionExamples/how-to-localize-the-drag-and-drop-window-text-in-treegrid/tree/master/UWP).

## Edit default culture resource 

You can edit default resource file by adding it to your application where the treegrid reads the static texts from here. You can download the default resource file from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Syncfusion.SfGrid.UWP.Resources-531431521.zip).

![Default resource file](Localization_images/Localization_img5.jpeg)

Now, change the Name/Value pair in Resource Designer of `Syncfusion.SfGrid.UWP.Resources.resw` file.

![Modifying the default localization in resource](Localization_images/Localization_img6.jpeg)


![Drag and drop window of UWP treegrid with modified resource](Localization_images/Localization_img7.jpeg)

