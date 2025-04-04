---
layout: post
title: Watermark in UWP Charts control | Syncfusion
description: Learn everything about Watermark support in Syncfusion® UWP Charts (SfChart) control and explore additional features.
platform: uwp
control: SfChart
documentation: ug
---
# Watermark in UWP Charts (SfChart)

[`SfChart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html) provides watermark support which is used to add text or images to the chart area. The major application of watermark is to define the copyright information of the user it belongs to.

This section is to help you understand how to use the [`Watermark`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.Watermark.html) in your chart.

## Adding text watermark

You can add the text to chart background using the Content property of [`Watermark`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html#Syncfusion_UI_Xaml_Charts_SfChart_Watermark).

The following code example explains how to set your custom text as Watermark.

{% tabs %}

{% highlight xaml %}

<chart:SfChart.Watermark>

<chart:Watermark VerticalAlignment="Center"         

HorizontalAlignment="Center" >

<chart:Watermark.Content>

<TextBlock Text="Metals"  

FontSize="70"

Foreground="Black" >

</TextBlock>

</chart:Watermark.Content>

</chart:Watermark>

</chart:SfChart.Watermark>

{% endhighlight %}

{% highlight c# %}

chart.Watermark = new Watermark()
{

       HorizontalAlignment = HorizontalAlignment.Center,

       VerticalAlignment = VerticalAlignment.Center

};

chart.Watermark.Content = new TextBlock()
{

       Text = "Metals",

       FontSize = 70,

       Foreground = new SolidColorBrush(Colors.Black)

};

{% endhighlight %}

{% endtabs %}

![Text watermark support in UWP Chart](Watermark_images/Watermark_1.png)

## Adding image watermark

You can also set images as Watermark as in below code snippet.

{% tabs %}

{% highlight xaml %}

<chart:SfChart.Watermark>

<chart:Watermark VerticalAlignment="Center"               

HorizontalAlignment="Center" >

<chart:Watermark.Content>

<Image Source="demands.png" Height="175" Width="175"/>

</chart:Watermark.Content>

</chart:Watermark>

</chart:SfChart.Watermark>

{% endhighlight %}

{% highlight c# %}

chart.Watermark = new Watermark()
{

       HorizontalAlignment = HorizontalAlignment.Center,

       VerticalAlignment = VerticalAlignment.Center

};

chart.Watermark.Content = new Image()
{

       Height = 175,

       Width = 175,

       Source = new BitmapImage(new Uri(@"demands.png", UriKind.RelativeOrAbsolute))

};


{% endhighlight %}

{% endtabs %}

![Image watermark support in UWP Chart](Watermark_images/Watermark_2.png)


