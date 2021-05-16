---
layout: post
title: Customizing DropDown in UWP DropDown Button control | Syncfusion
description: Learn here all about Customizing DropDown support in Syncfusion UWP DropDown Button (SfDropDownButton) control and more.
platform: uwp
control:  SfDropDownButton
documentation: ug
---
# Customizing DropDown in UWP DropDown Button (SfDropDownButton)


## DropDown direction

The direction of drop down can be changed using DropDownDirection property.
{% tabs %}

{% highlight xaml %}

<input:SfDropDownButton Content="5/24/2016" DropDownDirection="Top" x:Name="dropdownbutton">

<input:SfDropDownButton.DropDownContent>

<input:SfCalendar/>

</input:SfDropDownButton.DropDownContent>

</input:SfDropDownButton>





{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

dropdownbutton.DropDownDirection = Syncfusion.UI.Xaml.Controls.Input.DropDownDirection.Top;


{% endhighlight %}

{% highlight VB %}

dropdownbutton.DropDownDirection = Syncfusion.UI.Xaml.Controls.Input.DropDownDirection.Top

{% endhighlight %}

{% endtabs %}

![Customizing-DropDown_img1](Customizing-DropDown_images/Customizing-DropDown_img1.jpeg)


## DropDown height

The height of drop down can be changed using DropDownHeight property.

{% tabs %}

{% highlight xaml %}

<input:SfDropDownButton Content="5/24/2016" DropDownHeight="250" x:Name="dropdownbutton">

<input:SfDropDownButton.DropDownContent>

<input:SfCalendar/>

</input:SfDropDownButton.DropDownContent>

</input:SfDropDownButton>



{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

dropdownbutton.DropDownHeight = 250.0;


{% endhighlight %}

{% highlight VB %}

dropdownbutton.DropDownHeight = 250.0

{% endhighlight %}

{% endtabs %}

![Customizing-DropDown_img2](Customizing-DropDown_images/Customizing-DropDown_img2.jpeg)


## IsDropDownOpen

Drop down can be programmatically opened or closed using the property IsDropDownOpen.

