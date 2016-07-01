---
layout: post
title: NavigationMode of Syncfusion Rotator control for UWP 
description: Learn how to view the different navigation modes of the Rotator control in UWP
platform: UWP 
control: Rotator
documentation: ug
---

# NavigationStripMode

The `NavigationStripMode` property specifies the appearance of navigation bar items. The image datas can be selected either by Thumbnail or by Dots navigation modes.

* `Thumbnail` - The image panel items will be loaded in thumbnail view additionally. When a thumbnail item is clicked, the image panel will switch to the corresponding image data.

{% highlight C# %}

	Rotator.NavigationStripMode = NavigationStripMode.Thumbnail;	

{% endhighlight %}

{% highlight Xaml %}

    <syncfusion:SfRotator NavigationStripMode="Thumbnail"/>

{% endhighlight  %}

![](images/thumbnail.png)

* `Dots` - The image panel items will be loaded in dots view additionally. When a dots item is clicked, the image panel will switch to the corresponding image data.

{% highlight C# %}

	Rotator.NavigationStripMode = NavigationStripMode.Dots;	

{% endhighlight %}

{% highlight Xaml %}

    <syncfusion:SfRotator NavigationStripMode="Dots"/>

{% endhighlight  %}

![](images/dots.png)