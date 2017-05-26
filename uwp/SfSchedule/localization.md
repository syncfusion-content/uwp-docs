---
layout: post
title: Localization | SfSchedule | uwp | Syncfusion
description: Localization
platform: uwp
control: SfSchedule
documentation: ug
---

# Localization
Schedule control is available with complete localization support. Localization can be specified by setting the local language to the `PrimaryLanguageOverride`. In the format of `Language code`.

## Change default control language
Based on the locale specified the strings in the control such as Date, time, days are localized accordingly.
By default, schedule control is available with en locale, which is English.



{% highlight c# %} 

        ApplicationLanguages.PrimaryLanguageOverride = "fr";

{% endhighlight %}   


>**Note:** AM/PM in the timeline will not be localized in the Schedule views.


![](Localization_images/Localization_img1.png)


## Localizing custom text in UWP renderer.
You can localize custom text available in the control by adding equivalent localized string in the fr.resw file. Here we have used French language.

>**Note:** Here resw file name should be match with the given locale language code.

![](Localization_images/Localization_CustomText.png)


