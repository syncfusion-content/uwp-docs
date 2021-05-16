---
layout: post
title: Getting Started with UWP Carousel control | Syncfusion
description: Learn here all about getting started with Syncfusion UWP Carousel (SfCarousel) control and more.
platform: uwp
control: SfCarousel
documentation: ug
---

# Getting Started with UWP Carousel (SfCarousel)

This section explains how to create a preview of slides using SfCarousel control.

## Adding SfCarousel control

Create a Universal Windows Platform project in Visual Studio and refer to the following assemblies.

* Syncfusion. SfCarousel.UWP

* Syncfusion.SfShared.UWP

1.Include the namespace for Syncfusion.SfCarousel.UWP assembly in MainPage.xaml

{% tabs %}

{% highlight XAML %}
 
<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:layout="using:Syncfusion.UI.Xaml.Controls.Layout">

{% endhighlight %}

{% endtabs %}

2.Now add the SfCarousel control with a required optimal name using the included namespace

{% tabs %}

{% highlight XAML %}

<layout:SfCarousel x:Name="carousel">

{% endhighlight %}

{% highlight C# %}

SfCarousel carousel = new SfCarousel();

{% endhighlight %}

{% highlight VB %}

Dim carousel As New SfCarousel()

{% endhighlight %}

{% endtabs %}

## Adding SfCarouselItems to the control

Here SfCarouselItems are added as the children of the SfCarousel.

{% tabs %}

{% highlight XAML %}

<layout:SfCarousel x:Name="carousel">

<layout:SfCarouselItem/>

<layout:SfCarouselItem/>

<layout:SfCarouselItem/>

<layout:SfCarouselItem/>

</layout:SfCarousel>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

SfCarousel carousel = new SfCarousel();

carousel.Items.Add(new SfCarouselItem());

carousel.Items.Add(new SfCarouselItem());

carousel.Items.Add(new SfCarouselItem());

carousel.Items.Add(new SfCarouselItem());

carousel.Items.Add(new SfCarouselItem());

{% endhighlight %}

{% highlight VB %}

Dim carousel As New SfCarousel()

carousel.Items.Add(New SfCarouselItem())

carousel.Items.Add(New SfCarouselItem())

carousel.Items.Add(New SfCarouselItem())

carousel.Items.Add(New SfCarouselItem())

carousel.Items.Add(New SfCarouselItem())

{% endhighlight %}

{% endtabs %}

## Setting content for CarouselItems

Content property helps to set the content for SfCarouselItem. `SfCarouselItem` is a ContentControl so that any object can be added as its content. Here images are set as the content of carousel items.

{% tabs %}

{% highlight XAML %}

<layout:SfCarousel x:Name="carousel">

<layout:SfCarouselItem >

<Image Source="Assets/1.jpg" Stretch="Uniform"/>

</layout:SfCarouselItem>

<layout:SfCarouselItem >

<Image Source="Assets/2.jpg" Stretch="Uniform"/>

</layout:SfCarouselItem>

<layout:SfCarouselItem >

<Image Source="Assets/3.jpg" Stretch="Uniform"/>

</layout:SfCarouselItem>

<layout:SfCarouselItem >

<Image Source="Assets/4.jpg" Stretch="Uniform"/>

</layout:SfCarouselItem>

</layout:SfCarousel>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

SfCarousel carousel = new SfCarousel() { Height = 500, Width = 500 };

carousel.Items.Add(new SfCarouselItem() { Content = new Image() { Source = new BitmapImage(new Uri(@"ms-appx:///Assets/1.jpg", UriKind.RelativeOrAbsolute)) } });

carousel.Items.Add(new SfCarouselItem() { Content = new Image() { Source = new BitmapImage(new Uri(@"ms-appx:///Assets/2.jpg", UriKind.RelativeOrAbsolute)) } });

carousel.Items.Add(new SfCarouselItem() { Content = new Image() { Source = new BitmapImage(new Uri(@"ms-appx:///Assets/3.jpg", UriKind.RelativeOrAbsolute)) } });

carousel.Items.Add(new SfCarouselItem() { Content = new Image() { Source = new BitmapImage(new Uri(@"ms-appx:///Assets/4.jpg", UriKind.RelativeOrAbsolute)) } });

{% endhighlight %}

{% highlight VB %}

Dim carousel As New SfCarousel() With {
	.Height = 500,
	.Width = 500
}

carousel.Items.Add(New SfCarouselItem() With {
	.Content = New Image() With {.Source = New BitmapImage(New Uri("ms-appx:///Assets/1.jpg", UriKind.RelativeOrAbsolute))}
})

carousel.Items.Add(New SfCarouselItem() With {
	.Content = New Image() With {.Source = New BitmapImage(New Uri("ms-appx:///Assets/2.jpg", UriKind.RelativeOrAbsolute))}
})

carousel.Items.Add(New SfCarouselItem() With {
	.Content = New Image() With {.Source = New BitmapImage(New Uri("ms-appx:///Assets/3.jpg", UriKind.RelativeOrAbsolute))}
})

carousel.Items.Add(New SfCarouselItem() With {
	.Content = New Image() With {.Source = New BitmapImage(New Uri("ms-appx:///Assets/4.jpg", UriKind.RelativeOrAbsolute))}
})


{% endhighlight %}

{% endtabs %}

![Step by Step Carousel](SfCarousel-images/SfCarousel-img1.jpeg)