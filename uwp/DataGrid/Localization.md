---
layout: post
title: Localization in UWP DataGrid control | Syncfusion®
description: Learn here all about Localization support in Syncfusion® UWP DataGrid (SfDataGrid) control and more.
platform: uwp
control: SfDataGrid
documentation: ug
---


# Localization in UWP DataGrid (SfDataGrid)

Localization is the process of translating the application resources into different language for the specific cultures. You can localize the SfDataGrid by adding [resource] (https://msdn.microsoft.com/library/aa992030.aspx) file. Application culture can be changed by setting [CurrentUICulture](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.currentuiculture.aspx) before `InitializeComponent()` method.
 
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


To localize the SfDataGrid based on [CurrentUICulture](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.currentuiculture.aspx)  using .resw files, follow the below steps.
 
1. Right-click on the project, select **Add** and then **NewItem**.

2. In Add New Item wizard, select the **Resource File** option and name the filename as **Syncfusion.SfGrid.UWP.Resources.&lt;culture name&gt;.resw** .
 
![Shows the name of resource file to be added for UWP DataGrid](Localization_images/Localization_img1.png)

For example, you have to give name as **Syncfusion.SfGrid.UWP.Resources.de.resw** for German culture.
 
3. The culture name that indicates the name of language and country.
 
4. Now the resource file is added.


![Shows the added resource file for German language in UWP DataGrid](Localization_images/Localization_img2.png)

5.Add the Name/Value pair in Resource Designer of **Syncfusion.SfGrid.UWP.Resources.de.resw** file and change its corresponding value to corresponding culture.
 
![Shows the added resource file name / value pair in the resource designer in UWP DataGrid](Localization_images/Localization_img3.png)


You can get the SfDataGrid’s key from default resource  [Syncfusion.SfGrid.UWP.Resources.resw](https://www.syncfusion.com/downloads/support/directtrac/general/ze/Syncfusion.SfGrid.UWP.Resources-145129753.zip).


![Shows the localized in German for UWP DataGrid](Localization_images/Localization_img4.png)


## Editing default culture resource


You can edit default resource file by adding it to your application where SfDataGrid reads the static texts from here. You can download the default resource file from [here](https://www.syncfusion.com/downloads/support/directtrac/general/ze/Syncfusion.SfGrid.UWP.Resources-145129753.zip).

![Displaying the default culture resource editing for UWP SfDataGrid](Localization_images/Localization_img5.png)

Now, change the Name/Value pair in Resource Designer of **Syncfusion.SfGrid.UWP.Resources.resw** file.

![Displaying the name / value pair in the resource designer for default culture resource in UWP SfDataGrid](Localization_images/Localization_img6.png)


![Displaying UWP SfDataGrid with the default culture resource edited](Localization_images/Localization_img7.png)

