---
layout: post
title: Appearance and Styling in UWP Tile View control | Syncfusion
description: Learn here all about Appearance and Styling support in Syncfusion UWP Tile View (SfTileView) control and more.
platform: uwp
control: SfTileView
documentation: ug
---

# Appearance and Styling in UWP Tile View (SfTileView)

## Customizing item height

`ItemHeight` property is used to set a common height value for all the items in TileView control only in Normal state.

{% tabs %}

{% highlight XAML %}

<layout:SfTileView x:Name="tileView" ItemHeight="50">

<layout:SfTileViewItem Background="LightBlue" Content="PaulVent"
                       MaximizedContent="Description about Paul"/>

<layout:SfTileViewItem Background="LightBlue" Content="James"
                       MaximizedContent="Description about James"/>

<layout:SfTileViewItem Background="LightBlue" Content="Carl"
                       MaximizedContent="Description about Carl"/>

<layout:SfTileViewItem Background="LightBlue" Content="Niko"
                       MaximizedContent="Description about Niko"/>

</layout:SfTileView>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

tileView.ItemHeight = 50.0;

{% endhighlight %}

{% highlight VB %}

tileView.ItemHeight = 50.0

{% endhighlight %}

{% endtabs %}

![Appearance-and-Styling-img1](Appearance-and-Styling-images/Appearance-and-Styling-img1.jpeg)

## Customizing item width

`ItemWidth` property is used to set a common width value for all the items in TileView control only in Normal state.

{% tabs %}

{% highlight XAML %}

<layout:SfTileView x:Name="tileView" ItemWidth="100">

<layout:SfTileViewItem Background="LightBlue" Content="PaulVent"
                       MaximizedContent="Description about Paul"/>

<layout:SfTileViewItem Background="LightBlue" Content="James"
                       MaximizedContent="Description about James"/>

<layout:SfTileViewItem Background="LightBlue" Content="Carl"
                       MaximizedContent="Description about Carl"/>

<layout:SfTileViewItem Background="LightBlue" Content="Niko"
                       MaximizedContent="Description about Niko"/>

</layout:SfTileView>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

tileView.ItemWidth = 100.0;

{% endhighlight %}

{% highlight VB %}

tileView.ItemWidth = 100.0

{% endhighlight %}

{% endtabs %}

![Appearance-and-Styling-img2](Appearance-and-Styling-images/Appearance-and-Styling-img2.jpeg)
