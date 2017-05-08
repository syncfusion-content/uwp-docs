---
layout: post
title: Markers 
description: Markers for sparkline
platform: uwp
control: SfSparkline
documentation: ug
---
# Markers

Markers are used to indicate the value point for line and area series, and we can customize with different template.It is applicable for LineSparkLine and AreaSparkLine

* [`MarkerVisibility`](http://help.syncfusion.com/cr/cref_files/uwp/sfchart/frlrfSyncfusionUIXamlChartsMarkerBaseClassMarkerVisibilityTopic.html) – Gets or sets the visibility for marker.

{% tabs %}

{% highlight xaml %}

<Syncfusion:SfLineSparkline  Interior="#4a4a4a"   

BorderBrush="DarkGray"  BorderThickness="1"    

MarkerVisibility="Visible" 

ItemsSource="{Binding UsersList}" 

YBindingPath="NoOfUsers">

</Syncfusion:SfLineSparkline >

{% endhighlight %}

{% highlight c# %}

SfLineSparkline sparkline = new SfLineSparkline()
{

    ItemsSource = new SparkViewModel().UsersList,

    YBindingPath = "NoOfUsers",

    MarkerVisibility = Visibility.Visible,

    Interior = new SolidColorBrush(Colors.Gray),

    BorderBrush = new SolidColorBrush(Colors.DarkGray),

    BorderThickness = new Thickness(1, 1, 1, 1)

};

{% endhighlight %}

{% endtabs %}

![Marker visibility](Markers_images/Markers_img1.jpeg)


