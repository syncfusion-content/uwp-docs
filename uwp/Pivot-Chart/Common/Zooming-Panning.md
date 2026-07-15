---
layout: post
title: Zooming and Panning in UWP Pivot Chart control | Syncfusion
description: Learn here all about Zooming and Panning support in Syncfusion® UWP Pivot Chart (SfPivotChart) control and more.
platform: uwp
control: SfPivotChart
documentation: ug
---

# Zooming and Panning in UWP Pivot Chart (SfPivotChart)

The SfPivotChart allows you to zoom in, zoom out, and pan the chart area with the help of this support. Zooming is used to view the in-depth information of a specific chart area, when there are a large number of data points inside the chart. Panning is used to navigate the chart area.

Zooming and panning allow you to take a close-up look at the data point plotted in the series.

**Initialization**

By using the [`ZoomPanBehavior`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.PivotChart.PivotChartZoomPanBehavior.html) property in the SfPivotChart, you can enable the zooming and panning support as shown in the following code snippet.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.ZoomPanBehavior>
   <syncfusion:PivotChartZoomPanBehavior/>
</syncfusion:SfPivotChart.ZoomPanBehavior>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ZoomPanBehavior = new PivotChartZoomPanBehavior();

{% endhighlight %}

{% highlight vb %}

PivotChart1.ZoomPanBehavior = New PivotChartZoomPanBehavior()

{% endhighlight %}

{% endtabs %}

## Zooming chart area

Zooming can be performed by any of the following ways:

### Mouse wheel zooming

Zooming can be performed through mouse wheel action by setting the [`EnableMouseWheelZooming`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_EnableMouseWheelZooming) property to true as shown in the following code snippet.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.ZoomPanBehavior>
   <syncfusion:PivotChartZoomPanBehavior EnableMouseWheelZooming="True" />
</syncfusion:SfPivotChart.ZoomPanBehavior>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ZoomPanBehavior = new PivotChartZoomPanBehavior();
PivotChart1.ZoomPanBehavior.EnableMouseWheelZooming = true;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ZoomPanBehavior = New PivotChartZoomPanBehavior()
PivotChart1.ZoomPanBehavior.EnableMouseWheelZooming = True

{% endhighlight %}

{% endtabs %}

**Zooming relative to cursor**

To enable the zooming relative to cursor position, you can set the [`ZoomRelativeToCursor`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_ZoomRelativeToCursor) property to true. This support is applicable only for the mouse wheel zooming.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.ZoomPanBehavior>
   <syncfusion:PivotChartZoomPanBehavior EnableMouseWheelZooming="True" ZoomRelativeToCursor="True" />
</syncfusion:SfPivotChart.ZoomPanBehavior>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ZoomPanBehavior = new PivotChartZoomPanBehavior();
PivotChart1.ZoomPanBehavior.EnableMouseWheelZooming = true;
PivotChart1.ZoomPanBehavior.ZoomRelativeToCursor = true;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ZoomPanBehavior = New PivotChartZoomPanBehavior()
PivotChart1.ZoomPanBehavior.EnableMouseWheelZooming = True
PivotChart1.ZoomPanBehavior.ZoomRelativeToCursor = True

{% endhighlight %}

{% endtabs %}

### Pinch zooming

If you want to zoom the chart area using fingers by touch, then you have to set the [`EnablePinchZooming`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_EnablePinchZooming) property to true as shown in the following code snippet.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.ZoomPanBehavior>
   <syncfusion:PivotChartZoomPanBehavior EnablePinchZooming="True" />
</syncfusion:SfPivotChart.ZoomPanBehavior>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ZoomPanBehavior = new PivotChartZoomPanBehavior();
PivotChart1.ZoomPanBehavior.EnablePinchZooming = true;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ZoomPanBehavior = New PivotChartZoomPanBehavior()
PivotChart1.ZoomPanBehavior.EnablePinchZooming = True

{% endhighlight %}

