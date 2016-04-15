---
layout: post
title: Various features in Syncfusion Rotator control for UWP
description: Learn how to set the autoplay option, loop the items, enable Text Area  and choose the navigation direction in Rotator control for Xamarin.Forms
platform: UWP
control: Rotator
documentation: ug
---

# Features

## AutoPlay

The `EnableAutoPlay` property specifies whether the items should navigate automatically based on `NavigationDelay` property, when the property value is set to true.

N> By default, the property value is set to false.

{% highlight C# %}

	sfRotator.EnableAutoPlay = True;

{% endhighlight %}

{% highlight Xaml %}

    <syncfusion:SfRotator EnableAutoPlay="true"/>
  
 {% endhighlight %}

## Navigation Delay

The `NavigationDelay` property specifies the duration to delay the switch to next navigation item, when `EnableAutoPlay` property is enabled.

N> The property value should be in milliseconds.

{% highlight C# %}

	sfRotator.NavigationDelay = 2000;

{% endhighlight %}

{% highlight Xaml %}

    <syncfusion:SfRotator NavigationDelay ="2000"/>
  
 {% endhighlight %}

## Item Looping

The `EnableLooping` property specifies whether the items should navigate to first item once it reaches the last item and vice-versa.

{% highlight C# %}

	sfRotator.EnableLooping = True;

{% endhighlight %}

{% highlight Xaml %}

    <syncfusion:SfRotator EnableLooping="true"/>
  
 {% endhighlight %}


## Text Area 

The `IsTextVisible` property can be used to enable the text area visibility in bottom area of rotator for providing additional information of items.

N> By default, the property value is false.

{% highlight C# %}

	sfRotator.IsTextVisible = True;

{% endhighlight %}

{% highlight Xaml %}

    <syncfusion:SfRotator IsTextVisible="true"/>
  
 {% endhighlight %}

## Navigation Direction

The `NavigationDirection` property specifies the direction in which items should be navigated in Rotator control.

* `Horizontal` - Items can be navigated in horizontal direction.

{% highlight C# %}

	sfRotator.NavigationDirection = NavigationDirection.Horizontal;

{% endhighlight %}

{% highlight Xaml %}

    <syncfusion:SfRotator NavigationDirection="Horizontal"/>

{% highlight c# %}

* `Vertical` - Items can be navigated in vertical direction.

{% highlight C# %}

	sfRotator.NavigationDirection = NavigationDirection.Vertical;

{% endhighlight %}

{% highlight Xaml %}

    <syncfusion:SfRotator NavigationDirection="Vertical"/>

{% endhighlight %}