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

1.Right click the project, select **Add** and then **NewItem**.

2.In Add New Item  dialog, select the Resource File  and name the filename as **<culture name>** **. ** **resw **. The culture name that indicates the name of language and country. 

For example, you will have to give name as **fr.resw** for French culture.
 
3.The culture name that indicates the name of language and country. 

![](Localization_images/AddResource.png)

4.Add the Name/Value pair in Resource Designer of **fr.resw** file and change its corresponding value to corresponding culture. 

![](Localization_images/FinalOutput.png)

You can download the sample for localization of Gantt from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Localization-918242921.zip)