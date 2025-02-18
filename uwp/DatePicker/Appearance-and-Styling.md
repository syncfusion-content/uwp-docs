---
layout: post
title: Appearance and Styling in UWP DatePicker control | Syncfusion®
description: Learn here all about Appearance and Styling support in Syncfusion® UWP DatePicker (SfDatePicker) control and more.
platform: uwp
control: SfDatePicker
documentation: ug
---

# Appearance and Styling in UWP DatePicker (SfDatePicker)

## Accent Brush	

The AccentBrush property is used to decorate the hot spots of a control with a solid color.

{% highlight xaml %}


<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

        <syncfusion:SfDatePicker  VerticalAlignment="Center"

                                HorizontalAlignment="Center"

                                Width="200"

                                AccentBrush="Green"/>

</Grid>

{% endhighlight  %}

The following image shows the control with various Accent brushes:

![Appearance-and-Styling_img1](Appearance-and-Styling_images/Appearance-and-Styling_img1.png)


## Selected Foreground

The SelectedForeground property is used to change the foreground color of  the Selected Date

{% highlight xaml %}



<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

        <syncfusion:SfDatePicker VerticalAlignment="Center"

                         HorizontalAlignment="Center"

                         Width="200">

            <syncfusion:SfDatePicker.SelectorStyle>

                <Style TargetType="syncfusion:SfDateSelector">
                 
                    <Setter Property="SelectedForeground" Value="Red"/>
                    
                </Style>

            </syncfusion:SfDatePicker.SelectorStyle>

        </syncfusion:SfDatePicker>

</Grid>

{% endhighlight  %}


![Appearance-and-Styling_img2](Appearance-and-Styling_images/Appearance-and-Styling_img2.png)
