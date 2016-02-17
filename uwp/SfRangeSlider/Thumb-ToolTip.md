---
layout: post
title: Deals with Tooltip options supported by SfRangeSlider control for UWP
description: Explains about the Tooltip options supported by SfRangeSlider control for UWP
platform: uwp
control: SfRange Slider 
documentation: ug
---

# Thumb ToolTip  

The Thumb tooltip shows the current value on which the Thumb stands. 

![](Thumb-ToolTip_images/Thumb-ToolTip_img1.jpg)

## Thumb ToolTip Precision  

ThumbToolTipPrecision property is used to define the precision of the value displayed in the tooltip.  

{% highlight xaml %}

<editors:SfRangeSlider Width="200" VerticalAlignment="Center" Minimum="0" Maximum="100" Value="50" ThumbToolTipPrecision="2"/>

{% endhighlight %}

![](Thumb-ToolTip_images/Thumb-ToolTip_img2.jpg)

## Thumb ToolTip Position 

The position of the Thumb tooltip in relation to the Thumb can be controlled by the ThumbToolTipPlacement property. It has the following options.  

1. BottomRight 
2. TopLeft 
3. None 

### BottmRight  

Tooltip placed either below the Thumb in horizontal orientation or right of the Thumb in vertical orientation. 

{% highlight xaml %}

<editors:SfRangeSlider Width="200" Minimum="0" Maximum="100" Value="50" ThumbToolTipPlacement="BottomRight" />

{% endhighlight %}

![](Thumb-ToolTip_images/Thumb-ToolTip_img3.jpg)

N>  This option will show tooltip to right in vertical orientation.

### TopLeft 

Tooltip placed either above the Thumb in horizontal orientation or left of the Thumb in vertical orientation. 

{% highlight xaml %}

<editors:SfRangeSlider Width="200" Minimum="0" Maximum="100" Value="50" ThumbToolTipPlacement="TopLeft" />

{% endhighlight %}

![](Thumb-ToolTip_images/Thumb-ToolTip_img5.jpg)

N>  This option will show tooltip to left in vertical orientation.

### None 

Tooltip will not appear. 

![](Thumb-ToolTip_images/Thumb-ToolTip_img7.jpg)





