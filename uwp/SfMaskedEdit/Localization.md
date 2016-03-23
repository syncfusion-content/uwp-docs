---
layout: post
title: Culture of the SfMaskedEdit control for UWP
description: Culture of the SfMaskedEdit control for UWP
platform: uwp
control: SfMaskedEdit
documentation: ug
---

# Localization

SfMaskedEdit allows to build rich form-filling user interfaces by using culture-aware, localizable editor control. Text is formatted based on the specified Culture. 

The following code example shows how to localize the control to German culture.

{% highlight XAML %}

<syncfusion:SfMaskedEdit Grid.Row="8" Margin="10 5" Name="maskedEdit"
                                        Mask="$\d,\d{3}.\d{2}" MaskType="Regular" 
                                        Value="$1,000.00"  Width="400" Height="50"/>

{% endhighlight %}

{% highlight C# %}

 maskedEdit.Culture=new System.Globalization.CultureInfo("fr-FR");

{% endhighlight %}

{% highlight VB %}

 maskedEdit.Culture = New System.Globalization.CultureInfo("fr-FR")

{% endhighlight %}

![](Culture_images/Culture_img1.png)



