---
layout: post
title: Selecting Item of SfCarousel control for UWP
description: Selecting Item of SfCarousel control for UWP
platform: uwp
control: SfCarousel
documentation: ug
---
# Selecting Item

Items can be selected programmatically using the properties `SelectedIndex`, `SelectedItem`.

## SelectedIndex

`SelectedIndex` property is used to select an item in `SfCarousel` using the index of item. 

{% tabs %}

{% highlight XAML %}

<layout:SfCarousel x:Name="carousel" SelectedIndex="2">

<layout:SfCarouselItem x:Name="item1" Content="Item 1"/>

<layout:SfCarouselItem x:Name="item2" Content="Item 2"/>

<layout:SfCarouselItem x:Name="item3" Content="Item 3"/>

<layout:SfCarouselItem x:Name="item4" Content="Item 4"/>

<layout:SfCarouselItem x:Name="item5" Content="Item 5"/>

</layout:SfCarousel>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

carousel.SelectedIndex = 2;

{% endhighlight %}

{% endtabs %}

![](SfCarousel-images/SfCarousel-img7.jpeg)


## SelectedItem

SelectedItem property is used to select an item in SfCarousel using the instance of item. 

{% tabs %}

{% highlight XAML %}

<layout:SfCarousel x:Name="carousel" SelectedItem="item3">

<layout:SfCarouselItem x:Name="item1" Content="Item 1"/>

<layout:SfCarouselItem x:Name="item2" Content="Item 2"/>

<layout:SfCarouselItem x:Name="item3" Content="Item 3"/>

<layout:SfCarouselItem x:Name="item4" Content="Item 4"/>

<layout:SfCarouselItem x:Name="item5" Content="Item 5"/>

</layout:SfCarousel>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

carousel.SelectedItem = item3;

{% endhighlight %}

{% endtabs %}

![](SfCarousel-images/SfCarousel-img8.jpeg)

## Select Next Item

`MoveNext` method is used to select next item of the selected item in `SfCarousel`.

{% tabs %}

{% highlight C# %}

carousel.MoveNext();

{% endhighlight %}

{% endtabs %}

## Select Previous Item

`MovePrevious` method is used to select previous item of the selected item in `SfCarousel`.

{% tabs %}

{% highlight C# %}

carousel.MovePrevious();

{% endhighlight %}

{% endtabs %}

## SelectedItemTemplate

`SelecteItemTemplate` property is used to apply a template for the selected item

## Refresh

`Refresh` method is used to refresh the layout of `SfCarousel` control.

