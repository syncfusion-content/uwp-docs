---
layout: post
title: Footer in UWP DatePicker control | Syncfusion®
description: Explore Footer support in Syncfusion® UWP DatePicker (SfDatePicker) control, including key features, customization options, and more.
platform: uwp
control: SfDatePicker
documentation: ug
---

# Footer in UWP DatePicker (SfDatePicker)

## Done and Cancel Buttons

The done and cancel buttons can be made visible or hidden using the following properties.

## ShowDoneButton

The ShowDoneButton property is used to show or hide the done button. The default value is true.

The following code sample shows how to hide the done button:

{% highlight xaml %}

<syncfusion:SfDatePicker VerticalAlignment="Center"

                               HorizontalAlignment="Center"

                               Width="200">

            <syncfusion:SfDatePicker.SelectorStyle>

                <Style TargetType="syncfusion:SfDateSelector">

                    <Setter Property="ShowDoneButton" Value="false"/>

                </Style>

            </syncfusion:SfDatePicker.SelectorStyle>  

        </syncfusion:SfDatePicker>
		
{% endhighlight %}

![Features_img11](Features_images/Features_img11.png)




## ShowCancelButton

The ShowCancelButton property is used to show or hide the cancel button. The default value is true.

The following code sample shows how to hide the cancel button:

{% highlight xaml %}



<syncfusion:SfDatePicker VerticalAlignment="Center"

                               HorizontalAlignment="Center"

                               Width="200">

            <syncfusion:SfDatePicker.SelectorStyle>

                <Style TargetType="syncfusion:DateSelector">

<Setter Property="ShowCancelButton" Value="false"/>

                </Style>

            </syncfusion:SfDatePicker.SelectorStyle>        </syncfusion:SfDatePicker>

			{% endhighlight  %}
			
![Features_img12](Features_images/Features_img12.png)
