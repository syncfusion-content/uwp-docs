---
layout: post
title: Setting Null Value in UWP TimePicker control | Syncfusion®
description: Learn here all about Setting Null Value support in Syncfusion® UWP TimePicker (SfTimePicker) control and more.
platform: uwp
control: SfTimePicker
documentation: ug
---

# Setting Null Value in UWP TimePicker (SfTimePicker)


AllowNull property can be used to set the SfTimePicker value to Null. When this property is enabled along with the Value property whose value is Null, then the SfTimePicker control will not display any value 

The following code example and screen shot illustrate the usage of the AllowNull property.


{% highlight xaml %}


<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

<syncfusion:SfTimePicker VerticalAlignment="Center" Width="200" Value="{x:Null}" AllowNull="true"/>

</Grid>

{% endhighlight %}

![Features_img16](Features_images/Features_img16.png)

## Setting the Input Scope for the On-Screen Keyboard

To set the input scope of the on-screen keyboard, use the InputScope property. When the InputScope property set to Number, only the numeric keypad will be visible in the on-screen keyboard. The following code example and screen shot illustrate this property.


N>  The AllowInlineEditing property must be set to `true` for this property to take effect.

{% highlight xaml %}


<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

<syncfusion:SfTimePicker VerticalAlignment="Center" Width="200"

AllowInlineEditing="true" InputScope="Number"/>

</Grid>
{% endhighlight %}


![Features_img18](Features_images/Features_img18.png)
