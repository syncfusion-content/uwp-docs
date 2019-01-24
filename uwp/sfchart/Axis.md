---
layout: post
title: Axis | SfChart | uwp | Syncfusion
description: Explains the types of axis, axis features, styling the header and labels, customizing the gridlines and ticklines. 
platform: uwp
control: SfChart
documentation: ug
---

# Axis

[`ChartAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis.html) is used to locate a data point inside the chart area. Generally, to locate a data point, you require two axes, along each direction, that is, horizontal and vertical, in a chart. The vertical axis, or y-axis, usually represents numerical values .The horizontal axis, or x-axis, represents categorical or numerical or date and time values. [`ChartAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis.html) supports the following types.

* Double                

* DateTime(Linear)

* DateTime(Category)

* String

* TimeSpan

* Logarithmic

You can choose any [`ChartAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis.html) derived types, like [`DateTimeAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.DateTimeAxis.html), [`NumericalAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.NumericalAxis.html), [`CategoryAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.CategoryAxis.html), [`LogarithmicAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.LogarithmicAxis.html) or [`TimeSpanAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.TimeSpanAxis.html) depending on the value type. [`DateTimeCategoryAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.DateTimeCategoryAxis.html) is a special type, used to plot date and time values for the given datapoints. 

## NumericAxis

[`NumericalAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.NumericalAxis.html) is used to plot numerical value to the chart. You can set [`NumericalAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.NumericalAxis.html) for both [`PrimaryAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.SfChart~PrimaryAxis.html) and [`SecondaryAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.SfChart~SecondaryAxis.html).

The following APIs are used to customize [`NumericalAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.NumericalAxis.html).

Properties

<table>
<tr>
<th>
Property</th><th>
Definition</th></tr>
<tr>
<td>
{{'[`Interval`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.NumericalAxis~Interval.html)'| markdownify }}</td><td>
Gets or sets the double that represents the interval between the labels.</td></tr>
<tr>
<td>
{{'[`Minimum`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.NumericalAxis~Minimum.html)'| markdownify }}</td><td>
Gets or sets the double that represents the Minimum value for the Axis.</td></tr>
<tr>
<td>
{{'[`Maximum`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.NumericalAxis~Maximum.html)'| markdownify }}</td><td>
Gets or sets the double that represents the Maximum value for the Axis.</td></tr>
<tr>
<td>
{{'[`RangePadding`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.NumericalAxis~RangePadding.html)'| markdownify }}</td><td>
Gets or sets the NumericalPadding that specifies how to render the segments in chart area.</td></tr>
<tr>
<td>
{{'[`StartRangeFromZero`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.NumericalAxis~StartRangeFromZero.html)'| markdownify }}</td><td>
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

![NumericalAxis support in UWP Chart](Axis_images/Axis_img1.png)



## CategoryAxis

[`CategoryAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.CategoryAxis.html) is an index based axis that plots values based on the index of the data point collection. The points are equally spaced here.

The following APIs are used in [`CategoryAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.CategoryAxis.html).

CategoryAxis

<table>
<tr>
<th>
Property</th><th>
Definition</th></tr>
<tr>
<td>
{{'[`Interval`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.CategoryAxis~Interval.html)'| markdownify }}</td><td>
Gets or sets the double value that represents the interval between the labels.</td></tr>
<tr>
<td>
{{'[`LabelPlacement`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.CategoryAxis~LabelPlacement.html)'| markdownify }}</td><td>
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

![CategoryAxis support in UWP Chart](Axis_images/Axis_img2.png)


## DateTimeAxis

[`DateTimeAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.DateTimeAxis.html) is used to plot DateTime values. The DateTimeAxis is widely used to make financial charts in places like the Stock Market, where index plotting is done everyday.

The following APIs are used for customizing [`DateTimeAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.DateTimeAxis.html).

DateTimeAxis