{% endtabs %}

### Selection zooming

Zooming can also be performed by selecting a particular region in rectangular form. To enable the selection zooming, you should set the [`EnableSelectionZooming`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_EnableSelectionZooming) property to true.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.ZoomPanBehavior>
   <syncfusion:PivotChartZoomPanBehavior EnableSelectionZooming ="True" />
</syncfusion:SfPivotChart.ZoomPanBehavior>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ZoomPanBehavior = new PivotChartZoomPanBehavior();
PivotChart1.ZoomPanBehavior.EnableSelectionZooming = true;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ZoomPanBehavior = New PivotChartZoomPanBehavior()
PivotChart1.ZoomPanBehavior.EnableSelectionZooming = True

{% endhighlight %}

{% endtabs %}

![default_selctionBox](Zooming-Panning_images/default_selctionBox.png)

**Customizing the selection rectangle**

The rectangle that is displayed while selecting a region for zooming can be customized by using the [`Fill`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_Fill), [`Stroke`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_Stroke), and [`StrokeThickness`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_StrokeThickness) properties.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.ZoomPanBehavior>
   <syncfusion:PivotChartZoomPanBehavior EnableSelectionZooming="True" Fill="LightBlue" Stroke="Black" StrokeThickness="2" />
</syncfusion:SfPivotChart.ZoomPanBehavior>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ZoomPanBehavior = new PivotChartZoomPanBehavior();
PivotChart1.ZoomPanBehavior.EnableSelectionZooming = true;
PivotChart1.ZoomPanBehavior.Fill = new SolidColorBrush(Colors.LightBlue);
PivotChart1.ZoomPanBehavior.Stroke = new SolidColorBrush(Colors.Black);
PivotChart1.ZoomPanBehavior.StrokeThickness = 2;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ZoomPanBehavior = New PivotChartZoomPanBehavior()
PivotChart1.ZoomPanBehavior.EnableSelectionZooming = True
PivotChart1.ZoomPanBehavior.Fill = New SolidColorBrush(Colors.LightBlue)
PivotChart1.ZoomPanBehavior.Stroke = New SolidColorBrush(Colors.Black)
PivotChart1.ZoomPanBehavior.StrokeThickness = 2

{% endhighlight %}

{% endtabs %}

![customized_selctionBox](Zooming-Panning_images/customized_selctionBox.png)

## Zooming mode

Zooming can be done horizontally and vertically based on the axis that is defined by using the [`ZoomMode`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_ZoomMode) property. By default, the [`ZoomMode`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_ZoomMode) is set as `XY`, so that the zooming can be performed on both the axes.

**Zooming along x-axis**

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.ZoomPanBehavior>
   <syncfusion:PivotChartZoomPanBehavior EnableSelectionZooming="True" ZoomMode="X" />
</syncfusion:SfPivotChart.ZoomPanBehavior>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ZoomPanBehavior = new PivotChartZoomPanBehavior();
PivotChart1.ZoomPanBehavior.EnableSelectionZooming = true;
PivotChart1.ZoomPanBehavior.ZoomMode = ZoomMode.X;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ZoomPanBehavior = New PivotChartZoomPanBehavior()
PivotChart1.ZoomPanBehavior.EnableSelectionZooming = True
PivotChart1.ZoomPanBehavior.ZoomMode = ZoomMode.X

{% endhighlight %}

{% endtabs %}

![zoomModeX](Zooming-Panning_images/zoomModeX.png)

**Zooming along y-axis**

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.ZoomPanBehavior>
   <syncfusion:PivotChartZoomPanBehavior EnableSelectionZooming="True" ZoomMode="Y" />
</syncfusion:SfPivotChart.ZoomPanBehavior>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ZoomPanBehavior = new PivotChartZoomPanBehavior();
PivotChart1.ZoomPanBehavior.EnableSelectionZooming = true;
PivotChart1.ZoomPanBehavior.ZoomMode = ZoomMode.Y;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ZoomPanBehavior = New PivotChartZoomPanBehavior()
PivotChart1.ZoomPanBehavior.EnableSelectionZooming = True
PivotChart1.ZoomPanBehavior.ZoomMode = ZoomMode.Y

