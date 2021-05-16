---
layout: post
title: Appearance and Styling in UWP DropDown Button control | Syncfusion
description: Learn here all about Appearance and Styling support in Syncfusion UWP DropDown Button (SfDropDownButton) control and more.
platform: uwp
control:  SfDropDownButton
documentation: ug
---

# Appearance and Styling in UWP DropDown Button (SfDropDownButton)

## Accent brush

AccentBrush property is used to decorate the hot spots of a control with a solid color.

{% highlight xaml %}
<input:SfDropDownButton Content="5/24/2016" AccentBrush="Red" x:Name="dropdownbutton

"/>


{% endhighlight %}

![Apperance-and-Styling_img1](Apperance-and-Styling_images/Apperance-and-Styling_img1.jpeg)


## ContentTemplate

ContentTemplate property is used to decorate the content of the SfDropDownButton.

{% highlight xaml %}
<input:SfDropDownButton Content="5/24/2016" x:Name="dropdownbutton">

<input:SfDropDownButton.ContentTemplate>

<DataTemplate>

<TextBlock Foreground="Green" Text="{Binding}"/>

</DataTemplate>

</input:SfDropDownButton.ContentTemplate>

</input:SfDropDownButton>



{% endhighlight %}

![Apperance-and-Styling_img2](Apperance-and-Styling_images/Apperance-and-Styling_img2.jpeg)


## DropdownContentTemplate

DropDownContentTemplate is used to decorate the drop down content of SfDropDownButton.

{% highlight xaml %}
<input:SfDropDownButton DropDownContent="Drop down content">

<input:SfDropDownButton.DropDownContentTemplate>

<DataTemplate>

<TextBlock Foreground="Green" HorizontalAlignment="Center" Text="{Binding}"/>

</DataTemplate>

</input:SfDropDownButton.DropDownContentTemplate>

</input:SfDropDownButton>



{% endhighlight %}

![Apperance-and-Styling_img3](Apperance-and-Styling_images/Apperance-and-Styling_img3.jpeg)


