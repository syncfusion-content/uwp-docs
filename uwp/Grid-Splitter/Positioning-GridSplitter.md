---
layout: post
title: Positioning GridSplitter in UWP Grid Splitter control | Syncfusion
description: Learn here all about Positioning GridSplitter support in Syncfusion UWP Grid Splitter (SfGridSplitter) control and more.
platform: uwp
control: SfGridSplitter
documentation: ug
---

# Positioning GridSplitter in UWP Grid Splitter (SfGridSplitter)

`SfGridSplitter` can be positioned in Horizontal and Vertical orientation.

## Horizontal GridSplitter

To position a GridSplitter horizontally, split the container into rows and place it in the middle row as follows:

{% tabs %}

{% highlight XAML %}

<Grid>

<Grid.RowDefinitions>

<RowDefinition MinHeight="50"/>

<RowDefinition Height="15"/>

<RowDefinition MinHeight="50"/>

</Grid.RowDefinitions>

<input:SfCalculator/>

<input:SfGridSplitter Grid.Row="1"/>

<input:SfCalendar Grid.Row="2"/>

</Grid>

{% endhighlight %}

{% endtabs %}

![Positioning-GridSplitter-img1](Positioning-GridSplitter-images/Positioning-GridSplitter-img1.jpeg)

## Vertical GridSplitter

To position a GridSplitter vertically, split the container into columns and place it in the middle column as follows:

{% tabs %}

{% highlight XAML %}

<Grid>

<Grid.ColumnDefinitions>

<ColumnDefinition MinWidth="50"/>

<ColumnDefinition Width="25"/>

<ColumnDefinition MinWidth="50"/>

</Grid.ColumnDefinitions>

<input:SfCalculator/>

<input:SfGridSplitter Grid.Column="1" VerticalAlignment="Stretch"/>

<input:SfCalendar Grid.Column="2"/>

</Grid>

{% endhighlight %}

{% endtabs %}

![Positioning-GridSplitter-img2](Positioning-GridSplitter-images/Positioning-GridSplitter-img2.jpeg)

## Move splitter programmatically

MoveSplitter method is used to move the grid splitter programmatically for a specified value.

{% tabs %}

{% highlight XAML %}

<input:SfGridSplitter x:Name="gridSplitter"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

gridSplitter.MoveSplitter(30);

{% endhighlight %}

{% highlight VB %}

gridSplitter.MoveSplitter(30)

{% endhighlight %}

{% endtabs %}

