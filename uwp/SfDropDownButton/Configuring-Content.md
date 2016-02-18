---
layout: post
title: Configuring content of the SfDropDownButton control for UWP
description: Configuring content of the SfDropDownButton control for UWP
platform: uwp
control:  SfDropDownButton
documentation: ug
---
# Configuring Content

Content and DropDownContent can be added to the SfDropDownButton control as follows:

## Content

Set the Content property to display a content with both dropdown open and close.

{% highlight xaml %}
<input:SfDropDownButton Content="5/24/2016"/>



{% endhighlight %}

![](Configuring-Content_images/Configuring-Content_img1.jpeg)


## DropDownContent

Set the DropDownContent property to display a content when the dropdown is open.

{% highlight xml %}
<input:SfDropDownButton Content="5/24/2016">

<input:SfDropDownButton.DropDownContent>

<input:SfCalendar x:Name="calendar"/>

</input:SfDropDownButton.DropDownContent>

</input:SfDropDownButton>



{% endhighlight %}

![](Configuring-Content_images/Configuring-Content_img2.jpeg)


