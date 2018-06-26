---
layout: post
title: Track ball 
description: Track ball
platform: uwp
control: SfSparkline
documentation: ug
---
# Track ball

This is used to indicate the value point on mouse move and this feature is applicable for line and area sparkline.

* [`ShowTrackBall`](http://help.syncfusion.com/cr/cref_files/uwp/sfchart/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.MarkerBase~ShowTrackBall.html) – Gets or sets the bool value whether showing track ball.
* [`TrackBallStyle`](http://help.syncfusion.com/cr/cref_files/uwp/sfchart/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.MarkerBase~TrackBallStyle.html) – Gets or sets the style for track ball.
* [`LineStyle`](http://help.syncfusion.com/cr/cref_files/uwp/sfchart/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.MarkerBase~LineStyle.html) – Gets or sets the style for trackball line.

**Show TrackBall**

{%highlight xaml%}

<Syncfusion:SfLineSparkline  Interior="#4a4a4a"   

BorderBrush="DarkGray" BorderThickness="1"

ItemsSource="{Binding UsersList}" ShowTrackBall="True" 

YBindingPath="NoOfUsers">

</Syncfusion:SfLineSparkline >

{%endhighlight%}

![Show Trackball](Track-ball_images/Trackball_img1.jpeg)


**Customizing TrackBall**

{% tabs %}

{% highlight xaml %}

<Grid.Resources>

    <Style TargetType="Ellipse" x:Key="lineStyle1">

        <Setter Property="Fill" Value="Blue"></Setter>

        <Setter Property="Height" Value="12"></Setter>

        <Setter Property="Width" Value="12"></Setter>

    </Style>

    <Style TargetType="Line" x:Key="lineStyle2">

        <Setter Property="Stroke" Value="Blue"/>

        <Setter Property="StrokeThickness" Value="2"></Setter>

        <Setter Property="StrokeDashArray" Value="1,2"></Setter>

    </Style>

</Grid.Resources>

<Syncfusion:SfLineSparkline Height="250" Width="350" Interior="#4a4a4a"   

BorderBrush="DarkGray" BorderThickness="1"

ItemsSource="{Binding UsersList}" ShowTrackBall="True" 

TrackBallStyle="{StaticResource lineStyle1}" 

LineStyle="{StaticResource lineStyle2}"

YBindingPath="NoOfUsers">

</Syncfusion:SfLineSparkline >

{%endhighlight%}

{% highlight c# %}

SfLineSparkline sparkline = new SfLineSparkline()
{

    ItemsSource = new SparkViewModel().Data,

    YBindingPath = "Day",

    ShowTrackBall = true,

    Interior = new SolidColorBrush(Colors.Gray),

    BorderBrush = new SolidColorBrush(Colors.DarkGray),

    BorderThickness = new Thickness(1, 1, 1, 1),

    LineStyle = this.Resources["lineStyle1"] as Style,

    TrackBallStyle = this.Resources["lineStyle2"] as Style

};

{% endhighlight %}

{% endtabs %}

![Customizing TrackBall](Track-ball_images/Trackball_img2.jpeg)
