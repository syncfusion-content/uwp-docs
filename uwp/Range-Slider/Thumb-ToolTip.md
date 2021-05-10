---
layout: post
title: Thumb ToolTip in UWP Range Slider control | Syncfusion
description: Learn here all about Thumb ToolTip support in Syncfusion UWP Range Slider (SfRangeSlider) control and more.
platform: uwp
control: SfRange Slider 
documentation: ug
---

# Thumb ToolTip in UWP Range Slider (SfRangeSlider)

The Thumb tooltip shows the current value on which the Thumb stands. 

![RangeSlider Thumb ToolTip view](Thumb-ToolTip_images/Thumb-ToolTip_img1.jpg)

## Thumb ToolTip Precision  

ThumbToolTipPrecision property is used to define the precision of the value displayed in the tooltip.  

{% tabs %}

{% highlight xaml %}

<editors:SfRangeSlider x:Name="rangeSlider" Width="200" VerticalAlignment="Center" Minimum="0" Maximum="100" Value="50" ThumbToolTipPrecision="2"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

   rangeSlider.ThumbToolTipPrecision = 2;

{% endhighlight %}

{% highlight VB %}

   rangeSlider.ThumbToolTipPrecision = 2

{% endhighlight %}

{% endtabs %}

![RangeSlider ThumbToolTipPrecision view](Thumb-ToolTip_images/Thumb-ToolTip_img2.jpg)

## Thumb ToolTip Position 

The position of the Thumb tooltip in relation to the Thumb can be controlled by the ThumbToolTipPlacement property. It has the following options.  

1. BottomRight 
2. TopLeft 
3. None 

### BottomRight  

Tooltip placed either below the Thumb in horizontal orientation or right of the Thumb in vertical orientation. 

{% tabs %}

{% highlight xaml %}

<editors:SfRangeSlider x:Name="rangeSlider" Width="200" Minimum="0" Maximum="100" Value="50" ThumbToolTipPlacement="BottomRight" />

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

   rangeSlider.ThumbToolTipPlacement = Syncfusion.UI.Xaml.Controls.Input.ThumbToolTipPlacement.BottomRight;

{% endhighlight %}

{% highlight VB %}

   rangeSlider.ThumbToolTipPlacement = Syncfusion.UI.Xaml.Controls.Input.ThumbToolTipPlacement.BottomRight

{% endhighlight %}

{% endtabs %}

![RangeSlider ThumbToolTipPlacement BottomRight view](Thumb-ToolTip_images/Thumb-ToolTip_img3.jpg)

N>  This option will show tooltip to right in vertical orientation.

### TopLeft 

Tooltip placed either above the Thumb in horizontal orientation or left of the Thumb in vertical orientation. 

{% tabs %}

{% highlight xaml %}

<editors:SfRangeSlider x:Name="rangeSlider" Width="200" Minimum="0" Maximum="100" Value="50" ThumbToolTipPlacement="TopLeft" />

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

   rangeSlider.ThumbToolTipPlacement = Syncfusion.UI.Xaml.Controls.Input.ThumbToolTipPlacement.TopLeft;

{% endhighlight %}

{% highlight VB %}

   rangeSlider.ThumbToolTipPlacement = Syncfusion.UI.Xaml.Controls.Input.ThumbToolTipPlacement.TopLeft

{% endhighlight %}

{% endtabs %}

![RangeSlider ThumbToolTipPlacement TopLeft view](Thumb-ToolTip_images/Thumb-ToolTip_img5.jpg)

N>  This option will show tooltip to left in vertical orientation.

### None 

Tooltip will not appear. 

![RangeSlider Tooltip None view](Thumb-ToolTip_images/Thumb-ToolTip_img7.jpg)





