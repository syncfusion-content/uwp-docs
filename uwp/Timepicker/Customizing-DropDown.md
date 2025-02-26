---
layout: post
title: Customizing DropDown in UWP TimePicker control | Syncfusion®
description: Learn here all about Customizing DropDown support in Syncfusion® UWP TimePicker (SfTimePicker) control and more.
platform: uwp
control:  SfTimePicker
documentation: ug
---
# Customizing DropDown in UWP TimePicker (SfTimePicker)

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

![Customizing-DropDown_img2](Features_images/Customizing-DropDown_img2.png)


## IsDropDownOpen

Drop down can be programmatically opened or closed using the property IsDropDownOpen.

## ShowDropDownButton

DropDownButton visibility can be changed by using the ShowDropDownButton property

{% tabs %}

{% highlight xaml %}

   <syncfusion:SfTimePicker x:Name="timePicker" VerticalAlignment="Center"  Width="200" Margin="15" ShowDropDownButton="true"/>

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

![Customizing-DropDown_img3](Features_images/Customizing-DropDown_img3.png)
