---
layout: post
title: Appearance and Styling in UWP Rating control | Syncfusion
description: Learn here all about Appearance and Styling support in Syncfusion UWP Rating (SfRating) control and more.
platform: uwp
control: SfRating
documentation: ug
---

# Appearance and Styling in UWP Rating (SfRating)

Rating items are customizable in much simpler and easier way. The following properties of `SfRatingItem` are accessible in SfRating.ItemContainerStyle.

## PointerOverFill

`PointerOverFill` property fills the pointer over area with the specified solid color. 

{% tabs %}

{% highlight XAML %}

<input:SfRating ItemsCount="5">

<input:SfRating.ItemContainerStyle>

<Style TargetType="input:SfRatingItem">

<Setter Property="PointerOverFill" Value="Red"/>

</Style>

</input:SfRating.ItemContainerStyle>

</input:SfRating>

{% endhighlight %}


{% endtabs %}

![Rating PointerOverFill view](Appearance-and-Styling-images/Appearance-and-Styling-img1.jpeg)


##  PointerOverStroke

``PointerOverStroke` sets the stroke for the pointer over area with the specified solid color.

{% tabs %}

{% highlight XAML %}

<input:SfRating ItemsCount="5">

<input:SfRating.ItemContainerStyle>

<Style TargetType="input:SfRatingItem">

<Setter Property="PointerOverStroke" Value="Red"/>

</Style>

</input:SfRating.ItemContainerStyle>

</input:SfRating>


{% endhighlight %}


{% endtabs %}

![Rating PointerOverStroke view](Appearance-and-Styling-images/Appearance-and-Styling-img2.jpeg)


## PointerOverStrokeThickness

`PointerOverStrokeThickness` sets the stroke thickness for the pointer over area with the specified thickness.

{% tabs %}

{% highlight XAML %}

<input:SfRating ItemsCount="5">

<input:SfRating.ItemContainerStyle>

<Style TargetType="input:SfRatingItem">

<Setter Property="PointerOverStroke" Value="Red"/>

<Setter Property="PointerOverStrokeThickness" Value="2"/>

</Style>

</input:SfRating.ItemContainerStyle>

</input:SfRating>

{% endhighlight %}

{% endtabs %}


![Rating PointerOverStrokeThickness view](Appearance-and-Styling-images/Appearance-and-Styling-img3.jpeg)


## RatedFill

`RatedFill` property fills the rated area with the specified solid color. 

{% tabs %}

{% highlight XAML %}

<input:SfRating ItemsCount="5">

<input:SfRating.ItemContainerStyle>

<Style TargetType="input:SfRatingItem">

<Setter Property="RatedFill" Value="Red"/>

</Style>

</input:SfRating.ItemContainerStyle>

</input:SfRating>

{% endhighlight %}


{% endtabs %}


![Rating RatedFill view](Appearance-and-Styling-images/Appearance-and-Styling-img4.jpeg)


## RatedStroke

`RatedStroke` sets the stroke for the rated area with the specified solid color. 

{% tabs %}

{% highlight XAML %}

<input:SfRating ItemsCount="5">

<input:SfRating.ItemContainerStyle>

<Style TargetType="input:SfRatingItem">

<Setter Property="RatedStroke" Value="Red"/>

</Style>

</input:SfRating.ItemContainerStyle>

</input:SfRating>


{% endhighlight %}


{% endtabs %}


![Rating RatedStroke view](Appearance-and-Styling-images/Appearance-and-Styling-img5.jpeg)


## Rated StrokeThickness

`RatedStrokeThickness` sets the stroke thickness for the rated area with the specified value. 

{% tabs %}

{% highlight XAML %}

<input:SfRating ItemsCount="5">

<input:SfRating.ItemContainerStyle>

<Style TargetType="input:SfRatingItem">

<Setter Property="RatedStroke" Value="Red"/>

<Setter Property="RatedStrokeThickness" Value="2"/>

</Style>

</input:SfRating.ItemContainerStyle>

</input:SfRating>

{% endhighlight %}

{% endtabs %}


![Rating Rated StrokeThickness view](Appearance-and-Styling-images/Appearance-and-Styling-img6.jpeg)


## Unrated Fill

`UnratedFill` property fills the unrated area with the specified solid color. 

{% tabs %}

{% highlight XAML %}

<input:SfRating ItemsCount="5">

<input:SfRating.ItemContainerStyle>

<Style TargetType="input:SfRatingItem">

<Setter Property="UnratedFill" Value="Red"/>

</Style>

</input:SfRating.ItemContainerStyle>

</input:SfRating>

{% endhighlight %}

{% endtabs %}

![Rating Unrated Fill view](Appearance-and-Styling-images/Appearance-and-Styling-img7.jpeg)


## Unrated Stroke

`UnRatedStroke` sets the stroke for the unrated area with the specified solid color. 

{% tabs %}

{% highlight XAML %}

<input:SfRating ItemsCount="5">

<input:SfRating.ItemContainerStyle>

<Style TargetType="input:SfRatingItem">

<Setter Property="UnratedStroke" Value="Red"/>

</Style>

</input:SfRating.ItemContainerStyle>

</input:SfRating>

{% endhighlight %}

{% endtabs %}


![Rating Unrated Stroke view](Appearance-and-Styling-images/Appearance-and-Styling-img8.jpeg)


## Unrated StrokeThickness

`UnRatedStrokeThickness` sets the stroke thickness for the unrated area with the specified value. 

{% tabs %}

{% highlight XAML %}

<input:SfRating ItemsCount="5">

<input:SfRating.ItemContainerStyle>

<Style TargetType="input:SfRatingItem">

<Setter Property="UnratedStroke" Value="Red"/>

<Setter Property="UnratedStrokeThickness" Value="2"/>

</Style>

</input:SfRating.ItemContainerStyle>

</input:SfRating>

{% endhighlight %}

{% endtabs %}

![Rating Unrated StrokeThickness view](Appearance-and-Styling-images/Appearance-and-Styling-img9.jpeg)


