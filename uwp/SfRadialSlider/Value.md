---
layout: post
title: Value of SfRadialSlider control for UWP
description: Value of SfRadialSlider control for UWP
platform: uwp
control: SfRadial Slider 
documentation: ug
---

# Value

Gets or sets the value of the SfRadialSlider. (Inherited from [RangeBase](http://msdn.microsoft.com/en-us/library/windows/apps/windows.ui.xaml.controls.primitives.rangebase.aspx)). 

{% tabs %}

{% highlight xaml %}

<syncfusion:SfRadialSlider x:Name="radialSlider"

            Minimum="0"  Maximum="100" Value="40" />

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

radialSlider.Value = 40;

{% endhighlight %}

{% highlight VB %}

radialSlider.Value = 40

{% endhighlight %}

{% endtabs %}


The value can be changed by dragging the pointer along the circular track. 

![](Concepts--and-Features_images/Concepts--and-Features_img1.png)
