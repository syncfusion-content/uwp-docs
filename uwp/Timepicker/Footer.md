---
layout: post
title: Footer in UWP TimePicker control | Syncfusion®
description: Learn here all about Footer support in Syncfusion® UWP TimePicker (SfTimePicker) control and more features.
platform: uwp
control: SfTimePicker
documentation: ug
---

# Footer in UWP TimePicker (SfTimePicker)

## Done and Cancel Buttons

The Done and Cancel buttons can be made visible or hidden using the following properties:

## ShowDoneButton

The ShowDoneButton property is used to show or hide the Done button. The default value is true.

The following code sample shows how to hide the Done button:


{% highlight xaml %}




<Page
   ...
   xmlns:input="using:Syncfusion.UI.Xaml.Controls.Input">

    <syncfusion:SfTimePicker VerticalAlignment="Center"

                                   HorizontalAlignment="Center"

                                   Width="200">

                <syncfusion:SfTimePicker.SelectorStyle>

                    <Style TargetType="syncfusion:SfTimeSelector">

                        <Setter Property="ShowDoneButton" Value="false"/>

                    </Style>

                </syncfusion:SfTimePicker.SelectorStyle>         
     
     </syncfusion:SfTimePicker>

</Page>

{% endhighlight %}

![Features_img13](Features_images/Features_img13.png)





## ShowCancelButton

The ShowCancelButton property is used to show or hide the Cancel button. The default value is true.

The following code sample shows how to hide the Cancel button:
{% highlight xaml %}




<Page
   ...
   xmlns:input="using:Syncfusion.UI.Xaml.Controls.Input">

    <syncfusion:SfTimePicker VerticalAlignment="Center"

                                   HorizontalAlignment="Center"

                                   Width="200">

                <syncfusion:SfTimePicker.SelectorStyle>

                    <Style TargetType="syncfusion:SfTimeSelector">

    <Setter Property="ShowCancelButton" Value="false"/>

                    </Style>

                </syncfusion:SfTimePicker.SelectorStyle>       
                
    </syncfusion:SfTimePicker>

</Page>

{% endhighlight %}

![Features_img14](Features_images/Features_img14.png)
