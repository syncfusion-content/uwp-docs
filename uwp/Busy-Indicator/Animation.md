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

busyIndicator.IsEnabled = false;

{% endhighlight %}

{% highlight VB %}

Dim busyIndicator As New SfBusyIndicator()

busyIndicator.IsEnabled = False

{% endhighlight %}

{% endtabs %}

![Steps for Enable the Animation](SfBusyIndicator1/Enable.png)

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

{% highlight VB %}

Dim busyIndicator As New SfBusyIndicator()

busyIndicator.AnimationType = AnimationTypes.Ball

{% endhighlight %}

{% endtabs %}

![Animation Arrow](SfBusyIndicator1/Arrow.png)		![Animation Ball](SfBusyIndicator1/Ball.png)	![Animation Battery](SfBusyIndicator1/Battery.png)

![Animation Delete](SfBusyIndicator1/Delete.png)	![Animation Double Circle](SfBusyIndicator1/DoubleCircle.png)	![Animation Drop](SfBusyIndicator1/Drop.png)

![Animation ECG](SfBusyIndicator1/Ecg.png)	![Animation Flight](SfBusyIndicator1/Flight.png)	![Animation Flower](SfBusyIndicator1/Flower.png)

![Animation Gear](SfBusyIndicator1/Gear.png)	![Animation Globe](SfBusyIndicator1/Globe.png)	![Animation GPS](SfBusyIndicator1/Gps.png)

![Animation Horizontal](SfBusyIndicator1/Horizontal.png)	![Animation Liquid](SfBusyIndicator1/liquid.png)	![Animation Pen](SfBusyIndicator1/pen.png)

![Animation Print](SfBusyIndicator1/print.png)	![Animation Rainy](SfBusyIndicator1/rainy.png)	![Animation Rect](SfBusyIndicator1/Rect.png)

![Animation Rot](SfBusyIndicator1/Rot.png)	![Animation Slice Circle](SfBusyIndicator1/SilceCircle.png)	![Animation Single Circle](SfBusyIndicator1/SingleCircle.png)

![Animation Slice](SfBusyIndicator1/Slice.png)	![Animation Snow](SfBusyIndicator1/Snow.png)	![Animation Sunny](SfBusyIndicator1/Sunny.png)

![Animation Sunrise](SfBusyIndicator1/Sunrise.png)	![Animation Temp](SfBusyIndicator1/Temp.png)	![Animation Thunder](SfBusyIndicator1/Thunder.png)

![Animation Umberlla](SfBusyIndicator1/Umberlla.png)	![Animation Winmil](SfBusyIndicator1/Winmil.png)	![Animation Box](SfBusyIndicator1/Box.png)

![Animation Bulb](SfBusyIndicator1/Bulb.png)


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

{% highlight VB %}

busyIndicator.AnimationSpeed = 120.0

{% endhighlight %}

{% endtabs %}
