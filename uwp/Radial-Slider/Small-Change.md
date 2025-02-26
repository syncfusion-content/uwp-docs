---
layout: post
title: Small Change in UWP Radial Slider control | Syncfusion®
description: Learn here all about Small Change support in Syncfusion® UWP Radial Slider (SfRadialSlider) control and more.
platform: uwp
control: SfRadial Slider 
documentation: ug
---


# Small Change in UWP Radial Slider (SfRadialSlider)

The SmallChange property can be used to control the smallest possible range of value to be selected in SfRadialSlider.  For example, if SmallChange is set to 5, then it is only possible to select values that are multiples of 5. 

{% tabs %}

{% highlight xaml %}

<syncfusion:SfRadialSlider x:Name="radialSlider"

            Minimum="0" Maximum="100"  

            SmallChange="5" />

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

radialSlider.SmallChange = 5;

{% endhighlight %}

{% highlight VB %}

radialSlider.SmallChange = 5

{% endhighlight %}

{% endtabs %}
