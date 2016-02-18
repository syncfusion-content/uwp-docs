---
layout: post
title: Deals with the Customization of the SfDropDownButton control for UWP
description: Explains about Customization of the SfDropDownButton control for UWP
platform: uwp
control:  SfDropDownButton
documentation: ug
---
# Customizing DropDown


## DropDown direction

The direction of drop down can be changed using DropDownDirection property.

{% highlight xaml %}
<input:SfDropDownButton Content="5/24/2016" DropDownDirection="Top" x:Name="dropdownbutton">

<input:SfDropDownButton.DropDownContent>

<input:SfCalendar/>

</input:SfDropDownButton.DropDownContent>

</input:SfDropDownButton>





{% endhighlight %}

{% highlight c# %}

dropdownbutton.DropDownDirection = Syncfusion.UI.Xaml.Controls.Input.DropDownDirection.Top;


{% endhighlight %}

![](Customizing-DropDown_images/Customizing-DropDown_img1.jpeg)


## DropDown height

The height of drop down can be changed using DropDownHeight property.

{% highlight xaml %}

<input:SfDropDownButton Content="5/24/2016" DropDownHeight="250" x:Name="dropdownbutton">

<input:SfDropDownButton.DropDownContent>

<input:SfCalendar/>

</input:SfDropDownButton.DropDownContent>

</input:SfDropDownButton>



{% endhighlight %}

{% highlight c# %}

dropdownbutton.DropDownHeight = 250.0;


{% endhighlight %}

![](Customizing-DropDown_images/Customizing-DropDown_img2.jpeg)


## IsDropDownOpen

Drop down can be programmatically opened or closed using the property IsDropDownOpen.