{% endhighlight %}

{% endtabs %}

![zoomModeY](Zooming-Panning_images/zoomModeY.png)

## Zoom level

You can also limit the zooming by setting the [`MaximumZoomLevel`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_MaximumZoomLevel) property as illustrated in the following code snippet.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.ZoomPanBehavior>
   <syncfusion:PivotChartZoomPanBehavior MaximumZoomLevel="5" />
</syncfusion:SfPivotChart.ZoomPanBehavior>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ZoomPanBehavior = new PivotChartZoomPanBehavior();
PivotChart1.ZoomPanBehavior.MaximumZoomLevel = 5;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ZoomPanBehavior = New PivotChartZoomPanBehavior()
PivotChart1.ZoomPanBehavior.MaximumZoomLevel = 5

{% endhighlight %}

{% endtabs %}

## Zooming toolbar

The zooming toolbar is encompassed with buttons for performing actions such as zoom in, zoom out, reset, pan, etc. You can add the zooming toolbar to the chart area by enabling the [`EnableZoomingToolBar`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_EnableZoomingToolBar) property as follows.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.ZoomPanBehavior>
    <syncfusion:PivotChartZoomPanBehavior EnableZoomingToolBar="True" EnableSelectionZooming="True" />
</syncfusion:SfPivotChart.ZoomPanBehavior>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ZoomPanBehavior = new PivotChartZoomPanBehavior();
PivotChart1.ZoomPanBehavior.EnableZoomingToolBar = true;
PivotChart1.ZoomPanBehavior.EnableSelectionZooming = true;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ZoomPanBehavior = New PivotChartZoomPanBehavior()
PivotChart1.ZoomPanBehavior.EnableZoomingToolBar = True
PivotChart1.ZoomPanBehavior.EnableSelectionZooming = True

{% endhighlight %}

{% endtabs %}

![defaultZoomingToolbar](Zooming-Panning_images/defaultZoomingToolbar.png)

**Positioning zooming toolbar**

The zooming toolbar can be positioned by using the [`HorizontalPosition`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_HorizontalPosition) and [`VerticalPosition`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_VerticalPosition) properties as illustrated in the following code snippet.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.ZoomPanBehavior>
   <syncfusion:PivotChartZoomPanBehavior EnableZoomingToolBar="True" HorizontalPosition="Left" VerticalPosition="Bottom" />
</syncfusion:SfPivotChart.ZoomPanBehavior>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ZoomPanBehavior = new PivotChartZoomPanBehavior();
PivotChart1.ZoomPanBehavior.EnableZoomingToolBar  = true;
PivotChart1.ZoomPanBehavior.HorizontalPosition = HorizontalAlignment.Left;
PivotChart1.ZoomPanBehavior.VerticalPosition = VerticalAlignment.Bottom;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ZoomPanBehavior = New PivotChartZoomPanBehavior()
PivotChart1.ZoomPanBehavior.EnableZoomingToolBar = True
PivotChart1.ZoomPanBehavior.HorizontalPosition = HorizontalAlignment.Left
PivotChart1.ZoomPanBehavior.VerticalPosition = VerticalAlignment.Bottom

{% endhighlight %}

{% endtabs %}

![alignedZoomingToolbar](Zooming-Panning_images/alignedZoomingToolbar.png)

**Customization of zooming toolbar**

The zooming toolbar can be customized by using the following properties:

