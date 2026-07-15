---
layout: post
title: Data Markers in UWP Smith Chart control | Syncfusion
description: Learn here all about Data Markers support in Syncfusion UWP Smith Chart (SfSmithChart) control and more.
platform: uwp
control: SfSmithChart
documentation: ug
---

# Data Markers in UWP Smith Chart (SfSmithChart)

Data markers are used to provide information about a data point to the user. You can add a shape and label to adorn each data point.

## Add shapes

Shapes can be added to line series to indicate each data point and they can also be added to the chart by enabling the [`ShowMarker`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.SmithChart.ChartSeries.html#Syncfusion_UI_Xaml_SmithChart_ChartSeries_ShowMarker) option of the [`Series`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.SmithChart.SfSmithChart.html#Syncfusion_UI_Xaml_SmithChart_SfSmithChart_Series) property. Different shapes can be added to the chart by using the [`MarkerType`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.SmithChart.ChartSeries.html#Syncfusion_UI_Xaml_SmithChart_ChartSeries_MarkerType) option such as rectangle, circle, diamond, etc.

The following code example explains how to enable series marker and add shapes,

{% tabs %}

{% highlight xaml %}

<syncfusion:SfSmithChart x:Name="SmithChart">
     <syncfusion:LineSeries ShowMarker="True" MarkerType="Circle">
     </syncfusion:LineSeries>
 </syncfusion:SfSmithChart>

{% endhighlight %}

{% highlight C# %} 

LineSeries series = new LineSeries();
series.ShowMarker = true;
series.MarkerType = MarkerType.Circle;
chart.Series.Add(series);

{% endhighlight %}
    
{% endtabs %}

![SfSmithChart Add Shapes](Data-Markers_images/Data-Markers_img1.png)

## Customizing marker

The markers interior, stroke, and size can be customized as demonstrated in the below code snippet.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfSmithChart x:Name="SmithChart">
     <syncfusion:LineSeries ShowMarker="True" MarkerType="Circle" MarkerHeight="12" MarkerWidth="12" MarkerInterior="Red" MarkerStroke="Yellow" />
 </syncfusion:SfSmithChart>

{% endhighlight %}

{% highlight C# %} 

LineSeries series = new LineSeries();
series.ShowMarker = true;
series.MarkerType = MarkerType.Circle;
series.MarkerHeight = 12;
series.MarkerWidth = 12;
series.MarkerInterior = new SolidColorBrush(Colors.Red);
series.MarkerStroke = new SolidColorBrush(Colors.Yellow);
chart.Series.Add(series);

{% endhighlight %}
    
{% endtabs %}

![SfSmithChart Customizing Marker](Data-Markers_images/Data-Markers_img2.png)

**MarkerTemplate**

Apart from the shapes, custom shapes can also be added to mark the data point by using the [`MarkerTemplate`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.SmithChart.ChartSeries.html#Syncfusion_UI_Xaml_SmithChart_ChartSeries_MarkerTemplate) property. To add custom shapes, define the [`MarkerType`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.SmithChart.ChartSeries.html#Syncfusion_UI_Xaml_SmithChart_ChartSeries_MarkerType) as **Custom**.

The following code example illustrates how to add custom shapes:

{% tabs %}

{% highlight xaml %}

<syncfusion:SfSmithChart x:Name="SmithChart">
   <syncfusion:SfSmithChart.Resources>
       <DataTemplate x:Key="Ellipse">
           <Ellipse Stretch="Fill" Fill="{Binding Interior}" Stroke="{Binding Stroke}" StrokeThickness="2" Width="10" Height="17" />
       </DataTemplate>
   </syncfusion:SfSmithChart.Resources>
   <syncfusion:LineSeries ShowMarker="True" MarkerType="Custom" MarkerTemplate="{StaticResource Ellipse}">
   </syncfusion:LineSeries>
 </syncfusion:SfSmithChart>

{% endhighlight %}

{% highlight C# %} 

LineSeries series = new LineSeries();
series.ShowMarker = true;
series.MarkerType = MarkerType.Custom;
series.MarkerTemplate = this.Grid1.Resources["Ellipse"] as DataTemplate;
chart.Series.Add(series);

{% endhighlight %}
    
{% endtabs %}

![SfSmithChart MarkerTemplate](Data-Markers_images/Data-Markers_img3.png)

## Add labels

Data label can be added to a chart series by setting the [`ShowLabel`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.SmithChart.DataLabel.html#Syncfusion_UI_Xaml_SmithChart_DataLabel_ShowLabel) property as True in the series [`DataLabel`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.SmithChart.DataLabel.html) option. By default, the data labels are displayed on top of the data point and their position is automatically adjusted when they collide with another label.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfSmithChart x:Name="SmithChart">
   <syncfusion:LineSeries ItemsSource="{Binding Data}" ResistancePath="Resistance" ReactancePath="Reactance">
     <syncfusion:LineSeries.DataLabel>
         <syncfusion:DataLabel ShowLabel="True"></syncfusion:DataLabel>
     </syncfusion:LineSeries.DataLabel>
    </syncfusion:LineSeries>
 </syncfusion:SfSmithChart>

{% endhighlight %}

{% highlight C# %} 

LineSeries series = new LineSeries();
series.DataLabel.ShowLabel = true;
chart.Series.Add(series);

{% endhighlight %}
    
{% endtabs %}

N> The position changed data label will be connected by using a connector line and the label will be hidden if there is no place to position it around the data point.

The following screenshot illustrates how the data labels can be positioned.

![SfSmithChart Add Labels](Data-Markers_images/Data-Markers_img4.png)

**LabelStyle**

The style for the data label can be defined by using *LabelStyle* property of [`DataLabel`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.SmithChart.DataLabel.html).

{% tabs %}

{% highlight xaml %}

<syncfusion:SfSmithChart x:Name="SmithChart">
 <syncfusion:SfSmithChart.Resources>
   <Style TargetType="TextBlock" x:Key="labelStyle">
       <Setter Property="Foreground" Value="Yellow"/>
       <Setter Property="FontSize" Value="12"/>
       <Setter Property="FontFamily" Value="Calibri"/>
       <Setter Property="FontWeight" Value="Bold"/>
   </Style>
  </syncfusion:SfSmithChart.Resources>
  <syncfusion:LineSeries>
     <syncfusion:LineSeries.DataLabel>
         <syncfusion:DataLabel ShowLabel="True" LabelStyle="{StaticResource labelStyle}">
         </syncfusion:DataLabel>
     </syncfusion:LineSeries.DataLabel>
    </syncfusion:LineSeries>
 </syncfusion:SfSmithChart>

{% endhighlight %}

{% highlight C# %} 

LineSeries series = new LineSeries();
series.DataLabel.ShowLabel = true;
series.DataLabel.LabelStyle = this.Grid1.Resources["labelStyle"] as Style;
chart.Series.Add(series);

{% endhighlight %}
    
{% endtabs %}

![SfSmithChart LabelStyle](Data-Markers_images/Data-Markers_img5.png)

**LabelTemplate**

The label content can be formatted and customized by using the *LabelTemplate* property of [`DataLabel`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.SmithChart.DataLabel.html). The following code example illustrates how the label content can be formatted and customized.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfSmithChart x:Name="SmithChart">
 <syncfusion:SfSmithChart.Resources>
     <DataTemplate x:Key="labelTemplate">
         <Border CornerRadius="4" Background="{Binding Background}" BorderThickness="1" Padding="8,4,8,4" BorderBrush="{Binding BorderBrush}">
             <Grid>
                 <Grid.RowDefinitions>
                     <RowDefinition/>
                     <RowDefinition/>
                 </Grid.RowDefinitions>
                 <TextBlock Grid.Row="0" Text="{Binding Resistance}" Style="{Binding LabelStyle}"/>
                 <TextBlock Grid.Row="1" Text="{Binding Reactance}"  Style="{Binding LabelStyle}"/>
             </Grid>
         </Border>
     </DataTemplate>
 </syncfusion:SfSmithChart.Resources>
     <syncfusion:LineSeries ShowMarker="True" ItemsSource="{Binding Data}" ResistancePath="Resistance" ReactancePath="Reactance">
     <syncfusion:LineSeries.DataLabel>
         <syncfusion:DataLabel ShowLabel="True" LabelTemplate="{StaticResource labelTemplate}"></syncfusion:DataLabel>
     </syncfusion:LineSeries.DataLabel>
    </syncfusion:LineSeries>
</syncfusion:SfSmithChart>

{% endhighlight %}

{% highlight C# %} 

LineSeries series = new LineSeries();
series.DataLabel.ShowLabel = true;
series.DataLabel.LabelTemplate = this.Grid1.Resources["labelTemplate"] as DataTemplate;
chart.Series.Add(series);

{% endhighlight %}
    
{% endtabs %}

![SfSmithChart LabelTemplate](Data-Markers_images/Data-Markers_img6.png)
