---
layout: post
title: NavigationMode of Syncfusion Rotator control for UWP 
description: Learn how to view the different navigation modes of the Rotator control in UWP
platform: UWP 
control: Rotator
documentation: ug
---

# Navigation Modes

The `NavigationStripMode` property specifies the appearance of navigation bar items. The image datas can be selected either by Thumbnail or by Dots navigation modes.

* `Thumbnail` - The slider items will be loaded in thumbnail view additionally. When a thumbnail item is clicked, the slider will switch to the corresponding image data.

{% highlight C# %}

	sfRotator.NavigationStripMode = NavigationStripMode.Thumbnail;	

{% endhighlight %}

{% highlight Xaml %}

    <syncfusion:SfRotator NavigationMode="Thumbnail"/>

{% endhighlight %}

![](Images/thumbnail.png)

* `Dots` - The slider items will be loaded in dots view additionally. When a dots item is clicked, the slider will switch to the corresponding image data.

{% highlight C# %}

	sfRotator.NavigationStripMode = NavigationStripMode.Dots;	

{% endhighlight %}

{% highlight Xaml %}

    <syncfusion:SfRotator NavigationMode="Dots"/>

{% endhighlight %}

![](Images/dots.png)