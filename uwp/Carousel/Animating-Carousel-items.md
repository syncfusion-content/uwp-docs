---
layout: post
title: Animation in UWP Carousel control | Syncfusion
description: Learn here all about Animation support in Syncfusion UWP Carousel (SfCarousel) control and more.
platform: UWP
control: SfCarousel
documentation: ug
---

# Animation in UWP Carousel (SfCarousel)

The default animation used during the selection of carousel items can be customized using the following properties.

* Duration

* EasingFunction

* RotationAngle

## Change animation duration

The time taken to move a selected item from its position to center of the control is specified by `Duration` property.

{% tabs %}

{% highlight XAML %}

<layout:SfCarousel x:Name="carousel" Duration="00:00:05.900">

</layout:SfCarousel>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

carousel.Duration =  TimeSpan.FromSeconds(1.0);

{% endhighlight %}

{% highlight VB %}

carousel.Duration = TimeSpan.FromSeconds(1.0)

{% endhighlight %}

{% endtabs %}

## Customizing the item selection animation

The animation effect on selecting items can be customized with `EasingFunction` property.

{% tabs %}

{% highlight XAML %}

<layout:SfCarousel x:Name="carousel">

<layout:SfCarousel.EasingFunction>

<BackEase EasingMode="EaseInOut" Amplitude="0.3"/>

</layout:SfCarousel.EasingFunction>

</layout:SfCarousel>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

using Windows.UI.Xaml.Media.Animation; 


public MainPage()

{
	
carousel.EasingFunction = new BackEase() { EasingMode = EasingMode.EaseInOut, Amplitude = 0.3 };

}

{% endhighlight %}

{% highlight VB %}

Imports Windows.UI.Xaml.Media.Animation

Public Sub New()


carousel.EasingFunction = New BackEase() With {
	.EasingMode = EasingMode.EaseInOut,
	.Amplitude = 0.3
}

End Sub

{% endhighlight %}

{% endtabs %}

## Rotate items

`RotationAngle` property is used to rotate all the items in carousel control to a specified angle.

{% tabs %}

{% highlight XAML %}

<layout:SfCarousel x:Name="carousel" RotationAngle="70">

</layout:SfCarousel>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

carousel.RotationAngle = 70.0;

{% endhighlight %}

{% highlight VB %}

carousel.RotationAngle = 70.0

{% endhighlight %}

{% endtabs %}

![Provided the Animated to Carousel](SfCarousel-images/SfCarousel-img12.jpeg)


