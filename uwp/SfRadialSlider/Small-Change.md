---
layout: post
title: Dealing with SmallChange of SfRadialSlider control for UWP
description: Dealing with SmallChange of SfRadialSlider control for UWP
platform: uwp
control: SfRadial Slider 
documentation: ug
---


# Small Change 

The SmallChange property (Inherited from [RangeBase](http://msdn.microsoft.com/en-us/library/windows/apps/windows.ui.xaml.controls.primitives.rangebase.aspx)) can be used to control the smallest possible range of value to be selected in SfRadialSlider.  For example, if SmallChange is set to 5, then it is only possible to select values that are multiples of 5. 

{% highlight xaml %}

<syncfusion:SfRadialSlider

            Minimum="0" Maximum="100"  

            SmallChange="5" />

{% endhighlight %}
