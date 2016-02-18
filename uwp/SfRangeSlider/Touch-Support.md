---
layout: post
title: Touch Support options of SfRangeSlider control for UWP
description: Touch Support options of SfRangeSlider control for UWP
platform: uwp
control: SfRange Slider 
documentation: ug
---

# Touch Support

With the MoveToPoint property, you can move the thumb of the SfRangeSlider by tapping or clicking on the track of the SfRangeSlider. This property provides the following options:

* MoveToTapPosition
* IncrementBySmallChange
* IncrementByLargeChange
* None



### MoveToTapPosition

To move the thumb of the SfRangeSlider to the tapped position, you must set the MoveToPoint property to MoveToTapPosition, and then tap or click on the track of the SfRangeSlider. This will move the thumb to the tapped position.

The following code example and screen shot illustrate this.

{% highlight xaml %}

<editors:SfRangeSlider Width="200" HorizontalAlignment="Center" Minimum="0" Maximum="100" Value="50" SmallChange="5" LargeChange="10" MoveToPoint="MoveToTapPosition"/>

{% endhighlight %}

![](Touch-Support_images/Touch-Support_img1.png)

### IncrementBySmallChange

To move the thumb of the RangeSlider based on the SmallChange value, you must set the MoveToPoint property to IncrementBySmallChange, and then tap or click on the track of the SfRangeSlider. This will increment the SfRangeSlider value by the SmallChange value.

The following code example and screen shot illustrates this.

{% highlight xaml %}

<editors:SfRangeSlider Width="200" HorizontalAlignment="Center" Minimum="0" Maximum="100" Value="50" SmallChange="5" LargeChange="10" MoveToPoint="IncrementBySmallChange"/>

{% endhighlight %}

![](Touch-Support_images/Touch-Support_img2.png)

### IncrementByLargeChange

To move the thumb of the SfRangeSlider based on the LargeChange value, you must set the MoveToPoint property to IncrementByLargeChange, and then tap on the track of the SfRangeSlider. This will increment the SfRangeSlider value by the LargeChange value.

The following code example and screen shot illustrates this.

{% highlight xaml %}

<editors:SfRangeSlider Width="200" HorizontalAlignment="Center" Minimum="0" Maximum="100" Value="50" SmallChange="5" LargeChange="10" MoveToPoint="IncrementByLargeChange"/>

{% endhighlight %}

![](Touch-Support_images/Touch-Support_img3.png)

### None

To fix the thumb movement of the SfRangeSlider, you must set the MoveToPoint property to _None_. This will not allow thumb movement of the SfRangeSlider.

The following code example and screen shot illustrates this.

{% highlight xaml %}

<editors:SfRangeSlider Width="200" HorizontalAlignment="Center" Minimum="0" Maximum="100" Value="50" SmallChange="5" LargeChange="10" MoveToPoint="None"/>

{% endhighlight %}

![](Touch-Support_images/Touch-Support_img4.png)





