---
layout: post
title: NavigationStripPosition in Syncfusion Rotator Control for UWP
description: Learn how to set the position of the navigation bar items in Rotator control
platform: UWP
control: Rotator
documentation: ug
---

# NavigationStripPosition

The `NavigationStripPosition` position specifies the placement position of the navigation bar items such as thumbnail or dots relative to the slider area. 

There are four available positions,

* `Bottom` - Sets the position of the navigation bar items to bottom.

{% highlight C# %}

	sfRotator.NavigationStripPosition = NavigationStripPosition.Bottom;

{% endhighlight %}

{% highlight Xaml %}

    <syncfusion:SfRotator NavigationStripPosition="Bottom"/>

{% endhighlight %}

* `Left` - Sets the position of the navigation bar items to left.

{% highlight C# %}

	sfRotator.NavigationStripPosition = NavigationStripPosition.Left;

{% endhighlight %}

{% highlight Xaml %}

    <syncfusion:SfRotator NavigationStripPosition="Left"/>

{% endhighlight %}

* `Top` - Sets the position of the navigation bar items to top.

{% highlight C# %}

	sfRotator.NavigationStripPosition = NavigationStripPosition.Top;

{% endhighlight %}

{% highlight Xaml %}

    <syncfusion:SfRotator NavigationStripPosition="Top"/>

{% endhighlight %}

* `Right` - Sets the position of the navigation bar items to right.

{% highlight C# %}

	sfRotator.NavigationStripPosition = NavigationStripPosition.Right;

{% endhighlight %}

{% highlight Xaml %}

    <syncfusion:SfRotator NavigationStripPosition="Right"/>

{% endhighlight %}

![](Images/tabstrip.png)