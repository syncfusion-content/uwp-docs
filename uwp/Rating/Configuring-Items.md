---
layout: post
title: Configuring Items in UWP SfRating | Syncfusion®
description: The configuring items feature in SfRating specifies the number of rating items using the ItemsCount property to set up the rating display.
platform: uwp
control: SfRating
documentation: ug
---

# Configuring Items in UWP Rating

Specifying the number of rating items in `UWP Rating` control is much simpler with the property ItemsCount.

## Setting items count

`ItemsCount` property defines the number of rating items in control. By default, the count is zero.

{% tabs %}

{% highlight XAML %}

<input:SfRating ItemsCount="5" x:Name="rating"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

rating.ItemsCount = 5;

{% endhighlight %}

{% highlight VB %}

rating.ItemsCount = 5

{% endhighlight %}

{% endtabs %}


![Rating ItemsCount view](Configuring-Items-images/Configuring-Items-img1.jpeg)


