---

layout: post
title: Zooming in UWP Sunburst Chart control | Syncfusion
description: Learn here all about Zooming support in Syncfusion UWP Sunburst Chart (SfSunburstChart) control and more.
platform: uwp 
control: SfSunburstChart 
documentation: ug

---

# Zooming in UWP Sunburst Chart (SfSunburstChart)

Sunburst chart provides zooming (drill down) experience with animation for both mouse and touch enabled devices. It allows you to virtualize large sets of data into minimum data view. 

The following code shows how to initialize the zooming behavior.

{% tabs %}

{% highlight xaml %}

<sunburst:SfSunburstChart.Behaviors>
  <sunburst:SunburstZoomingBehavior/>
</sunburst:SfSunburstChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

SunburstZoomingBehavior zoom = new SunburstZoomingBehavior();
chart.Behaviors.Add(zoom);

{% endhighlight %}

{% endtabs %}

N> You can enable or disable the zooming by using [`EnableZooming`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.SunburstChart.SunburstZoomingBehavior.html#Syncfusion_UI_Xaml_SunburstChart_SunburstZoomingBehavior_EnableZooming) property. By default, EnableZooming property value is True.

![Zooming_img1](Zooming_images/Zooming_img1.gif)

## Zooming toolbar

By default, zooming toolbar will be enabled while zooming the segment; it contains both back and reset option.

You can align the zooming toolbar position by using [`ToolBarHorizontalAlignment`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.SunburstChart.SunburstZoomingBehavior.html#Syncfusion_UI_Xaml_SunburstChart_SunburstZoomingBehavior_ToolBarHorizontalAlignment) and [`ToolBarVerticalAlignment`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.SunburstChart.SunburstZoomingBehavior.html#Syncfusion_UI_Xaml_SunburstChart_SunburstZoomingBehavior_ToolBarVerticalAlignment) property.

{% highlight xaml %}

<sunburst:SfSunburstChart.Behaviors>
  <sunburst:SunburstZoomingBehavior EnableZooming="True"
                                    ToolBarHorizontalAlignment="Center"
                                    ToolBarVerticalAlignment="Center"/>
</sunburst:SfSunburstChart.Behaviors>

{% endhighlight %}

You can customize the zooming toolbar using the following properties.

* `ToolBarItemHeight` – Gets or sets the height for the toolbar item.
* `ToolBarItemWidth` – Gets or sets the width for the toolbar item.
* `ToolBarItemMargin` – Gets or sets the margin of the toolbar item.

{% highlight xaml %}

<sunburst:SfSunburstChart.Behaviors>
  <sunburst:SunburstZoomingBehavior EnableZooming="True"
                                    ToolBarHorizontalAlignment="Center"
                                    ToolBarVerticalAlignment="Center"
                                    ToolBarItemHeight="30"
                                    ToolBarItemWidth="50"
                                    ToolBarItemMargin="5"/>
</sunburst:SfSunburstChart.Behaviors>

{% endhighlight %}

![Zooming_img2](Zooming_images/Zooming_img2.jpeg)
