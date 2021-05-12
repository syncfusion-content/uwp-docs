---
layout: post
title: Custom Dictionary in UWP Spell Checker control | Syncfusion
description: Learn here all about Custom Dictionary support in Syncfusion UWP Spell Checker (SfSpellChecker) control and more.
platform: UWP
control: SfSpellChecker
documentation: ug
---

# Custom Dictionary in UWP Spell Checker (SfSpellChecker)

`SfSpellChecker` provides predefined dictionary for English language and also supports to custom dictionary based on Application requirement. `SfSpellChecker` provides suggestions based on custom dictionary. Users can use their own dictionaries for the different languages. Please follow the below steps for custom language spell checking.

**Step 1:** Need to create dictionary file for user desired language and add necessary words details in it. 
 
**Step 2:** Then need to attach it with the application and define this file location in its property named CustomDictionaryPath. 
 
`CustomDictionaryPath` property is used to passing the file path of the user defined custom dictionary.

>**Note:** The BuildAction of dictionary file should set as "Content".

## Setting CustomDictionaryPath

Create a `SfSpellChecker` instance and set the `CustomDictionaryPath` as given in the below code.

{% tabs %}

{% highlight C# %}

SfSpellChecker SpellCheck = new SfSpellChecker(); 

SpellCheck.CustomDictionaryPath = "custom.txt";

{% endhighlight %}

{% endtabs %}
