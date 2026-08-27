---
layout: post
title: Localization in UWP Gantt Chart | Syncfusion
description: Learn about Localization support in Syncfusion UWP Gantt Chart using culture-specific resources and localization settings.
platform: uwp
control: SfGantt
documentation: ug
---

# Localization in UWP Gantt Chart

Localization is the process of translating the application resources into different languages for specific cultures. You can localize the UWP Gantt Chart by adding a resource file. The application culture can be changed by setting the `PrimaryLanguageOverride` in the MainPage() constructor.

The following code sample demonstrates how to configure the application culture to French language.

{% tabs %}
{% highlight c# %}
public MainPage()
{
    this.InitializeComponent();
    ApplicationLanguages.PrimaryLanguageOverride = "fr";
}   
{% endhighlight %}
{% endtabs %}

To localize the UWP Gantt Chart based on `PrimaryLanguageOverride` using resource files, use the following steps:

1. Right-click the project, click **Add**, click **New Folder**, and then name the folder **Resources**.
2. Right-click the **Resources** folder, click **Add**, click **New Folder**, and then name the folder **[culture name]**. The culture name indicates name of the language and country.

For example, you will have to give name as **fr-FR** for French culture.

3. Right-click the **[culture name]** folder, click **Add**, and then click **NewItem**.

4. In the Add New Item dialog, click the Resource File, and then name the file name as **Syncfusion.SfGantt.UWP.Resources.resw**.

![AddResource](Localization_images/AddResource.png)

5. Add the Name/Value pair in Resource Designer of **Syncfusion.SfGantt.UWP.Resources.resw** file, and change the corresponding value to the corresponding culture.

You can get the localization keys from the default resource [Syncfusion.UWP Gantt Chart.UWP.Resources.resw](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Syncfusion.UWP Gantt Chart.UWP.Resources845531575.zip).

![FinalOutput](Localization_images/FinalOutput.png)

You can download [the sample](http://www.syncfusion.com/downloads/support/directtrac/general/ze/UWP Gantt Chart_Localization1607055000.zip) for localization.
