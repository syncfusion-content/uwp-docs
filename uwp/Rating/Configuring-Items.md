---
layout: post
title: Configuring Items in UWP Rating control | Syncfusion
description: Learn here all about Configuring Items support in Syncfusion UWP Rating (SfRating) control and more.
platform: uwp
control: SfRating
documentation: ug
---

# Configuring Items in UWP Rating (SfRating)

Specifying the number of rating items in `SfRating` control is much simpler with the property ItemsCount.

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


