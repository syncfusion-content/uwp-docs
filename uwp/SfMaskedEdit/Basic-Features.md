---
layout: post
title: Basic Features provided by SfMaskedEdit control for UWP
description: Basic Features provided by SfMaskedEdit control for UWP
platform: uwp
control:  SfMaskedEdit
documentation: ug
---

# Basic Features

## Mask the input

To mask the input, set the MaskType and Mask property as follows:

{% tabs %}

{% highlight xaml %}
	
<syncfusion:SfMaskedEdit MaskType="Simple" Mask="00/00/0000"  HorizontalAlignment="Left"  TextWrapping="Wrap"  VerticalAlignment="Top" Width="255" Height="46"/>

{% endhighlight %}

{% highlight c# %}

SfMaskedEdit maskededit = new SfMaskedEdit() { Width = 255, Height = 46 };
maskededit.MaskType = MaskType.Simple;
maskededit.Mask ="00 / 00 / 0000";

{% endhighlight %}

{% endtabs %}
   
This mask expression allows only numeric inputs in the places of 0.

## Setting Value
Set the Value property as follows:

{% tabs %}
{% highlight xaml %}

<syncfusion:SfMaskedEdit MaskType="Simple" Mask="00/00/0000" Value="14/11/2014" HorizontalAlignment="Left"  TextWrapping="Wrap"  VerticalAlignment="Top" Width="255" Height="46"/>

{% endhighlight %}

{% highlight c# %}

 SfMaskedEdit maskedEdit = new SfMaskedEdit();
 maskedEdit.MaskType = MaskType.Simple;
 maskedEdit.Mask ="00 / 00 / 0000";
 maskedEdit.Value ="14 / 11 / 2014";
   
{% endhighlight %}
{% endtabs %}

## Setting Prompt Char
Set the PromptChar property as follows:
{% tabs %}

{% highlight c# %}
 SfMaskedEdit maskedEdit = new SfMaskedEdit();
 maskedEdit.MaskType = MaskType.Simple;
 maskedEdit.Mask ="00 / 00 / 0000";
 maskedEdit.PromptChar = Convert.ToChar("$");
   
{% endhighlight %}

{% endtabs %}

By default, the prompt character is ‘_’.

## Setting Watermark
Set the Watermark property as follows:
{% tabs %}
{% highlight xaml %}
<syncfusion:SfMaskedEdit  MaskType="Simple" Mask="00/00/0000" Watermark="Mask"  HorizontalAlignment="Left"  TextWrapping="Wrap"  VerticalAlignment="Top" Width="255" Height="46"/>
{% endhighlight %}

{% highlight c# %}

SfMaskedEdit maskedEdit = new SfMaskedEdit();
maskedEdit.MaskType = MaskType.Simple;
maskedEdit.Mask ="00 / 00 / 0000";
maskedEdit.Watermark ="Type here";

{% endhighlight %}
{% endtabs %}