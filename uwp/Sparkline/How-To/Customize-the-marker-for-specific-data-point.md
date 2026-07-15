---
layout: post
title: Customize the marker for specific data point 
description: Customize the marker for specific data point
platform: uwp
control: SfSparkline
documentation: ug
---

# Customize the marker for specific data point

We can customize the marker for a specific data point with a custom template for LineSparkline and AreaSparkline. In order to customize the marker, we need to inherit the [`MarkerTemplateSelector`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.MarkerTemplateSelector.html) class and override the SelectTemplate method.

{% highlight c# %}

public class CustomMarkersTemplateSelector : MarkerTemplateSelector
{
    protected override DataTemplate SelectTemplate(double x, double y)
    {
        if (y == MaximumY)
        {
            DataTemplate markerTemplate = Application.Current.Resources["markerTemplate"] as DataTemplate;
            return markerTemplate;
        }
        else
            return base.SelectTemplate(x, y);
    }
}

{% endhighlight %}

{% highlight xaml %}

<Syncfusion:SfLineSparkline BorderBrush="DarkGray"

BorderThickness="1" ItemsSource="{Binding UsersList}"

Interior="#4a4a4a" MarkerVisibility="Visible"

YBindingPath="NoOfUsers">

<Syncfusion:SfLineSparkline.MarkerTemplateSelector>

<local:CustomMarkersTemplateSelector MarkerHeight="10" MarkerWidth="10"/>

</Syncfusion:SfLineSparkline.MarkerTemplateSelector>

</Syncfusion:SfLineSparkline>

{% endhighlight %}

![Customizing marker for specific datapoint](Customize-the-marker-for-specific-data-point_images/Customizethemarkerforspecificdatapoint_img1.jpeg)
