---
layout: post
title: ShowHide Axis in UWP Sparkline control | Syncfusion
description: Learn here all about ShowHide Axis support in Syncfusion UWP Sparkline (SfSparkline) control and more.
platform: uwp
control: SfSparkline
documentation: ug
---
# ShowHide Axis in UWP Sparkline (SfSparkline)

ShowAxis is used to enable the axis and this feature is applicable for all the sparkline except WinLoss sparkline, also you can style the axis by AxisStyle property and position the axis by AxisOrigin property.

* [`ShowAxis`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.MarkerBase.html#Syncfusion_UI_Xaml_Charts_MarkerBase_ShowAxis) – Gets or sets the bool value whether to show or hide the axis.
* [`AxisOrigin`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.MarkerBase.html#Syncfusion_UI_Xaml_Charts_MarkerBase_AxisOrigin) - Gets or sets the double for axis origin.
* [`AxisStyle`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.MarkerBase.html#Syncfusion_UI_Xaml_Charts_MarkerBase_AxisStyle) – Gets or sets the style for axis line.

**Show Axis**

{% tabs %}

{%highlight xaml%}

<Syncfusion:SfLineSparkline  Interior="#4a4a4a"  

BorderBrush="DarkGray" BorderThickness="1"

ShowAxis="True" ItemsSource="{Binding UsersList}" 

YBindingPath="NoOfUsers">

</Syncfusion:SfLineSparkline >

{%endhighlight%}

{% highlight c# %}

SfLineSparkline sparkline = new SfLineSparkline()
{

    ItemsSource = new SparkViewModel().UsersList,

    YBindingPath = "NoOfUsers",

    ShowAxis = true,

    Interior = new SolidColorBrush(Color.FromRgb(0x4a, 0x4a, 0x4a)),

    BorderBrush = new SolidColorBrush(Colors.DarkGray),

    BorderThickness = new Thickness(1)

};

{% endhighlight %}

{% endtabs %}

![Show Axis](ShowHide-Axis_images/ShowHideAxis_img1.jpeg)


**Axis Origin**

{% tabs %}

{%highlight xaml%}

<Syncfusion:SfLineSparkline Height="250" Width="350" Interior="#4a4a4a"  

BorderBrush="DarkGray" BorderThickness="1"

ShowAxis="True" 

AxisOrigin="2" ItemsSource="{Binding UsersList}" 

YBindingPath="NoOfUsers">

</Syncfusion:SfLineSparkline >

{%endhighlight%}

{% highlight c# %}

SfLineSparkline sparkline = new SfLineSparkline()
{

    ItemsSource = new SparkViewModel().UsersList,

    YBindingPath = "NoOfUsers",

    ShowAxis = true,

    AxisOrigin = 2,

    Interior = new SolidColorBrush(Color.FromRgb(0x4a, 0x4a, 0x4a)),

    BorderBrush = new SolidColorBrush(Colors.DarkGray),

    BorderThickness = new Thickness(1)

};

{% endhighlight %}

{% endtabs %}

![Axis Origin](ShowHide-Axis_images/ShowHideAxis_img2.jpeg)


**Axis LineStyle**

{% tabs %}

{%highlight xaml%}

<Grid.Resources>

    <Style TargetType="Line" x:Key="lineStyle2">

        <Setter Property="Stroke" Value="Blue"/>

        <Setter Property="StrokeThickness" Value="2"></Setter>

        <Setter Property="StrokeDashArray" Value="1,1"></Setter>

    </Style>

</Grid.Resources>

<Syncfusion:SfLineSparkline Height="250" Width="350" Interior="#4a4a4a"   

BorderBrush="DarkGray"  BorderThickness="1"

ShowAxis="True" AxisStyle="{StaticResource lineStyle2}"   

AxisOrigin="1" ItemsSource="{Binding UsersList}"   

YBindingPath="NoOfUsers">

</Syncfusion:SfLineSparkline >

{%endhighlight%}

{% highlight c# %}

SfLineSparkline sparkline = new SfLineSparkline()
{

    ItemsSource = new SparkViewModel().UsersList,

    YBindingPath = "NoOfUsers",

    ShowAxis = true,

    AxisOrigin = 1,

    AxisStyle = grid.Resources["lineStyle2"] as Style,

    Interior = new SolidColorBrush(Color.FromRgb(0x4a, 0x4a, 0x4a)),

    BorderBrush = new SolidColorBrush(Colors.DarkGray),

    BorderThickness = new Thickness(1)

};

{% endhighlight %}

{% endtabs %}

![Customizing Axis line](ShowHide-Axis_images/ShowHideAxis_img3.jpeg)


