---
layout: post
title: Interactivity in UWP Range Selector control | Syncfusion®
description: Learn here all about Interactivity support in Syncfusion® UWP Range Selector (SfDateTimeRangeNavigator) control and more.
platform: uwp
control: SfDateTimeRangeNavigator
documentation: ug
---
# Interactivity in UWP Range Selector (SfDateTimeRangeNavigator)

The SfDateTimeRangeNavigator helps the user to visualize large data in a simplified manner. The timespan of the data is represented in the higher level bar and lower level bar. The timespan in default is calculated smartly and provide suitable DateTime format and Interval for the given data. It can hold any type of UI element inside the Navigator.

The following properties are used while selecting the range of data from the SfDateTimeRangeNavigator.

* [`ViewRangeStart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfRangeNavigator_ViewRangeStart)- Gets or sets Navigator's Start Thumb value, Value can be DateTime if Minimum and Maximum are set as DateTime values.
* [`ViewRangeEnd`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfRangeNavigator_ViewRangeEnd)- Gets or sets Navigator's End Thumb value, Value can be DateTime if Minimum and Maximum are set as DateTime values.

{% tabs %}

{% highlight xaml %}

<chart:SfDateTimeRangeNavigator x:Name="RangeNavigator" 

Width="700" Height="179" 

ViewRangeStart="February,2015" 

ViewRangeEnd="March,2015"

XBindingPath="Date" 

ItemsSource="{Binding StockPriceDetails}">

</chart:SfDateTimeRangeNavigator>                             

{% endhighlight %}

{% highlight c# %}

SfDateTimeRangeNavigator rangeNavigator = new SfDateTimeRangeNavigator()
{

    ItemsSource = new ViewModel().StockPriceDetails,

    XBindingPath = "Date",

    ViewRangeStart = new DateTime(2015,02,01),

    ViewRangeEnd = new DateTime(2015, 03, 01)

};

{% endhighlight %}

{% endtabs %}

![ViewRange](Interactivity_images/Interactivity_img1.jpeg)

## Region Selection

In two ways the selected region of the SfDateTimeRangeNavigator can be viewed in the chart.

1. By using ZoomFactor and ZoomPosition.
2. By binding the SelectedData.

Both the ways produce the same result.

* [`ZoomPosition`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfRangeNavigator_ZoomPosition)- Gets or sets zoom position. Value must fall within 0 to 1. It determines starting value of visible range.
* [`ZoomFactor`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfRangeNavigator_ZoomFactor)- Gets or sets zoom factor. Value must fall within 0 to 1. It determines delta of visible range.

The ZoomPosition and ZoomFactor of the chart axis can be bind with the SfDateTimeRangeNavigator.

{% tabs %}

{% highlight xaml %}

<chart:SfChart VerticalAlignment="Bottom" 

AreaBorderThickness="0,1,1,1"

Height="200"  Width="700" x:Name="financialChart"

Grid.Row="0">

<chart:SfChart.Header>

<TextBlock FontSize="14"   Foreground="Black" 

FontFamily="Segoe UI" Margin="0,0,0,20">

USD – INR   Foreign   Exchange Rate Analysis</TextBlock>

</chart:SfChart.Header>

<chart:SfChart.PrimaryAxis>

<chart:CategoryAxis Name="axis1" PlotOffset="25"  FontSize="12" 

ZoomFactor="{Binding ElementName=RangeNavigator,

Path=ZoomFactor, Mode=TwoWay}" 

ZoomPosition="{Binding 

ElementName=RangeNavigator,

Path=ZoomPosition, Mode=TwoWay}"

Header="Date" LabelFormat="MMM/dd" />                           

</chart:SfChart.PrimaryAxis>

<chart:SfChart.SecondaryAxis>

<chart:NumericalAxis Minimum="820" Interval="20" 

Maximum="900" 

FontSize="12"

StartRangeFromZero="False" x:Name="axis2" 

Header="Stock Price" />                                   

</chart:SfChart.SecondaryAxis>

<chart:CandleSeries Name="series" ItemsSource="{Binding StockPriceDetails}" 
                   XBindingPath="Date"  High="High" Open="Open" 
                   Close="Close" Low="Low"  Label="CandleSeries">

</chart:CandleSeries>

</chart:SfChart>

<Grid Grid.Row="1" >

<chart:SfDateTimeRangeNavigator x:Name="RangeNavigator" Width="700" Height="130"
                                ItemsSource="{Binding StockPriceDetails}" 
                                XBindingPath="Date" 
                                VerticalAlignment="Top">

<chart:SfDateTimeRangeNavigator.Content>

<chart:SfLineSparkline ItemsSource="{Binding StockPriceDetails}"
                       YBindingPath="High" >

</chart:SfLineSparkline>

</chart:SfDateTimeRangeNavigator.Content>

</chart:SfDateTimeRangeNavigator>      

</Grid>    

{% endhighlight %}

{% highlight c# %}

SfDateTimeRangeNavigator rangeNavigator = new SfDateTimeRangeNavigator()
{

    ItemsSource = new ViewModel().StockPriceDetails,

    XBindingPath = "Date",

    VerticalAlignment = VerticalAlignment.Top

};

SfLineSparkline sparkline = new SfLineSparkline()
{

    ItemsSource = new ViewModel().StockPriceDetails,

    YBindingPath = "High"

};

rangeNavigator.Content = sparkline;

Grid.SetColumn(rangeNavigator, 1);

SfChart chart = new SfChart()
{

    VerticalAlignment = VerticalAlignment.Bottom,

    AreaBorderThickness = new Thickness(1, 1, 1, 1),

    Header = "USD – INR   Foreign Exchange Rate Analysis"

};

chart.PrimaryAxis = new CategoryAxis()
{

    PlotOffset = 25,

    Header = "Date",

    LabelFormat = "MMM/dd",

    ZoomPosition = rangeNavigator.ZoomPosition,

    ZoomFactor = rangeNavigator.ZoomFactor

};

chart.SecondaryAxis = new NumericalAxis()
{

    Minimum = 820,

    Interval = 20,

    Maximum = 900,

    FontSize = 12,

    StartRangeFromZero = false,

    Header = "Stock Price"

};

CandleSeries candleSeries=new CandleSeries ()
{

    ItemsSource = new ViewModel().StockPriceDetails,

    High ="High", Low = "Low",

    Open ="Open", Close ="Close",

    XBindingPath ="Date",

    Label ="CandleSeries"

};

chart.Series.Add(candleSeries);

{% endhighlight %}

{% endtabs %}

* [`SelectedData`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfDateTimeRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfDateTimeRangeNavigator_SelectedData)- Gets an IEnumerable source for the particular selected region.

Displays the selected data alone from the SfDateTimeRangeNavigator, into the chart.

{% tabs %}

{% highlight xaml %}

<chart:SfChart VerticalAlignment="Bottom" AreaBorderThickness="0,1,1,1" 
               Height="200" 
               Width="700" x:Name="financialChart" Grid.Row="0">

<chart:SfChart.Header>

<TextBlock FontSize="14"   Foreground="Black" FontFamily="Segoe UI"
           Margin="0,0,0,20">USD - INR Foreign  Exchange Rate Analysis</TextBlock>

</chart:SfChart.Header>

<chart:SfChart.PrimaryAxis>

<chart:CategoryAxis Name="axis1" PlotOffset="25"  FontSize="12"                              
                   Header="Date" LabelFormat="MMM/dd" />                           

</chart:SfChart.PrimaryAxis>

<chart:SfChart.SecondaryAxis>

<chart:NumericalAxis Minimum="820" Interval="20" 
                   Maximum="900"  FontSize="12"                     
                   StartRangeFromZero="False" x:Name="axis2" 
                   Header="Stock Price" />                                   

</chart:SfChart.SecondaryAxis>

<chart:CandleSeries Name="series" ItemsSource="{Binding
                   ElementName=RangeNavigator, Path=SelectedData}" 
                   XBindingPath="Date"  High="High" Open="Open" 
                   Close="Close" Low="Low"  Label="CandleSeries">

</chart:CandleSeries>

</chart:SfChart>

<Grid Grid.Row="1" >

<chart:SfDateTimeRangeNavigator x:Name="RangeNavigator" Width="700"
            Height="130" XBindingPath="Date"  VerticalAlignment="Top"
            ItemsSource="{Binding StockPriceDetails}">                              
                                             

<chart:SfDateTimeRangeNavigator.Content>

<chart:SfLineSparkline ItemsSource="{Binding StockPriceDetails}"
                       YBindingPath="High" >

</chart:SfLineSparkline>

</chart:SfDateTimeRangeNavigator.Content>               

</chart:SfDateTimeRangeNavigator>       

</Grid>  

{% endhighlight %}

{% highlight c# %}

{% endhighlight %}

{% endtabs %}

The following output is displayed as the result of above code sample.

![Bound SelectedData](Interactivity_images/Interactivity_img2.jpeg)


The following are the properties used to provide interactive features.

* [`ShowGridLines`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfDateTimeRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfDateTimeRangeNavigator_ShowGridLines)- Gets or sets a value that indicates whether to show grid lines inside the content.
* [`RangePadding`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfDateTimeRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfDateTimeRangeNavigator_RangePadding)- Gets or sets value which is used to shift the SfDateTimeRangeNavigator axis range inside or outside.
* [`OverlayBrush`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfRangeNavigator_OverlayBrush)- Gets or sets the overlay brush color.

{% tabs %}

{% highlight xaml %}

<chart:SfDateTimeRangeNavigator x:Name="RangeNavigator"  ShowGridLines="True"
                                XBindingPath="Date" OverlayBrush="#5534b4e3" >                                                                               
</chart:SfDateTimeRangeNavigator>

{% endhighlight %}

{% highlight c# %}

SfDateTimeRangeNavigator rangeNavigator = new SfDateTimeRangeNavigator()
{

    ItemsSource = new ViewModel().StockPriceDetails,

    XBindingPath = "Date",

    ShowGridLines = true,

    OverlayBrush = new SolidColorBrush(Color.FromArgb(55,34,0xb4,0xe3))

};

{% endhighlight %}

{% endtabs %}

![Interactive feature support for DateTimeRangeNavigator](Interactivity_images/Interactivity_img3.jpeg)


## Resizable Scrollbar

SfDateTimeRangeNavigator provides interactive features such as zooming, panning. The navigator has a resizable scrollbar which is used to zoom in large amount of data and also helps to navigate to particular timespan by moving the scrollbar.

* [`EnableDeferredUpdate`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfDateTimeRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfDateTimeRangeNavigator_EnableDeferredUpdate)- Gets or sets a value that indicates whether to defer the ValueChanged notification.
* [`ScrollbarVisibility`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfRangeNavigator_ScrollbarVisibility) – Gets or sets bool value whether enable or disable the scrollbar.
* [`DeferredUpdateDelay`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfDateTimeRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfDateTimeRangeNavigator_DeferredUpdateDelay) - Gets or sets the delay value, when EnableDeferredUpdate is enabled.

![interactive](Interactivity_images/Interactivity_img4.jpeg)


## Events

<table>
<tr>
<td>
Event<br/><br/></td><td>
Parameters<br/><br/></td><td>
Description<br/><br/></td></tr>
<tr>
<td>
{{'[`ValueChanged`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfRangeNavigator.html)'| markdownify }}<br/><br/></td><td>
ValueChanged(Object sender, EventArgs e)<br/><br/></td><td>
This event is triggered when the position of the scrollbar changed.<br/><br/></td></tr>
<tr>
<td>
`LowerBarLabelsCreated`<br/><br/></td><td>
LowerBarLabelsCreated(Object sender, LowerBarLabelsCreatedEventArgs e)<br/><br/></td><td>
This event is triggered when the lower bar labels gets created.<br/><br/></td></tr>
<tr>
<td>
`UpperBarLabelsCreated`<br/><br/></td><td>
UpperBarLabelsCreated(Object sender, UpperBarLabelsCreatedEventArgs e)<br/><br/></td><td>
This event is triggered when the upper bar labels gets created.<br/><br/></td></tr>
</table>
