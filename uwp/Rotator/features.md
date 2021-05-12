---
layout: post
title: Features in UWP Rotator control | Syncfusion
description: Learn here all about Features support in Syncfusion UWP Rotator (SfRotator) control and more.
platform: UWP
control: Rotator
documentation: ug
---

# Features in UWP Rotator (SfRotator)

## AutoPlay

The `EnableAutoPlay` property specifies whether the items should navigate automatically based on `NavigationDelay` property, when the property value is set to true.

N> By default, the property value is set to false.

{% highlight C# %}

	Rotator.EnableAutoPlay = True;

{% endhighlight %}

{% highlight Xaml %}

    <syncfusion:SfRotator EnableAutoPlay="true"/>
  
 {% endhighlight %}

## Navigation Delay

The `NavigationDelay` property specifies the duration to delay the switch to next navigation item, when `EnableAutoPlay` property is enabled.

N> The property value should be in milliseconds.

{% highlight C# %}

	Rotator.NavigationDelay = new TimeSpan(0,0,2);

{% endhighlight %}

{% highlight Xaml %}

    <syncfusion:SfRotator NavigationDelay="00:00:02"/>
  
 {% endhighlight %}

## Item Looping

The `EnableLooping` property specifies whether the items should navigate to first item once it reaches the last item and vice-versa.

{% highlight C# %}

	Rotator.EnableLooping = true;

{% endhighlight %}

{% highlight Xaml %}

    <syncfusion:SfRotator EnableLooping="true"/>
  
 {% endhighlight %}


## Text Area 

The `ShowText` property can be used to enable the text area visibility in bottom area of rotator for providing additional information of items.

N> By default, the property value is false.

{% highlight C# %}

	Rotator.ShowText = True;

{% endhighlight %}

{% highlight Xaml %}

    <syncfusion:SfRotator ShowText="true"/>
  
 {% endhighlight %}

## Navigation Direction

The `NavigationDirection` property specifies the direction in which items should be navigated in Rotator control.

* `Horizontal` - Items can be navigated in horizontal direction.

{% highlight C# %}

	Rotator.NavigationDirection = NavigationDirection.Horizontal;

{% endhighlight %}

{% highlight Xaml %}

    <syncfusion:SfRotator NavigationDirection="Horizontal"/>

{% endhighlight %}

* `Vertical` - Items can be navigated in vertical direction.

{% highlight C# %}

	Rotator.NavigationDirection = NavigationDirection.Vertical;

{% endhighlight %}

{% highlight Xaml %}

    <syncfusion:SfRotator NavigationDirection="Vertical"/>

{% endhighlight %}

* `LeftToRight` - Items can be navigated from Left to Right only.

{% highlight C# %}

	Rotator.NavigationDirection = NavigationDirection.LeftToRight;

{% endhighlight %}

{% highlight Xaml %}

    <syncfusion:SfRotator NavigationDirection="LeftToRight"/>

{% endhighlight %}

* `RightToLeft` - Items can be navigated from Right to Left only.

{% highlight C# %}

	Rotator.NavigationDirection = NavigationDirection.RightToLeft;

{% endhighlight %}

{% highlight Xaml %}

    <syncfusion:SfRotator NavigationDirection="RightToLeft"/>

{% endhighlight %}

* `TopToBottom` - Items can be navigated from Top to Bottom only.

{% highlight C# %}

	Rotator.NavigationDirection = NavigationDirection.TopToBottom;

{% endhighlight %}

{% highlight Xaml %}

    <syncfusion:SfRotator NavigationDirection="TopToBottom"/>

{% endhighlight %}

* `BottomToTop` - Items can be navigated from Bottom to Top only.

{% highlight C# %}

	Rotator.NavigationDirection = NavigationDirection.BottomToTop;

{% endhighlight %}

{% highlight Xaml %}

    <syncfusion:SfRotator NavigationDirection="BottomToTop"/>

{% endhighlight %}
