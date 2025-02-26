---
layout: post
title: Configuring Content in UWP DropDown Button control | Syncfusion®
description: Learn here all about Configuring Content support in Syncfusion® UWP DropDown Button (SfDropDownButton) control and more.
platform: uwp
control:  SfDropDownButton
documentation: ug
---
# Configuring Content in UWP DropDown Button (SfDropDownButton)

Content and DropDownContent can be added to the SfDropDownButton control as follows:

## Content

Set the Content property to display a content with both dropdown open and close.

{% tabs %}

{% highlight xaml %}

<input:SfDropDownButton x:Name="dropDownButton" Content="5/24/2016"/>


{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

dropDownButton.Content =" 5 / 24 / 2016";

{% endhighlight %}

{% highlight VB %}

dropDownButton.Content =" 5 / 24 / 2016"

{% endhighlight %}

{% endtabs %}

![Configuring-Content_img1](Configuring-Content_images/Configuring-Content_img1.jpeg)


## DropDownContent

Set the DropDownContent property to display a content when the dropdown is open.

{% tabs %}

{% highlight xml %}
<input:SfDropDownButton Content="5/24/2016">

<input:SfDropDownButton.DropDownContent>

<input:SfCalendar x:Name="calendar"/>

</input:SfDropDownButton.DropDownContent>

</input:SfDropDownButton>



{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

SfCalendar calendar = new SfCalendar();

dropDownButton.DropDownContent = calendar;

{% endhighlight %}

{% highlight VB %}

Dim calendar As New SfCalendar()

dropDownButton.DropDownContent = calendar

{% endhighlight %}

{% endtabs %}

![Configuring-Content_img2](Configuring-Content_images/Configuring-Content_img2.jpeg)


