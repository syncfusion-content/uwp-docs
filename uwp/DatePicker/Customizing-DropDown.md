---
layout: post
title: Customizing DropDown in UWP DatePicker control | Syncfusion®
description: Learn here all about Customizing DropDown support in Syncfusion® UWP DatePicker (SfDatePicker) control and more.
platform: uwp
control: SfDatePicker
documentation: ug
---
# Customizing DropDown in UWP DatePicker (SfDatePicker)

## DropDown height

The height of the drop-down can be changed using the DropDownHeight property.

{% tabs %}

{% highlight xaml %}

<Page
   ...
   xmlns:input="using:Syncfusion.UI.Xaml.Controls.Input">

    <syncfusion:SfDatePicker x:Name="sfdatePicker" VerticalAlignment="Center"  Width="200" Margin="15" DropDownHeight="300" />

</Page>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

using Syncfusion.UI.Xaml.Controls.Input;

sfdatePicker.DropDownHeight = 300;

{% endhighlight %}

{% highlight VB %}

Imports Syncfusion.UI.Xaml.Controls.Input;

sfdatePicker.DropDownHeight = 300

{% endhighlight %}

{% endtabs %}

![Customizing-DropDown_img2](Customizing-DropDown_images/Customizing-DropDown_img2.png)


## IsDropDownOpen

The drop-down can be programmatically opened or closed using the IsDropDownOpen property.

## ShowDropDownButton

The drop-down button visibility can be changed by using the ShowDropDownButton property.

{% tabs %}

{% highlight xaml %}

<Page
   ...
   xmlns:input="using:Syncfusion.UI.Xaml.Controls.Input">

    <syncfusion:SfDatePicker x:Name="sfdatePicker" VerticalAlignment="Center"  Width="200" Margin="15" ShowDropDownButton="true"/>

</Page>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

using Syncfusion.UI.Xaml.Controls.Input;

 sfdatePicker.ShowDropDownButton = true;

{% endhighlight %}

{% highlight VB %}

Imports Syncfusion.UI.Xaml.Controls.Input;

 sfdatePicker.ShowDropDownButton = True

{% endhighlight %}

{% endtabs %}

![Customizing-DropDown_img3](Customizing-DropDown_images/Customizing-DropDown_img3.png)
