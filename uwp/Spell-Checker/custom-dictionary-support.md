---
layout: post
title: Custom Dictionary in UWP SfSpellChecker | Syncfusion®
description: The Custom Dictionary support in SfSpellChecker provides suggestions based on user-defined dictionaries for different languages.
platform: uwp
control: SfSpellChecker
documentation: ug
---

# Custom Dictionary in UWP Spell Checker

`UWP Spell Checker` provides predefined dictionary for English language and also supports to custom dictionary based on Application requirement. It also provides suggestions based on custom dictionary. Users can use their own dictionaries for the different languages. Please follow the below steps for custom language spell checking.

**Step 1:** Need to create dictionary file for user desired language and add necessary words details in it. 
 
**Step 2:** Then need to attach it with the application and define this file location in its property named CustomDictionaryPath. 
 
`CustomDictionaryPath` property is used to passing the file path of the user defined custom dictionary.

>**Note:** The BuildAction of dictionary file should set as "Content".

## Setting CustomDictionaryPath

Create a `UWP Spell Checker` instance and set the `CustomDictionaryPath` as given in the below code.

{% tabs %}

{% highlight C# %}

SfSpellChecker SpellCheck = new SfSpellChecker(); 

SpellCheck.CustomDictionaryPath = "custom.txt";

{% endhighlight %}

{% endtabs %}
