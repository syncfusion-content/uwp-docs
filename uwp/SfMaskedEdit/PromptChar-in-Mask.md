---
layout: post
title: PromptChar in Mask| SfMaskedEdit | UWP | Syncfusion
description: Default and customize PromptChar in Mask
platform: uwp
control: SfMaskedEdit
documentation: ug
---
## Default PromptChar in Mask

Displays prompt character for the absence of your input in Mask and its default value is ‘_’.

![](PromptChar_In_Mask_Images/PromptChar_In_Mask_Img1.jpg)

## Custom PromptChar

The following example shows how to customize the prompt character using `PromptChar` property

{% tabs %}

{% highlight xaml %}

<Input:SfMaskedEdit  MaskType="Simple" Mask="00/00/0000" PromptChar="*" Width="255" Height="46"/>

{% endhighlight %}

{% highlight C# %}

SfMaskedEdit maskededit = new SfMaskedEdit();
maskededit.MaskType = MaskType.Simple;
maskedEdit.Mask = "00/00/0000";
maskedEdit.PromptChar = "*";

{% endhighlight %}

{% endtabs %}

![](PromptChar_In_Mask_Images/PromptChar_In_Mask_Img2.jpg)