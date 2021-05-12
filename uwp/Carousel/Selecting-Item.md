---
layout: post
title: Selecting Item in UWP Carousel control | Syncfusion
description: Learn here all about Selecting Item support in Syncfusion UWP Carousel (SfCarousel) control and more.
platform: uwp
control: SfCarousel
documentation: ug
---
# Selecting Item in UWP Carousel (SfCarousel)

Items can be selected programmatically using the properties `SelectedIndex`, `SelectedItem`.

## Selecting an item using SelectedIndex

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

{% highlight VB %}

carousel.SelectedIndex = 2

{% endhighlight %}

{% endtabs %}

![Provided SelectedIndex for Carousel](SfCarousel-images/SfCarousel-img7.jpeg)


## Selecting an item using SelectedItem

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

{% highlight VB %}

carousel.SelectedItem = item3

{% endhighlight %}

{% endtabs %}

![Provided SelectedItem for Carousel](SfCarousel-images/SfCarousel-img8.jpeg)

## Navigating to next item

`MoveNext` method is used to select next item of the selected item in `SfCarousel`.

{% tabs %}

{% highlight C# %}

carousel.MoveNext();

{% endhighlight %}

{% highlight VB %}

carousel.MoveNext()

{% endhighlight %}

{% endtabs %}

## Navigating to previous item

`MovePrevious` method is used to select previous item of the selected item in `SfCarousel`.

{% tabs %}

{% highlight C# %}

carousel.MovePrevious();

{% endhighlight %}

{% highlight VB %}

carousel.MovePrevious()

{% endhighlight %}

{% endtabs %}

## Customizing the selected item

`SelectedItemTemplate` property is used to apply a template for the selected item

## Refresh the layout

`Refresh` method is used to refresh the layout of `SfCarousel` control.

