---
layout: post
title: Handle Animation of SfBusyIndicator control for UWP
description: Handle Animation of SfBusyIndicator control for UWP
platform: uwp
control: SfBusyIndicator
documentation: ug
---

# Animation

`SfBusyIndicator` animation can be frozen and also change the animation type.

##  Freezing Animation

`SfBusyIndicator` can be enabled/disabled using the `IsEnabled` property. By default, `IsEnabled` is `true`.

* IsEnabled=False –  freezes the indicator 
* IsEnabled=True –  activates the indicator

Here is an example showing disabled `SfBusyIndicator`.

{% tabs %}

{% highlight XAML %}

<Grid Background=”CornFlowerBlue”/>

<notification:SfBusyIndicator IsEnabled=”false”/>

</Grid>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

SfBusyIndicator busyIndicator = new SfBusyIndicator();

busyIndicator. IsEnabled = false;

{% endhighlight %}

{% endtabs %}

![](SfBusyIndicator1/Enable.png)

## Change Animation

There are nearly 30 built-in animations defined for `SfBusyIndicator`. Different animations can be set using the property `AnimationType` which accepts value of type AnimationTypes(enum). Only one animation is possible to set at a time for a control. The default animation is Flower.

Here is an example showing different animation types in `SfBusyIndicator`.

{% tabs %}

{% highlight XAML %}

<Grid Background=”CornFlowerBlue”/>

<notification:SfBusyIndicator AnimationType=”Ball”/>

</Grid>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

SfBusyIndicator busyIndicator = new SfBusyIndicator();

busyIndicator.AnimationType = AnimationTypes.Ball;

{% endhighlight %}

{% endtabs %}

![](SfBusyIndicator1/Arrow.png)		![](SfBusyIndicator1/Ball.png)	![](SfBusyIndicator1/Battery.png)

![](SfBusyIndicator1/Delete.png)	![](SfBusyIndicator1/DoubleCircle.png)	![](SfBusyIndicator1/Drop.png)

![](SfBusyIndicator1/Ecg.png)	![](SfBusyIndicator1/Flight.png)	![](SfBusyIndicator1/Flower.png)

![](SfBusyIndicator1/Gear.png)	![](SfBusyIndicator1/Globe.png)	![](SfBusyIndicator1/Gps.png)

![](SfBusyIndicator1/Horizontal.png)	![](SfBusyIndicator1/liquid.png)	![](SfBusyIndicator1/pen.png)

![](SfBusyIndicator1/print.png)	![](SfBusyIndicator1/rainy.png)	![](SfBusyIndicator1/Rect.png)

![](SfBusyIndicator1/Rot.png)	![](SfBusyIndicator1/SilceCircle.png)	![](SfBusyIndicator1/SingleCircle.png)

![](SfBusyIndicator1/Slice.png)	![](SfBusyIndicator1/Snow.png)	![](SfBusyIndicator1/Sunny.png)

![](SfBusyIndicator1/Sunrise.png)	![](SfBusyIndicator1/Temp.png)	![](SfBusyIndicator1/Thunder.png)

![](SfBusyIndicator1/Umberlla.png)	![](SfBusyIndicator1/Winmil.png)	![](SfBusyIndicator1/Box.png)

![](SfBusyIndicator1/Bulb.png)


## Accelerating Animation Speed

Animation speed property is used to change the speed of animation. Minimum animation speed is 10 and maximum animation speed is 500. The default speed is 115. 

{% tabs %}

{% highlight XAML %}

<notification:SfBusyIndicator AnimationSpeed="200" />

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

busyIndicator.AnimationSpeed = 120.0;

{% endhighlight %}

{% endtabs %}
