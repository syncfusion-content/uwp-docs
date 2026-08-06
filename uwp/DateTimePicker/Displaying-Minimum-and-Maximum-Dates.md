---
layout: post
title: Display Minimum and Maximum Dates in UWP DateTimePicker | Syncfusion
description: Learn here all about Displaying Minimum and Maximum Dates support in Syncfusion UWP DateTimePicker (SfDateTimeCombo) control and more.
platform: uwp
control: SfDateTimeCombo
documentation: ug
---

# Displaying Minimum and Maximum Dates in UWP DateTimePicker

To display the minimum and maximum dates in SfDateTimeCombo, use the DisplayMinDate and DisplayMaxDate properties, respectively.

The following code example and screenshots illustrate this.

{% tabs %}

{% highlight XAML %}

<Page
   ...
   xmlns:input="using:Syncfusion.UI.Xaml.Controls.Input">

    <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

    <syncfusion:SfDateTimeCombo FormatString="Mdy" x:Name="combo" Width="350" HorizontalAlignment="Left"/>

    </Grid>

</Page>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

using Syncfusion.UI.Xaml.Controls.Input;

combo.DisplayMinDate = new DateTime(2012,10,2);

combo.DisplayMaxDate = new DateTime(2013,11,22);

{% endhighlight %}

{% highlight VB %}

Imports Syncfusion.UI.Xaml.Controls.Input;

combo.DisplayMinDate = New Date(2012,10,2)

combo.DisplayMaxDate = New Date(2013,11,22)

{% endhighlight %}

{% endtabs %}

![Displaying-Minimum-and-Maximum-Dates_img1](Displaying-Minimum-and-Maximum-Dates_images/Displaying-Minimum-and-Maximum-Dates_img1.png)

![Displaying-Minimum-and-Maximum-Dates_img2](Displaying-Minimum-and-Maximum-Dates_images/Displaying-Minimum-and-Maximum-Dates_img2.png)

![Displaying-Minimum-and-Maximum-Dates_img3](Displaying-Minimum-and-Maximum-Dates_images/Displaying-Minimum-and-Maximum-Dates_img3.png)