<table>
<tr>
<th>
Property</th><th>
Definition</th></tr>
<tr>
<td>
{{'[`Minimum`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.DateTimeAxis~Minimum.html)'| markdownify }}</td><td>
Gets or sets the DateTime value that represents a minimum value of the Axis.</td></tr>
<tr>
<td>
{{'[`Maximum`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.DateTimeAxis~Maximum.html)'| markdownify }}</td><td>
Gets or sets the DateTime value that represents a maximum value of the Axis.</td></tr>
<tr>
<td>
{{'[`RangePadding`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.DateTimeAxis~RangePadding.html)'| markdownify }}</td><td>
Gets or sets the DateTimeRangePadding value that specifies segment arrangement in the chart area.</td></tr>
<tr>
<td>
{{'[`Interval`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.DateTimeAxis~Interval.html)'| markdownify }}</td><td>
Gets or sets the double value as the interval between labels.</td></tr>
<tr>
<td>
{{'[`IntervalType`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.DateTimeAxis~IntervalType.html)'| markdownify }}</td><td>
Gets or sets the DateTimeIntervalType. It represents the type of the interval. This property is used to define the type of interval to be displayed and considered for plotting the series.</td></tr>
<tr>
<td>
{{'[`EnableBusinessHours`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.DateTimeAxis~EnableBusinessHours.html)'| markdownify }}</td><td>
Gets or sets the bool value that represents a value to enable business hours.</td></tr>
<tr>
<td>
{{'[`OpenTime`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.DateTimeAxis~OpenTime.html)'| markdownify }}</td><td>
Gets or sets the double value that represents the open working time of a day.</td></tr>
<tr>
<td>
{{'[`CloseTime`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.DateTimeAxis~CloseTime.html)'| markdownify }}</td><td>
Gets or sets the double value that represents the close working time of a day.</td></tr>
<tr>
<td>
{{'[`WorkingDays`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.DateTimeAxis~WorkingDays.html)'| markdownify }}</td><td>
Gets or sets the double value that represents the working days of a week.</td></tr>
</table>

### DateTimeIntervalType

