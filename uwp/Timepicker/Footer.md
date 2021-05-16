---
layout: post
title: Footer in UWP TimePicker control | Syncfusion
description: Learn here all about Footer support in Syncfusion UWP TimePicker (SfTimePicker) control and more.
platform: uwp
control: SfTimePicker
documentation: ug
---

# Footer in UWP TimePicker (SfTimePicker)

## Done and Cancel Buttons

The done and cancel buttons can be made visible or hidden using the following properties:



## ShowDoneButton

The ShowDoneButton property is used to show or hide the done button. The default value is true.

The following code sample shows how to hide the done button:


{% highlight xaml %}




<syncfusion:SfTimePicker VerticalAlignment="Center"

                               HorizontalAlignment="Center"

                               Width="200">

            <syncfusion:SfTimePicker.SelectorStyle>

                <Style TargetType="syncfusion:SfTimeSelector">

                    <Setter Property="ShowDoneButton" Value="false"/>

                </Style>

            </syncfusion:SfTimePicker.SelectorStyle>        
 
 </syncfusion:SfTimePicker>

{% endhighlight %}

![Features_img13](Features_images/Features_img13.png)





## ShowCancelButton

The ShowCancelButton property is used to show or hide the cancel button. The default value is true.

The following code sample shows how to hide the cancel button:
{% highlight xaml %}




<syncfusion:SfTimePicker VerticalAlignment="Center"

                               HorizontalAlignment="Center"

                               Width="200">

            <syncfusion:SfTimePicker.SelectorStyle>

                <Style TargetType="syncfusion:SfTimeSelector">

<Setter Property="ShowCancelButton" Value="false"/>

                </Style>

            </syncfusion:SfTimePicker.SelectorStyle>       
            
</syncfusion:SfTimePicker>

{% endhighlight %}

![Features_img14](Features_images/Features_img14.png)
