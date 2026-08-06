---
layout: post
title: Customizing DropDown in UWP TimePicker control | Syncfusion®
description: Learn here all about Customizing DropDown support in Syncfusion® UWP TimePicker (SfTimePicker) control and more.
platform: uwp
control: SfTimePicker
documentation: ug
---
# Customizing DropDown in UWP TimePicker (SfTimePicker)

## DropDown height

The height of the drop-down can be changed using the DropDownHeight property.

{% tabs %}

{% highlight xaml %}

<Page
   ...
   xmlns:input="using:Syncfusion.UI.Xaml.Controls.Input">

    <syncfusion:SfTimePicker x:Name="timePicker" HorizontalAlignment="Center" VerticalAlignment="Center"  Width="200" Margin="15" DropDownHeight="300" />

</Page>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

using Syncfusion.UI.Xaml.Controls.Input;

timePicker.DropDownHeight = 300;

{% endhighlight %}

{% highlight VB %}

Imports Syncfusion.UI.Xaml.Controls.Input;

timePicker.DropDownHeight = 300

{% endhighlight %}

{% endtabs %}

![Customizing-DropDown_img2](Features_images/Customizing-DropDown_img2.png)


## IsDropDownOpen

The drop-down can be programmatically opened or closed using the IsDropDownOpen property.

## ShowDropDownButton

The DropDownButton visibility can be changed by using the ShowDropDownButton property.

{% tabs %}

{% highlight xaml %}

<Page
   ...
   xmlns:input="using:Syncfusion.UI.Xaml.Controls.Input">

    <syncfusion:SfTimePicker x:Name="timePicker" VerticalAlignment="Center"  Width="200" Margin="15" ShowDropDownButton="true"/>

</Page>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

using Syncfusion.UI.Xaml.Controls.Input;

 timePicker.ShowDropDownButton = true;

{% endhighlight %}

{% highlight VB %}

Imports Syncfusion.UI.Xaml.Controls.Input;

 timePicker.ShowDropDownButton = True

{% endhighlight %}


{% endtabs %}

![Customizing-DropDown_img3](Features_images/Customizing-DropDown_img3.png)