The DateTime interval corresponds to the type specified in the [`IntervalType`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.DateTimeAxis~IntervalType.html#) property.

For instance, if the Interval is set as 2 and IntervalType is set as Days, the labels are plotted for every two days. The following are the values for [`IntervalType`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.DateTimeAxis~IntervalType.html#) property:

* Auto
* Days
* Hours
* Milliseconds
* Minutes 
* Months
* Seconds
* Years



The default [`IntervalType`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.DateTimeAxis~IntervalType.html#) of a [`DateTimeAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.DateTimeAxis.html) is Auto. It calculates the type automatically and the interval, accordingly.

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

![DateTimeAxis support in UWP Chart](Axis_images/Axis_img3.png)



## DateTimeCategoryAxis

[`DateTimeCategoryAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.DateTimeCategoryAxis.html) is a special type of axis used mainly with financial series. All the data points are plotted with equal spaces, similar to [`CategoryAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.CategoryAxis.html), thereby removing space for missing dates. Intervals and range for the axis are calculated similar to [`DateTimeAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.DateTimeAxis.html). There are no visual gaps between points, even when the difference between two points is more than a year.

DateTimeCategoryAxis

<table>
<tr>
<th>
Property</th><th>
Definition</th></tr>
<tr>
<td>
{{'[`Interval`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.DateTimeCategoryAxis~Interval.html)'| markdownify }}</td><td>
Gets or sets the double value that represents the interval between the labels.</td></tr>
<tr>
<td>
{{'[`IntervalType`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.DateTimeCategoryAxis~IntervalType.html)'| markdownify }}</td><td>
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

![DateTimeCategoryAxis support in UWP Chart](Axis_images/Axis_img4.png)



## TimeSpanAxis

[`TimeSpanAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.TimeSpanAxis.html) is used to plot the time span values in the PrimaryAxis. TimeSpanAxis has the advantage of plotting data with milliseconds difference. The limitation of TimeSpanAxis is that it can only accept timespan values (hh:mm:ss) and datetime values are not accepted.

The following APIs are used in [`TimeSpanAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.TimeSpanAxis.html).

TimeSpanAxis

<table>
<tr>
<th>
Property</th><th>
Definition</th></tr>
<tr>
<td>
{{'[`Interval`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.TimeSpanAxis~Interval.html)'| markdownify }}</td><td>
Gets or sets the double value that represents the interval between the labels.</td></tr>
<tr>
<td>
{{'[`Minimum`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.TimeSpanAxis~Minimum.html)'| markdownify }}</td><td>
Gets or sets the timespan value that represents the minimum value for the Axis.</td></tr>
<tr>
<td>
{{'[`Maximum`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.TimeSpanAxis~Maximum.html)'| markdownify }}</td><td>
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

![TimeSpanAxis support in UWP Chart](Axis_images/Axis_img5.png)



## LogarithmicAxis

[`LogarithmicAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.LogarithmicAxis.html) is used to plot the logarithmic scale for the chart. In order to plot the logarithmic scale, you must specify the base value using [`LogarithmicBase`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.LogarithmicAxis~LogarithmicBase.html) Property.

The following APIs are used to customize the [`LogarithmicAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.LogarithmicAxis.html).

LogarithmicAxis

<table>
<tr>
<th>
Property</th><th>
Definition</th></tr>
<tr>
<td>
{{'[`Interval`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.LogarithmicAxis~Interval.html)'| markdownify }}</td><td>
Gets or sets the double value that represents the interval between the labels</td></tr>
<tr>
<td>
{{'[`Minimum`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.LogarithmicAxis~Minimum.html)'| markdownify }}</td><td>
Gets or sets the double value that represents the minimum value for the Axis.</td></tr>
<tr>
<td>
{{'[`Maximum`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.LogarithmicAxis~Maximum.html)'| markdownify }}</td><td>
Gets or sets the double value that represents the maximum value of the Axis. </td></tr>
<tr>
<td>
{{'[`LogarithmicBase`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.LogarithmicAxis~LogarithmicBase.html)'| markdownify }}</td><td>
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

Logarithmic Axis does not support zero or negative values.

The following screenshot illustrates the SfChart with LogarithmicAxis.

![LogarithmicAxis support in UWP Chart](Axis_images/Axis_img6.png)



## Multiple Axes

[`SfChart`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.SfChart.html) provides a way to arrange multiple series inside the same chart area, giving the chart more space than x-axis and y-axis.These axes can be arranged in a stack or in a side by side pattern. 

By default, all the series are plotted based on Primary and Secondary Axis. You can add more axes by adding additional axis to the series. There are two properties [`XAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.CartesianSeries~XAxis.html) and [`YAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.CartesianSeries~YAxis.html) in all the series, except Accumulation Series.

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

![Multiple axes support in UWP Chart](Axis_images/Axis_img7.jpg)



 The first series is plotting based on additional X & Y axis and second series (or remaining series) is plotting against the Primary and Secondary axis.

### Axis Positioning

By default, the x-axis is arranged horizontally at the bottom of the chart and the y-axis is arranged vertically on the left-side of the chart. You can change the alignment of the axes by setting OpposedPosition to True. It arranges the x-axis at the top and the y-axis on the right-side of the chart. 

The following is the code example for setting the [`OpposedPosition`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis~OpposedPosition.html) property.

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

The following is a screenshot demonstrating y-axis of a chart arranged in [`OpposedPosition`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis~OpposedPosition.html).

![Axis Positioning support in UWP Chart](Axis_images/Axis_img8.png)



## Inversed Axis

[`IsInversed`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis~IsInversed.html) property is used to reverse chart plotting inverse the axis scaling.

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

![Inversed axis support in UWP Chart](Axis_images/Axis_img9.png)



## Axis range and Interval

[`ChartAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis.html) calculates the range and intervals automatically based on the values of series data points. You can also explicitly specify the range and interval using the Minimum, Maximum and Interval properties. 

T> You cannot specify range for [`CategoryAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.CategoryAxis.html) instead you can use [`ZoomFactor`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxisBase2D~ZoomFactor.html) and [`ZoomPosition`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxisBase2D~ZoomPosition.html).



 You can force the [`NumericalAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.NumericalAxis.html) to start range from zero by enabling [`StartRangeFromZero`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.NumericalAxis~StartRangeFromZero.html). The following is the code example for setting the ChartAxis properties.

 The following is the code sample for setting the [`ChartAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis.html) properties:

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

The [`NumericalAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.NumericalAxis.html) and [`DateTimeAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.DateTimeAxis.html) have a [`RangePadding`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.NumericalAxis~RangePadding.html) property that can be used to add padding to the range of a chart's axes.

### NumericalAxis RangePadding

The following types are available for [`NumericalAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.NumericalAxis.html): 

* Additional
* None
* Normal
* Round

By default, the default [`RangePadding`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.NumericalAxis~RangePadding.html) value for [`PrimaryAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.SfChart~PrimaryAxis.html) is [`Auto`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.NumericalPadding.html) and for [`SecondaryAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.SfChart~SecondaryAxis.html), the default value is [`Round`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.NumericalPadding.html).

![NumericalAxis range padding support in UWP Chart](Axis_images/Axis_img10.png)



The following screenshot demonstrates [`RangePadding`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.NumericalAxis~RangePadding.html) as [`None`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.NumericalPadding.html), where no padding is applied for the axis.

![NumericalAxis range padding support in UWP Chart](Axis_images/Axis_img11.png)



[`Normal`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.NumericalPadding.html) [`RangePadding`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.NumericalAxis~RangePadding.html) for a [`NumericalAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.NumericalAxis.html) is used mostly for the y-axis to have padding based on the Range calculation.

The following screenshot illustrates a chart’s y-axis with [`RangePadding`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.NumericalAxis~RangePadding.html) set to [`Normal`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.NumericalPadding.html).

![NumericalAxis range padding support in UWP Chart](Axis_images/Axis_img12.png)



Round [`RangePadding`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.NumericalAxis~RangePadding.html) for a [`NumericalAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.NumericalAxis.html) rounds the range of the chart axis to the nearest possible value.

The following screenshot demonstrates a chart’s x-axis with [`RangePadding`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.NumericalAxis~RangePadding.html) set to [`Round`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.NumericalPadding.html).

![NumericalAxis range padding support in UWP Chart](Axis_images/Axis_img13.png)



If [`RangePadding`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.NumericalAxis~RangePadding.html) for [`NumericalAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.NumericalAxis.html) is set to [`Additional`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.NumericalPadding.html), the interval of the axis is added as padding.

The following screenshot demonstrates a chart’s x-axis with [`RangePadding`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.NumericalAxis~RangePadding.html) set to [`Additional`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.NumericalPadding.html).

![NumericalAxis range padding support in UWP Chart](Axis_images/Axis_img14.png)



### DateTimeAxis RangePadding

The [`RangePadding`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.DateTimeAxis~RangePadding.html) types available in the [`DateTimeAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.DateTimeAxis.html) are: 

* Additional
* None
* Round

By default, the [`RangePadding`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.DateTimeAxis~RangePadding.html) for a [`DateTimeAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.DateTimeAxis.html) is [`None`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.DateTimeRangePadding.html).

The following screenshot demonstrates a chart’s x-axis with [`RangePadding`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.DateTimeAxis~RangePadding.html) set to [`None`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.DateTimeRangePadding.html). 

![DateTimeAxis range padding support in UWP Chart](Axis_images/Axis_img15.jpg)



When [`RangePadding`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.DateTimeAxis~RangePadding.html) for [`DateTimeAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.DateTimeAxis.html) is set to [`Additional`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.DateTimeRangePadding.html), the DateTime interval of the axis is added as padding, as shown in the following screenshot.

![DateTimeAxis range padding support in UWP Chart](Axis_images/Axis_img16.jpg)



When [`RangePadding`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.DateTimeAxis~RangePadding.html) for [`DateTimeAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.DateTimeAxis.html) is set to [`Round`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.DateTimeRangePadding.html), the range of the chart axis is rounded off to the nearest possible DateTime value, as shown in the following screenshot.

![DateTimeAxis range padding support in UWP Chart](Axis_images/Axis_img17.jpg)



## Positioning axis labels

### Label Placement

The [`CategoryAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.CategoryAxis.html) includes the [`LabelPlacement`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.CategoryAxis~LabelPlacement.html) property, used to set the labels of the axis between the tick lines or on the tick lines of the category axis. By default the [`LabelPlacement`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.CategoryAxis~LabelPlacement.html) value for the [`CategoryAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.CategoryAxis.html) is [`OnTicks`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.LabelPlacement.html).

There are two types of [`LabelPlacement`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.CategoryAxis~LabelPlacement.html):

* BetweenTicks
* OnTicks

The following code example and screenshot shows [`LabelPlacement`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.CategoryAxis~LabelPlacement.html) set to [`OnTicks`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.LabelPlacement.html).

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

![Axis label placement support in UWP Chart](Axis_images/Axis_img18.png)



The following code example and screenshot shows [`LabelPlacement`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.CategoryAxis~LabelPlacement.html) set to [`BetweenTicks`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.LabelPlacement.html).

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


![Axis label placement support in UWP Chart](Axis_images/Axis_img19.png)



### Label Position 

The [`LabelsPosition`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis~LabelsPosition.html) property is used to position the axis label either inside or outside the chart plotting area.

The following code example and screenshot illustrate the use of [`LabelsPosition`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis~LabelsPosition.html).

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

![Axis label positioning support in UWP Chart](Axis_images/Axis_img20.jpg)

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


![Axis label positioning support in UWP Chart](Axis_images/Axis_img21.png)



### Positioning Edge Labels

[`SfChart`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.SfChart.html) provides support to customize the edge labels of the axis to adjust its position using the [`EdgeLabelsDrawingMode`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis~EdgeLabelsDrawingMode.html) property. 

The following are the customizing options in [`EdgeLabelsDrawingMode`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis~EdgeLabelsDrawingMode.html).

* Center- Positions the label with tickline as center.
* Fit- Position the gridline inside based on the edge label size.
* Hide- Hides the edge labels.
* Shift- Shifts the edge labels inside to label width.



The following code example and screenshot show [`EdgeLabelsDrawingMode`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis~EdgeLabelsDrawingMode.html) set to [`Center`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.EdgeLabelsDrawingMode.html).

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

![Axis edge label positioning support in UWP Chart](Axis_images/Axis_img22.png)



The following code example and screenshot shows [`EdgeLabelsDrawingMode`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis~EdgeLabelsDrawingMode.html) set to [`Fit`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.EdgeLabelsDrawingMode.html).

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

![Axis edge label positioning support in UWP Chart](Axis_images/Axis_img23.png)



The following code example and screenshot shows [`EdgeLabelDrawingMode`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis~EdgeLabelsDrawingMode.html) set to [`Hide`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.EdgeLabelsDrawingMode.html).

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

![Axis edge label positioning support in UWP Chart](Axis_images/Axis_img24.png)



The following code example and screenshot shows [`EdgeLabelsDrawingMode`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis~EdgeLabelsDrawingMode.html) set to [`Shift`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.EdgeLabelsDrawingMode.html).

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

![Axis edge label positioning support in UWP Chart](Axis_images/Axis_img25.png)



## Smart Labels

When a number of axis labels exist, they may overlap with each other. [`SfChart`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.SfChart.html) provides features to handle the overlapping labels using the [`LabelsIntersectAction`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis~LabelsIntersectAction.html) property.

The following are the options for intersecting action.

* None
* Hide
* MultipleRows



The following code example and screenshot shows [`LabelsIntersectAction`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis~LabelsIntersectAction.html) set to [`None`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.AxisLabelsIntersectAction.html).

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

![Smart axis labels support in UWP Chart](Axis_images/Axis_img26.png)



The following code example and screenshot shows [`LabelsIntersectAction`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis~LabelsIntersectAction.html) set to [`Hide`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.AxisLabelsIntersectAction.html).

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

![Smart axis labels support in UWP Chart](Axis_images/Axis_img27.png)



The following code example and screenshot show [`LabelsIntersectAction`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis~LabelsIntersectAction.html) set to [`MultipleRows`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.AxisLabelsIntersectAction.html).

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

![Smart axis labels support in UWP Chart](Axis_images/Axis_img28.png)

## Custom Labels

SfChart allows user to define the labels for the axis. For defining the axis label you have to set the [`LabelContent`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxisLabel~LabelContent.html#) and [`Position`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxisLabel~Position.html#) properties.You can define the labels using [`CustomLabels`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis~CustomLabels.html#) property as demonstrated in the following code snippet.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.PrimaryAxis>

<syncfusion:CategoryAxis >

<syncfusion:CategoryAxis.CustomLabels>

<syncfusion:ChartAxisLabel Position="0" LabelContent="0-1"/>

<syncfusion:ChartAxisLabel Position="1" LabelContent="1-2"/>

<syncfusion:ChartAxisLabel Position="2" LabelContent="2-3"/>

<syncfusion:ChartAxisLabel Position="3" LabelContent="3-4"/>

<syncfusion:ChartAxisLabel Position="4" LabelContent="4-5"/>

<syncfusion:ChartAxisLabel Position="5" LabelContent="5-5"/>

</syncfusion:CategoryAxis.CustomLabels>

</syncfusion:CategoryAxis>

</syncfusion:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

CategoryAxis axis = new CategoryAxis();

axis.CustomLabels.Add(new ChartAxisLabel() { Position = 0, LabelContent = "0-1" });

axis.CustomLabels.Add(new ChartAxisLabel() { Position = 1, LabelContent = "1-2" });

axis.CustomLabels.Add(new ChartAxisLabel() { Position = 2, LabelContent = "2-3" });

axis.CustomLabels.Add(new ChartAxisLabel() { Position = 3, LabelContent = "3-4" });

axis.CustomLabels.Add(new ChartAxisLabel() { Position = 4, LabelContent = "4-5" });

axis.CustomLabels.Add(new ChartAxisLabel() { Position = 5, LabelContent = "5-5" });

chart.PrimaryAxis = axis;

{% endhighlight %}

{% endtabs %}

![Axis label customization support in UWP Chart](Axis_images/Axis_img35.jpg)


You can also directly bind the collection of labels to the [`LabelsSource`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis~LabelsSource.html#) property for defining custom labels. The following code example demonstrates how to define a label collection in code behind and binding the property in XAML page.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.PrimaryAxis>

<syncfusion:CategoryAxis LabelsSource="{Binding Labels}" ContentPath="Content" PositionPath="Position">

</syncfusion:CategoryAxis>

</syncfusion:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight C# %}

chart.PrimaryAxis = new CategoryAxis()
{

    ContentPath ="Content",

    PositionPath = "Position",

    LabelsSource = Labels

};


public List<LabelItem> Labels { get; set; }

Labels = new List<LabelItem>
{

    new LabelItem() {Position=0, Content = "0-1"},

    new LabelItem() {Position=1, Content = "1-2"},

    new LabelItem() {Position=2, Content = "2-3"},

    new LabelItem() {Position=3, Content = "3-4"},

    new LabelItem() {Position=4, Content = "4-5"},

    new LabelItem() {Position=5, Content = "5-6"},

    new LabelItem() {Position=6, Content = "6-7"},

    new LabelItem() {Position=7, Content = "7-8"},

};

public class LabelItem
{

    public string Content { get; set; }

    public int Position { get; set; }

}

{% endhighlight %}

{% endtabs %}

![Axis label customization support in UWP Chart](Axis_images/Axis_img36.jpg)

## Add units to labels

You can customize the axis label to display its measuring units by adding a prefix or a suffix. This feature can be achieved using the [`PrefixLabelTemplate`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis~PrefixLabelTemplate.html) and [`PostfixLabelTemplate`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis~PostfixLabelTemplate.html) properties.

The following code example and screenshot demonstrate the usage of [`PrefixLabelTemplate`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis~PrefixLabelTemplate.html).

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

![Adding units to axis labels in UWP Chart](Axis_images/Axis_img29.png)



The following code example and screenshot demonstrate the usage of [`PostfixLabelTemplate`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis~PostfixLabelTemplate.html).

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

![Adding units to axis labels in UWP Chart](Axis_images/Axis_img30.png)



## Formatting axis labels

[`SfChart`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.SfChart.html) provides the [`LabelFormat`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis~LabelFormat.html) property for defining the custom formatting for the axis labels. This property supports all standard formatting type of numerical and date time values.

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

![Axis labels formatting support in UWP Chart](Axis_images/Axis_img31.png)



## Styling Header and Labels

[`SfChart`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.SfChart.html) provides support to customize the axis [`Header`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis~Header.html) and label. The following APIs are used to customize the header and label.

[`HeaderStyle`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis~HeaderStyle.html) and [`LabelStyle`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis~LabelStyle.html)

<table>
<tr>
<th>
Property</th><th>
Definition</th></tr>
<tr>
<td>
HeaderStyle</td><td>
Gets or sets the style for the axis header. The header’s {{'[`Foreground`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.LabelStyle~Foreground.html), {{'[`FontSize`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.LabelStyle~FontSize.html)'| markdownify }} and {{'[`FontFamily`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.LabelStyle~FontFamily.html)'| markdownify }} are customized using this property.</td></tr>
<tr>
<td>
LabelStyle</td><td>
Gets or sets the style for the axis labels. The label’s {{'[`Foreground`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.LabelStyle~Foreground.html), {{'[`FontSize`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.LabelStyle~FontSize.html)'| markdownify }} and {{'[`FontFamily`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.LabelStyle~FontFamily.html)'| markdownify }} are customized using this property.</td></tr>
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

[`ChartAxis`](https://help.syncfusion.com/uwp/sfchart/axis) provides support to place border around its label.To place the border around axis, we should enable  [`ShowLabelBorder`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxisBase2D~ShowLabelBorder.html) property of axis and it can be set as shown in the below code snippet,

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

![Axis labels border support in UWP Chart](Axis_images/label1.png)

The border color and width can be customized with [`LabelBorderBrush`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxisBase2D~LabelBorderBrush.html) and [`LabelBorderWidth`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxisBase2D~LabelBorderWidth.html) properties of chart axis and it can be set as shown in the below code snippet,

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

![Axis labels border support in UWP Chart](Axis_images/label2.png)


## GridLines and TickLines 

### GridLines

By default, gridlines are automatically added to the [`ChartAxis`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis.html) in its defined intervals. [`SfChart`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.SfChart.html) supports customization of gridline. You can control the visibility of the gridlines using the [`ShowGridLines`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis~ShowGridLines.html) property. 

The following code example and screenshot show [`ShowGridLines`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis~ShowGridLines.html) set to False.

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

![Gridlines customization support in UWP Chart](Axis_images/Axis_img32.png)



### Ticklines

Ticklines are small markers extending from the gridlines, used to indicate the axis scaling. Tickline can be positioned either inside or outside of the axis line.

The following code example and screenshot illustrate major and small ticklines set to [`Inside`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.AxisElementPosition.html).

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

![Ticklines customization support in UWP Chart](Axis_images/Axis_img33.png)



You can customize the appearance of major gridline, minor gridlines and ticklines using the [`MajorTickLineStyle`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis~MajorTickLineStyle.html), [`MinorTickLineStyle`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis~MinorTickLineStyle.html), [`MajorGridLineStyle`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis~MajorGridLineStyle.html) and [`MinorGridLineStyle`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis~MinorGridLineStyle.html) properties. Also axis lines can be customized using [`AxisLineStyle`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis~AxisLineStyle.html) as follows.

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

![Gridlines customization support in UWP Chart](Axis_images/Axis_img34.jpg)



## Multi-level Labels

[`Axis`](https://help.syncfusion.com/uwp/sfchart/axis) can be customized with multiple levels of label by using its [`MultiLevelLabels`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxisBase2D~MultiLevelLabels.html) property. These labels are placed based on the provided [`Start`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartMultiLevelLabel~Start.html) and [`End`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartMultiLevelLabel~End.html) range values and we can add any number of labels to an axis. The below code snippet shows how to set a multilevel label,

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

![Multi-level axis labels support in UWP Chart](Axis_images/label3.png)

**Regarding** **Start** **and** **End** **Property**

[`Start`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartMultiLevelLabel~Start.html) and [`End`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartMultiLevelLabel~End.html) properties of [`ChartMultiLevelLabel`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartMultiLevelLabel.html) are type of objects, we can provide the start and end values for a multi-level label based on its Axis type. It is described  in the following table,

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

[`ChartMultiLevelLabel's`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartMultiLevelLabel.html) border width and color can be customized with [`LabelBorderWidth`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxisBase2D~LabelBorderWidth.html) and [`LabelBorderBrush`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxisBase2D~LabelBorderBrush.html) properties of chart axis.It can be set as shown in the below code snippet,

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

![Axis border customization support in UWP Chart](Axis_images/label4.png)


**Border** **Type**

[`ChartAxis`](https://help.syncfusion.com/uwp/sfchart/axis) provides support to various types of border for [`ChartMultiLevelLabels`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartMultiLevelLabel.html) and it can be applied by using its [`MultiLevelLabelsBorderType`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxisBase2D~MultiLevelLabelsBorderType.html) property.The default [`MultiLevelLabelsBorderType`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxisBase2D~MultiLevelLabelsBorderType.html) is [`Rectangle`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.BorderType.html). The another supported border types are [`Brace`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.BorderType.html),[`None`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.BorderType.html) and [`WithoutTopAndBottomBorder`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.BorderType.html).

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

![Axis border customization support in UWP Chart](Axis_images/label5.png)


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

![Axis border customization support in UWP Chart](Axis_images/label6.png)

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

![Axis border customization support in UWP Chart](Axis_images/label7.png)

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

![Axis border customization support in UWP Chart](Axis_images/label8.png)


**Text** **Customization**

[`ChartMultiLevelLabel's`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartMultiLevelLabel.html) text can be customized with its [`FontSize`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartMultiLevelLabel~FontSize.html), [`FontFamily`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartMultiLevelLabel~FontFamily.html) and [`Foreground`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartMultiLevelLabel~Foreground.html) property and it is shown in below code snippet,

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

![Multi-level axis labels text customization support in UWP Chart](Axis_images/label9.png)


**Label** **Alignment**

The text of [`ChartMultiLevelLabel`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartMultiLevelLabel.html) can be aligned with its [`LabelAlignment`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartMultiLevelLabel~LabelAlignment.html) property. The default value of [`LabelAlignment`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartMultiLevelLabel~LabelAlignment.html) property is [`Center`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.LabelAlignment.html).

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

![Multi-level axis label alignment support in UWP Chart](Axis_images/label13.png)


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

![Multi-level axis label alignment support in UWP Chart](Axis_images/label10.png)


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

![Multi-level axis label alignment support in UWP Chart](Axis_images/label11.png)

The text of [`ChartMultiLevelLabel`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartMultiLevelLabel.html) text will automatically trim, when the text width exceeds the width of [`ChartMultiLevelLabel`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartMultiLevelLabel.html) and it is shown below,

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

![Multi-level axis label alignment support in UWP Chart](Axis_images/label12.png)

## Events

### ActualRangeChanged

The [`ActualRangeChanged`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis~ActualRangeChanged_EV.html) event occurs when an axis range is changed. This argument contains the following information.

* [`ActualMinimum`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ActualRangeChangedEventArgs~ActualMinimum.html) - Gets or sets the actual minimum value of axis.
* [`ActualMaximum`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ActualRangeChangedEventArgs~ActualMaximum.html) - Gets or sets the actual maximum value of axis.
* [`VisibleMinimum`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ActualRangeChangedEventArgs~VisibleMinimum.html) - Gets or sets the visible minimum value of axis.
* [`VisibleMaximum`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ActualRangeChangedEventArgs~VisibleMaximum.html) - Gets or sets the visible maximum value of axis.
* [`ActualInterval`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ActualRangeChangedEventArgs~ActualInterval.html) - Gets the actual interval of axis.

### LabelCreated

The [`LabelCreated`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis~LabelCreated_EV.html) event occurs when the axis label is created. This argument contains [`AxisLabel`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.LabelCreatedEventArgs~AxisLabel.html) of [`ChartAxisLabel`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxisLabel.html), which contains the following properties.

* [`LabelContent`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxisLabel~LabelContent.html) - Gets or sets the content of label.
* [`Position`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxisLabel~Position.html) - Gets or sets the position of label.

### AxisBoundChanged

The [`AxisBoundChanged`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxis~AxisBoundsChanged_EV.html) event occurs when the bounds of the axis are changed. This argument contains the following information.

* [`NewBounds`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxisBoundsEventArgs~NewBounds.html) - Gets the new axis bounds.
* [`OldBounds`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxisBoundsEventArgs~OldBounds.html) - Gets the old axis bounds.

### LabelClicked

The [`LabelClicked`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxisBase2D~LabelClicked_EV.html) event is triggered when labels are clicked. Supports for 2D axis. The argument contains [`AxisLabel`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.AxisLabelClickedEventArgs~AxisLabel.html) of [`ChartAxisLabel`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxisLabel.html), which contains the following properties.

* [`LabelContent`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxisLabel~LabelContent.html) - Gets the content of label.
* [`Position`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxisLabel~Position.html) - Gets the position of label.
* [`PrefixLabelTemplate`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxisLabel~PrefixLabelTemplate.html) - Gets the prefix template of label.
* [`PostfixLabelTemplate`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartAxisLabel~PostfixLabelTemplate.html) - Gets the postfix template of label.


