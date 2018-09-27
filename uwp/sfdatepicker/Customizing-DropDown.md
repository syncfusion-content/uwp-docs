---
layout: post
title: Deals with the DropDown Customization of the SfDatePicker control for UWP
description: Explains about DropDown Customization of the SfDatePicker control for UWP
platform: uwp
control:  SfDatePicker
documentation: ug
---
# Customizing DropDown

## DropDown height

The height of drop down can be changed using DropDownHeight property.

{% tabs %}

{% highlight xaml %}

  <syncfusion:SfDatePicker x:Name="sfdatePicker" VerticalAlignment="Center"  Width="200" Margin="15" DropDownHeight="300" />

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

sfdatePicker.DropDownHeight = 200;

{% endhighlight %}

{% highlight VB %}

sfdatePicker.DropDownHeight = 200

{% endhighlight %}

{% endtabs %}

![](Customizing-DropDown_images/Customizing-DropDown_img2.png)


## IsDropDownOpen

Drop down can be programmatically opened or closed using the property IsDropDownOpen.

## ShowDropDownButton

DropDownButton visibility can be changed by using the ShowDropDownButton property

{% tabs %}

{% highlight xaml %}

   <syncfusion:SfDatePicker x:Name="sfdatePicker" VerticalAlignment="Center"  Width="200" Margin="15" ShowDropDownButton="true"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

 sfdatePicker.ShowDropDownButton = true;

{% endhighlight %}

{% highlight VB %}

 sfdatePicker.ShowDropDownButton = True

{% endhighlight %}

{% endtabs %}

![](Customizing-DropDown_images/Customizing-DropDown_img3.png)