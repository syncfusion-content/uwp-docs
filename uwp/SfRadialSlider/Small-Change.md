---
layout: post
title: Dealing with SmallChange of SfRadialSlider control for UWP
description: Dealing with SmallChange of SfRadialSlider control for UWP
platform: uwp
control: SfRadial Slider 
documentation: ug
---


# Small Change 

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
