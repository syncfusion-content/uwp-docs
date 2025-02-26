---
layout: post
title: Appearance and Styling in UWP TimePicker control | Syncfusion®
description: Learn here all about Appearance and Styling support in Syncfusion® UWP TimePicker (SfTimePicker) control and more.
platform: uwp
control: SfTimePicker
documentation: ug
---

# Appearance and Styling in UWP TimePicker (SfTimePicker)

## Accent Brush

The AccentBrush property is used to decorate the hot spots of a control with a solid color.


{% tabs %}

{% highlight xaml %}

<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

        <syncfusion:SfTimePicker  VerticalAlignment="Center" x:Name="timePicker"

                                HorizontalAlignment="Center"

                                Width="200"

                                AccentBrush="Green"/>

</Grid>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

 timePicker.AccentBrush = new SolidColorBrush(Colors.Green);

{% endhighlight %}

{% highlight VB %}

 timePicker.AccentBrush = New SolidColorBrush(Colors.Green)

{% endhighlight %}

{% endtabs %}

The following images showcase the control with various Accent Brushes:



![Features_img15](Features_images/Features_img15.png)

## Selected Foreground

The SelectedForeground property is used to change the foreground color of  the Selected Time

{% highlight xaml %}



<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

       <syncfusion:SfTimePicker VerticalAlignment="Center"

                         HorizontalAlignment="Center"

                         Width="200">

            <syncfusion:SfTimePicker.SelectorStyle>

                <Style TargetType="syncfusion:SfTimeSelector">

                    <Setter Property="SelectedForeground" Value="Red"/>

                </Style>

            </syncfusion:SfTimePicker.SelectorStyle>

      </syncfusion:SfTimePicker>

</Grid>

{% endhighlight  %}


![Appearance-and-Styling_img2](Features_images/Appearance-and-Styling_img2.png)
