---
layout: post
title: Deals with the DropDown Customization of the SfTimePicker control for UWP
description: Explains about DropDown Customization of the SfTimePicker control for UWP
platform: uwp
control:  SfTimePicker
documentation: ug
---
# Customizing DropDown

## DropDown height

The height of drop down can be changed using DropDownHeight property.

{% tabs %}

{% highlight xaml %}

 <syncfusion:SfTimePicker x:Name="timePicker" HorizontalAlignment="Center" VerticalAlignment="Center"  Width="200" Margin="15" DropDownHeight="300" />

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

timePicker.DropDownHeight = 200;

{% endhighlight %}

{% highlight VB %}

timePicker.DropDownHeight = 200

{% endhighlight %}

{% endtabs %}

![](Features_images/Customizing-DropDown_img2.png)


## IsDropDownOpen

Drop down can be programmatically opened or closed using the property IsDropDownOpen.

## ShowDropDownButton

DropDownButton visibility can be changed by using the ShowDropDownButton property

{% tabs %}

{% highlight xaml %}

   <syncfusion:SfTimePicker x:Name="timePicker" VerticalAlignment="Center"  Width="200" Margin="15" ShowDropDownButton="True"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

 timePicker.ShowDropDownButton = true;

{% endhighlight %}

{% highlight VB %}

 timePicker.ShowDropDownButton = True

{% endhighlight %}


{% endtabs %}

![](Features_images/Customizing-DropDown_img3.png)