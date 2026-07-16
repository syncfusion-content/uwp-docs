---
layout: post
title: Localization in UWP Spell Checker control | Syncfusion
description: Learn here all about Localization support in Syncfusion UWP Spell Checker (SfSpellChecker) control and more.
platform: UWP
control: SfSpellChecker
documentation: ug
---

# Localization in UWP Spell Checker (SfSpellChecker)

Localization is the process of translating the application resources into different languages for specific cultures. You can localize the SfSpellChecker by adding a resource file. The application culture can be changed by setting [ApplicationLanguages.PrimaryLanguageOverride](https://msdn.microsoft.com/en-us/library/windows/apps/windows.globalization.applicationlanguages.primarylanguageoverride.aspx) before the `InitializeComponent()` method.
 
The example below sets the application culture to Arabic.

{% tabs %}

{% highlight c# %}

public MainPage()

{

    Windows.Globalization.ApplicationLanguages.PrimaryLanguageOverride = "ar-SA";

    this.InitializeComponent();
}

{% endhighlight %}

{% endtabs %}

To localize the SfSpellChecker based on [ApplicationLanguages.PrimaryLanguageOverride](https://msdn.microsoft.com/en-us/library/windows/apps/windows.globalization.applicationlanguages.primarylanguageoverride.aspx) using .resw files, follow the below steps.

1. Create a folder named **Resource** in the application.

2. Create a folder named **culture name** in the application. The culture name that indicates the name of language and country.

![localizationimg1](localization-images/localizationimg1.png)

3. Right-click the project and select the "Add New Item" dialog using Ctrl+Shift+A keys.

4. Create a resource (.resw) file and name it as `<assembly-name>.Resources.resw` (for example, `Syncfusion.SfSpellChecker.UWP.Resources.resw`).

![localizationimg2](localization-images/localizationimg2.png)

For example, you have to give name as **Syncfusion.SfSpellChecker.UWP.Resources.resw** for Arabic culture.

5. Open the Resource Designer for `Syncfusion.SfSpellChecker.UWP.Resources.resw` and add the Name/Value pairs. Change each value to its corresponding culture's translation.

![Localizationimg3](localization-images/Localizationimg3.png)

You can get the SfSpellChecker’s key from default resource  [Syncfusion.SfSpellChecker.UWP.Resources.resw]
(http://www.syncfusion.com/downloads/support/directtrac/general/ze/Syncfusion.SfSpellChecker.UWP.Resources-1005709407.zip).

![localizationimg4](localization-images/localizationimg4.png)