* [`ToolBarBackground`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_ToolBarBackground): Represents the background of the zooming toolbar.
* [`ToolBarItems`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_ToolBarItems): Represents the collection of toolbar items.
* [`ToolBarItemMargin`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_ToolBarItemMargin): Represents the margin for the toolbar item.
* [`ToolBarItemWidth`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_ToolBarItemWidth): Represents the width of the toolbar item.
* [`ToolBarItemHeight`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_ToolBarItemHeight): Represents the height of the toolbar item.
* [`ToolBarOrientation`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_ToolBarOrientation): Represents the orientation of the toolbar.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.ZoomPanBehavior>
    <syncfusion:PivotChartZoomPanBehavior EnableZoomingToolBar="True" ToolBarBackground="SaddleBrown" ToolBarItems="All" ToolBarOrientation="Vertical" ToolBarItemHeight="15" ToolBarItemWidth="15" ToolBarItemMargin="5" />
</syncfusion:SfPivotChart.ZoomPanBehavior>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ZoomPanBehavior = new PivotChartZoomPanBehavior();
PivotChart1.ZoomPanBehavior.EnableZoomingToolBar  = true;
PivotChart1.ZoomPanBehavior.ToolBarBackground = new SolidColorBrush(Colors.SaddleBrown);
PivotChart1.ZoomPanBehavior.ToolBarItems = ZoomToolBarItems.All;
PivotChart1.ZoomPanBehavior.ToolBarOrientation = Orientation.Vertical;
PivotChart1.ZoomPanBehavior.ToolBarItemHeight = 15;
PivotChart1.ZoomPanBehavior.ToolBarItemWidth = 15;
PivotChart1.ZoomPanBehavior.ToolBarItemMargin = new Thickness(5);

{% endhighlight %}

{% highlight vb %}

PivotChart1.ZoomPanBehavior = New PivotChartZoomPanBehavior()
PivotChart1.ZoomPanBehavior.EnableZoomingToolBar = True
PivotChart1.ZoomPanBehavior.ToolBarBackground = New SolidColorBrush(Colors.SaddleBrown)
PivotChart1.ZoomPanBehavior.ToolBarItems = ZoomToolBarItems.All
PivotChart1.ZoomPanBehavior.ToolBarOrientation = Orientation.Vertical
PivotChart1.ZoomPanBehavior.ToolBarItemHeight = 15
PivotChart1.ZoomPanBehavior.ToolBarItemWidth = 15
PivotChart1.ZoomPanBehavior.ToolBarItemMargin = New Thickness(5)

{% endhighlight %}

{% endtabs %}

![customizedZoomingToolBar](Zooming-Panning_images/customizedZoomingToolBar.png)

## Panning chart area

Panning allows you to navigate the visible area of the chart when it is zoomed in. To enable panning, you can set the [`EnablePanning`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_EnablePanning) property to true as follows.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.ZoomPanBehavior>
   <syncfusion:PivotChartZoomPanBehavior EnablePanning="True" />
</syncfusion:SfPivotChart.ZoomPanBehavior>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ZoomPanBehavior = new PivotChartZoomPanBehavior();
PivotChart1.ZoomPanBehavior.EnablePanning = true;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ZoomPanBehavior = New PivotChartZoomPanBehavior()
PivotChart1.ZoomPanBehavior.EnablePanning = True

{% endhighlight %}

{% endtabs %}

![pannedChartArea](Zooming-Panning_images/pannedChartArea.png)

## Reset zooming and panning

The SfPivotChart supports resetting the default view when you double-tap the chart area by setting the [`ResetOnDoubleTap`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_ResetOnDoubleTap) property to true.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.ZoomPanBehavior>
   <syncfusion:PivotChartZoomPanBehavior ResetOnDoubleTap="True" />
</syncfusion:SfPivotChart.ZoomPanBehavior>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ZoomPanBehavior = new PivotChartZoomPanBehavior();
PivotChart1.ZoomPanBehavior.ResetOnDoubleTap = true;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ZoomPanBehavior = New PivotChartZoomPanBehavior()
PivotChart1.ZoomPanBehavior.ResetOnDoubleTap = True

{% endhighlight %}

{% endtabs %}
