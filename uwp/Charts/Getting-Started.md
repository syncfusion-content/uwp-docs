---
layout: post
title: Getting Started | SfChart | uwp | Syncfusion
description: Explains you the steps required to populate the Chart with data, header, add data labels, legend and tooltips to the Chart.
platform: uwp
control: SfChart
documentation: ug
---

# Getting Started

This section explains you the steps required to populate the Chart with data, header, add data labels, legend and tooltips to the Chart. This section covers only the minimal features that you need to know to get started with the Chart.

## Adding Chart Reference

Refer this [article](https://help.syncfusion.com/uwp/add-syncfusion-controls) to know how to add Syncfusion controls in Visual Studio projects through various way. You can also refer [this](https://help.syncfusion.com/uwp/control-dependencies) link to know about the assemblies required for adding Chart to your project. 
 
## Initialize Chart

Import the [`SfChart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html) namespace as shown below in your respective Page,

{% tabs %} 

{% highlight xaml %} 

xmlns:syncfusion="using:Syncfusion.UI.Xaml.Charts"

{% endhighlight %}

{% highlight C# %} 

using Syncfusion.UI.Xaml.Charts;

{% endhighlight %}

{% highlight VB %} 

Imports Syncfusion.UI.Xaml.Charts

{% endhighlight %}

{% endtabs %} 

Then initialize an empty chart with two axes as shown below,

{% tabs %} 

{% highlight xaml %} 

 <syncfusion:SfChart> 
      <syncfusion:SfChart.PrimaryAxis> 
           <syncfusion:CategoryAxis /> 
      </syncfusion:SfChart.PrimaryAxis> 
      <syncfusion:SfChart.SecondaryAxis> 
           <syncfusion:NumericalAxis/> 
      </syncfusion:SfChart.SecondaryAxis>
 </syncfusion:SfChart>

{% endhighlight %}

{% highlight C# %} 

SfChart chart = new SfChart();

CategoryAxis primaryAxis = new CategoryAxis();

chart.PrimaryAxis = primaryAxis; 
   
NumericalAxis secondaryAxis = new NumericalAxis();

chart.SecondaryAxis = secondaryAxis;

{% endhighlight %}

{% highlight VB %}

Dim chart As New SfChart()

Dim primaryAxis As New CategoryAxis () 

chart.PrimaryAxis = primaryAxis 

Dim secondaryAxis As New NumericalAxis ()  

chart.SecondaryAxis = secondaryAxis

{% endhighlight %}

{% endtabs %} 

Run the project and check if you get following output to make sure you have configured your project properly to add [`SfChart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html).

![Initializing UWP Chart](Getting-Started_images/img1.png)

N> [`SfChart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html) supports default axes, so that these axes ([`PrimaryAxis`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html#Syncfusion_UI_Xaml_Charts_SfChart_PrimaryAxis) and [`SecondaryAxis`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html#Syncfusion_UI_Xaml_Charts_SfChart_SecondaryAxis)) will get generated automatically based upon the data bind to the chart, if you didn’t specify the axes explicitly. 

## Initialize view model

Now, let us define a simple data model that represents a data point in [`SfChart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html).

{% tabs %}

{% highlight c# %}

public class Person   
{   
    public string Name { get; set; }

    public double Height { get; set; }
}

{% endhighlight %} 

{% highlight VB %}

Public Class Person

    Public Property Name As String

    Public Property Height As Double

End Class

{% endhighlight %} 

{% endtabs %}

Next, create a view model class and initialize a list of `Person` objects as shown below,

{% tabs %}

{% highlight c# %}

public class ViewModel  
{
      public List<Person> Data { get; set; }      

      public ViewModel()       
      {
            Data = new List<Person>()
            {
                new Person { Name = "David", Height = 180 },
                new Person { Name = "Michael", Height = 170 },
                new Person { Name = "Steve", Height = 160 },
                new Person { Name = "Joel", Height = 182 }
            }; 
       }
 }

{% endhighlight %} 

{% highlight VB %}

Public Class ViewModel

    Public Property Data As List(Of Person)

    Public Sub New()
        Data = New List(Of Person)() From
        {
            New Person With {.Name = "David", .Height = 180},
            New Person With {.Name = "Michael", .Height = 170},
            New Person With {.Name = "Steve", .Height = 160},
            New Person With {.Name = "Joel", .Height = 182}
        }
    End Sub
End Class

{% endhighlight %}

{% endtabs %} 

Set the `ViewModel` instance as the `DataContext` of your Page; this is done to bind properties of `ViewModel` to [`SfChart`.](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html)
 
N> Add namespace of `ViewModel` class in your XAML page if you prefer to set `DataContext` in XAML.

{% tabs %} 

{% highlight xaml %} 

<Page
    x:Class="ChartDemo.MainPage"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:local="using:ChartDemo"
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
    xmlns:syncfusion="using:Syncfusion.UI.Xaml.Charts"
    mc:Ignorable="d">

    <Page.DataContext>
        <local:ViewModel/>
    </Page.DataContext>

</Page> 

{% endhighlight %}

{% highlight C# %} 

this.DataContext = new ViewModel();

{% endhighlight %}

{% highlight VB %} 

Me.DataContext = New ViewModel()

{% endhighlight %}

{% endtabs %} 

## Populate Chart with data

As we are going to visualize the comparison of heights in the data model, add [`ColumnSeries`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ColumnSeries.html) to [`SfChart.Series`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html#Syncfusion_UI_Xaml_Charts_SfChart_Series) property, and then bind the `Data` property of the above `ViewModel` to the [`ColumnSeries.ItemsSource`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_ItemsSource) property as shown below.

N> You need to set [`XBindingPath`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_XBindingPath) and [`YBindingPath`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.XyDataSeries.html#Syncfusion_UI_Xaml_Charts_XyDataSeries_YBindingPath) properties, so that [`SfChart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html) would fetch values from the respective properties in the data model to plot the series.

{% tabs %}   

{% highlight xaml %}

<syncfusion:SfChart>
   
  <syncfusion:SfChart.PrimaryAxis>
    
      <syncfusion:CategoryAxis Header="Name" />             
   
  </syncfusion:SfChart.PrimaryAxis>

  <syncfusion:SfChart.SecondaryAxis>
  
      <syncfusion:NumericalAxis Header="Height(in cm)" >                        

  </syncfusion:SfChart.SecondaryAxis>
    
   <syncfusion:ColumnSeries  ItemsSource="{Binding Data}" XBindingPath="Name" YBindingPath="Height" >
  </syncfusion:ColumnSeries>

 </syncfusion:SfChart> 

{% endhighlight %}

{% highlight C# %}

SfChart chart = new SfChart();

//Adding horizontal axis to the chart 

CategoryAxis primaryAxis = new CategoryAxis();

primaryAxis.Header = "Name";      

chart.PrimaryAxis = primaryAxis;


//Adding vertical axis to the chart 

NumericalAxis secondaryAxis = new NumericalAxis();

secondaryAxis.Header = "Height(in cm)";          

chart.SecondaryAxis = secondaryAxis;


//Initialize the two series for SfChart
ColumnSeries series = new ColumnSeries();

series.ItemsSource = (new ViewModel()).Data;
series.XBindingPath = "Name";            
series.YBindingPath = "Height";         
            
//Adding Series to the Chart Series Collection
chart.Series.Add(series);

{% endhighlight %}

{% highlight VB %}

Dim chart As New SfChart()

'Adding horizontal axis to the chart 

Dim primaryAxis As New CategoryAxis()

primaryAxis.Header = "Name"
chart.PrimaryAxis = primaryAxis


'Adding vertical axis to the chart  

Dim secondaryAxis As New NumericalAxis()

secondaryAxis.Header = "Height(in cm)"

chart.SecondaryAxis = secondaryAxis        

'Initialize the two series for SfChart
Dim series As New ColumnSeries()

series.ItemsSource = New ViewModel().Demands
series.XBindingPath = "Name"
series.YBindingPath = "Height"
        
'Adding Series to the Chart Series Collection

chart.Series.Add(series)

{% endhighlight %}

{% endtabs %} 

N> Syncfusion Chart also supports rendering combination of multiple series. Refer [`this`](https://help.syncfusion.com/uwp/sfchart/area#multiple-area) for details.

## Add Title

The header of the chart acts as the title, to provide quick information to the user about the data being plotted in the chart. You can set title using  [`Header`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartAxis.html#Syncfusion_UI_Xaml_Charts_ChartAxis_Header) property of chart as shown below.

{% tabs %} 

{% highlight xaml %}

<Grid> 

   <syncfusion:SfChart Header="Chart" > 

   </syncfusion:SfChart> 

</Grid>

{% endhighlight %}

{% highlight C# %} 

chart.Header = "Chart";

{% endhighlight %}

{% highlight VB %}

chart.Header = "Chart"

{% endhighlight %}

{% endtabs %}  


## Enable data labels

You can add data labels to improve the readability of the chart and it can be enabled using [`AdornmentInfo`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfo.html) property of [`ChartSeries`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSeries.html). By default, there is no label displayed, you have to set [`ShowLabel`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_ShowLabel) property of [`ChartAdornmentInfo`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfo.html) as True.

{% tabs %} 

{% highlight xaml %}

<syncfusion:SfChart>

	...

  <syncfusion:ColumnSeries > 
     <syncfusion:ColumnSeries.AdornmentsInfo>
          <syncfusion:ChartAdornmentInfo ShowLabel="True"/> 
     </syncfusion:ColumnSeries.AdornmentsInfo> 
  </syncfusion:ColumnSeries>     

	...

</syncfusion:SfChart>

{% endhighlight %}

{% highlight C# %} 

series.AdornmentsInfo = new ChartAdornmentInfo (){ ShowLabel = true }; 

{% endhighlight %}

{% highlight VB %} 

series.AdornmentsInfo = New ChartAdornmentInfo() With {.ShowLabel = True} 

{% endhighlight %}

{% endtabs %}  

Refer [`this`](https://help.syncfusion.com/uwp/sfchart/adornments) link  to learn more about the options available in [`SfChart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html) to customize chart adornments.

## Enable legend

You can enable legend using [`SfChart.Legend`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartBase.html#Syncfusion_UI_Xaml_Charts_ChartBase_Legend) property as shown below,

{% tabs %} 

{% highlight xaml %}

<syncfusion:SfChart>

	...

    <syncfusion:SfChart.Legend>

        <syncfusion:ChartLegend/>

    </syncfusion:SfChart.Legend>

    ...

</syncfusion:SfChart>

{% endhighlight %}

{% highlight C# %} 

chart.Legend = new ChartLegend (); 

{% endhighlight %}

{% highlight VB %} 

chart.Legend = New ChartLegend () 

{% endhighlight %}

{% endtabs %}  

Additionally, you need to set label for each series using [`Label`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_Label) property of ChartSeries, which will be displayed in corresponding legend.

{% tabs %} 

{% highlight xaml %}

<syncfusion:SfChart>

	...

      <syncfusion:ColumnSeries Label="Heights" ItemsSource="{Binding Data}" XBindingPath="Name" YBindingPath="Height" />

	...

</syncfusion:SfChart>

{% endhighlight %}

{% highlight C# %} 

ColumnSeries series = new ColumnSeries (); 
series.ItemsSource = (new ViewModel()).Data;
series.XBindingPath = "Name"; 
series.YBindingPath = "Height"; 
series.Label = "Heights";

{% endhighlight %}

{% highlight VB %} 

Dim series As New ColumnSeries () 
series.ItemsSource = New ViewModel().Data
series.XBindingPath = "Name" 
series.YBindingPath = "Height" 
series.Label = "Heights"

{% endhighlight %}

{% endtabs %}  

Refer this [`link`](https://help.syncfusion.com/uwp/sfchart/legend) to learn more about the options available in [`SfChart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html) to customize legend.

## Enable tooltip

Tooltips are used to show information about the segment, when you click on the segment. You can enable tooltip by setting series [`ShowTooltip`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_ShowTooltip)  property to true.

{% tabs %} 

{% highlight xaml %}

<syncfusion:SfChart>

	...

   <syncfusion:ColumnSeries ShowTooltip="True" ItemsSource="{Binding Data}" XBindingPath="Name" YBindingPath="Height"/>

	...

</syncfusion:SfChart> 

{% endhighlight %}

{% highlight C# %} 

ColumnSeries series = new ColumnSeries();
series.ItemsSource = (new ViewModel()).Data;
series.XBindingPath = "Name";          
series.YBindingPath = "Height";
series.ShowTooltip = true;

{% endhighlight %}

{% highlight VB %} 

Dim series As New ColumnSeries () 
series.ItemsSource = New ViewModel().Data
series.XBindingPath = "Name" 
series.YBindingPath = "Height" 
series.ShowTooltip = True

{% endhighlight %}

{% endtabs %}

Refer [`this`](https://help.syncfusion.com/uwp/sfchart/interactive-features#tooltip) link to learn more about the options available in [`SfChart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html) to customize tooltip.

The following code example gives you the complete code of above configurations.

{% tabs %} 

{% highlight xaml %}

<Page
    x:Class="ChartDemo.MainPage"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:local="using:ChartDemo"
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
    xmlns:syncfusion="using:Syncfusion.UI.Xaml.Charts"
    mc:Ignorable="d">

    <!--Setting DataContext for SfChart-->
    <Page.DataContext>
        <local:ViewModel/>
    </Page.DataContext>

    <Grid Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">

        <syncfusion:SfChart Header="Chart" Height="300" Width="500">
            <!--Initialize the horizontal axis for SfChart-->
            <syncfusion:SfChart.PrimaryAxis>
                <syncfusion:CategoryAxis Header="Name" FontSize="14"/>
            </syncfusion:SfChart.PrimaryAxis>

            <!--Initialize the vertical axis for SfChart-->
            <syncfusion:SfChart.SecondaryAxis>
                <syncfusion:NumericalAxis Header="Height(in cm)" FontSize="14"/>
            </syncfusion:SfChart.SecondaryAxis>

            <!--Adding Legend to the SfChart-->
            <syncfusion:SfChart.Legend>
                <syncfusion:ChartLegend/>
            </syncfusion:SfChart.Legend>

            <!--Initialize the series for SfChart-->
            <syncfusion:ColumnSeries Label="Heights" ItemsSource="{Binding Data}" XBindingPath="Name" YBindingPath="Height" ShowTooltip="True" >
                <syncfusion:ColumnSeries.AdornmentsInfo>
                    <syncfusion:ChartAdornmentInfo ShowLabel="True" >
                    </syncfusion:ChartAdornmentInfo>
                </syncfusion:ColumnSeries.AdornmentsInfo>
            </syncfusion:ColumnSeries>
                      
        </syncfusion:SfChart>

    </Grid>
</Page>
 
{% endhighlight %}

{% highlight C# %} 

using Syncfusion.UI.Xaml.Charts;

namespace ChartDemo
{
    
    public sealed partial class MainPage : Page
    {
        public MainPage()
        {
            this.InitializeComponent();
            
            SfChart chart = new SfChart() { Header = "Chart", Height = 300, Width = 500 };

            //Adding horizontal axis to the chart 
            CategoryAxis primaryAxis = new CategoryAxis();
            primaryAxis.Header = "Name";
            primaryAxis.FontSize = 14;
            chart.PrimaryAxis = primaryAxis;

            //Adding vertical axis to the chart 
            NumericalAxis secondaryAxis = new NumericalAxis();
            secondaryAxis.Header = "Height(in cm)";
            secondaryAxis.FontSize = 14;
            chart.SecondaryAxis = secondaryAxis;

            //Adding Legends for the chart
            ChartLegend legend = new ChartLegend();
            chart.Legend = legend;

            //Initializing column series
            ColumnSeries series = new ColumnSeries();
            series.ItemsSource = (new ViewModel()).Data;
            series.XBindingPath = "Name";            
            series.YBindingPath = "Height";
            series.ShowTooltip = true;
            series.Label = "Heights";      

            //Setting adornment to the chart series
            series.AdornmentsInfo = new ChartAdornmentInfo() { ShowLabel = true };

            //Adding Series to the Chart Series Collection
            chart.Series.Add(series);
            this.Content = chart;
                      
        }
    }   
}

{% endhighlight %}

{% highlight VB %}

Imports Syncfusion.UI.Xaml.Charts
Public NotInheritable Class MainPage
    Inherits Page  
    Public Sub New()
        InitializeComponent()

        Dim chart As New SfChart()
        chart.Header = "Chart"
        chart.Height = 300
        chart.Width = 500

        'Adding horizontal axis to the chart 

        Dim primaryAxis As New CategoryAxis()
        primaryAxis.Header = "Name"
        primaryAxis.FontSize = 14
        chart.PrimaryAxis = primaryAxis

        'Adding vertical axis to the chart  

        Dim secondaryAxis As New NumericalAxis()
        secondaryAxis.Header = "Height(in cm)"
        secondaryAxis.FontSize = 14
        chart.SecondaryAxis = secondaryAxis

        'Adding Legends for the chart
        Dim legend As New ChartLegend()
        chart.Legend = legend

        'Initializing column series
        Dim series As New ColumnSeries()
        series.ItemsSource = New ViewModel().Data
        series.XBindingPath = "Name"
        series.YBindingPath = "Height"
        series.Label = "Heights"
        series.ShowTooltip = True

        'Setting adornment to the chart series
        series.AdornmentsInfo = New ChartAdornmentInfo() With {.ShowLabel = True}       

        'Adding Series to the Chart Series Collection

        chart.Series.Add(series)

        Me.Content = chart

    End Sub
End Class

{% endhighlight %}

{% endtabs %}

The following chart is created as a result of the above codes.

![Tooltip support in UWP Chart](Getting-Started_images/img3.png)

You can find the complete getting started sample from this [link](https://www.syncfusion.com/downloads/support/directtrac/general/ze/SfChart-GettingStarted1293886778.zip).

