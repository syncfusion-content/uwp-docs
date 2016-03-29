---
layout: post
title: Appearence and Styling of SfNumericupDown control for UWP
description: Appearence and Styling of SfNumericupDown control for UWP
platform: uwp
control: SfNumeric UpDown
documentation: ug
---

# Appearance and Styling

## Spin Buttons Alignment

Spin Button position in the SfNumericUpDown control can be changed relative to the TextBox based on SpinButtonsAlignment. There are three built-in modes.

1. Right
2. Left
3. Both



### Right

Spin Buttons will get aligned to the right side of the control.

{% tabs %}

{% highlight XAML %}

<Page xmlns:editors="using:Syncfusion.UI.Xaml.Controls.Input">

    <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">



        <editors:SfNumericUpDown x:Name="numericUpDown"

                               HorizontalAlignment="Center"

                               VerticalAlignment="Center"

                               Width="200" 

SpinButtonsAlignment="Right"

                               Value="123.45"/>

    </Grid>

</Page>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

numericUpDown.SpinButtonsAlignment = Syncfusion.UI.Xaml.Controls.SpinButtonsAlignment.Right;

{% endhighlight %}

{% highlight VB %}

numericUpDown.SpinButtonsAlignment = Syncfusion.UI.Xaml.Controls.SpinButtonsAlignment.Right

{% endhighlight %}

{% endtabs %}

![](Appearance-and-Styling_images/Appearance-and-Styling_img1.png)

### Left

Spin Buttons will get aligned to the left side of the control.

{% tabs %}

{% highlight XAML %}

<Page xmlns:editors="using:Syncfusion.UI.Xaml.Controls.Input">

    <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">



        <editors:SfNumericUpDown x:Name="numericUpDown"

                               HorizontalAlignment="Center"

                               VerticalAlignment="Center"

                               Width="200" 

SpinButtonsAlignment="Left"

                               Value="123.45"/>

    </Grid>

</Page>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

 numericUpDown.SpinButtonsAlignment = Syncfusion.UI.Xaml.Controls.SpinButtonsAlignment.Left;

{% endhighlight %}

{% highlight VB %}

 numericUpDown.SpinButtonsAlignment = Syncfusion.UI.Xaml.Controls.SpinButtonsAlignment.Left

{% endhighlight %}

{% endtabs %}

![](Appearance-and-Styling_images/Appearance-and-Styling_img2.png)

### Both

 Spin Buttons will get aligned to the both sides of the control.

{% tabs %}

{% highlight XAML %}

<Page xmlns:editors="using:Syncfusion.UI.Xaml.Controls.Input">

    <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">



        <editors:SfNumericUpDown x:Name="numericUpDown"

                               HorizontalAlignment="Center"

                               VerticalAlignment="Center"

                               Width="200" 

SpinButtonsAlignment="Both"

                               Value="123.45"/>

    </Grid>

</Page>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

numericUpDown.SpinButtonsAlignment = Syncfusion.UI.Xaml.Controls.SpinButtonsAlignment.Both;

{% endhighlight %}

{% highlight VB %}

numericUpDown.SpinButtonsAlignment = Syncfusion.UI.Xaml.Controls.SpinButtonsAlignment.Both

{% endhighlight %}

{% endtabs %}

![](Appearance-and-Styling_images/Appearance-and-Styling_img3.png)

## Accent Brush

Accent Brush property is used to decorate the hot spots of a control with a solid color. 

{% tabs %}

{% highlight XAML %}

<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

        <syncfusion:SfNumericUpDown VerticalAlignment="Center"

                                  HorizontalAlignment="Center"

                                  Width="200" 

AccentBrush="Green"/>

</Grid>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

 numericUpDown.AccentBrush = new SolidColorBrush(Colors.Green);

{% endhighlight %}

{% highlight VB %}

 numericUpDown.AccentBrush = New SolidColorBrush(Colors.Green)

{% endhighlight %}

{% endtabs %}

The following image shows the control with various accent brushes.

![](Appearance-and-Styling_images/Appearance-and-Styling_img4.png)