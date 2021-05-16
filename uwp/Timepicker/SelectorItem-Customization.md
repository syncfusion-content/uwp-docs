---
layout: post
title: SelectorItem Customization in UWP TimePicker control | Syncfusion
description: Learn here all about SelectorItem Customization support in Syncfusion UWP TimePicker (SfTimePicker) control and more.
platform: uwp
control: SfTimePicker
documentation: ug
---

# SelectorItem Customization in UWP TimePicker (SfTimePicker)

## SelectorItemWidth and SelectorItemHeight

The item size in the SfTimeSelector control can be changed by setting the SelectorItemWidth and SelectorItemHeight properties.



## SelectorItemSpacing

The SelectorItemSpacing property provides the space between the items in SfTimeSelector.



## SelectorItemCount

The SelectorItemCount property is used to specify the number of items to be used in SfTimeSelector.

The following code sample shows the usage of the SelectorItemWidth, SelectorItemHeight, SelectorItemSpacing, and SelectorItemCount properties. 

{% tabs %}

{% highlight xaml %}


<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

            <syncfusion:SfTimePicker VerticalAlignment="Center" x:Name="timePicker"

                Width="200" SelectorItemWidth="100"

                SelectorItemHeight="100"

                SelectorItemSpacing="50"

                SelectorItemCount="4"/>



</Grid>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

timePicker.SelectorItemHeight = 100;
timePicker.SelectorItemWidth = 100;
timePicker.SelectorItemCount = 5;
timePicker.SelectorItemSpacing = 40;

{% endhighlight %}

{% highlight VB %}

timePicker.SelectorItemHeight = 100
timePicker.SelectorItemWidth = 100
timePicker.SelectorItemCount = 5
timePicker.SelectorItemSpacing = 40

{% endhighlight %}

{% endtabs %}

The output is displayed in the following image:



![Features_img12](Features_images/Features_img12.png)
