---
layout: post
title: Axis | SfChart | uwp | Syncfusion
description: axis
platform: uwp
control: SfChart
documentation: ug
---

# Axis

ChartAxis is used to locate a data point inside the chart area. Generally, to locate a data point, you require two axes, along each direction, that is, horizontal and vertical, in a chart. The vertical axis, or y-axis, usually represents numerical values .The horizontal axis, or x-axis, represents categorical or numerical or date and time values. ChartAxis supports the following types.

* Double                

* DateTime(Linear)

* DateTime(Category)

* String

* TimeSpan

* Logarithmic

You can choose any ChartAxis derived types, like DateTimeAxis, NumericalAxis, CategoryAxis, LogarithmicAxis or TimeSpanAxis depending on the value type. DateTimeCategoryAxis is a special type, used to plot date and time values for the given datapoints. 

## NumericAxis

NumericalAxis is used to plot numerical value to the chart. You can set NumericalAxis for both PrimaryAxis and SecondaryAxis.

The following APIs are used to customize NumericalAxis.

Properties

<table>
<tr>
<th>
Property</th><th>
Definition</th></tr>
<tr>
<td>
Interval</td><td>
Gets or sets the double that represents the interval between the labels.</td></tr>
<tr>
<td>
Minimum</td><td>
Gets or sets the double that represents the Minimum value for the Axis.</td></tr>
<tr>
<td>
Maximum</td><td>
Gets or sets the double that represents the Maximum value for the Axis.</td></tr>
<tr>
<td>
RangePadding</td><td>
Gets or sets the NumericalPadding that specifies how to render the segments in chart area.</td></tr>
<tr>
<td>
StartRangeFromZero</td><td>
Gets or sets the bool that represents a value to enable start the range from zero. </td></tr>
</table>

{% tabs %}
 
{% highlight xml %}

<syncfusion:SfChart x:Name="Chart"   Margin="5,0,10,0">

            <syncfusion:SfChart.DataContext>

                <local:ViewModel/>

            </syncfusion:SfChart.DataContext>

            <syncfusion:SfChart.PrimaryAxis>

                <syncfusion:CategoryAxis   Header="Company Name"/>

            </syncfusion:SfChart.PrimaryAxis>

            <syncfusion:SfChart.SecondaryAxis>

                <syncfusion:NumericalAxis Interval="100" Minimum="0" Maximum="1000" RangePadding="Round"   Header="Gross Revenue "/>

            </syncfusion:SfChart.SecondaryAxis>



            <syncfusion:ColumnSeries x:Name="series1" Label="Company Details"   XBindingPath="CompanyName" YBindingPath="CompanyTurnOver"   ItemsSource="{Binding CompanyDetails}">

            </syncfusion:ColumnSeries>

        </syncfusion:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();

chart.Margin = new Thickness(5, 0, 10, 0);

chart.DataContext = new ViewModel();

chart.PrimaryAxis = new CategoryAxis() { Header = "Company Name" };

chart.SecondaryAxis = new NumericalAxis()
{

    Header = "Gross Revenue",

    Minimum = 0,

    Maximum = 1000,

    Interval = 100,

    RangePadding = NumericalPadding.Round

};

