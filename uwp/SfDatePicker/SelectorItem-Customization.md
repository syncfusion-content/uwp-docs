---
layout: post
title: Deals with the Selector Item Customization of the SfDatePicker control for UWP
description: Deals with the Selector Item Customization of the SfDatePicker control for UWP
platform: uwp
control: SfDatePicker
documentation: ug
---

# SelectorItem Customization

## SelectorItemWidth and SelectorItemHeight

The item size in the SfDateSelector control can be changed by setting the SelectorItemWidth and SelectorItemHeight properties.



## SelectorItemSpacing 

The SelectorItemSpacing property provides the space between the items in SfDateSelector.



## SelectorItemCount

The SelectorItemCount property is used to specify the number of items to be used in SfDateSelector.

The following code sample shows the usage of the SelectorItemWidth, SelectorItemHeight, SelectorItemSpacing, and SelectorItemCount properties. 

{% tabs %}

{% highlight xaml %}



<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

            <syncfusion:SfDatePicker VerticalAlignment="Center"

               Width="200" x:Name="datePicker" SelectorItemWidth="100"

                SelectorItemHeight="100"

                SelectorItemSpacing="50"

                SelectorItemCount="4"/>



</Grid>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

datePicker.SelectorItemWidth = 100;
datePicker.SelectorItemHeight = 100;
datePicker.SelectorItemSpacing = 50;
datePicker.SelectorItemCount = 4;

{% endhighlight %}

{% highlight VB %}

 datePicker.SelectorItemWidth = 100
 datePicker.SelectorItemHeight = 100
 datePicker.SelectorItemSpacing = 50
 datePicker.SelectorItemCount = 4

{% endhighlight %}

{% endtabs %}

The output is displayed in the following image:

![](Features_images/Features_img10.png)





