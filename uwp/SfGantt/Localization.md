---
layout: post
title: Localization | SfGantt | Uwp | Syncfusion
description: The following section describes the localization in SfGantt.
platform: uwp
control: SfGantt
documentation: ug
---

# Localization 

Localization is the process of translating the application resources into different languages for the specific cultures. You can localize the SfGantt by adding resource file. Application culture can be changed by setting `PrimaryLanguageOverride` in the MainPage() constructor. 

In the below code example, culture is configured to French language.

{% tabs %}
{% highlight c# %}
public MainPage()
{
    this.InitializeComponent();
    ApplicationLanguages.PrimaryLanguageOverride = "fr";
}   
{% endhighlight %}
{% endtabs %}


To localize the SfGantt based on `PrimaryLanguageOverride` using resource files, follow the below steps: 

1.Right click the project, select **Add** and then **NewFolder**, name the folder name as **Resources**.

2.Right click on the **Resources** folder, select **Add** and then **NewFolder**, name the folder name as **[culture name]**. The culture name that indicates the name of language and country. 

For example, you will have to give name as **fr-FR** for French culture.

3.Right click the **[culture name]** folder, select **Add** and then **NewItem**.

4.In Add New Item  dialog, select the Resource File  and name the filename as **Syncfusion.SfGantt.UWP.Resources.resw**.

![](Localization_images/AddResource.png)

5.Add the Name/Value pair in Resource Designer of **Syncfusion.SfGantt.UWP.Resources.resw** file and change its corresponding value to corresponding culture.

![](Localization_images/FinalOutput.png)

You can download the sample for localization of Gantt from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/SfGantt_Localization-817789850.zip)