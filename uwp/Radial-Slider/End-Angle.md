---
layout: post
title: Setting End Angle of SfRadialSlider control for UWP
description: Setting End Angle of SfRadialSlider control for UWP
platform: uwp
control: SfRadial Slider 
documentation: ug
---

# End Angle 

The EndAngle property can be used to set the ending position for the ticks in the circular track. 

{% tabs %}

{% highlight xaml %}

<syncfusion:SfRadialSlider  x:Name="radialSlider" StartAngle="180" EndAngle="360" />

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

 radialSlider.StartAngle = 180;

 radialSlider.EndAngle = 360;

{% endhighlight %}

{% highlight VB %}

radialSlider.StartAngle = 180

radialSlider.EndAngle = 360

{% endhighlight %}

{% endtabs %}

![](Concepts--and-Features_images/Concepts--and-Features_img5.png)
