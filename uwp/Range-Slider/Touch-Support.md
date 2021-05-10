---
layout: post
title: Touch Support in UWP Range Slider control | Syncfusion
description: Learn here all about Touch Support support in Syncfusion UWP Range Slider (SfRangeSlider) control and more.
platform: uwp
control: SfRange Slider 
documentation: ug
---

# Touch Support in UWP Range Slider (SfRangeSlider)

With the MoveToPoint property, you can move the thumb of the SfRangeSlider by tapping or clicking on the track of the SfRangeSlider. This property provides the following options:

* MoveToTapPosition
* IncrementBySmallChange
* IncrementByLargeChange
* None



### MoveToTapPosition

To move the thumb of the SfRangeSlider to the tapped position, you must set the MoveToPoint property to MoveToTapPosition, and then tap or click on the track of the SfRangeSlider. This will move the thumb to the tapped position.

The following code example and screen shot illustrate this.

{% tabs %}

{% highlight xaml %}

<editors:SfRangeSlider x:Name="rangeSlider" Width="200" HorizontalAlignment="Center" Minimum="0" Maximum="100" Value="50" SmallChange="5" LargeChange="10" MoveToPoint="MoveToTapPosition"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

 rangeSlider.MoveToPoint = Syncfusion.UI.Xaml.Controls.Input.MovePoint.MoveToTapPosition;

{% endhighlight %}

{% highlight VB %}

 rangeSlider.MoveToPoint = Syncfusion.UI.Xaml.Controls.Input.MovePoint.MoveToTapPosition

{% endhighlight %}

{% endtabs %}

![RangeSlider MoveToPoint view](Touch-Support_images/Touch-Support_img1.png)

### IncrementBySmallChange

To move the thumb of the RangeSlider based on the SmallChange value, you must set the MoveToPoint property to IncrementBySmallChange, and then tap or click on the track of the SfRangeSlider. This will increment the SfRangeSlider value by the SmallChange value.

The following code example and screen shot illustrates this.

{% tabs %}

{% highlight xaml %}

<editors:SfRangeSlider x:Name="rangeSlider" Width="200" HorizontalAlignment="Center" Minimum="0" Maximum="100" Value="50" SmallChange="5" LargeChange="10" MoveToPoint="IncrementBySmallChange"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

 rangeSlider.MoveToPoint = Syncfusion.UI.Xaml.Controls.Input.MovePoint.IncrementBySmallChange;

{% endhighlight %}

{% highlight VB %}

 rangeSlider.MoveToPoint = Syncfusion.UI.Xaml.Controls.Input.MovePoint.IncrementBySmallChange

{% endhighlight %}

{% endtabs %}

![RangeSlider MoveToPoint IncrementBySmallChange view](Touch-Support_images/Touch-Support_img2.png)

### IncrementByLargeChange

To move the thumb of the SfRangeSlider based on the LargeChange value, you must set the MoveToPoint property to IncrementByLargeChange, and then tap on the track of the SfRangeSlider. This will increment the SfRangeSlider value by the LargeChange value.

The following code example and screen shot illustrates this.


{% tabs %}

{% highlight xaml %}

<editors:SfRangeSlider x:Name="rangeSlider" Width="200" HorizontalAlignment="Center" Minimum="0" Maximum="100" Value="50" SmallChange="5" LargeChange="10" MoveToPoint="IncrementByLargeChange"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

  rangeSlider.MoveToPoint = Syncfusion.UI.Xaml.Controls.Input.MovePoint.IncrementByLargeChange;

{% endhighlight %}

{% highlight VB %}

  rangeSlider.MoveToPoint = Syncfusion.UI.Xaml.Controls.Input.MovePoint.IncrementByLargeChange

{% endhighlight %}

{% endtabs %}

![RangeSlider MoveToPoint IncrementByLargeChange view](Touch-Support_images/Touch-Support_img3.png)

### None

To fix the thumb movement of the SfRangeSlider, you must set the MoveToPoint property to _None_. This will not allow thumb movement of the SfRangeSlider.

The following code example and screen shot illustrates this.

{% tabs %}

{% highlight xaml %}

<editors:SfRangeSlider x:Name="rangeSlider" Width="200" HorizontalAlignment="Center" Minimum="0" Maximum="100" Value="50" SmallChange="5" LargeChange="10" MoveToPoint="None"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

   rangeSlider.MoveToPoint = Syncfusion.UI.Xaml.Controls.Input.MovePoint.None;

{% endhighlight %}

{% highlight VB %}

   rangeSlider.MoveToPoint = Syncfusion.UI.Xaml.Controls.Input.MovePoint.None


{% endhighlight %}

{% endtabs %}

![RangeSlider MoveToPoint None view](Touch-Support_images/Touch-Support_img4.png)





