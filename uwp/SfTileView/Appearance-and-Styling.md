---
layout: post
title: Appearance and Styling of SfTileView control for UWP
description: Appearance and Styling of SfTileView control for UWP
platform: uwp
control: SfTileView
documentation: ug
---

# Appearance and Styling

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

{% endtabs %}

![](Appearance-and-Styling-images/Appearance-and-Styling-img1.jpeg)

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

{% endtabs %}

![](Appearance-and-Styling-images/Appearance-and-Styling-img2.jpeg)
