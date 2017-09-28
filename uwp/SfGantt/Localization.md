---
layout: post
title: Localization | SfGantt | Uwp | Syncfusion
description: The following section describes the localization in SfGantt.
platform: uwp
control: SfGantt
documentation: ug
---


# Localization 

Localization is the process of translating the application resources into different language for the specific cultures. You can localize the GanttControl by [adding resource file](https://msdn.microsoft.com/library/aa992030.aspx). Application culture can be changed by setting `PrimaryLanguageOverride` in the MainPage() constructor. 

In the below application, culture is configured to French language.

{% tabs %}
{% highlight c# %}
public MainPage()
{
    this.InitializeComponent();
    ApplicationLanguages.PrimaryLanguageOverride = "fr";
}   
{% endhighlight %}
{% endtabs %}


To localize the GanttControl based on `PrimaryLanguageOverride` using resource files, follow the below steps. 

1.Right-click the project, select **Add** and then **NewItem**.

2.In `Add New Item` wizard, select the **Resource File** option and name the filename as **&lt;culture name&gt;.resw**. 

For example, you have to give name as **fr.resw** for French culture.
 
3.The culture name that indicates the name of language and country. 

![](Localization_images/AddResource.png)

4.Add the Name/Value pair in Resource Designer of **fr.resw** file and change its corresponding value to corresponding culture. 

![](Localization_images/FinalOutput.png)

You can download the sample for localization of Gantt from [here](http://www.syncfusion.com/downloads/support/directtrac/general/SFGANT~11958419239.ZIP)