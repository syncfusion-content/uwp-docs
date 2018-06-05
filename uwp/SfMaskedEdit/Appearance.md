---
layout: post
title: Appearance | SfMaskedEdit | UWP | Syncfusion
description: Appearance of SfMaskedEdit
platform: uwp
control: SfMaskedEdit
documentation: ug
---
# Appearance

Appearance of the `SfMaskedEdit` control can be customized by using the `BorderBrush` and `ErrorBorderBrush` properties.

## Border

### BorderBrush

Customize the `BorderBrush` property that provides border color for the `SfMaskedEdit`.

{% tabs %}

{% highlight xaml %}

<Input:SfMaskedEdit Width="255" Height="46" BorderBrush="Blue"/>

{% endhighlight %}

{% highlight C# %}

SfMaskedEdit maskededit = new SfMaskedEdit();
maskededit.BorderBrush = Brushes.Blue;

{% endhighlight %}

{% endtabs %}

![](Appearence_Images/Appearence_Img1.jpg)


### ErrorBorderBrush

Customize the `ErrorBorderBrush` property that provides border color for the `SfMaskedEdit` when the validation becomes failed.

{% tabs %}

{% highlight xaml %}

<Input:SfMaskedEdit Width="255" Height="46" ErrorBorderBrush="DarkOrange"/>

{% endhighlight %}

{% highlight C# %}

SfMaskedEdit maskededit = new SfMaskedEdit();
maskededit.ErrorBorderBrush = Brushes.DarkOrange;

{% endhighlight %}

{% endtabs %}

![](Appearence_Images/Appearence_Img2.jpg)

## ShowPromptOnFocus

If the `ShowPromptOnFocus` property is set to true, the prompt characters will be ignored when the control lost it focus. The prompt characters will be restored when focusing the control.

{% tabs %}

{% highlight xaml %}

<Input:SfMaskedEdit Width="255" Height="46" MaskType="Simple" Mask="(000) 000-0000" ShowPromptOnFocus="True"/>

{% endhighlight %}

{% highlight C# %}

SfMaskedEdit maskededit = new SfMaskedEdit();
maskededit.MaskType = MaskType.Simple;
maskedEdit.Mask = "(000) 000-0000";
maskedEdit.ShowPromptOnFocus = true;

{% endhighlight %}

{% endtabs %}

Control loses focus

![](Appearence_Images/Appearence_Img3.jpg)

Control gets focus

![](Appearence_Images/Appearence_Img4.jpg)