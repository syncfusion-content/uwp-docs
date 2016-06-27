---
layout: post
title: ShowHide Axis support for sparkline
description: ShowHide Axis support for sparkline
platform: uwp
control: SfSparkline
documentation: ug
---
# Show/Hide Axis

ShowAxis is used to enable the axis and this feature is applicable for all the sparkline except WinLoss sparkline, also you can style the axis by AxisStyle property and position the axis by AxisOrigin property.

* [`ShowAxis`](http://help.syncfusion.com/cr/cref_files/uwp/sfchart/frlrfSyncfusionUIXamlChartsMarkerBaseClassShowAxisTopic.html) – Gets or sets the bool value whether to show or hide the axis.
* [`AxisOrigin`](http://help.syncfusion.com/cr/cref_files/uwp/sfchart/frlrfSyncfusionUIXamlChartsMarkerBaseClassAxisOriginTopic.html) - Gets or sets the double for axis origin.
* [`AxisStyle`](http://help.syncfusion.com/cr/cref_files/uwp/sfchart/frlrfSyncfusionUIXamlChartsMarkerBaseClassAxisStyleTopic.html) – Gets or sets the style for axis line.

**Show Axis**

{%highlight xaml%}

<Syncfusion:SfLineSparkline  Interior="#4a4a4a"  

BorderBrush="DarkGray" BorderThickness="1"

ShowAxis="True" ItemsSource="{Binding UsersList}" 

YBindingPath="NoOfUsers">

</Syncfusion:SfLineSparkline >

{%endhighlight%}

![Show Axis](ShowHide-Axis_images/ShowHideAxis_img1.jpeg)


**Axis Origin**

{%highlight xaml%}

<Syncfusion:SfLineSparkline Height="250" Width="350" Interior="#4a4a4a"  

BorderBrush="DarkGray" BorderThickness="1"

ShowAxis="True" 

AxisOrigin="2" ItemsSource="{Binding UsersList}" 

YBindingPath="NoOfUsers">

</Syncfusion:SfLineSparkline >

{%endhighlight%}

![Axis Origin](ShowHide-Axis_images/ShowHideAxis_img2.jpeg)


**Axis LineStyle**

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

![Customizing Axis line](ShowHide-Axis_images/ShowHideAxis_img3.jpeg)