ColumnSeries series = new ColumnSeries()
{

    ItemsSource = new ViewModel().CompanyDetails,

    XBindingPath = "CompanyName",

    YBindingPath = "CompanyTurnOver"

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![](Axis_images/Axis_img1.png)



## CategoryAxis

CategoryAxis is an index based axis that plots values based on the index of the data point collection. The points are equally spaced here.

The following APIs are used in CategoryAxis.

CategoryAxis

<table>
<tr>
<th>
Property</th><th>
Definition</th></tr>
<tr>
<td>
Interval</td><td>
Gets or sets the double value that represents the interval between the labels.</td></tr>
<tr>
<td>
LabelPlacement</td><td>
Gets or sets the LabelPlacement that represents the position of the label in the axis.</td></tr>
</table>

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart x:Name="Chart"   Margin="5,0,10,0">

                <syncfusion:SfChart.DataContext>

                    <local:ViewModel/>

                </syncfusion:SfChart.DataContext>



                <syncfusion:SfChart.PrimaryAxis>

                    <syncfusion:CategoryAxis   Header="Company Name"/>

                </syncfusion:SfChart.PrimaryAxis>



                <syncfusion:SfChart.SecondaryAxis>

                    <syncfusion:NumericalAxis Interval="10" Minimum="200" Maximum="400" RangePadding="Round"   Header="Gross Revenue "/>

                </syncfusion:SfChart.SecondaryAxis>



                <syncfusion:ColumnSeries x:Name="series1" Label="Company Details"   XBindingPath="CompanyName" YBindingPath="CompanyTurnOver"   ItemsSource="{Binding CompanyDetails}">

                </syncfusion:ColumnSeries>



            </syncfusion:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();

chart.Margin = new Thickness(5, 0, 10, 0);

chart.DataContext = new ViewModel();

chart.PrimaryAxis = new CategoryAxis() { Header = "Company Name" };

chart.SecondaryAxis = new NumericalAxis()
{

    Header = "Gross Revenue",

    Minimum = 200,

    Maximum = 400,

    Interval = 10,

    RangePadding = NumericalPadding.Round

};

ColumnSeries series = new ColumnSeries()
{

    ItemsSource = new ViewModel().CompanyDetails,

    XBindingPath = "CompanyName",

    YBindingPath = "CompanyTurnOver"

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![](Axis_images/Axis_img2.png)


## DateTimeAxis

DateTimeAxis is used to plot DateTime values. The DateTimeAxis is widely used to make financial charts in places like the Stock Market, where index plotting is done everyday.

The following APIs are used for customizing DateTimeAxis.

DateTimeAxis

<table>
<tr>
<th>
Property</th><th>
Definition</th></tr>
<tr>
<td>
Minimum</td><td>
Gets or sets the DateTime value that represents a minimum value of the Axis.</td></tr>
<tr>
<td>
Maximum</td><td>
Gets or sets the DateTime value that represents a maximum value of the Axis.</td></tr>
<tr>
<td>
RangePadding</td><td>
Gets or sets the DateTimeRangePadding value that specifies segment arrangement in the chart area.</td></tr>
<tr>
<td>
Interval</td><td>
Gets or sets the double value as the interval between labels.</td></tr>
<tr>
<td>
IntervalType</td><td>
Gets or sets the DateTimeIntervalType. It represents the type of the interval. This property is used to define the type of interval to be displayed and considered for plotting the series.</td></tr>
<tr>
<td>
EnableBusinessHours</td><td>
Gets or sets the bool value that represents a value to enable business hours.</td></tr>
<tr>
<td>
OpenTime</td><td>
Gets or sets the double value that represents the open working time of a day.</td></tr>
<tr>
<td>
CloseTime</td><td>
Gets or sets the double value that represents the close working time of a day.</td></tr>
<tr>
<td>
WorkingDays</td><td>
Gets or sets the double value that represents the working days of a week.</td></tr>
</table>

### DateTimeIntervalType

The DateTime interval corresponds to the type specified in the IntervalType property.

For instance, if the Interval is set as 2 and IntervalType is set as Days, the labels are plotted for every two days. The following are the values for IntervalType property:

* Auto
* Days
* Hours
* Milliseconds
* Minutes 
* Months
* Seconds
* Years



The default IntervalType of a DateTimeAxis is Auto. It calculates the type automatically and the interval, accordingly.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.PrimaryAxis>

                <syncfusion:DateTimeAxis Name="Primary" 

                                    IntervalType="Years" Interval="1" />

            </syncfusion:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new DateTimeAxis()
{

    IntervalType = DateTimeIntervalType.Years,

    Interval = 1

};

{% endhighlight %}

{% endtabs %}

The following code example and screenshot are for DateTimeAxis.

{% tabs %}

{% highlight xml %}

  <syncfusion:SfChart x:Name="Chart"   Margin="5,0,10,0">

            <syncfusion:SfChart.DataContext>

                <local:ViewModel/>

            </syncfusion:SfChart.DataContext>



            <syncfusion:SfChart.PrimaryAxis>

                <syncfusion:DateTimeAxis Interval="1" LabelFormat="yyyy" IntervalType="Years”/>

            </syncfusion:SfChart.PrimaryAxis>



            <syncfusion:SfChart.SecondaryAxis>

                <syncfusion:NumericalAxis />

            </syncfusion:SfChart.SecondaryAxis>



            <syncfusion:LineSeries x:Name="series1" Label="Company Details"   XBindingPath="Year" YBindingPath="CompanyTurnOver"  ItemsSource="{Binding CompanyDetails}">

            </syncfusion:LineSeries>

        </syncfusion:SfChart>

{% endhighlight %}

{% highlight c# %}

chart.Margin = new Thickness(5, 0, 10, 0);

chart.DataContext = new ViewModel();

chart.PrimaryAxis = new DateTimeAxis()
{

    IntervalType = DateTimeIntervalType.Years,

    Interval = 1,

    LabelFormat = "yyyy"

};

chart.SecondaryAxis = new NumericalAxis();

ColumnSeries series = new ColumnSeries()
{

    ItemsSource = new ViewModel().CompanyDetails,

    XBindingPath = "Year",

    YBindingPath = "CompanyTurnOver"

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![](Axis_images/Axis_img3.png)



## DateTimeCategoryAxis

DateTimeCategoryAxis is a special type of axis used mainly with financial series. All the data points are plotted with equal spaces, similar to CategoryAxis, thereby removing space for missing dates. Intervals and range for the axis are calculated similar to DateTimeAxis. There are no visual gaps between points, even when the difference between two points is more than a year.

DateTimeCategoryAxis

<table>
<tr>
<th>
Property</th><th>
Definition</th></tr>
<tr>
<td>
Interval</td><td>
Gets or sets the double value that represents the interval between the labels.</td></tr>
<tr>
<td>
IntervalType</td><td>
Gets or sets the DateTimeIntervalType that represents the type of the interval.</td></tr>
</table>

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart x:Name="Chart"   Margin="5,0,10,0">

            <syncfusion:SfChart.DataContext>

                <local:ViewModel/>

            </syncfusion:SfChart.DataContext>



            <syncfusion:SfChart.PrimaryAxis>

                <syncfusion:DateTimeCategoryAxis Interval="1" LabelFormat="yyyy" IntervalType="Years"  Header="Company Name"/>

            </syncfusion:SfChart.PrimaryAxis>



            <syncfusion:SfChart.SecondaryAxis>

                <syncfusion:NumericalAxis   Header="Gross Revenue (cr.)"/>

            </syncfusion:SfChart.SecondaryAxis>



            <syncfusion:LineSeries x:Name="series1" Label="Company Details"   XBindingPath="Year" YBindingPath="CompanyTurnOver"   ItemsSource="{Binding CompanyDetails}">

            </syncfusion:LineSeries>



        </syncfusion:SfChart>

{% endhighlight %}

{% highlight c# %}

chart.Margin = new Thickness(5, 0, 10, 0);

chart.DataContext = new ViewModel();

chart.PrimaryAxis = new DateTimeCategoryAxis()
{

    IntervalType = DateTimeIntervalType.Years,

    Interval = 1,

    LabelFormat = "yyyy",

    Header = "Company Name"

};

chart.SecondaryAxis = new NumericalAxis()
{
    Header="Gross Revenue (cr.)"
};

ColumnSeries series = new ColumnSeries()
{

    ItemsSource = new ViewModel().CompanyDetails,

    XBindingPath = "Year",

    YBindingPath = "CompanyTurnOver"

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![](Axis_images/Axis_img4.png)



## TimeSpanAxis

TimeSpanAxis is used to plot the time span values in the PrimaryAxis. TimeSpanAxis has the advantage of plotting data with milliseconds difference. The limitation of TimeSpanAxis is that it can only accept timespan values (hh:mm:ss) and datetime values are not accepted.

The following APIs are used in TimeSpanAxis.

TimeSpanAxis

<table>
<tr>
<th>
Property</th><th>
Definition</th></tr>
<tr>
<td>
Interval</td><td>
Gets or sets the double value that represents the interval between the labels.</td></tr>
<tr>
<td>
Minimum</td><td>
Gets or sets the timespan value that represents the minimum value for the Axis.</td></tr>
<tr>
<td>
Maximum</td><td>
Gets or sets the timespan value that represents the maximum value for the Axis. </td></tr>
</table>

{% tabs %}

{% highlight xml %}

 <syncfusion:SfChart x:Name="Chart"   Margin="5,0,10,0">

            <syncfusion:SfChart.DataContext>

                <local:ViewModel/>

            </syncfusion:SfChart.DataContext>



            <syncfusion:SfChart.PrimaryAxis>

                <syncfusion:TimeSpanAxis Interval="00:00:01" Header="Company Name"/>

            </syncfusion:SfChart.PrimaryAxis>



            <syncfusion:SfChart.SecondaryAxis>

                <syncfusion:NumericalAxis   Header="Gross Revenue (cr.)"/>

            </syncfusion:SfChart.SecondaryAxis>

            <syncfusion:LineSeries x:Name="series1" Label="Company Details"   XBindingPath="Year" YBindingPath="CompanyTurnOver"  ItemsSource="{Binding CompanyDetails}">

            </syncfusion:LineSeries>

        </syncfusion:SfChart>

{% endhighlight %}

{% highlight c# %}

chart.Margin = new Thickness(5, 0, 10, 0);

chart.DataContext = new ViewModel();

chart.PrimaryAxis = new TimeSpanAxis()
{

    Interval = new TimeSpan(00, 00, 01),

    Header = "Company Name"

};


chart.SecondaryAxis = new NumericalAxis()
{
    Header="Gross Revenue (cr.)"
};

ColumnSeries series = new ColumnSeries()
{

    ItemsSource = new ViewModel().CompanyDetails,

    XBindingPath = "Year",

    YBindingPath = "CompanyTurnOver"

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![](Axis_images/Axis_img5.png)



## LogarithmicAxis

LogarithmicAxis is used to plot the logarithmic scale for the chart. In order to plot the logarithmic scale, you must specify the base value using LogarithmicBase Property.

The following APIs are used to customize the LogarithmicAxis.

LogarithmicAxis

<table>
<tr>
<th>
Property</th><th>
Definition</th></tr>
<tr>
<td>
Interval</td><td>
Gets or sets the double value that represents the interval between the labels</td></tr>
<tr>
<td>
Minimum</td><td>
Gets or sets the double value that represents the minimum value for the Axis.</td></tr>
<tr>
<td>
Maximum</td><td>
Gets or sets the double value that represents the maximum value of the Axis. </td></tr>
<tr>
<td>
LogarithmicBase</td><td>
Gets or sets the double value that represents the logarithmic base value of the Axis.</td></tr>
</table>

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart x:Name="Chart"   Margin="5,0,10,0">

            <syncfusion:SfChart.DataContext>

                <local:ViewModel/>

            </syncfusion:SfChart.DataContext>



            <syncfusion:SfChart.PrimaryAxis>

                <syncfusion:CategoryAxis   Header="Company Name"/>

            </syncfusion:SfChart.PrimaryAxis>



            <syncfusion:SfChart.SecondaryAxis>

                <syncfusion:LogarithmicAxis LogarithmicBase="10"   Header="Gross Revenue (cr.)"/>

            </syncfusion:SfChart.SecondaryAxis>

            <syncfusion:LineSeries x:Name="series1" Label="Company Details"   XBindingPath="CompanyName" YBindingPath="CompanyTurnOver"   ItemsSource="{Binding CompanyDetails}">

            </syncfusion:LineSeries>



        </syncfusion:SfChart>

{% endhighlight %}

{% highlight c# %}

chart.Margin = new Thickness(5, 0, 10, 0);

chart.DataContext = new ViewModel();

chart.PrimaryAxis = new CategoryAxis()
{

    Header = "Company Name"

};

chart.SecondaryAxis = new LogarithmicAxis()
{

    Header = "Gross Revenue",

    LogarithmicBase = 10

};

ColumnSeries series = new ColumnSeries()
{

    ItemsSource = new ViewModel().CompanyDetails,

    XBindingPath = "Year",

    YBindingPath = "CompanyTurnOver"

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

Logarithmic Axis does not support zero or negative values._

The following screenshot illustrates the SfChart with LogarithmicAxis.

![](Axis_images/Axis_img6.png)



## Multiple Axes

SfChart provides a way to arrange multiple series inside the same chart area, giving the chart more space than x-axis and y-axis.These axes can be arranged in a stack or in a side by side pattern. 

By default, all the series are plotted based on Primary and Secondary Axis. You can add more axes by adding additional axis to the series. There are two properties XAxis and YAxis in all the series, except Accumulation Series.

{% tabs %}

{% highlight xml %}


 <syncfusion:ColumnSeries Label="2010" 

     ItemsSource="{Binding Demands}"

     XBindingPath="Demand"

     YBindingPath="Year2010"

     Interior="Green"

     

            <syncfusion:ColumnSeries.XAxis>

                <syncfusion:NumericalAxis Header="Additional X Axis"/>

            </syncfusion:ColumnSeries.XAxis>



            <syncfusion:ColumnSeries.YAxis>

                <syncfusion:NumericalAxis Header="Additional Y Axis"/>

            </syncfusion:ColumnSeries.YAxis>



        </syncfusion:ColumnSeries>



        <syncfusion:LineSeries Label="2011" 

    ItemsSource="{Binding Demands}"

    XBindingPath="Demand"

    YBindingPath="Year2011"

    Interior="Black"

    StrokeThickness="2"/>


{% endhighlight %}

{% highlight c# %}

ColumnSeries series1 = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    Label ="2010",

    Interior = new SolidColorBrush(Colors.Green)

};

series1.XAxis = new NumericalAxis()
{

    Header = "Additional X Axis"

};

series1.YAxis = new NumericalAxis()
{

    Header = "Additional Y Axis"

};

LineSeries series2 = new LineSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2011",

    Label = "2011",

    Interior = new SolidColorBrush(Colors.Black),

    StrokeThickness = 2

};

chart.Series.Add(series1);

chart.Series.Add(series2);

{% endhighlight %}

{% endtabs %}

The following screenshot illustrates SfChart with multiple axes.

![C:/Users/rachel/Desktop/snaps/6.png](Axis_images/Axis_img7.png)



 The first series is plotting based on additional X & Y axis and second series (or remaining series) is plotting against the Primary and Secondary axis.

### Axis Positioning

By default, the x-axis is arranged horizontally at the bottom of the chart and the y-axis is arranged vertically on the left-side of the chart. You can change the alignment of the axes by setting OpposedPosition to True. It arranges the x-axis at the top and the y-axis on the right-side of the chart. 

The following is the code example for setting the OpposedPosition property.

{% tabs %}

{% highlight xml %}



<syncfusion:ColumnSeries.XAxis>

            <syncfusion:NumericalAxis Header="Additional X Axis" OpposedPosition="True"/>

        </syncfusion:ColumnSeries.XAxis>



        <syncfusion:ColumnSeries.YAxis>

            <syncfusion:NumericalAxis Header="Additional Y Axis" OpposedPosition="True"/>

        </syncfusion:ColumnSeries.YAxis>
		
{% endhighlight %}

{% highlight c# %}

columnSeries.XAxis = new NumericalAxis()
{

    Header = "Additional X Axis",

    OpposedPosition = true

};

columnSeries.YAxis = new NumericalAxis()
{

    Header = "Additional Y Axis",

    OpposedPosition = true

};

{% endhighlight %}

{% endtabs %}

The following is a screenshot demonstrating y-axis of a chart arranged in OpposedPosition.

![C:/Users/rachel/Desktop/snaps/7.png](Axis_images/Axis_img8.png)



## Inversed Axis

This feature is used to reverse chart plotting inverse the axis scaling.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.PrimaryAxis>

                <syncfusion:CategoryAxis   FontSize="16" IsInversed="True" OpposedPosition="True" />

            </ syncfusion:SfChart.PrimaryAxis>



            <syncfusion:SfChart.SecondaryAxis>

                <syncfusion:NumericalAxis FontSize="16" Minimum="0" Maximum="2000" Interval=”200” IsInversed="True" OpposedPosition="True" />

            </syncfusion:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis()
{

    FontSize = 16,

    OpposedPosition = true,

    IsInversed = true

};

chart.SecondaryAxis = new NumericalAxis()
{

    FontSize = 16,

    Minimum = 0,

    Maximum = 2000,

    Interval = 200,

    IsInversed = true,

    OpposedPosition = true

};

{% endhighlight %}

{% endtabs %}

![C:/Users/rachel/Desktop/snaps/8.png](Axis_images/Axis_img9.png)



## Axis range and Interval

ChartAxis calculates the range and intervals automatically based on the values of series data points. You can also explicitly specify the range and interval using the Minimum, Maximum and Interval properties. 

T> You cannot specify range for CategoryAxis instead you can use ZoomFactor and ZoomPosition.



 You can force the NumericalAxis to start range from zero by enabling StartRangeFromZero. The following is the code example for setting the ChartAxis properties.

 The following is the code sample for setting the ChartAxis properties:

 {% tabs %}

{% highlight xml %}

<syncfusion:SfChart.PrimaryAxis>

                <syncfusion:CategoryAxis FontSize="14"/>

            </syncfusion:SfChart.PrimaryAxis>



            <syncfusion:SfChart.SecondaryAxis>

                <syncfusion:NumericalAxis FontSize="14"/>

            </syncfusion:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis()
{

    FontSize = 14

};

chart.SecondaryAxis = new NumericalAxis()
{

    FontSize = 14
};

{% endhighlight %}

{% endtabs %}

### Range Padding

The NumericalAxis and DateTimeAxis have a RangePadding property that can be used to add padding to the range of a chart's axes.

### NumericalAxis RangePadding

The following types are available for NumericalAxis: 

* Additional
* None
* Normal
* Round

By default, the default RangePadding value for PrimaryAxis is Auto and for SecondaryAxis, the default value is Round.

![](Axis_images/Axis_img10.png)



The following screenshot demonstrates RangePadding as None, where no padding is applied for the axis.

![](Axis_images/Axis_img11.png)



Normal RangePadding for a NumericalAxis is used mostly for the y-axis to have padding based on the Range calculation.

The following screenshot illustrates a chart’s y-axis with RangePadding set to Normal.

![](Axis_images/Axis_img12.png)



Round RangePadding for a NumericalAxis rounds the range of the chart axis to the nearest possible value.

The following screenshot demonstrates a chart’s x-axis with RangePadding set to Round.

![](Axis_images/Axis_img13.png)



If RangePadding for NumericalAxis is set to Additional, the interval of the axis is added as padding.

The following screenshot demonstrates a chart’s x-axis with RangePadding set to Additional.

![](Axis_images/Axis_img14.png)



### DateTimeAxis RangePadding

The RangePadding types available in the DateTimeAxis are: 

* Additional
* None
* Round

By default, the RangePadding for a DateTimeAxis is None.

The following screenshot demonstrates a chart’s x-axis with RangePadding set to None. 

![](Axis_images/Axis_img15.png)



When RangePadding for DateTimeAxis is set to Additional, the DateTime interval of the axis is added as padding, as shown in the following screenshot.

![](Axis_images/Axis_img16.png)



When RangePadding for DateTimeAxis is set to Round, the range of the chart axis is rounded off to the nearest possible DateTime value, as shown in the following screenshot.

![](Axis_images/Axis_img17.png)



## Positioning axis labels

### Label Placement

The CategoryAxis includes the LabelPlacement property, used to set the labels of the axis between the tick lines or on the tick lines of the category axis. By default the LabelPlacement value for the CategoryAxis is OnTicks.

There are two types of LabelPlacement:

* BetweenTicks
* OnTicks

The following code example and screenshot shows LabelPlacement set to OnTicks.

{% tabs %}

{% highlight xml %}

  <syncfusion:SfChart.PrimaryAxis>

     <syncfusion:CategoryAxis LabelPlacement="OnTicks" 

         FontSize="16"  />

 </syncfusion:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis()
{

    FontSize = 16,

    LabelPlacement = LabelPlacement.OnTicks

};

{% endhighlight %}

{% endtabs %}

![](Axis_images/Axis_img18.png)



The following code example and screenshot shows LabelPlacement set to BetweenTicks.

{% tabs %}

{% highlight xml %}

  <syncfusion:SfChart.PrimaryAxis>

    <syncfusion:CategoryAxis LabelPlacement="BetweenTicks" 

           FontSize="16"  />

    </syncfusion:SfChart.PrimaryAxis>


{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis()
{

    FontSize = 16,

    LabelPlacement = LabelPlacement.BetweenTicks

};

{% endhighlight %}

{% endtabs %}


![](Axis_images/Axis_img19.png)



### Label Position 

The LabelsPosition property is used to position the axis label either inside or outside the chart plotting area.

The following code example and screenshot illustrate the use of LabelsPosition.

{% tabs %}

{% highlight xml %}

  <syncfusion:SfChart.PrimaryAxis>

    <syncfusion:CategoryAxis  LabelsPosition="Inside" 

           FontSize="16"  />

    </syncfusion:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis()
{

    FontSize = 16,

    LabelsPosition = AxisElementPosition.Inside

};

{% endhighlight %}

{% endtabs %}

![](Axis_images/Axis_img20.png)

{% tabs %}

{% highlight xml %}

  <syncfusion:SfChart.PrimaryAxis>

    <syncfusion:CategoryAxis  LabelsPosition="Outside" 

           FontSize="16"  />

    </syncfusion:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis()
{

    FontSize = 16,

    LabelsPosition = AxisElementPosition.Outside

};

{% endhighlight %}

{% endtabs %}


![](Axis_images/Axis_img21.png)



### Positioning Edge Labels

SfChart provides support to customize the edge labels of the axis to adjust its position using the EdgeLabelDrawingMode property. 

The following are the customizing options in EdgeLabelDrawingMode.

* Center- Positions the label with tickline as center.
* Fit- Position the gridline inside based on the edge label size.
* Hide- Hides the edge labels.
* Shift- Shifts the edge labels inside to label width.



The following code example and screenshot show EdgeLabelsDrawingMode set to Center.

{% tabs %}

{% highlight xml %}

  <syncfusion:SfChart.PrimaryAxis>

  <syncfusion:DateTimeAxis    LabelFormat="MM/yy" EdgeLabelsDrawingMode="Center" FontSize="16"  />

    </syncfusion:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis()
{

    FontSize = 16,

    LabelFormat = "MM/yy",

    EdgeLabelsDrawingMode = EdgeLabelsDrawingMode.Center

};

{% endhighlight %}

{% endtabs %}

![](Axis_images/Axis_img22.png)



The following code example and screenshot shows EdgeLabelsDrawingMode set to Fit.

{% tabs %}

{% highlight xml %}

  <syncfusion:SfChart.PrimaryAxis>

  <syncfusion:DateTimeAxis    LabelFormat="MM/yy" EdgeLabelsDrawingMode="Fit" FontSize="16"  />

    </syncfusion:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis()
{

    FontSize = 16,

    LabelFormat = "MM/yy",

    EdgeLabelsDrawingMode = EdgeLabelsDrawingMode.Fit

};

{% endhighlight %}

{% endtabs %}

![](Axis_images/Axis_img23.png)



The following code example and screenshot shows EdgeLabelDrawingMode set to Hide.

{% tabs %}

{% highlight xml %}

  <syncfusion:SfChart.PrimaryAxis>

  <syncfusion:DateTimeAxis    LabelFormat="MM/yy" EdgeLabelsDrawingMode="Hide" FontSize="16"  />

    </syncfusion:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis()
{

    FontSize = 16,

    LabelFormat = "MM/yy",

    EdgeLabelsDrawingMode = EdgeLabelsDrawingMode.Hide

};

{% endhighlight %}

{% endtabs %}

![](Axis_images/Axis_img24.png)



The following code example and screenshot shows EdgeLabelsDrawingMode set to Shift.

{% tabs %}

{% highlight xml %}

  <syncfusion:SfChart.PrimaryAxis>

  <syncfusion:DateTimeAxis    LabelFormat="MM/yy" EdgeLabelsDrawingMode="Shift" FontSize="16"  />

    </syncfusion:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis()
{

    FontSize = 16,

    LabelFormat = "MM/yy",

    EdgeLabelsDrawingMode = EdgeLabelsDrawingMode.Shift

};

{% endhighlight %}

{% endtabs %}

![](Axis_images/Axis_img25.png)



## Smart Labels

When a number of axis labels exist, they may overlap with each other. SfChart provides features to handle the overlapping labels using the LabelsIntersectAction property.

The following are the options for intersecting action.

* None
* Hide
* MultipleRows



The following code example and screenshot shows LabelsIntersectAction set to None.

{% tabs %}

{% highlight xml %}

  <syncfusion:SfChart.PrimaryAxis>

    <syncfusion:DateTimeAxis   LabelsIntersectAction="None"  

           FontSize="16"  />

    </syncfusion:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis()
{

    FontSize = 16,

    LabelsIntersectAction = AxisLabelsIntersectAction.None

};

{% endhighlight %}

{% endtabs %}

![](Axis_images/Axis_img26.png)



The following code example and screenshot shows LabelsIntersectAction set to Hide.

{% tabs %}

{% highlight xml %}

  <syncfusion:SfChart.PrimaryAxis>

    <syncfusion:DateTimeAxis   LabelsIntersectAction="Hide"  

           FontSize="16"  />

    </syncfusion:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis()
{

    FontSize = 16,

    LabelsIntersectAction = AxisLabelsIntersectAction.Hide

};

{% endhighlight %}

{% endtabs %}

![](Axis_images/Axis_img27.png)



The following code example and screenshot show LabelsIntersectAction set to MultipleRows.

{% tabs %}

{% highlight xml %}



  <syncfusion:SfChart.PrimaryAxis>

    <syncfusion:DateTimeAxis   LabelsIntersectAction="MultipleRows"  

           FontSize="16"  />

    </syncfusion:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis()
{

    FontSize = 16,

    LabelsIntersectAction = AxisLabelsIntersectAction.MultipleRows

};

{% endhighlight %}

{% endtabs %}

![](Axis_images/Axis_img28.png)



## Add units to labels

You can customize the axis label to display its measuring units by adding a prefix or a suffix. This feature can be achieved using the PrefixLabelTemplate and PostfixLabelTemplate properties.

The following code example and screenshot demonstrate the usage of PrefixLabelTemplate.

{% tabs %}

{% highlight xml %}

  <DataTemplate x:Key="yPrefix">

     <TextBlock FontSize="15" VerticalAlignment="Center" Text="$"/>

  </DataTemplate>

<syncfusion:SfChart.SecondaryAxis>

       <syncfusion:NumericalAxis FontSize="16" Minimum="0" Maximum="1000" PrefixLabelTemplate="{StaticResource yPrefix}" />

</syncfusion:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.SecondaryAxis = new NumericalAxis()
{

    FontSize = 16,

    Minimum = 0,

    Maximum = 1000,

    PrefixLabelTemplate = this.Resources["yPrefix"] as DataTemplate

};

{% endhighlight %}

{% endtabs %}

![](Axis_images/Axis_img29.png)



The following code example and screenshot demonstrate the usage of PostfixLabelTemplate.

{% tabs %}

{% highlight xml %}

  <DataTemplate x:Key="yPostfix">

       <TextBlock FontSize="8" VerticalAlignment="Top" Text="0"/>

 </DataTemplate>

<chart:SfChart.SecondaryAxis>

       <chart:NumericalAxis FontSize="16" Minimum="0" Maximum="100" PostfixLabelTemplate="{StaticResource yPostfix}" />

</chart:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.SecondaryAxis = new NumericalAxis()
{

    FontSize = 16,

    Minimum = 0,

    Maximum = 1000,

    PostfixLabelTemplate = this.Resources["yPrefix"] as DataTemplate

};

{% endhighlight %}

{% endtabs %}

![](Axis_images/Axis_img30.png)



## Formatting axis labels

SfChart provides the LabelFormat property for defining the custom formatting for the axis labels. This property supports all standard formatting type of numerical and date time values.

{% tabs %}

{% highlight xml %}

 <syncfusion:SfChart.PrimaryAxis>

      <syncfusion:DateTimeAxis LabelFormat="hh:mm tt" IntervalType="Hours" Interval="1" Header="Computer sales" />

</syncfusion:SfChart.PrimaryAxis>



<syncfusion:SfChart.SecondaryAxis>

      <syncfusion:NumericalAxis Header="Quantity Sold" LabelFormat="##.00"/>

</syncfusion:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new DateTimeAxis()
{

    Header = "Computer sales",

    IntervalType = DateTimeIntervalType.Hours,

    Interval = 1,

    LabelFormat = "hh:mm:tt"

};

chart.SecondaryAxis = new NumericalAxis()
{

    Header = "Quantity Sold",

    LabelFormat ="##:00"

};

{% endhighlight %}

{% endtabs %}

![](Axis_images/Axis_img31.png)



## Styling Header and Labels

SfChart provides support to customize the axis header and label. The following APIs are used to customize the header and label.

HeaderStyle and LabelStyle

<table>
<tr>
<th>
Property</th><th>
Definition</th></tr>
<tr>
<td>
HeaderStyle</td><td>
Gets or sets the style for the axis header. The header’s Foreground, FontSize and FontFamily are customized using this property.</td></tr>
<tr>
<td>
LabelStyle</td><td>
Gets or sets the style for the axis labels. The label’s Foreground, FontSize and FontFamily are customized using this property.</td></tr>
</table>

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart Height="250" Width="500">

            < syncfusion:SfChart.PrimaryAxis>

                < syncfusion:CategoryAxis  Header="City">

                    < syncfusion:CategoryAxis.LabelStyle>

                        < syncfusion:LabelStyle FontSize="10" FontFamily="Arial" Foreground="Green" ></syncfusion:LabelStyle>

                    </syncfusion:CategoryAxis.LabelStyle>

                </syncfusion:CategoryAxis>

            </syncfusion:SfChart.PrimaryAxis>

            <syncfusion:SfChart.SecondaryAxis>

                <syncfusion:NumericalAxis x:Name="axis" Header="Year" >

                    <syncfusion:NumericalAxis.LabelStyle >

                        <syncfusion:LabelStyle FontSize="10" Foreground="Green" FontFamily="Arial" ></syncfusion:LabelStyle>

                    </syncfusion:NumericalAxis.LabelStyle>

                </syncfusion:NumericalAxis>

            </syncfusion:SfChart.SecondaryAxis>

            <syncfusion:LineSeries XBindingPath="City" YBindingPath="Year1950" ItemsSource="{Binding PopulationPercent}"></syncfusion:LineSeries>

        </syncfusion:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();

LabelStyle labelStyle;

chart.PrimaryAxis = new CategoryAxis() { Header = "City" };

labelStyle = new LabelStyle()
{

    FontSize = 10,

    FontFamily = new FontFamily("Arial"),

    Foreground = new SolidColorBrush(Colors.Green)

};

chart.PrimaryAxis.LabelStyle = labelStyle;

chart.SecondaryAxis = new NumericalAxis()
{

    Header = "Year",

};

chart.SecondaryAxis.LabelStyle = labelStyle;

LineSeries series = new LineSeries()
{

    ItemsSource = new ViewModel().PopulationPercent,

    XBindingPath = "City",

    YBindingPath = "Year1950"

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}


**Axis Label Border**

[`ChartAxis`](https://help.syncfusion.com/uwp/sfchart/axis) provides support to place border around its label.To place the border around axis, we should enable  [`ShowLabelBorder`] property of axis and it can be set as shown in the below code snippet,

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.PrimaryAxis>

<syncfusion:CategoryAxis ShowLabelBorder="True"/>

</syncfusion:SfChart.PrimaryAxis>

<syncfusion:SfChart.SecondaryAxis>

</syncfusion:NumericalAxis ShowLabelBorder="True"  />       

</syncfusion:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis()
            
{
     ShowLabelBorder = true,                
};

chart.SecondaryAxis = new NumericalAxis()

{
    ShowLabelBorder = true
};

{% endhighlight %}

{% endtabs %}

![](Axis_images/label1.png)

The border color and width can be customized with [`LabelBorderBrush`] and [`LabelBorderWidth`] properties of chart axis and it can be set as shown in the below code snippet,

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.PrimaryAxis>

<syncfusion:CategoryAxis LabelBorderWidth="3" ShowLabelBorder="True" LabelBorderBrush="Red"/>

</syncfusion:SfChart.PrimaryAxis>

<syncfusion:SfChart.SecondaryAxis>

</syncfusion:NumericalAxis ShowLabelBorder="True"  LabelBorderWidth="3" LabelBorderBrush="Red"/>       

</syncfusion:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis()
            
{
    ShowLabelBorder = true,  

    LabelBorderWidth = 3,

    LabelBorderBrush = new SolidColorBrush(Colors.Red)
           
};

chart.SecondaryAxis = new NumericalAxis()

{
       ShowLabelBorder = true,

       LabelBorderWidth = 3,

       LabelBorderBrush = new SolidColorBrush(Colors.Red),
               
};

{% endhighlight %}

{% endtabs %}

![](Axis_images/label2.png)


## GridLines and TickLines 

### GridLines

By default, gridlines are automatically added to the ChartAxis in its defined intervals. SfChart supports customization of gridline. You can control the visibility of the gridlines using the ShowGridLines property. 

The following code example and screenshot show ShowGridLines set to False.

{% tabs %}

{% highlight xml %}

  <syncfusion:SfChart.PrimaryAxis>

    <syncfusion:CategoryAxis ShowGridLines="False" 

           FontSize="16"  />

    </syncfusion:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis()
{

    ShowGridLines = false,

    FontSize = 16

};

{% endhighlight %}

{% endtabs %}

![](Axis_images/Axis_img32.png)



### Ticklines

Ticklines are small markers extending from the gridlines, used to indicate the axis scaling. Tickline can be positioned either inside or outside of the axis line.

The following code example and screenshot illustrate major and small ticklines set to Inside.

{% tabs %}

{% highlight xml %}

   <syncfusion:SfChart.PrimaryAxis>

<syncfusion:NumericalAxis LabelsPosition="Inside" TickLineSize="10" SmallTickLineSize="5" TickLinesPosition="Inside" SmallTickLinesPosition="Inside" SmallTicksPerInterval="2"  FontSize="16"  />

            </syncfusion:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new NumericalAxis()
{

    LabelsPosition = AxisElementPosition.Inside,

    TickLineSize = 10,

    SmallTickLineSize = 5,

    TickLinesPosition = AxisElementPosition.Inside,

    SmallTickLinesPosition = AxisElementPosition.Inside,

    SmallTicksPerInterval = 2,

    FontSize = 16

};

{% endhighlight %}

{% endtabs %}

![](Axis_images/Axis_img33.png)



You can customize the appearance of major gridline, minor gridlines and ticklines using the MajorTickLineStyle, MinorTickLineStyle, MajorGridLineStyle and MinorGridLineStyle properties. Also axis lines can be customized using AxisLineStyle as follows.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart>

   <syncfusion:SfChart.Resources>

                <Style x:Key="majorTickLineStyle" TargetType="Line">

                    <Setter Property="Stroke" Value="Red"/>

                    <Setter Property="StrokeThickness" Value="1"/>

                </Style>

                <Style x:Key="minorTickLineStyle" TargetType="Line">

                    <Setter Property="Stroke" Value="Green"/>

                    <Setter Property="StrokeThickness" Value="1"/>

                </Style>

                <Style x:Key="axisLineStyle" TargetType="Line">

                    <Setter Property="Stroke" Value="OrangeRed"/>

                    <Setter Property="StrokeThickness" Value="1"/>

                </Style>

                <Style x:Key="majorGridLineStyle" TargetType="Line">

                <Setter Property="Stroke" Value="Gray"/>

                <Setter Property="StrokeThickness" Value="1"/>

                    <Setter Property="StrokeDashArray" Value="4,2"/>

                 </Style>

                <Style x:Key="minorGridLineStyle" TargetType="Line">

                    <Setter Property="Stroke" Value="Gray"/>

                    <Setter Property="StrokeThickness" Value="1"/>

                    <Setter Property="StrokeDashArray" Value="1,2"/>

                </Style>

  </syncfusion:SfChart.Resources>



  <syncfusion:SfChart.PrimaryAxis>

                <syncfusion:DateTimeAxis  MajorGridLineStyle="{StaticResource majorGridLineStyle }"

                    MinorGridLineStyle="{StaticResource minorGridLineStyle}"

                    MajorTickLineStyle="{StaticResource majorTickLineStyle}"

                    MinorTickLineStyle="{StaticResource minorTickLineStyle}"

                    AxisLineStyle="{StaticResource axisLineStyle}"       

                    SmallTicksPerInterval="1" TickLineSize="10"

                    SmallTickLineSize="6" LabelFormat="yyyy"

                   />

            </syncfusion:SfChart.PrimaryAxis>

            <syncfusion:SfChart.SecondaryAxis>

                <syncfusion:NumericalAxis MajorTickLineStyle="{StaticResource majorTickLineStyle}"

                      MajorGridLineStyle="{StaticResource majorGridLineStyle }"

                      MinorGridLineStyle="{StaticResource minorGridLineStyle}"

                      MinorTickLineStyle="{StaticResource minorTickLineStyle}"

                      AxisLineStyle="{StaticResource axisLineStyle}"       

                      SmallTicksPerInterval="1" TickLineSize="10"

                      SmallTickLineSize="5" HorizontalAlignment="Right"  

            </syncfusion:SfChart.SecondaryAxis>



            <syncfusion:FastLineBitmapSeries   XBindingPath="Date" YBindingPath="Value" >

            </syncfusion:FastLineBitmapSeries>

        </syncfusion:SfChart>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new DateTimeAxis()
{

    MajorGridLineStyle = chart.Resources[" majorGridLineStyle"] as Style,

    MinorGridLineStyle = chart.Resources["minorGridLineStyle"] as Style,

    MajorTickLineStyle = chart.Resources["majorTickLineStyle"] as Style,

    MinorTickLineStyle = chart.Resources["minorTickLineStyle"] as Style,

    AxisLineStyle = chart.Resources["axisLineStyle"] as Style,

    TickLineSize = 10,

    SmallTickLineSize = 6,

    SmallTicksPerInterval = 1,

    LabelFormat = "yyyy"

};

chart.SecondaryAxis = new NumericalAxis()
{

    MajorGridLineStyle = chart.Resources[" majorGridLineStyle"] as Style,

    MinorGridLineStyle = chart.Resources["minorGridLineStyle"] as Style,

    MajorTickLineStyle = chart.Resources["majorTickLineStyle"] as Style,

    MinorTickLineStyle = chart.Resources["minorTickLineStyle"] as Style,

    AxisLineStyle = chart.Resources["axisLineStyle"] as Style,

    TickLineSize = 10,

    SmallTickLineSize = 6,

    SmallTicksPerInterval = 1,

    HorizontalAlignment = HorizontalAlignment.Center

};

FastLineBitmapSeries series = new FastLineBitmapSeries()
{

    ItemsSource = new ViewModel().Data,

    XBindingPath = "Date",

    YBindingPath = "Value"

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![](Axis_images/Axis_img34.png)



## Multi-level Labels

[`Axis`](https://help.syncfusion.com/uwp/sfchart/axis) can be customized with multiple levels of label by using its [`MultiLevelLabels`]() property. These labels are placed based on the provided [`Start`] and [`End`] range values and we can add any number of labels to an axis. The below code snippet shows how to set a multilevel label,

{% tabs %}

{% highlight xaml %}

<chart:SfChart.PrimaryAxis>

<chart:CategoryAxis ShowLabelBorder="True">

<chart:CategoryAxis.MultiLevelLabels>

<chart:ChartMultiLevelLabel Start="-0.5" End="2.5" Text="Quarter 1" />

</chart:CategoryAxis.MultiLevelLabels>

</chart:CategoryAxis>

</chart:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis =  new CategoryAxis()
            
{
     ShowLabelBorder = true,
            
};
            
ChartMultiLevelLabel label = new ChartMultiLevelLabel()
           
{
 
       Start = -0.5,

       End = 2.5,

       Text = "Quarter 1"

};

chart.PrimaryAxis.MultiLevelLabels.Add(label);

{% endhighlight %}

{% endtabs %}

![](Axis_images/label3.png)

**Regarding** **Start** **and** **End** **Property**

[`Start`] and [`End`] properties of [`ChartMultiLevelLabel`] are type of objects, we can provide the start and end values for a multi-level label based on its Axis type. It is described  in the following table,

<table>
<tr>
<th>S.No</th>
<th>Axis Type</th>
<th>Start/End value</th>
<th>Example</th>
</tr>
<tr>
<td>1</td>
<td>CategoryAxis</td>
<td>Index-Based</td>
<td>Start=0(zeroth index position) End = 1(first index position)</td>
</tr>
<tr>
<td>2</td>
<td>DateTimeCategoryAxis</td>
<td>Index-Based</td>
<td>Start = 0(zeroth index position) End = 1(first index position)</td>
</tr>
<tr>
<td>3</td>
<td>NumericalAxis</td>
<td>Value-Based</td>
<td>Start= 5( Value) End= 10( Value)</td>
</tr>
<tr>
<td>4</td>
<td>LogarithmicAxis</td>
<td>Value-Based</td>
<td>Start= 10(Value) End= 1000(Value)</td>
</tr>
<tr>
<td>5</td>
<td>DateTimeAxis</td>
<td>Value-Based</td>
<td>Start = "2017/01/01" End="2017/01/02"</td>
</tr>
<tr>
<td>6</td>
<td>TimeSpanAxis</td>
<td>Value-Based</td>
<td>Start = "00:00:01" End="00:00:05"</td>
</tr>
</table>


**Customizing** **multi-level** **labels**

**Border** **Customization**

[`ChartMultiLevelLabel's`] border width and color can be customized with [`LabelBorderWidth`] and [`LabelBorderBrush`] properties of chart axis.It can be set as shown in the below code snippet,

{% tabs %}

{% highlight xaml %}

<chart:SfChart.PrimaryAxis>

<chart:CategoryAxis  LabelBorderBrush="Red" LabelBorderWidth="3"  ShowLabelBorder="True">

<chart:CategoryAxis.MultiLevelLabels>

<chart:ChartMultiLevelLabel Start="-0.5" End="2.5" Text="Quarter 1"  />

</chart:CategoryAxis.MultiLevelLabels>

</chart:CategoryAxis>

</chart:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis =  new CategoryAxis()
            
{
    LabelBorderWidth = 3,

    ShowLabelBorder = true,

    LabelBorderBrush = new SolidColorBrush(Colors.Red),
            
};
            
ChartMultiLevelLabel label = new ChartMultiLevelLabel()
           
{
 
       Start = -0.5,

       End = 2.5,

       Text = "Quarter 1",

       BorderWidth = 4

};

chart.PrimaryAxis.MultiLevelLabels.Add(label);

{% endhighlight %}

{% endtabs %}

![](Axis_images/label4.png)


**Border** **Type**

[`Chart Axis`](https://help.syncfusion.com/uwp/sfchart/axis) provides support to various types of border for [`ChartMultiLevelLabels`] and it can be applied by using its [`MultiLevelLabelsBorderType`] property.The default [`MultiLevelLabelsBorderType`] is [`Rectangle`]. The another supported border types are [`Brace`],[`None`] and [`WithoutTopAndBottomBorder`].

**Rectangle**

{% tabs %}

{% highlight xaml %}

<chart:SfChart.PrimaryAxis>

<chart:CategoryAxis  ShowLabelBorder="True">

<chart:CategoryAxis.MultiLevelLabels>

<chart:ChartMultiLevelLabel Start="-0.5" End="2.5"  Text="Quarter 1" />

<chart:ChartMultiLevelLabel Start="2.5" End="5.5" Text="Quarter 2"/>

<chart:ChartMultiLevelLabel Start="5.5" End="8.5" Text="Quarter 3"/>

<chart:ChartMultiLevelLabel Start="8.5" End="11.5" Text="Quarter 4"/>

</chart:CategoryAxis.MultiLevelLabels>

</chart:CategoryAxis>

</chart:SfChart.PrimaryAxis>

<chart:SfChart.SecondaryAxis>

<chart:NumericalAxis  ShowLabelBorder="True">
                    
<chart:NumericalAxis.MultiLevelLabels>
                    
<chart:ChartMultiLevelLabel Start="32" End="36"  Text="Low"/>

<chart:ChartMultiLevelLabel Start="36" End="42" Text="Medium"/>

<chart:ChartMultiLevelLabel Start="42" End="48" Text="High"/>
                    
</chart:NumericalAxis.MultiLevelLabels>

</chart:NumericalAxis>

</chart:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis =  new CategoryAxis()
            
{
     ShowLabelBorder = true,          
};

ChartMultiLevelLabel label1 = new ChartMultiLevelLabel()
            
{
                
     Start = -0.5,

     End = 2.5,

     Text = "Quarter 1",
            
};

chart.PrimaryAxis.MultiLevelLabels.Add(label1);

ChartMultiLevelLabel label2 = new ChartMultiLevelLabel()
           
{
    
    Start = 2.5,
                
    End = 5.5,
                
    Text = "Quarter 2"
            
};

chart.PrimaryAxis.MultiLevelLabels.Add(label2);

ChartMultiLevelLabel label3 = new ChartMultiLevelLabel()

{
     
    Start = 5.5,
                
    End = 8.5,
                
    Text = "Quarter 3"
            
};

chart.PrimaryAxis.MultiLevelLabels.Add(label3);

ChartMultiLevelLabel label4 = new ChartMultiLevelLabel()

{
     Start = 8.5,
               
     End = 11.5,
                
     Text = "Quarter 4"
            
};

chart.PrimaryAxis.MultiLevelLabels.Add(label4);

chart.SecondaryAxis = new NumericalAxis()

{
      ShowLabelBorder = true,
};

ChartMultiLevelLabel label5 = new ChartMultiLevelLabel()
            
{
                
     Start = 32,
                
     End = 36,
     
     Text = "Low"
            
};
            
chart.SecondaryAxis.MultiLevelLabels.Add(label5);
            
ChartMultiLevelLabel label6 = new ChartMultiLevelLabel()

{
    Start = 36,
                
    End = 42,
    
    Text = "Medium"
};

chart.SecondaryAxis.MultiLevelLabels.Add(label6);

ChartMultiLevelLabel label7 = new ChartMultiLevelLabel()

{
     Start = 42,
     
     End = 48,
    
     Text = "High"
};

chart.SecondaryAxis.MultiLevelLabels.Add(label7);

{% endhighlight %}

{% endtabs %}

![](Axis_images/label5.png)


**Brace**

{% tabs %}

{% highlight xaml %}

<chart:SfChart.PrimaryAxis>

<chart:CategoryAxis MultiLevelLabelsBorderType="Brace" ShowLabelBorder="True">

<chart:CategoryAxis.MultiLevelLabels>

<chart:ChartMultiLevelLabel Start="-0.5" End="2.5"  Text="Quarter 1"  />

<chart:ChartMultiLevelLabel Start="2.5" End="5.5" Text="Quarter 2"  />

<chart:ChartMultiLevelLabel Start="5.5" End="8.5" Text="Quarter 3"  />

<chart:ChartMultiLevelLabel Start="8.5" End="11.5" Text="Quarter 4" />

</chart:CategoryAxis.MultiLevelLabels>

</chart:CategoryAxis>

</chart:SfChart.PrimaryAxis>

<chart:SfChart.SecondaryAxis>

<chart:NumericalAxis MultiLevelLabelsBorderType="Brace" ShowLabelBorder="True">
                    
<chart:NumericalAxis.MultiLevelLabels>
                    
<chart:ChartMultiLevelLabel Start="32" End="36"  Text="Low" />

<chart:ChartMultiLevelLabel Start="36" End="42" Text="Medium"/>

<chart:ChartMultiLevelLabel Start="42" End="48" Text="High" />
                    
</chart:NumericalAxis.MultiLevelLabels>

</chart:NumericalAxis>

</chart:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis =  new CategoryAxis()
            
{
   ShowLabelBorder = true,
  
   MultiLevelLabelsBorderType = BorderType.Brace
            
};

ChartMultiLevelLabel label1 = new ChartMultiLevelLabel()
            
{
                
     Start = -0.5,

     End = 2.5,

     Text = "Quarter 1",
};

chart.PrimaryAxis.MultiLevelLabels.Add(label1);

ChartMultiLevelLabel label2 = new ChartMultiLevelLabel()
           
{
    
    Start = 2.5,
                
    End = 5.5,
                
    Text = "Quarter 2",
};

chart.PrimaryAxis.MultiLevelLabels.Add(label2);

ChartMultiLevelLabel label3 = new ChartMultiLevelLabel()

{
     
    Start = 5.5,
                
    End = 8.5,
                
    Text = "Quarter 3",
            
};

chart.PrimaryAxis.MultiLevelLabels.Add(label3);

ChartMultiLevelLabel label4 = new ChartMultiLevelLabel()

{
     Start = 8.5,
               
     End = 11.5,
                
     Text = "Quarter 4",
            
};

chart.PrimaryAxis.MultiLevelLabels.Add(label4);

chart.SecondaryAxis = new NumericalAxis()

{
   ShowLabelBorder = true,

   MultiLevelLabelsBorderType = BorderType.Brace
};

ChartMultiLevelLabel label5 = new ChartMultiLevelLabel()
            
{
                
     Start = 32,
                
     End = 36,
     
     Text = "Low",
            
};
            
chart.SecondaryAxis.MultiLevelLabels.Add(label5);
            
ChartMultiLevelLabel label6 = new ChartMultiLevelLabel()

{
    Start = 36,
                
    End = 42,
    
    Text = "Medium",
};

chart.SecondaryAxis.MultiLevelLabels.Add(label6);

ChartMultiLevelLabel label7 = new ChartMultiLevelLabel()

{
     Start = 42,
     
     End = 48,
    
     Text = "High",
};

chart.SecondaryAxis.MultiLevelLabels.Add(label7);


{% endhighlight %}

{% endtabs %}

![](Axis_images/label6.png)

**None**

{% tabs %}

{% highlight xaml %}

<chart:SfChart.PrimaryAxis  MultiLevelLabelsBorderType="None" ShowLabelBorder="True">

<chart:CategoryAxis>

<chart:CategoryAxis.MultiLevelLabels>

<chart:ChartMultiLevelLabel Start="-0.5" End="2.5"  Text="Quarter 1" />

<chart:ChartMultiLevelLabel Start="2.5" End="5.5" Text="Quarter 2" />

<chart:ChartMultiLevelLabel Start="5.5" End="8.5" Text="Quarter 3" />

<chart:ChartMultiLevelLabel Start="8.5" End="11.5" Text="Quarter 4" />

</chart:CategoryAxis.MultiLevelLabels>

</chart:CategoryAxis>

</chart:SfChart.PrimaryAxis>

<chart:SfChart.SecondaryAxis>

<chart:NumericalAxis MultiLevelLabelsBorderType="None" ShowLabelBorder="True">
                    
<chart:NumericalAxis.MultiLevelLabels>
                    
<chart:ChartMultiLevelLabel Start="32" End="36"  Text="Low" />

<chart:ChartMultiLevelLabel Start="36" End="42" Text="Medium" />

<chart:ChartMultiLevelLabel Start="42" End="48" Text="High" />
                    
</chart:NumericalAxis.MultiLevelLabels>

</chart:NumericalAxis>

</chart:SfChart.SecondaryAxis>


{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis =  new CategoryAxis()
            
{
    ShowLabelBorder = true,          

    MultiLevelLabelsBorderType = BorderType.None
            
};

ChartMultiLevelLabel label1 = new ChartMultiLevelLabel()
            
{
                
     Start = -0.5,

     End = 2.5,

     Text = "Quarter 1"
            
};

chart.PrimaryAxis.MultiLevelLabels.Add(label1);

ChartMultiLevelLabel label2 = new ChartMultiLevelLabel()
           
{
    
    Start = 2.5,
                
    End = 5.5,
                
    Text = "Quarter 2"
            
};

chart.PrimaryAxis.MultiLevelLabels.Add(label2);

ChartMultiLevelLabel label3 = new ChartMultiLevelLabel()

{
     
    Start = 5.5,
                
    End = 8.5,
                
    Text = "Quarter 3"
};

chart.PrimaryAxis.MultiLevelLabels.Add(label3);

ChartMultiLevelLabel label4 = new ChartMultiLevelLabel()

{
     Start = 8.5,
               
     End = 11.5,
                
     Text = "Quarter 4"
            
};

chart.PrimaryAxis.MultiLevelLabels.Add(label4);

chart.SecondaryAxis = new NumericalAxis()

{
    
    ShowLabelBorder = true,          

    MultiLevelLabelsBorderType = BorderType.None

};

ChartMultiLevelLabel label5 = new ChartMultiLevelLabel()
            
{
                
     Start = 32,
                
     End = 36,
     
     Text = "Low"
            
};
            
chart.SecondaryAxis.MultiLevelLabels.Add(label5);
            
ChartMultiLevelLabel label6 = new ChartMultiLevelLabel()

{
    Start = 36,
                
    End = 42,
    
    Text = "Medium"
};

chart.SecondaryAxis.MultiLevelLabels.Add(label6);

ChartMultiLevelLabel label7 = new ChartMultiLevelLabel()

{
     Start = 42,
     
     End = 48,
    
     Text = "High"
};

chart.SecondaryAxis.MultiLevelLabels.Add(label7);


{% endhighlight %}

{% endtabs %}

![](Axis_images/label7.png)

**WithoutTopAndBottomBorder**

{% tabs %}

{% highlight xaml %}

<chart:SfChart.PrimaryAxis>

<chart:CategoryAxis   ShowLabelBorder="True" MultiLevelLabelsBorderType="WithoutTopAndBottomBorder">

<chart:CategoryAxis.MultiLevelLabels>

<chart:ChartMultiLevelLabel Start="-0.5" End="2.5"  Text="Quarter 1"/>

<chart:ChartMultiLevelLabel Start="2.5" End="5.5" Text="Quarter 2" />

<chart:ChartMultiLevelLabel Start="5.5" End="8.5" Text="Quarter 3" />

<chart:ChartMultiLevelLabel Start="8.5" End="11.5" Text="Quarter 4" />

</chart:CategoryAxis.MultiLevelLabels>

</chart:CategoryAxis>

</chart:SfChart.PrimaryAxis>

<chart:SfChart.SecondaryAxis>

<chart:NumericalAxis  ShowLabelBorder="True" MultiLevelLabelsBorderType="WithoutTopAndBottomBorder">
                    
<chart:NumericalAxis.MultiLevelLabels>
                    
<chart:ChartMultiLevelLabel Start="32" End="36"  Text="Low" />

<chart:ChartMultiLevelLabel Start="36" End="42" Text="Medium"/>

<chart:ChartMultiLevelLabel Start="42" End="48" Text="High"/>
                    
</chart:NumericalAxis.MultiLevelLabels>

</chart:NumericalAxis>

</chart:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis =  new CategoryAxis()
            
{
   ShowLabelBorder = true,

   MultiLevelLabelsBorderType = BorderType.WithoutTopAndBottomBorder
            
};

ChartMultiLevelLabel label1 = new ChartMultiLevelLabel()
            
{
                
     Start = -0.5,

     End = 2.5,

     Text = "Quarter 1",
            
};

chart.PrimaryAxis.MultiLevelLabels.Add(label1);

ChartMultiLevelLabel label2 = new ChartMultiLevelLabel()
           
{
    
    Start = 2.5,
                
    End = 5.5,
                
    Text = "Quarter 2",
           
};

chart.PrimaryAxis.MultiLevelLabels.Add(label2);

ChartMultiLevelLabel label3 = new ChartMultiLevelLabel()

{
     
    Start = 5.5,
                
    End = 8.5,
                
    Text = "Quarter 3",
            
};

chart.PrimaryAxis.MultiLevelLabels.Add(label3);

ChartMultiLevelLabel label4 = new ChartMultiLevelLabel()

{
     Start = 8.5,
               
     End = 11.5,
                
     Text = "Quarter 4",
};

chart.PrimaryAxis.MultiLevelLabels.Add(label4);

chart.SecondaryAxis = new NumericalAxis()

{
    
    ShowLabelBorder = true,

   MultiLevelLabelsBorderType = BorderType.WithoutTopAndBottomBorder

};

ChartMultiLevelLabel label5 = new ChartMultiLevelLabel()
            
{
                
     Start = 32,
                
     End = 36,
     
     Text = "Low",
            
};
            
chart.SecondaryAxis.MultiLevelLabels.Add(label5);
            
ChartMultiLevelLabel label6 = new ChartMultiLevelLabel()

{
    Start = 36,
                
    End = 42,
    
    Text = "Medium",
};

chart.SecondaryAxis.MultiLevelLabels.Add(label6);

ChartMultiLevelLabel label7 = new ChartMultiLevelLabel()

{
     Start = 42,
     
     End = 48,
    
     Text = "High",
};

chart.SecondaryAxis.MultiLevelLabels.Add(label7);

{% endhighlight %}

{% endtabs %}

![](Axis_images/label8.png)


**Text** **Customization**

[`ChartMultiLevelLabel's`] text can be customized with its [`FontSize`], [`FontFamily`] and [`Foreground`] property and it is shown in below code snippet,

{% tabs %}

{% highlight xaml %}

<chart:SfChart.PrimaryAxis>

<chart:CategoryAxis  ShowLabelBorder="True">

<chart:CategoryAxis.MultiLevelLabels>

<chart:ChartMultiLevelLabel Start="-0.5" End="11.5" FontFamily="Algerian" Foreground="Blue" FontSize="14" Text="Year - 2016"/>

</chart:CategoryAxis.MultiLevelLabels>

</chart:CategoryAxis>

</chart:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis =  new CategoryAxis()
            
{
      ShowLabelBorder = true,            
};
            
ChartMultiLevelLabel label = new ChartMultiLevelLabel()
           
{
 
    Start = -0.5,
                
    End = 11.5,
                
    Text = "Year - 2016",
                
    Foreground = new SolidColorBrush(Colors.Blue),
                
    FontSize = 14,
                
    FontFamily = new FontFamily("Algerian")

};

chart.PrimaryAxis.MultiLevelLabels.Add(label);

{% endhighlight %}

{% endtabs %}

![](Axis_images/label9.png)


**Label** **Alignment**

The text of [`ChartMultiLevelLabel`] can be aligned with its [`LabelAlignment`] property. The default value of [`LabelAlignment`] property is Center.

**Center**

{% tabs %}

{% highlight xaml %}

<chart:SfChart.PrimaryAxis>

<chart:CategoryAxis  ShowLabelBorder="True">

<chart:CategoryAxis.MultiLevelLabels>

<chart:ChartMultiLevelLabel Start="-0.5" End="2.5"  Text="Quarter 1" />

<chart:ChartMultiLevelLabel Start="2.5" End="5.5" Text="Quarter 2"/>

<chart:ChartMultiLevelLabel Start="5.5" End="8.5" Text="Quarter 3"/>

<chart:ChartMultiLevelLabel Start="8.5" End="11.5" Text="Quarter 4"/>

</chart:CategoryAxis.MultiLevelLabels>

</chart:CategoryAxis>

</chart:SfChart.PrimaryAxis>

<chart:SfChart.SecondaryAxis>

<chart:NumericalAxis ShowLabelBorder="True">
                    
<chart:NumericalAxis.MultiLevelLabels>
                    
<chart:ChartMultiLevelLabel Start="32" End="36"  Text="Low"/>

<chart:ChartMultiLevelLabel Start="36" End="42" Text="Medium"/>

<chart:ChartMultiLevelLabel Start="42" End="48" Text="High"/>
                    
</chart:NumericalAxis.MultiLevelLabels>

</chart:NumericalAxis>

</chart:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis =  new CategoryAxis()
            
{
     ShowLabelBorder = true,                       
};

ChartMultiLevelLabel label1 = new ChartMultiLevelLabel()
            
{
                
     Start = -0.5,

     End = 2.5,

     Text = "Quarter 1",
            
};

chart.PrimaryAxis.MultiLevelLabels.Add(label1);

ChartMultiLevelLabel label2 = new ChartMultiLevelLabel()
           
{
    
    Start = 2.5,
                
    End = 5.5,
                
    Text = "Quarter 2"
            
};

chart.PrimaryAxis.MultiLevelLabels.Add(label2);

ChartMultiLevelLabel label3 = new ChartMultiLevelLabel()

{
     
    Start = 5.5,
                
    End = 8.5,
                
    Text = "Quarter 3"
            
};

chart.PrimaryAxis.MultiLevelLabels.Add(label3);

ChartMultiLevelLabel label4 = new ChartMultiLevelLabel()

{
     Start = 8.5,
               
     End = 11.5,
                
     Text = "Quarter 4"
            
};

chart.PrimaryAxis.MultiLevelLabels.Add(label4);

chart.SecondaryAxis = new NumericalAxis()

{
      ShowLabelBorder = true,            
};

ChartMultiLevelLabel label5 = new ChartMultiLevelLabel()
            
{
                
     Start = 32,
                
     End = 36,
     
     Text = "Low"
            
};
            
chart.SecondaryAxis.MultiLevelLabels.Add(label5);
            
ChartMultiLevelLabel label6 = new ChartMultiLevelLabel()

{
    Start = 36,
                
    End = 42,
    
    Text = "Medium"
};

chart.SecondaryAxis.MultiLevelLabels.Add(label6);

ChartMultiLevelLabel label7 = new ChartMultiLevelLabel()

{
     Start = 42,
     
     End = 48,
    
     Text = "High"
};

chart.SecondaryAxis.MultiLevelLabels.Add(label7);

{% endhighlight %}

{% endtabs %}

![](Axis_images/label13.png)


**Near**

{% tabs %}

{% highlight xaml %}

<chart:SfChart.PrimaryAxis>

<chart:CategoryAxis ShowLabelBorder="True">

<chart:CategoryAxis.MultiLevelLabels>

<chart:ChartMultiLevelLabel Start="-0.5" End="2.5"  Text="Quarter 1"   LabelAlignment="Near" />

<chart:ChartMultiLevelLabel Start="2.5" End="5.5" Text="Quarter 2"  LabelAlignment="Near"/>

<chart:ChartMultiLevelLabel Start="5.5" End="8.5" Text="Quarter 3"  LabelAlignment="Near"/>

<chart:ChartMultiLevelLabel Start="8.5" End="11.5" Text="Quarter 4"  LabelAlignment="Near"/>

</chart:CategoryAxis.MultiLevelLabels>

</chart:CategoryAxis>

</chart:SfChart.PrimaryAxis>

<chart:SfChart.SecondaryAxis>

<chart:NumericalAxis ShowLabelBorder="True">
                    
<chart:NumericalAxis.MultiLevelLabels>
                    
<chart:ChartMultiLevelLabel Start="32" End="36"  Text="Low"  LabelAlignment="Near"/>

<chart:ChartMultiLevelLabel Start="36" End="42" Text="Medium"  LabelAlignment="Near"/>

<chart:ChartMultiLevelLabel Start="42" End="48" Text="High"  LabelAlignment="Near"/>
                    
</chart:NumericalAxis.MultiLevelLabels>

</chart:NumericalAxis>

</chart:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis =  new CategoryAxis()
            
{
    ShowLabelBorder = true,                       
};

ChartMultiLevelLabel label1 = new ChartMultiLevelLabel()
            
{
                
     Start = -0.5,

     End = 2.5,

     Text = "Quarter 1",
    
     LabelAlignment = LabelAlignment.Near
            
};

chart.PrimaryAxis.MultiLevelLabels.Add(label1);

ChartMultiLevelLabel label2 = new ChartMultiLevelLabel()
           
{
    
    Start = 2.5,
                
    End = 5.5,
                
    Text = "Quarter 2",

    LabelAlignment = LabelAlignment.Near
            
};

chart.PrimaryAxis.MultiLevelLabels.Add(label2);

ChartMultiLevelLabel label3 = new ChartMultiLevelLabel()

{
     
    Start = 5.5,
                
    End = 8.5,
                
    Text = "Quarter 3",

    LabelAlignment = LabelAlignment.Near
            
};

chart.PrimaryAxis.MultiLevelLabels.Add(label3);

ChartMultiLevelLabel label4 = new ChartMultiLevelLabel()

{
     Start = 8.5,
               
     End = 11.5,
                
     Text = "Quarter 4",

     LabelAlignment = LabelAlignment.Near
            
};

chart.PrimaryAxis.MultiLevelLabels.Add(label4);

chart.SecondaryAxis = new NumericalAxis()

{   
    ShowLabelBorder = true,            
};

ChartMultiLevelLabel label5 = new ChartMultiLevelLabel()
            
{
                
     Start = 32,
                
     End = 36,
     
     Text = "Low",

     LabelAlignment = LabelAlignment.Near
            
};
            
chart.SecondaryAxis.MultiLevelLabels.Add(label5);
            
ChartMultiLevelLabel label6 = new ChartMultiLevelLabel()

{
    Start = 36,
                
    End = 42,
    
    Text = "Medium",

    LabelAlignment = LabelAlignment.Near
};

chart.SecondaryAxis.MultiLevelLabels.Add(label6);

ChartMultiLevelLabel label7 = new ChartMultiLevelLabel()

{
     Start = 42,
     
     End = 48,
    
     Text = "High",

     LabelAlignment = LabelAlignment.Near
};

chart.SecondaryAxis.MultiLevelLabels.Add(label7);

{% endhighlight %}

{% endtabs %}

![](Axis_images/label10.png)


**Far**

{% tabs %}

{% highlight xaml %}

<chart:SfChart.PrimaryAxis>

<chart:CategoryAxis  ShowLabelBorder="True">

<chart:CategoryAxis.MultiLevelLabels>

<chart:ChartMultiLevelLabel Start="-0.5" End="2.5"  Text="Quarter 1"   LabelAlignment="Far" />

<chart:ChartMultiLevelLabel Start="2.5" End="5.5" Text="Quarter 2"  LabelAlignment="Far"/>

<chart:ChartMultiLevelLabel Start="5.5" End="8.5" Text="Quarter 3"  LabelAlignment="Far"/>

<chart:ChartMultiLevelLabel Start="8.5" End="11.5" Text="Quarter 4"  LabelAlignment="Far"/>

</chart:CategoryAxis.MultiLevelLabels>

</chart:CategoryAxis>

</chart:SfChart.PrimaryAxis>

<chart:SfChart.SecondaryAxis>

<chart:NumericalAxis  ShowLabelBorder="True">
                    
<chart:NumericalAxis.MultiLevelLabels>
                    
<chart:ChartMultiLevelLabel Start="32" End="36"  Text="Low"  LabelAlignment="Far"/>

<chart:ChartMultiLevelLabel Start="36" End="42" Text="Medium"  LabelAlignment="Far"/>

<chart:ChartMultiLevelLabel Start="42" End="48" Text="High" LabelAlignment="Far"/>
                    
</chart:NumericalAxis.MultiLevelLabels>

</chart:NumericalAxis>

</chart:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis =  new CategoryAxis()
            
{
      ShowLabelBorder = true,          
};

ChartMultiLevelLabel label1 = new ChartMultiLevelLabel()
            
{
                
     Start = -0.5,

     End = 2.5,

     Text = "Quarter 1",
    
     LabelAlignment = LabelAlignment.Near
            
};

chart.PrimaryAxis.MultiLevelLabels.Add(label1);

ChartMultiLevelLabel label2 = new ChartMultiLevelLabel()
           
{
    
    Start = 2.5,
                
    End = 5.5,
                
    Text = "Quarter 2",

    LabelAlignment = LabelAlignment.Near
            
};

chart.PrimaryAxis.MultiLevelLabels.Add(label2);

ChartMultiLevelLabel label3 = new ChartMultiLevelLabel()

{
     
    Start = 5.5,
                
    End = 8.5,
                
    Text = "Quarter 3",

    LabelAlignment = LabelAlignment.Near
            
};

chart.PrimaryAxis.MultiLevelLabels.Add(label3);

ChartMultiLevelLabel label4 = new ChartMultiLevelLabel()

{
     Start = 8.5,
               
     End = 11.5,
                
     Text = "Quarter 4",

     LabelAlignment = LabelAlignment.Near
            
};

chart.PrimaryAxis.MultiLevelLabels.Add(label4);

chart.SecondaryAxis = new NumericalAxis()

{
      ShowLabelBorder = true,          
};

ChartMultiLevelLabel label5 = new ChartMultiLevelLabel()
            
{
                
     Start = 32,
                
     End = 36,
     
     Text = "Low",

     LabelAlignment = LabelAlignment.Near
            
};
            
chart.SecondaryAxis.MultiLevelLabels.Add(label5);
            
ChartMultiLevelLabel label6 = new ChartMultiLevelLabel()

{
    Start = 36,
                
    End = 42,
    
    Text = "Medium",

    LabelAlignment = LabelAlignment.Near
};

chart.SecondaryAxis.MultiLevelLabels.Add(label6);

ChartMultiLevelLabel label7 = new ChartMultiLevelLabel()

{
     Start = 42,
     
     End = 48,
    
     Text = "High",

     LabelAlignment = LabelAlignment.Near
};

chart.SecondaryAxis.MultiLevelLabels.Add(label7);

{% endhighlight %}

{% endtabs %}

![](Axis_images/label11.png)

The text of [`ChartMultiLavelLabel`] text will automatically trim, when the text width exceeds the width of [`ChartMultiLevelLabel`] and it is shown below,

{% tabs %}

{% highlight xaml %}

<chart:SfChart.SecondaryAxis>

<chart:NumericalAxis ShowLabelBorder="True">

<chart:NumericalAxis.MultiLevelLabels>

<chart:ChartMultiLevelLabel Start="32" End="36" Text="Low Temperature"/>

<chart:ChartMultiLevelLabel Start="36" End="42" Text="Medium Temperature"/>
                        
<chart:ChartMultiLevelLabel Start="42" End="48" Text="High Temperature"/>

</chart:NumericalAxis.MultiLevelLabels>

</chart:NumericalAxis>

</chart:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.SecondaryAxis = new NumericalAxis()
            
{
     ShowLabelBorder = true,          
};

ChartMultiLevelLabel label5 = new ChartMultiLevelLabel()
            
{
                
        Start = 32,
        
        End = 36,
        
        Text = "Low Temperature"
};

chart.SecondaryAxis.MultiLevelLabels.Add(label5);

ChartMultiLevelLabel label6 = new ChartMultiLevelLabel()

{
        Start = 36,
                
        End = 42,
        
        Text = "Medium Temperature"
            
};
    
chart.SecondaryAxis.MultiLevelLabels.Add(label6);

ChartMultiLevelLabel label7 = new ChartMultiLevelLabel()

{
                
       Start = 42,
               
       End = 48,
       
       Text = "High Temperature"
 
 };

 chart.SecondaryAxis.MultiLevelLabels.Add(label7);

{% endhighlight %}

{% endtabs %}

![](Axis_images/label12.png)



