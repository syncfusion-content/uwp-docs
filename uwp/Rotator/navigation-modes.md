---
layout: post
title: NavigationStripMode in UWP SfRotator | Syncfusion®
description: Learn about the NavigationStripMode in the Syncfusion® UWP SfRotator control, including Thumbnail and Dots navigation modes.
platform: uwp
control: SfRotator
documentation: ug
---

# NavigationStripMode in UWP SfRotator

The `NavigationStripMode` property specifies the appearance of navigation bar items. The image data can be selected either by Thumbnail or by Dots navigation modes.

* `Thumbnail` - The image panel items will be loaded in thumbnail view additionally. When a thumbnail item is clicked, the image panel will switch to the corresponding image data.

{% highlight C# %}

	Rotator.NavigationStripMode = NavigationStripMode.Thumbnail;	

{% endhighlight %}

{% highlight Xaml %}

    <syncfusion:SfRotator NavigationStripMode="Thumbnail"/>

{% endhighlight  %}

![thumbnail](images/thumbnail.png)

* `Dots` - The image panel items will be loaded in dots view additionally. When a dots item is clicked, the image panel will switch to the corresponding image data.

{% highlight C# %}

	Rotator.NavigationStripMode = NavigationStripMode.Dots;	

{% endhighlight %}

{% highlight Xaml %}

    <syncfusion:SfRotator NavigationStripMode="Dots"/>

{% endhighlight  %}

![dots](images/dots.png)
