---
layout: post
title: Footer in UWP DatePicker control | Syncfusion
description: Learn how to show or hide the Done and Cancel buttons in the Syncfusion UWP DatePicker (SfDatePicker) control.
platform: uwp
control: SfDatePicker
documentation: ug
---

# Footer in UWP DatePicker

## Done and Cancel Buttons

The Done and Cancel buttons can be shown or hidden using the following properties.

## ShowDoneButton

The ShowDoneButton property is used to show or hide the done button. The default value is true.

The following code sample shows how to hide the done button:

{% highlight xaml %}

<Page
   ...
   xmlns:input="using:Syncfusion.UI.Xaml.Controls.Input">

    <syncfusion:SfDatePicker VerticalAlignment="Center"

                               HorizontalAlignment="Center"

                               Width="200">

            <syncfusion:SfDatePicker.SelectorStyle>

                <Style TargetType="syncfusion:SfDateSelector">

                    <Setter Property="ShowDoneButton" Value="false"/>

                </Style>

            </syncfusion:SfDatePicker.SelectorStyle>  

        </syncfusion:SfDatePicker>

</Page>

{% endhighlight %}

![UWP DatePickerFeatures_img11](Features_images/Features_img11.png)




## ShowCancelButton

The ShowCancelButton property is used to show or hide the cancel button. The default value is true.

The following code sample shows how to hide the cancel button:

{% highlight xaml %}

<Page
   ...
   xmlns:input="using:Syncfusion.UI.Xaml.Controls.Input">

    <syncfusion:SfDatePicker VerticalAlignment="Center"

                               HorizontalAlignment="Center"

                               Width="200">

            <syncfusion:SfDatePicker.SelectorStyle>

                <Style TargetType="syncfusion:SfDateSelector">

<Setter Property="ShowCancelButton" Value="false"/>

                </Style>

            </syncfusion:SfDatePicker.SelectorStyle>        </syncfusion:SfDatePicker>

</Page>

			{% endhighlight  %}
			
![UWP DatePickerFeatures_img12](Features_images/Features_img12.png)
