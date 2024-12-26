---
layout: post
title: Interactive Features in UWP Charts control | Syncfusion®
description: Learn here all about Interactive Features support in Syncfusion® UWP Charts (SfChart) control and more.
platform: uwp
control: SfChart
documentation: ug
---

# Interactive Features in UWP Charts (SfChart)

[`SfChart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html) provides interactive features such as zooming, selection, and tracking data points.

The following interactive features are supported in SfChart.

* Tooltip
* TrackBall
* Visual Data Editing
* Zoom and Pan
* Selection
* Resizing Scrollbar
* CrossHair

## Tooltip

The [`Tooltip`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase.html#Syncfusion_UI_Xaml_Charts_XySegmentDraggingBase_Tooltip) feature allows you to display any information over a [`ChartSeries`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSeries.html). It is used in conjunction with the pointer or at the data point position. It appears when the mouse hovers over any chart segment. It is set to display the metadata of the particular segment or data point.

By default, a small box containing the data points y values are displayed as the Tooltip. The y values vary depending on the [`ChartSeries`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSeries.html). For example, a single y value is usually displayed in the Column and [`BarSeries`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.BarSeries.html). In the [`FinancialSeries`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.FinancialSeriesBase.html), high, low, open, and close values are displayed in Tooltip.

The tooltip will be visible if you enable [`ShowTooltip`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_ShowTooltip) property as in the below code snippet.

{% tabs %}

{% highlight xaml %}

<syncfusion:ColumnSeries  ShowTooltip="True"                                                  

ItemsSource="{Binding Demands}" 

XBindingPath="Demand"  YBindingPath="Year2010"/>

<syncfusion:ColumnSeries ItemsSource="{Binding Demands}" 

ShowTooltip="True"                           

XBindingPath="Demand"  YBindingPath="Year2011"/>           

{% endhighlight %}

{% highlight c# %}

ColumnSeries series1 = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    ShowTooltip = true

};

ColumnSeries series2 = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2011",

    ShowTooltip = true

};

chart.Series.Add(series1);

chart.Series.Add(series2);

{% endhighlight %}

{% endtabs %}

![Tooltip support in UWP Chart](interactive-features_images/uwp-charts-interactive-features-tooltip.png)

### Customizing tooltip using ChartTooltipBehavior

The [`ChartTooltipBehavior`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTooltipBehavior.html) is commonly used for all series to customize the tooltip. For customizing the tooltip, you can create an instance [`ChartTooltipBehavior`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTooltipBehavior.html) and add it to the SfChart Behaviors collection.

The following properties are used to customize and configure tooltip which is available in the [`ChartTooltipBehavior`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTooltipBehavior.html).

* [`EnableAnimation`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTooltipBehavior.html?tabs=tabid-1#Syncfusion_UI_Xaml_Charts_ChartTooltipBehavior_EnableAnimation) - Used to enable the animation when showing the tooltip.
* [`Position`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTooltipBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTooltipBehavior_Position) - Used to position the tooltip at the data point position or the cursor position.
* [`Style`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTooltipBehavior.html?tabs=tabid-1#Syncfusion_UI_Xaml_Charts_ChartTooltipBehavior_Style) - Used to customize the fill and stroke of the tooltip.
* [`LabelStyle`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTooltipBehavior.html?tabs=tabid-1#Syncfusion_UI_Xaml_Charts_ChartTooltipBehavior_LabelStyle) - Used to customize the tooltip label.
* [`HorizontalOffset`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTooltipBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTooltipBehavior_HorizontalOffset) - Used to position the tooltip at a distance from the data point or cursor position horizontally.
* [`VerticalOffset`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTooltipBehavior.html?tabs=tabid-1#Syncfusion_UI_Xaml_Charts_ChartTooltipBehavior_VerticalOffset) - Used to position the tooltip at a distance from the data point or cursor position vertically.
* [`HorizontalAlignment`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTooltipBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTooltipBehavior_HorizontalAlignment) - Used to align the tooltip label at left, right and center of the data point position or cursor position horizontally.
* [`VerticalAlignment`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTooltipBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTooltipBehavior_VerticalAlignment) - Used to align the tooltip label at top, center and bottom of the data point position or cursor position vertically.
* [`ShowDuration`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTooltipBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTooltipBehavior_ShowDuration) - Used to set the amount of time that the tooltip remains visible in milliseconds.
* [`InitialShowDelay`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTooltipBehavior.html?tabs=tabid-1#Syncfusion_UI_Xaml_Charts_ChartTooltipBehavior_InitialShowDelay) - Used to delay in milliseconds to show the tooltip once the user interacts with series.

{% tabs %}

{% highlight xml %}

<chart:SfChart.Behaviors>

<chart:ChartTooltipBehavior/>                                                  

</chart:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();

ChartTooltipBehavior behavior = new ChartTooltipBehavior();

chart.Behaviors.Add(behavior);

{% endhighlight %}

{% endtabs %}

### Positioning the tooltip

Tooltip can be positioned at the data point position or the cursor position using the [`Position`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTooltipBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTooltipBehavior_Position) property. The `Auto` will position the tooltip at the data point position and the `Pointer` will display the tooltip in conjunction with the mouse pointer itself when hovering the mouse inside any chart segment.

N> By default, the tooltip [`Position`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTooltipBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTooltipBehavior_Position) is set to Auto.

The following code example explains positioning the tooltip at `Pointer` position.

{% tabs %}

{% highlight xml %}

<chart:SfChart.Behaviors>

<chart:ChartTooltipBehavior x:Name="chartTooltipBehavior" Position="Pointer"/>                                               

</chart:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...
ChartTooltipBehavior chartTooltipBehavior = new ChartTooltipBehavior();
chartTooltipBehavior.Position = TooltipPosition.Pointer;
chart.Behaviors.Add(chartTooltipBehavior);

{% endhighlight %}

{% endtabs %}

![Tooltip at pointer position in WPF Chart](interactive-features_images/uwp-charts-interactive-features-positioning-tooltip.png)

### Customizing the tooltip background

The tooltip's fill and stroke color can be customized using the [`Style`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTooltipBehavior.html?tabs=tabid-1#Syncfusion_UI_Xaml_Charts_ChartTooltipBehavior_Style) property. To define a style for tooltip background, specify the style of `TargetType` as `Path.`

The following code example explains applying the style for tooltip.

{% tabs %}

{% highlight xml %}

<chart:SfChart.Resources>
    <Style TargetType="Path" x:Key="style">
       <Setter Property="Stroke" Value="Gray"/>
       <Setter Property="Fill" Value="Black"/>
    </Style>
</chart:SfChart.Resources>
...
<chart:SfChart.Behaviors>
    <chart:ChartTooltipBehavior LabelStyle = {StaticResource style}/>
</chart:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
Style style = new Style(typeof(Path));
style.Setters.Add(new Setter(Path.StrokeProperty, new SolidColorBrush(Colors.Gray)));
style.Setters.Add(new Setter(Path.FillProperty, new SolidColorBrush(Colors.Black)));
...
ChartTooltipBehavior tooltipBehavior = new ChartTooltipBehavior();
tooltipBehavior.Style = style;
chart.Behaviors.Add(tooltipBehavior);

{% endhighlight %}

{% endtabs %}

![Tooltip background style customization in WPF Chart](interactive-features_images/uwp-charts-interactive-features-customizing-tooltip.png)

### Customizing the tooltip label style

The tooltip label style can be customized using the [`LabelStyle`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTooltipBehavior.html?tabs=tabid-1#Syncfusion_UI_Xaml_Charts_ChartTooltipBehavior_LabelStyle) property. To define a style for the tooltip label, specify the style of `TargetType` as `TextBlock.`

The following code example explains applying the style for a tooltip label.

{% tabs %}

{% highlight xml %}

<chart:SfChart.Resources>
    <Style TargetType="TextBlock" x:Key="labelStyle">
       <Setter Property="FontSize" Value="14"/>
       <Setter Property="Foreground" Value="Red"/>
    </Style>
</chart:SfChart.Resources>
...
<chart:SfChart.Behaviors>
   <chart:ChartTooltipBehavior LabelStyle = {StaticResource labelStyle}/>
</chart:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
Style labelStyle = new Style(typeof(TextBlock));
labelStyle.Setters.Add(new Setter(TextBlock.FontSizeProperty, 14d));
labelStyle.Setters.Add(new Setter(TextBlock.ForegroundProperty, new SolidColorBrush(Colors.Red)));
...
ChartTooltipBehavior tooltipBehavior = new ChartTooltipBehavior();
tooltipBehavior.LabelStyle = labelStyle;
chart.Behaviors.Add(tooltipBehavior);

{% endhighlight %}

{% endtabs %}

![Tooltip label style customization in WPF Chart](interactive-features_images/uwp-charts-interactive-features-customizing-tooltip-label-style.png)

### Customizing tooltip using ChartTooltip attached properties

### Aligning the Tooltip

The tooltip can be aligned with respect to the cursor position using [`HorizontalAlignment`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTooltipBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTooltipBehavior_HorizontalAlignment) and [`VerticalAlignment`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTooltipBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTooltipBehavior_VerticalAlignment) properties.

**HorizontalAlignment**

The following code example illustrates the positioning of tooltip to left of the cursor.

{% tabs %}

{% highlight xaml %}

<Chart:ColumnSeries ShowTooltip="True" ItemsSource="{Binding Demands}"  

Chart:ChartTooltip.HorizontalAlignment="Left"

XBindingPath="Demand"  YBindingPath="Year2010" />

<Chart:ColumnSeries ItemsSource="{Binding Demands}" 

Chart:ChartTooltip.HorizontalAlignment="Left" ShowTooltip="True"

XBindingPath="Demand"  YBindingPath="Year2011"/>

{% endhighlight %}

{% highlight c# %}

ColumnSeries series1 = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    ShowTooltip = true
    
};

ChartTooltip.SetHorizontalAlignment(series1, HorizontalAlignment.Left);

ColumnSeries series2 = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2011",

    ShowTooltip = true

};

ChartTooltip.SetHorizontalAlignment(series2, HorizontalAlignment.Left);

chart.Series.Add(series1);

chart.Series.Add(series2);

{% endhighlight %}

{% endtabs %}

![Tooltip alignment support in UWP Chart](interactive-features_images/uwp-charts-interactive-features-horizontal-alignment.png)

N> By default the [`HorizontalAlignment`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTooltipBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTooltipBehavior_HorizontalAlignment) is center for the tooltip.

**VerticalAlignment**

The following code example illustrates the positioning of tooltip to bottom of the cursor.

{% tabs %}

{% highlight xaml %}

<Chart:ColumnSeries ShowTooltip="True" ItemsSource="{Binding Demands}"  

Chart:ChartTooltip.VerticalAlignment="Bottom"

XBindingPath="Demand" YBindingPath="Year2010" />

<Chart:ColumnSeries ItemsSource="{Binding Demands}"

Chart:ChartTooltip.VerticalAlignment="Bottom"

ShowTooltip="True" XBindingPath="Demand"  YBindingPath="Year2011"/>

{% endhighlight %}

{% highlight c# %}

ColumnSeries series1 = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    ShowTooltip = true
    
};

ChartTooltip.SetVerticalAlignment(series1, VerticalAlignment.Bottom);

ColumnSeries series2 = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2011",

    ShowTooltip = true

};

ChartTooltip.SetVerticalAlignment(series2, VerticalAlignment.Bottom);

chart.Series.Add(series1);

chart.Series.Add(series2);

{% endhighlight %}

{% endtabs %}

![Tooltip alignment support in UWP Chart](interactive-features_images/uwp-charts-interactive-features-vertical-alignment.png)

**TooltipMargin**

You can also set the distance for the margin to be positioned from the cursor using the [`TooltipMargin`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTooltip.html#Syncfusion_UI_Xaml_Charts_ChartTooltip_TooltipMarginProperty) property as in the following code sample.

{% tabs %}

{% highlight xaml %}

<Chart:ColumnSeries Label="2010" ShowTooltip="True"

ItemsSource="{Binding Demands}"   Interior="#777777"

Chart:ChartTooltip.TooltipMargin="25"

XBindingPath="Demand" YBindingPath="Year2010" />

<Chart:ColumnSeries Label="2011"  ItemsSource="{Binding Demands}"

Interior="#4A4A4A"

Chart:ChartTooltip.TooltipMargin="25"

ShowTooltip="True" XBindingPath="Demand"  YBindingPath="Year2011"/>

{% endhighlight %}

{% highlight c# %}

ColumnSeries series1 = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    ShowTooltip = true,

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77)),

    Label = "2010"

};

ChartTooltip.SetTooltipMargin(series1, new Thickness(25));

ColumnSeries series2 = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2011",

    ShowTooltip = true,

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0x4A)),

    Label = "2011"

};

ChartTooltip.SetTooltipMargin(series2, new Thickness(25));

chart.Series.Add(series1);

chart.Series.Add(series2);

{% endhighlight %}

{% endtabs %}

![Margin for tooltip in UWP Chart](interactive-features_images/uwp-charts-interactive-features-tooltip-margin1.png)

N>By default the [`VerticalAlignment`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTooltipBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTooltipBehavior_VerticalAlignment) of the Tooltip is Top

**VerticalOffset and HorizontalOffset**

The tooltip can be positioned at a particular distance from the cursor horizontally using [`HorizontalOffset`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTooltipBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTooltipBehavior_HorizontalOffset) and vertically using [`VerticalOffset`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTooltipBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTooltipBehavior_VerticalOffset) properties.

{% tabs %}

{% highlight xaml %}

<Chart:ColumnSeries ShowTooltip="True"

ItemsSource="{Binding Demands}" 

Chart:ChartTooltip.HorizontalOffset="40"

Chart:ChartTooltip.VerticalOffset="40"

XBindingPath="Demand" YBindingPath="Year2010" />

<Chart:ColumnSeries ItemsSource="{Binding Demands}"

Chart:ChartTooltip.HorizontalOffset="40"

Chart:ChartTooltip.VerticalOffset="40" ShowTooltip="True"

XBindingPath="Demand"  YBindingPath="Year2011"/>

{% endhighlight %}

{% highlight c# %}

ColumnSeries series1 = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    ShowTooltip = true,

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77)),

    Label = "2010"

};

ChartTooltip.SetHorizontalOffset(series1, 40);

ChartTooltip.SetVerticalOffset(series1, 40);

ColumnSeries series2 = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2011",

    ShowTooltip = true,

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0x4A)),

    Label = "2011"

};

ChartTooltip.SetHorizontalOffset(series2, 40);

ChartTooltip.SetVerticalOffset(series2, 40);

chart.Series.Add(series1);

chart.Series.Add(series2);

{% endhighlight %}

{% endtabs %}

![VerticalOffset and HorizontalOffset support for tooltip in UWP Chart](interactive-features_images/uwp-charts-interactive-features-offset.png)

### Tooltip Duration

The [`ShowDuration`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTooltipBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTooltipBehavior_ShowDuration) property in the [`ChartTooltip`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTooltip.html) sets the duration time for the tooltip to be displayed in milliseconds.

The following code example demonstrates the duration of the tooltip set as 5 seconds.

{% tabs %}

{% highlight xml %}

<Chart:ColumnSeries ShowTooltip="True"  

Chart:ChartTooltip.ShowDuration="5000"                                          

ItemsSource="{Binding Demands}" Interior="#777777"                                     

XBindingPath="Demand"  YBindingPath="Year2010">                                   

</Chart:ColumnSeries>

{% endhighlight %}

{% highlight c# %}

ColumnSeries series = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    ShowTooltip = true,

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77)),

    Label = "2010"

};

ChartTooltip.SetShowDuration(series, 5000);

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

N> The tooltip by default will be displayed for 1000 milliseconds.

**Show delay**

Tooltip also has support for delay the time to display by setting the [`SetInitialShowDelay`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTooltipBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTooltipBehavior_InitialShowDelay) property in milliseconds.

The following code example explains the tooltip will be delayed for 1 second before the display.

{% tabs %}

{% highlight xml %}

<Chart:ColumnSeries Label="2010" ShowTooltip="True"  

Chart:ChartTooltip.InitialShowDelay="1000"                                          

ItemsSource="{Binding Demands}" Interior="#777777"                                     

XBindingPath="Demand"  YBindingPath="Year2010" />                                   

{% endhighlight %}

{% highlight c# %}

ColumnSeries series = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    ShowTooltip = true,

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77)),

    Label = "2010"

};

ChartTooltip.SetInitialShowDelay(series, 1000);

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

### Animation for Tooltip

You can also provide animation effects for tooltip by setting [`EnableAnimation`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTooltip.html#Syncfusion_UI_Xaml_Charts_ChartTooltip_SetEnableAnimation_Windows_UI_Xaml_UIElement_System_Boolean_) property as true as shown in the below code snippet.

{% tabs %}

{% highlight xml %}

<Chart:ColumnSeries Label="2010" ShowTooltip="True"  

Chart:ChartTooltip.EnableAnimation="True"                                          

ItemsSource="{Binding Demands}" Interior="#777777"                                     

XBindingPath="Demand"  YBindingPath="Year2010">                                   

</Chart:ColumnSeries>

{% endhighlight %}

{% highlight c# %}

ColumnSeries series = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    ShowTooltip = true,

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77)),

    Label = "2010"

};

ChartTooltip.SetEnableAnimation(series, true);

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

### Customizing the Tooltip

The [`TooltipTemplate`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_TooltipTemplate) property allows you to customize the default appearance of the tooltip as explained in the following code sample.

{% tabs %}

{% highlight xaml %}

...
<chart:SfChart.Resources>
    <DataTemplate x:Key="tooltipTemplate1">
        <StackPanel Orientation="Horizontal">
            <TextBlock Text="{Binding Item.Demand}"
                Foreground="Black" FontWeight="Medium" FontSize="12" HorizontalAlignment="Center" VerticalAlignment="Center"/>
            <TextBlock Text=" : " Foreground="Black" FontWeight="Medium" FontSize="12" HorizontalAlignment="Center" VerticalAlignment="Center"/>
            <TextBlock Text="{Binding Item.Year2010}"
                Foreground="Black" FontWeight="Medium" FontSize="12" HorizontalAlignment="Center" VerticalAlignment="Center"/>
        </StackPanel>
    </DataTemplate>

    <DataTemplate x:Key="tooltipTemplate2">
        <StackPanel Orientation="Horizontal">
            <TextBlock Text="{Binding Item.Demand}"
                Foreground="Black" FontWeight="Medium" FontSize="12" HorizontalAlignment="Center" VerticalAlignment="Center"/>
            <TextBlock Text=" : " Foreground="Black" FontWeight="Medium" FontSize="12" HorizontalAlignment="Center" VerticalAlignment="Center"/>
            <TextBlock Text="{Binding Item.Year2011}"
                Foreground="Black" FontWeight="Medium" FontSize="12" HorizontalAlignment="Center" VerticalAlignment="Center"/>
        </StackPanel>
    </DataTemplate>

    <Style TargetType="Path" x:Key="style">
        <Setter Property="Stroke" Value="Black"/>
        <Setter Property="Fill" Value="LightGreen"/>
        <Setter Property="StrokeThickness" Value="2"/>
    </Style>
</chart:SfChart.Resources>
...

<chart:ColumnSeries ShowTooltip="True" ItemsSource="{Binding Demands}"
    XBindingPath="Demand" YBindingPath="Year2010" 
    TooltipTemplate="{StaticResource tooltipTemplate1}">
</chart:ColumnSeries>

<chart:ColumnSeries  ItemsSource="{Binding Demands}"
    ShowTooltip="True" XBindingPath="Demand"  YBindingPath="Year2011"
    TooltipTemplate="{StaticResource tooltipTemplate2}">
</chart:ColumnSeries>
...
<chart:SfChart.Behaviors>
    <chart:ChartTooltipBehavior Style="{StaticResource style}"/>
</chart:SfChart.Behaviors>
...

{% endhighlight %}

{% highlight c# %}

...
ColumnSeries series1 = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    Label = "2010",

    ShowTooltip = true,

    TooltipTemplate = chart.Resources["tooltipTemplate1"] as DataTemplate,

};

ColumnSeries series2 = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2011",

    Label = "2011",

    ShowTooltip = true,

    TooltipTemplate = chart.Resources["tooltipTemplate2"] as DataTemplate,

};

chart.Series.Add(series1);

chart.Series.Add(series2);
...

{% endhighlight %}

{% endtabs %}

![Tooltip customization support in UWP Chart](interactive-features_images/uwp-charts-interactive-features-tooltip-customization.png)

N> The `ChartTooltipBehavior` is commonly used for all series to customize the tooltip. You can use the attached `ChartTooltip` properties in a series if you need to customize the appearance of the tooltip based on a particular series. Series attached properties are considered as a high precedence.

## TrackBall

[`ChartTrackBallBehavior`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html) enables you to track a data point closer to the cursor position. The x values are determined from the position of the vertical line in the axis and y values are determined from the points touching the vertical line in the series.

### Adding TrackBall to the SfChart

You can create an instance [`ChartTrackBallBehavior`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html) and add it to the Behaviors collection.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartTrackBallBehavior>                                                  

</syncfusion:ChartTrackBallBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();

ChartTrackBallBehavior behavior = new ChartTrackBallBehavior();

chart.Behaviors.Add(behavior);

{% endhighlight %}

{% endtabs %}

To view the TrackBall in the particular Axis you have to enable the [`ShowTrackBallInfo`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartAxis.html#Syncfusion_UI_Xaml_Charts_ChartAxis_ShowTrackBallInfo) property in that axis as in the below code snippet.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.PrimaryAxis>

<syncfusion:CategoryAxis  ShowTrackBallInfo="True" />

</syncfusion:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

ChartTrackBallBehavior behavior = new ChartTrackBallBehavior();

chart.Behaviors.Add(behavior);

chart.PrimaryAxis = new CategoryAxis()
{

    ShowTrackBallInfo = true

};

{% endhighlight %}

{% endtabs %}

The default appearance of the trackball in primary axis (CategoryAxis).

![TrackBall support in UWP Chart](interactive-features_images/uwp-charts-interactive-features-trackball-support.png)

The Trackball is composed of the following parts.

1. Vertical Line

2. Symbol

3. Axis Label

4. Series Label

### Vertical line

The vertical line in the trackball is visible when you initialize the TrackBallBehavior.If you want to collapse the visibility of the trackball line then you have to set [`ShowLine`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTrackBallBehavior_ShowLine) to false.

The following code snippet illustrates the collapsing the visibility of trackball line.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartTrackBallBehavior ShowLine="False" />

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartTrackBallBehavior behavior = new ChartTrackBallBehavior()
{

    ShowLine = false

};

chart.Behaviors.Add(behavior);

{% endhighlight %}

{% endtabs %}

![Visibility support for trackball line in UWP Chart](interactive-features_images/uwp-charts-interactive-features-vissibility.jpeg)


**Customization of TrackBall line**

[`SfChart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html) allows you to customize the appearance of  trackball vertical line using [`LineStyle`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTrackBallBehavior_LineStyle) property.

The following code snippet illustrates the customization of trackball line.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart x:Name="chart">

    <syncfusion:SfChart.Resources>

        <Style TargetType="Line" x:Key="lineStyle">

            <Setter Property="StrokeDashArray" Value="5,1,2"/>

            <Setter Property="Stroke" Value="Red"/>

            <Setter Property="StrokeThickness" Value="1.2"/>

        </Style>

    </syncfusion:SfChart.Resources>

    <syncfusion:SfChart.Behaviors>

        <syncfusion:ChartTrackBallBehavior LineStyle="{StaticResource lineStyle}"/>

    </syncfusion:SfChart.Behaviors>
            
</syncfusion:SfChart>

{% endhighlight %}

{% highlight c# %}

ChartTrackBallBehavior trackball = new ChartTrackBallBehavior()
{

    LineStyle = chart.Resources["lineStyle"] as Style

};

chart.Behaviors.Add(trackball);

{% endhighlight %}

{% endtabs %}

![TrackBall line customization in UWP Chart](interactive-features_images/uwp-charts-interactive-features-trackball-line.jpeg)


### Symbol

By default the trackball symbol is displayed as ellipse, to change the default style of the symbol using [`ChartTrackBallStyle`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTrackBallBehavior_ChartTrackBallStyle) property.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart x:Name="chart">

    <syncfusion:SfChart.Resources>

        <Style TargetType="syncfusion:ChartTrackBallControl" x:Key="trackballStyle">

            <Setter Property="Background" Value="red"></Setter>

        </Style>

    </syncfusion:SfChart.Resources>

    <syncfusion:SfChart.Behaviors>

        <syncfusion:ChartTrackBallBehavior ChartTrackBallStyle="{StaticResource trackballStyle}"/>

    </syncfusion:SfChart.Behaviors>

</syncfusion:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();

ChartTrackBallBehavior trackball = new ChartTrackBallBehavior()
{

    ChartTrackBallStyle = chart.Resources["trackballStyle"] as Style

};

chart.Behaviors.Add(trackball);

{% endhighlight %}

{% endtabs %}

![Symbol for trackball in UWP Chart](Interactive-Features_images/Interactive-Features_img10.jpeg)


### Axis label

The axis label will be viewed when the [`ShowTrackBallInfo`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartAxis.html#Syncfusion_UI_Xaml_Charts_ChartAxis_ShowTrackBallInfo) property is set to true. If you want to collapse the visibility of axis label in trackball then you have to set [`ShowTrackballInfo`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartAxis.html#Syncfusion_UI_Xaml_Charts_ChartAxis_ShowTrackBallInfo) as false.

N>By default the value of [`ShowTrackBallInfo`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartAxis.html#Syncfusion_UI_Xaml_Charts_ChartAxis_ShowTrackBallInfo) is false.

**Alignment of axis label**

The alignment of the axis label while moving trackball can be defined using [`AxisLabelAlignment`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTrackBallBehavior_AxisLabelAlignment) property.

[`Auto`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartAlignment.html#Syncfusion_UI_Xaml_Charts_ChartAlignment_Auto) –Axis label is aligned in Near/Far positions based on the trackball movement.

[`Far`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartAlignment.html#Syncfusion_UI_Xaml_Charts_ChartAlignment_Far)-Axis label is positioned far from the position of trackball.

[`Near`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartAlignment.html#Syncfusion_UI_Xaml_Charts_ChartAlignment_Near)- Axis label is near to the position of trackball.

[`Center`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartAlignment.html#Syncfusion_UI_Xaml_Charts_ChartAlignment_Center)-Axis label is aligned to the center of the trackball. By default the axis label will positioned in center.

**Far**

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartTrackBallBehavior AxisLabelAlignment="Far">

</syncfusion:ChartTrackBallBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartTrackBallBehavior behavior = new ChartTrackBallBehavior()
{

    AxisLabelAlignment = ChartAlignment.Far

};

chart.Behaviors.Add(behavior);

{% endhighlight %}

{% endtabs %}

![Alignment support for trackball axis label in UWP Chart](Interactive-Features_images/Interactive-Features_img11.jpeg)


**Near**

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartTrackBallBehavior AxisLabelAlignment="Near"  >       

</syncfusion:ChartTrackBallBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartTrackBallBehavior behavior = new ChartTrackBallBehavior()
{

    AxisLabelAlignment = ChartAlignment.Near

};

chart.Behaviors.Add(behavior);

{% endhighlight %}

{% endtabs %}

![Alignment support for trackball axis label in UWP Chart](Interactive-Features_images/Interactive-Features_img12.jpeg)


**Customization of axis label**

You can change the default appearance of the axis label in trackball using [`TrackballLabelTemplate`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartAxis.html#Syncfusion_UI_Xaml_Charts_ChartAxis_TrackBallLabelTemplate) property in [`ChartAxis`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartAxis.html) as in the below code snippet.

{% tabs %}

{% highlight xaml %}

 <syncfusion:SfChart x:Name="chart">

    <syncfusion:SfChart.Resources>

        <DataTemplate x:Key="labelTemplate">

            <Border CornerRadius="4" BorderThickness="1" BorderBrush="Black"
                            
                    Background="BlueViolet" Margin="8">

                    <TextBlock Foreground="White" Text="{Binding ValueX}"/>

            </Border>

        </DataTemplate>

    </syncfusion:SfChart.Resources>

    <syncfusion:SfChart.Behaviors>

            <syncfusion:ChartTrackBallBehavior />

    </syncfusion:SfChart.Behaviors>

    <syncfusion:SfChart.PrimaryAxis>

            <syncfusion:CategoryAxis ShowTrackBallInfo="True" 
                                         
                                     LabelTemplate="{StaticResource labelTemplate}"/>

    </syncfusion:SfChart.PrimaryAxis>

</syncfusion:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();

chart.PrimaryAxis = new NumericalAxis()
{

    ShowTrackBallInfo = true,

    TrackBallLabelTemplate = chart.Resources["labelTemplate"] as DataTemplate

};

{% endhighlight %}

{% endtabs %}

![Customization support for trackball axis label in UWP Chart](Interactive-Features_images/Interactive-Features_img13.jpeg)


### Series label

When the trackball is hovered over you can view the label is also displayed over the series in addition the axis label.

**ShowTrackballInfo**

[`ShowTrackballInfo`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.CartesianSeries.html#Syncfusion_UI_Xaml_Charts_CartesianSeries_ShowTrackballInfo) property of [`Cartesian Series`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.CartesianSeries.html) allows user to enable or disable the [`trackball`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html) label for corresponding series. By default, [`ShowTrackballInfo`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.CartesianSeries.html#Syncfusion_UI_Xaml_Charts_CartesianSeries_ShowTrackballInfo) property is true. The property can be set as shown in the below code example:

{% tabs %}

{% highlight xaml %}

  <syncfusion:SfChart >
            <syncfusion:SplineSeries Interior="#4a4a4a"/>    
            <syncfusion:SplineSeries Interior="#7f7f7f" ShowTrackballInfo="False"/>
            <syncfusion:SplineSeries Interior="#bcbcbc"/>
  </syncfusion:SfChart>
  
{% endhighlight %}

{% highlight c# %}

SplineSeries series1 = new SplineSeries()
  {
      Interior = new SolidColorBrush(Color.FromArgb(0, 0x4a, 0x4a, 0x4a))
  };
  chart.Series.Add(series1);
  SplineSeries series2 = new SplineSeries()
  {
      Interior = new SolidColorBrush(Color.FromArgb(0, 0x7f, 0x7f, 0x7f)),
      ShowTrackballInfo = false
  };
  chart.Series.Add(series2);
  SplineSeries series3 = new SplineSeries()
  {
      Interior = new SolidColorBrush(Color.FromArgb(0, 0xbc, 0xbc, 0xbc))
  };
  chart.Series.Add(series3);


{% endhighlight %}

{% endtabs %}

![TrackBall series label in UWP Chart](Interactive-Features_images/ShowTrackball.png)



**Alignment of series label**

The trackball label displayed over the series can be aligned using [`LabelHorizontalAlignment`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTrackBallBehavior_LabelHorizontalAlignment) and [`LabelVerticalAlignment`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTrackBallBehavior_LabelVerticalAlignment) properties. By default the series label will be horizontally aligned to the left and vertically to the top.

The following code snippet illustrates the aligning the series label to the center of the trackball.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartTrackBallBehavior LabelHorizontalAlignment="Center" 

LabelVerticalAlignment="Center">

</syncfusion:ChartTrackBallBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartTrackBallBehavior behavior = new ChartTrackBallBehavior()
{

    LabelHorizontalAlignment = ChartAlignment.Center,

    LabelVerticalAlignment = ChartAlignment.Center

};

chart.Behaviors.Add(behavior);

{% endhighlight %}

{% endtabs %}

![Alignment support for trackball series label in UWP Chart](Interactive-Features_images/Interactive-Features_img14.jpeg)


**LabelDisplayMode**

When there is a multiple series, by default the trackball series label will be displayed only for the nearest point. If you want to display all the y values with respect to the x value then the [`LabelDisplayMode`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTrackBallBehavior_LabelDisplayMode) property is set to [`FloatAllPoints`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.TrackballLabelDisplayMode.html#Syncfusion_UI_Xaml_Charts_TrackballLabelDisplayMode_FloatAllPoints).

**FloatAllPoints**

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartTrackBallBehavior LabelDisplayMode="FloatAllPoints" >

</syncfusion:ChartTrackBallBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartTrackBallBehavior behavior = new ChartTrackBallBehavior()
{

    LabelDisplayMode = TrackballLabelDisplayMode.FloatAllPoints

};

chart.Behaviors.Add(behavior);

{% endhighlight %}

{% endtabs %}

![LabelDisplayMode support for trackball in UWP Chart](Interactive-Features_images/Interactive-Features_img15.jpeg)


**NearestPoint**

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartTrackBallBehavior LabelDisplayMode="NearestPoint" >

</syncfusion:ChartTrackBallBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartTrackBallBehavior behavior = new ChartTrackBallBehavior()
{

    LabelDisplayMode = TrackballLabelDisplayMode.NearestPoint

};

chart.Behaviors.Add(behavior);

{% endhighlight %}

{% endtabs %}

![LabelDisplayMode support for trackball in UWP Chart](Interactive-Features_images/Interactive-Features_img16.jpeg)


### TrackBallLabelTemplate

[`TrackBallLabelTemplate`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_TrackBallLabelTemplate) property in [`ChartSeries`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSeries.html) allows you to customize the appearance of series label in trackball.

{% tabs %}

{% highlight xaml %}

  <syncfusion:SfChart x:Name="chart">

        <syncfusion:SfChart.Resources>

            <DataTemplate x:Key="labelTemplate">

                <Border CornerRadius="5" BorderThickness="1" 
                            
                        BorderBrush="Black" Background="BlueViolet" Margin="8">

                    <TextBlock Foreground="White" Text="{Binding ValueY}"/>

                </Border>

            </DataTemplate>

         </syncfusion:SfChart.Resources>

        <syncfusion:SfChart.Behaviors>

                <syncfusion:ChartTrackBallBehavior />

        </syncfusion:SfChart.Behaviors>

        <syncfusion:ColumnSeries Label="2010" 
        
        Interior="#4A4A4A" 
        
        ItemsSource="{Binding Demands}" 
        
        XBindingPath="Demand" 
        
        YBindingPath="Year2010" 
        
        TrackBallLabelTemplate="{StaticResource labelTemplate}"/>
          
</syncfusion:SfChart>


{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();

ChartTrackBallBehavior trackball = new ChartTrackBallBehavior();

chart.Behaviors.Add(trackball);

ColumnSeries series = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    TrackBallLabelTemplate = chart.Resources["labelTemplate"] as DataTemplate,

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0x4A))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Customization support for trackball series label in UWP Chart](Interactive-Features_images/Interactive-Features_img17.jpeg)


**Applying Palette to the Series Label**

[`Palette`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_Palette) or [`Interior`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_Interior) color of the [`Series`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html#Syncfusion_UI_Xaml_Charts_SfChart_Series) is applied to the series label by setting [`UseSeriesPalette`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTrackBallBehavior_UseSeriesPalette) to True as shown in the below code snippet.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartTrackBallBehavior UseSeriesPalette="True" >

</syncfusion:ChartTrackBallBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartTrackBallBehavior behavior = new ChartTrackBallBehavior()
{

     UseSeriesPalette = true

};

chart.Behaviors.Add(behavior);

{% endhighlight %}

{% endtabs %}

![Applying palette to the trackball series label in UWP Chart](Interactive-Features_images/Interactive-Features_img18.jpeg)


### Events

The following events are available in ChartTrackBallBehavior,

## PositionChanging

The [`PositionChanging`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTrackBallBehavior_PositionChanging) event occurs when the [`trackball`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html) position is changing from current mouse position to new mouse position. This argument contains the following information.

* [`Cancel`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.PositionChangingEventArgs.html#Syncfusion_UI_Xaml_Charts_PositionChangingEventArgs_Cancel) - Gets or sets a value that indicates whether to show the trackball on new mouse pointer position.
* [`PointInfos`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.PositionChangingEventArgs.html#Syncfusion_UI_Xaml_Charts_PositionChangingEventArgs_PointInfos) - Gets or sets the current [`ChartPointInfo`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html).

## PositionChanged

The [`PositionChanged`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTrackBallBehavior_PositionChanged) event occurs when the [`trackball`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html) position is changed from current mouse position to new mouse position. This argument contains the following information.

* [`PreviousPointInfos`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.PositionChangedEventArgs.html#Syncfusion_UI_Xaml_Charts_PositionChangedEventArgs_PreviousPointInfos) - Gets or sets the previous [`ChartPointInfo`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html).
* [`CurrentPointInfos`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.PositionChangedEventArgs.html#Syncfusion_UI_Xaml_Charts_PositionChangedEventArgs_CurrentPointInfos) -  Gets or sets the current [`ChartPointInfo`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html).

The [`ChartPointInfo`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html) class contains the following properties to customize the appearance of trackball label:

* [`Axis`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_Axis) - Gets the associated axis in which the trackball is activated.
* [`BaseX`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_BaseX) - Gets the x-initial coordinate of the trackball label.
* [`BaseY`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_BaseY) - Gets the y-initial coordinate of the trackball label.
* [`BorderBrush`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_BorderBrush) - Gets or sets the border color of the trackball label.
* [`Close`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_Close) - Gets the close value of the trackball label when it is applicable.
* [`Foreground`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_Foreground) - Gets or sets the foreground color of the trackball label.
* [`High`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_High) - Gets the high value of the trackball label when it is applicable.
* [`Interior`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_Interior) - Gets or sets the interior color of the trackball label.
* [`Item`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_Item) - Gets the respective underlying object of the data in which the trackball is activated.
* [`Low`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_Low) - Gets the low value of the trackball label when it is applicable.
* [`LowerLine`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_LowerLine) - Gets the y-value of the lower line in indicator.  
* [`Median`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_Median) - Gets the median value when it is applicable.
* [`Open`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_Open) - Gets the open value of the trackball label when it is applicable.
* [`PolygonPoints`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_PolygonPoints) - Gets the point collection to render trackball.
* [`Series`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_Series) - Gets the associated series in which the trackball is activated.
* [`SeriesValues`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_SeriesValues) - Gets the SeriesValues in which the trackball is activated.
* [`SignalLine`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_SignalLine) - Gets the y-value of the signal line in indicator.  
* [`UpperLine`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_UpperLine) - Gets the y-value of the upper line in indicator.  
* [`ValueX`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_ValueX) - Gets the x-value of the trackball label.
* [`ValueY`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_ValueY) - Gets the y-value of the trackball label.
* [`X`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_X) - Gets the x-coordinate of the trackball label.
* [`Y`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartPointInfo.html#Syncfusion_UI_Xaml_Charts_ChartPointInfo_Y) - Gets the y-coordinate of the trackball label.

## Visual data editing

[`SfChart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html) has a feature that allows you to edit an entire series or a single data point at run time by dragging the single point or the series as a whole.

### Segment dragging

Segment Dragging defines the dragging a particular point or segment based on the series type. The segment dragging can be enabled using [`EnableSegmentDragging`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase.html#Syncfusion_UI_Xaml_Charts_XySegmentDraggingBase_EnableSegmentDragging) property as true.

**LineSeries**

{% tabs %}

{% highlight xml %}

<syncfusion:LineSeries Label="2010" EnableSegmentDragging="True"

XBindingPath="Demand"   Interior="#777777"

ItemsSource="{Binding Demands}"                                   

YBindingPath="Year2010">

</syncfusion:LineSeries>

{% endhighlight %}

{% highlight c# %}

LineSeries series = new LineSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    EnableSegmentDragging = true,

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77)),

    Label = "2010"

};

chart.Series.Add(series)

{% endhighlight %}

{% endtabs %}

![Segment dragging support in UWP Chart](Interactive-Features_images/Interactive-Features_img19.png)


**ColumnSeries**

{% tabs %}

{% highlight xml %}

<syncfusion:ColumnSeries Label="2010" EnableDragTooltip="True" EnableSegmentDragging="True"

XBindingPath="Demand"   Interior="#777777"

ItemsSource="{Binding Demands}"                                   

YBindingPath="Year2010">

</syncfusion:ColumnSeries>

{% endhighlight %}

{% highlight c# %}

ColumnSeries series = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    EnableSegmentDragging = true,

    EnableDragTooltip = true,

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77)),

    Label = "2010"

};

chart.Series.Add(series)

{% endhighlight %}

{% endtabs %}

![Segment dragging support in UWP Chart](Interactive-Features_images/Interactive-Features_img20.png)


**ScatterSeries**

This series supports dragging in both the x and y co-ordinates. The dragging co – ordinates can be set by using the enum property [`DragDirection`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ScatterSeries.html#Syncfusion_UI_Xaml_Charts_ScatterSeries_DragDirection).

{% tabs %}

{% highlight xml %}

<syncfusion:ScatterSeries ItemsSource="{Binding Data}" XBindingPath="Index"
                         YBindingPath="Value" EnableSegmentDragging="True"          
                         Interior="#4A4A4A" DragDirection="XY" />


{% endhighlight %}

{% highlight c# %}

ScatterSeries scatterSeries = new ScatterSeries()
  {
   ItemsSource = new ViewModel().Data,
   XBindingPath = "Index",
   YBindingPath = "Value",
   Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77)),
   EnableSegmentDragging = true
  };

chart.Series.Add(series)

{% endhighlight %}

{% endtabs %}

![Segment dragging support in UWP Chart](Interactive-Features_images/Scatter_Dragging.png)


N> By default the [`DragDirection`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ScatterSeries.html#Syncfusion_UI_Xaml_Charts_ScatterSeries_DragDirection) of the scatter series is XY.


### Series dragging

[`SfChart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html) provides support to drag the [`LineSeries`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.LineSeries.html) and [`SplineSeries`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SplineSeries.html). This allows the series to move to a new position by dragging. To enable the series dragging, you have to set [`EnableSeriesDragging`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.XySeriesDraggingBase.html#Syncfusion_UI_Xaml_Charts_XySeriesDraggingBase_EnableSeriesDragging) property to true.

The following code snippet explains the series dragging feature in [`LineSeries`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.LineSeries.html)

{% tabs %}

{% highlight xaml %}

<syncfusion:LineSeries Label="2010" EnableDragTooltip="True" EnableSeriesDragging="True"

XBindingPath="Demand"   Interior="#777777" ItemsSource="{Binding Demands}"

YBindingPath="Year2010"/>

{% endhighlight %}

{% highlight c# %}

LineSeries series = new LineSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    EnableSeriesDragging = true,

    EnableDragTooltip = true ,

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77)),

    Label = "2010"

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Series dragging support in UWP Chart](Interactive-Features_images/Interactive-Features_img21.png)


N>In line and Spline Series if segment and series dragging is enabled, the series dragging is having higher priority over segment dragging.

### Adding ToolTip for dragging

While the series or segment is dragged by default you can view the tooltip showing the new y value. To disable the tooltip while dragging you have to set the [`EnableDragToolTip`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase.html#Syncfusion_UI_Xaml_Charts_XySegmentDraggingBase_EnableDragTooltip) as false.

{% tabs %}

{% highlight xml %}

<syncfusion:LineSeries Label="2010"  EnableSegmentDragging="True" EnableDragTooltip="False"

XBindingPath="Demand"   Interior="#777777"

Focusable="False"

ItemsSource="{Binding Demands}"                                   

</syncfusion:LineSeries>

{% endhighlight %}

{% highlight c# %}

LineSeries series = new LineSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    EnableSeriesDragging = true,

    EnableDragTooltip = true ,

    Focusable = false,

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77)),

    Label = "2010"

};

chart.Series.Add(series);


{% endhighlight %}

{% endtabs %}

![Adding tooltip for dragging in UWP Chart](Interactive-Features_images/Interactive-Features_img22.png)


**DragTooltipTemplate**

[`DragTooltipTemplate`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase.html#Syncfusion_UI_Xaml_Charts_XySegmentDraggingBase_DragTooltipTemplate)  property allows you to customize the default appearance of the tooltip while dragging.

{% tabs %}

{% highlight xaml %}


   <syncfusion:SfChart x:Name="chart">

            <syncfusion:SfChart.Resources>

                <DataTemplate x:Key="tooltipTemplate">

                    <Border CornerRadius="4" BorderBrush="Black"
                            
                            BorderThickness="1" Background="CadetBlue"
                           
                            Margin="0,0,0,15">

                        <TextBlock  FontSize="12" Text="{Binding NewValue}" 
                                    
                                    Width="35" Foreground="White"
                        
                                    Margin="2"></TextBlock>

                    </Border>

                </DataTemplate>

            </syncfusion:SfChart.Resources>

            <syncfusion:LineSeries Label="2010" EnableSegmentDragging="True" 
                                   
                              Interior="#777777" Focusable="False" 

                               XBindingPath="Demand" ItemsSource="{Binding Demands}"          
                                   
                               YBindingPath="Year2010"
                                   
                               DragTooltipTemplate="{StaticResource tooltipTemplate }">

            </syncfusion:LineSeries>

</syncfusion:SfChart>

{% endhighlight %}

{% highlight c# %}

ColumnSeries series = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    Focusable = false,

    EnableSegmentDragging = true,

    DragTooltipTemplate = chart.Resources["tooltipTemplate"] as DataTemplate,

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Customizing tooltip while dragging in UWP Chart](Interactive-Features_images/Interactive-Features_img23.png)


**Drag Tooltip style**

The dragging tooltip can be customized by using the [`DragTooltipStyle`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase.html#Syncfusion_UI_Xaml_Charts_XySegmentDraggingBase_DragTooltipStyle) property of the series.

The following are the API’s in ChartDragTooltipStyle.

[`FontFamily`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartDragTooltipStyle.html#Syncfusion_UI_Xaml_Charts_ChartDragTooltipStyle_FontFamily) – Gets or sets the font family for dragging tooltip text.

[`FontSize`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartDragTooltipStyle.html#Syncfusion_UI_Xaml_Charts_ChartDragTooltipStyle_FontSize) – Gets or sets the font size for dragging tooltip text.

[`FontStyle`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartDragTooltipStyle.html#Syncfusion_UI_Xaml_Charts_ChartDragTooltipStyle_FontStyle) – Gets or sets the font style for dragging tooltip text.

[`Foreground`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartDragTooltipStyle.html#Syncfusion_UI_Xaml_Charts_ChartDragTooltipStyle_Foreground) – Gets or sets the brush for dragging tooltip text.

[`Background`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartDragTooltipStyle.html#Syncfusion_UI_Xaml_Charts_ChartDragTooltipStyle_Background) – Gets or sets the background brush for dragging tooltip.

{% tabs %}

{% highlight xaml %}

<syncfusion:LineSeries.DragTooltipStyle>
      <syncfusion:ChartDragTooltipStyle FontFamily="Calibri" FontSize="14" 
                                   FontStyle="Italic" Background="DarkGray" 
                                   Foreground="Black" />
</syncfusion:LineSeries.DragTooltipStyle>

{% endhighlight %}

{% highlight c# %}


  this.lineSeries.DragTooltipStyle = new ChartDragTooltipStyle()
  {
     FontFamily = new FontFamily("Calibri"),
     FontSize = 14,
     FontStyle = FontStyle.Italic,
     Background = new SolidColorBrush(Colors.DarkGray),
     Foreground = new SolidColorBrush(Colors.Black)
  };

{% endhighlight %}

{% endtabs %}

![Customizing tooltip while dragging in UWP Chart](Interactive-Features_images/Drag_Tooltip.png)


**Rounding Off the dragged value**

To round off the dragged values, you have to set the [`SnapToPoint`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase.html#Syncfusion_UI_Xaml_Charts_XySegmentDraggingBase_SnapToPoint) and [`RoundToDecimal`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase.html#Syncfusion_UI_Xaml_Charts_XySegmentDraggingBase_RoundToDecimal) properties. The following code snippet explains rounding the dragged y value to 2 decimal digits.

{% tabs %}

{% highlight xml %}

<syncfusion:SplineSeries   EnableSegmentDragging="True"

SnapToPoint="Round" RoundToDecimal="2" YBindingPath = "Year2010"

UpdateSource="True" XBindingPath="Demand"   Interior="#777777"

ItemsSource="{Binding Demands}"                                   

</syncfusion:SplineSeries>

{% endhighlight %}

{% highlight c# %}

SplineSeries series = new SplineSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    EnableSegmentDragging = true,

    UpdateSource = true ,

    RoundToDecimal = 2,

    SnapToPoint = SnapToPoint.Round,

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

### Updating the dragged values to the source

When dragging the series or segment at run time, to update the underlying data based on the values you have to set the [`UpdateSource`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase.html#Syncfusion_UI_Xaml_Charts_XySegmentDraggingBase_UpdateSource) property to true as in the below code snippet.

{% tabs %}

{% highlight xml %}

<syncfusion:SplineSeries   EnableSegmentDragging="True" UpdateSource="True"

XBindingPath="Demand"   Interior="#777777"

ItemsSource="{Binding Demands}"                                   

YBindingPath="Year2010">

</syncfusion:SplineSeries>

{% endhighlight %}

{% highlight c# %}

SplineSeries series = new SplineSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    EnableSegmentDragging = true,

    UpdateSource = true ,

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

### Drag cancel using KeyModifiers

While you are dragging you can set the [`KeyModifiers`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_KeyModifiers) to cancel the drag by setting [`DragCancelKeyModifier`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase.html#Syncfusion_UI_Xaml_Charts_XySegmentDraggingBase_DragCancelKeyModifiers) property as in the below code snippet.

{% tabs %}

{% highlight xml %}

<syncfusion:SplineSeries  

EnableSegmentDragging="True" 

DragCancelKeyModifiers="Alt"  

UpdateSource="True"

XBindingPath="Demand"                                   

ItemsSource="{Binding Demands}"                                   

YBindingPath="Year2010">

</syncfusion:SplineSeries>

{% endhighlight %}

{% highlight c# %}

SplineSeries series = new SplineSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    EnableSegmentDragging = true,

    DragCancelKeyModifiers = ModifierKeys.Alt,

    UpdateSource = true ,

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}


### Events

Series with visual data editing has support for following events,

* [`DragStart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase.html#Syncfusion_UI_Xaml_Charts_XySegmentDraggingBase_DragStart)- Occurs when segment/series drag started. 
* [`DragDelta`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase.html#Syncfusion_UI_Xaml_Charts_XySegmentDraggingBase_DragDelta)- Occurs when segment/series dragging.
* [`DragEnd`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase.html#Syncfusion_UI_Xaml_Charts_XySegmentDraggingBase_DragEnd)- Occurs when segment/series drag end. 
* [`PreviewDragEnd`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase.html#Syncfusion_UI_Xaml_Charts_XySegmentDraggingBase_PreviewDragEnd)- Occurs before drag end triggered. 
* [`SegmentEnter`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.XySegmentDraggingBase.html#Syncfusion_UI_Xaml_Charts_XySegmentDraggingBase_SegmentEnter)- Occurs when mouse enters in segment. 


## Zoom and Pan

[`SfChart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html) allows you to zoom the chart area with the help of the zoom feature. This behavior is mostly used to view the data point in the specific area, when there are a number of data points inside the chart.

Zooming and panning provides you to take a close-up look of the data point plotted in the series

### Adding zooming/panning to the SfChart

You can create an instance [`ChartZoomPanBehavior`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html) and add it to the [`Behaviors`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html#Syncfusion_UI_Xaml_Charts_SfChart_Behaviors) collection.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior >                                             

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior();

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

### Zooming the ChartArea

**Zooming by setting ZoomFactor and ZoomPosition**

[`ZoomFactor`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartAxisBase2D.html#Syncfusion_UI_Xaml_Charts_ChartAxisBase2D_ZoomFactor) defines the percentage of visible range from the total range of axis values. [`ZoomPosition`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartAxisBase2D.html#Syncfusion_UI_Xaml_Charts_ChartAxisBase2D_ZoomPosition) defines the ranges of values that need to be displayed as a result of [`ZoomFactor`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartAxisBase2D.html#Syncfusion_UI_Xaml_Charts_ChartAxisBase2D_ZoomFactor). 

The following code example demonstrates the zooming the chart axis by setting zoom position and zoom factor.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.PrimaryAxis>

<syncfusion:CategoryAxis 

ShowGridLines="False"

ZoomFactor="0.3" ZoomPosition="0.1" />

</syncfusion:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis()
{

    ShowGridLines = false,

    ZoomFactor = 0.1,

    ZoomPosition = 0.3

};

{% endhighlight %}

{% endtabs %}

![Zooming support in UWP Chart](Interactive-Features_images/Interactive-Features_img24.jpeg)

**Mouse wheel zooming**

Zooming can be performed by mouse wheel action by setting [`EnableMouseWheelZooming`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_EnableMouseWheelZooming) property to true.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior EnableMouseWheelZooming="True" >                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    EnableMouseWheelZooming = true

};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

**Pinch** **Zooming**

If you want to zoom using fingers by touch, then you have to set [`EnablePinchZooming`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_EnablePinchZooming) property to true as shown in the below code snippet.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior EnablePinchZooming="True" >                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    EnablePinchZooming = true

};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

**Zooming relative to cursor**

To enable the zooming relative to cursor position you can set [`ZoomRelativeToCursor`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_ZoomRelativeToCursor) property to true. This support is applicable only for mouse wheel zooming.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior ZoomRelativeToCursor="True" >                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    ZoomRelativeToCursor = true

};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}


**SelectionZooming**

SelectionZooming helps us to zoom a particular area by selecting the region using  rectangle.To enable the selection ,you have to set [`EnableSelectionZooming`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_EnableSelectionZooming) property to true.

The following code snippet demonstrated selection zooming.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior EnableSelectionZooming="True" >                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    EnableSelectionZooming = true

};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

![Selection zooming support in UWP Chart](Interactive-Features_images/Interactive-Features_img25.jpeg)


**Customization** **of** **Selection** **Rectangle**

Selection Rectangle can be customized by setting the following properties 

* [`Fill`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_Fill)-Represents the brush filled in selection rectangle. 
* [`Stroke`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_Stroke)- Represents the outer line color of selection rectangle.
* [`StrokeThickness`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_StrokeThickness)- Represents the selection rectangle outer line thickness. 

The following code example demonstrates the customization of selection rectangle

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior EnableSelectionZooming="True" 

Fill="LightBlue" Stroke="Blue" StrokeThickness="2" >                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    EnableSelectionZooming = true,

    Fill = new SolidColorBrush(Colors.LightBlue),

    Stroke = new SolidColorBrush(Colors.Blue),

    StrokeThickness = 2

};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

![Customizing selection rectangle support in UWP Chart](Interactive-Features_images/Interactive-Features_img26.jpeg)


**Zooming mode**

The zooming can be done both horizontally and vertically. The zooming direction is defined using [`ZoomMode`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_ZoomMode) property.

Zooming along [`X`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ZoomMode.html#Syncfusion_UI_Xaml_Charts_ZoomMode_X) axis

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior EnableSelectionZooming="True" ZoomMode="X">                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    EnableSelectionZooming = true,

    ZoomMode = ZoomMode.X

};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

![Zoom mode support in UWP Chart](Interactive-Features_images/Interactive-Features_img27.jpeg)


Zooming along Y axis

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior EnableSelectionZooming="True" ZoomMode="Y">                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    EnableSelectionZooming = true,

    ZoomMode = ZoomMode.Y

};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

![Zoom mode support in UWP Chart](Interactive-Features_images/Interactive-Features_img28.jpeg)

**Maximum zoom level**

You can also limit the zooming by setting [`MaximumZoomLevel`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_MaximumZoomLevel) property as shown in the below code snippet.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior EnableSelectionZooming="True" MaximumZoomLevel="100">                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    EnableSelectionZooming = true,

    MaximumZoomLevel = 100

};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

### Zooming Toolbar

Zooming Toolbar encompassed with buttons for performing actions like Zoom In/Out, Reset, Pan, etc. You can add the zooming toolbar to the chart area by setting [`EnableZoomingToolBar`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_EnableZoomingToolBar) property to True.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior EnableZoomingToolBar="True">                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    EnableZoomingToolBar = true

};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

The following image depicts the default view of the zooming toolbar.

![Zooming toolbar in UWP Chart](Interactive-Features_images/Interactive-Features_img29.jpeg)


**Positioning the zooming toolbar**

Zooming Toolbar can be positioned using the [`HorizontalPosition`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_HorizontalPosition) and [`VerticalPosition`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_VerticalPosition) properties.The following code demonstrates the positioning of the toolbar.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior EnableZoomingToolBar="True" HorizontalPosition="Left" VerticalPosition="Bottom">                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    EnableZoomingToolBar = true,

    HorizontalPosition = HorizontalAlignment.Left,

    VerticalPosition = VerticalAlignment.Bottom

};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

![Positioning the zooming toolbar in UWP Chart](Interactive-Features_images/Interactive-Features_img30.jpeg)


**Customization of zooming Toolbar**

Zooming Toolbar can be customized using the following API’s

* [`ToolBarBackground`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_ToolBarBackground)- Represents the zooming toolkit background.
* [`ToolBarItems`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_ToolBarItems)- Collection value that contains zooming toolkit items. 
* [`ToolBarItemMargin`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_ToolBarItemMargin)-Represents the margin for the toolbar item.
* [`ToolBarItemWidth`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_ToolBarItemWidth) -Represents the width of the toolbar item
* [`ToolBarItemHeight`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_ToolBarItemHeight)-Represents the height of the toolbar item

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior EnableZoomingToolBar="True" ToolBarItemHeight="15" 

ToolBarItemWidth="15" ToolBarBackground="Black" 

ToolBarItems="All" ToolBarItemMargin="10">                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    EnableZoomingToolBar = true,

    ToolBarBackground = new SolidColorBrush(Colors.Black),

    ToolBarItemHeight = 15,

    ToolBarItemWidth = 15,

    ToolBarItemMargin = new Thickness(10),

    ToolBarItems = ZoomToolBarItems.All

};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

![Customization of zooming toolbar in UWP Chart](Interactive-Features_images/Interactive-Features_img31.jpeg)


**Orientation of zooming Toolbar**

Zooming toolbar orientation is horizontal by default.You can change the orientation to vertical by setting 

[`ToolBarOrientation`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_ToolBarOrientation) property to Vertical.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior EnableZoomingToolBar="True" 

ToolBarOrientation="Vertical">                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    EnableZoomingToolBar = true,

    ToolBarOrientation = Orientation.Vertical

};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

![Orientation of zooming toolbar in UWP Chart](Interactive-Features_images/Interactive-Features_img32.jpeg)


### Panning the chart area

Panning feature allows moving the visible area of the chart when it is zoomed in. To enable panning, you have to set [`EnablePanning`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_EnablePanning) property to true.

{% tabs %}

{% highlight xml %}
<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior EnableMouseWheelZooming="True" EnablePanning="True">                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    EnableMouseWheelZooming = true,

    EnablePanning = true
     
};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}

The following image demonstrates the cursor panning in the left direction.

![Panning support in UWP Chart](Interactive-Features_images/Interactive-Features_img33.jpeg)


### Resetting the zooming/panning

[`SfChart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html) provides support to reset to the default view when you double tap the chart area by setting [`ResetOnDoubleTap`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html#Syncfusion_UI_Xaml_Charts_ChartZoomPanBehavior_ResetOnDoubleTap) property to true.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior  ResetOnDoubleTap="True">                                              

</syncfusion:ChartZoomPanBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zooming = new ChartZoomPanBehavior()
{

    ResetOnDoubleTap = true
     
};

chart.Behaviors.Add(zooming);

{% endhighlight %}

{% endtabs %}


### Events

The following events are available in [`SfChart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html) for [`ChartZoomPanBehavior`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartZoomPanBehavior.html),

* [`ZoomChanging`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html#Syncfusion_UI_Xaml_Charts_SfChart_ZoomChanging)- Occurs when zoom started in chart area.
* [`ZoomChanged`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html#Syncfusion_UI_Xaml_Charts_SfChart_ZoomChanged)- Occurs when zooming done in chart area.
* [`SelectionZoomingStart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html#Syncfusion_UI_Xaml_Charts_SfChart_SelectionZoomingStart)- Occurs when selection zooming started. 
* [`SelectionZoomingDelta`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html#Syncfusion_UI_Xaml_Charts_SfChart_SelectionZoomingDelta)- Occurs when selection zooming.
* [`SelectionZoomingEnd`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html#Syncfusion_UI_Xaml_Charts_SfChart_SelectionZoomingEnd)- Occurs when selection zooming end. 
* [`ResetZooming`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html#Syncfusion_UI_Xaml_Charts_SfChart_ResetZooming)- Occurs when zooming get reset in chart area.


## Selection:

[`SfChart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html) supports selection that enables you to select a segment in a series or series itself by using [`ChartSelectionBehavior`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSelectionBehavior.html). 

### Adding selection behavior to SfChart

You can create an instance [`ChartSelectionBehavior`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSelectionBehavior.html) and add it to the [`Behaviors`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html#Syncfusion_UI_Xaml_Charts_SfChart_Behaviors) collection.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartSelectionBehavior >

</syncfusion:ChartSelectionBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartSelectionBehavior selection = new ChartSelectionBehavior();

chart.Behaviors.Add(selection);

{% endhighlight %}

{% endtabs %}

### SegmentSelection

Segment Selection allows you to highlight a segment in a chart series. To enable a segment selection in a chart series, you have to set the [`EnableSegmentSelection`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSelectionBehavior.html#Syncfusion_UI_Xaml_Charts_ChartSelectionBehavior_EnableSegmentSelection) property to True.For highlighting a segment the  brush color can be set using [`SegmentSelectionBrush`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ColumnSeries.html#Syncfusion_UI_Xaml_Charts_ColumnSeries_SegmentSelectionBrush) property.

**ColumnSeries**

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartSelectionBehavior   EnableSegmentSelection="True" >

</syncfusion:ChartSelectionBehavior>

</syncfusion:SfChart.Behaviors>

<syncfusion:ColumnSeries Label="2011" SegmentSelectionBrush="Green" Interior="#777777"

ItemsSource="{Binding Demands}" XBindingPath="Demand" YBindingPath="Year2011"/>

{% endhighlight %}

{% highlight c# %}

ChartSelectionBehavior selection = new ChartSelectionBehavior()
{

    EnableSegmentSelection = true

};

chart.Behaviors.Add(selection);

ColumnSeries series = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    Label ="2011",

    SegmentSelectionBrush = new SolidColorBrush(Colors.Green),

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77))

};

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Segment selection support in UWP Chart](Interactive-Features_images/Interactive-Features_img34.jpeg)

**SplineSeries**

In Linear type series the segment selection can be viewed by changing the adornments symbol interior.

The following code example demonstrates the spline series segment selection by changing the adornments interior.

{% tabs %}

{% highlight xml %}

<syncfusion:SplineSeries SegmentSelectionBrush="Red"

ItemsSource="{Binding Demands}" Interior="#4A4A4A"

XBindingPath="Demand"

YBindingPath="Year2010">

<syncfusion:SplineSeries.AdornmentsInfo>

<syncfusion:ChartAdornmentInfo ShowMarker="True" Symbol="Ellipse" HighlightOnSelection="True"></syncfusion:ChartAdornmentInfo>

</syncfusion:SplineSeries.AdornmentsInfo>

</syncfusion:SplineSeries>

{% endhighlight %}

{% highlight c# %}

ChartSelectionBehavior selection = new ChartSelectionBehavior()
{

    EnableSegmentSelection = true

};

chart.Behaviors.Add(selection);

SplineSeries series = new SplineSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    SegmentSelectionBrush = new SolidColorBrush(Colors.Red),

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0x4A))

};

ChartAdornmentInfo adornmentInfo = new ChartAdornmentInfo()
{

    ShowMarker = true,

    HighlightOnSelection = true,

    Symbol = ChartSymbol.Ellipse

};

series.AdornmentsInfo = adornmentInfo;

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Segment selection support in UWP Chart](Interactive-Features_images/Interactive-Features_img35.jpeg)

### Series selection

Series selection is used in case of multiple series when you want to highlight a particular series.Series Selection can be enabled by setting [`EnableSeriesSelection`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSelectionBehavior.html#Syncfusion_UI_Xaml_Charts_ChartSelectionBehavior_EnableSeriesSelection)  property to True. The [`SeriesSelectionBrush`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_SeriesSelectionBrush) property is used to set the brush color to highlight the series.

The following code example demonstrates highlighting a series.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartSelectionBehavior EnableSegmentSelection="False" EnableSeriesSelection="True"/>

</syncfusion:SfChart.Behaviors>   

<syncfusion:ScatterSeries Label="2010"  SeriesSelectionBrush="Green"

ItemsSource="{Binding Demands}" Interior="#4A4A4A"

XBindingPath="Demand"

YBindingPath="Year2010">

</syncfusion:ScatterSeries>

<syncfusion:ScatterSeries Label="2011" SeriesSelectionBrush="Green" Interior="#777777"

ItemsSource="{Binding Demands}" XBindingPath="Demand" 

YBindingPath="Year2011"/>    

{% endhighlight %}

{% highlight c# %}

ChartSelectionBehavior selection = new ChartSelectionBehavior()
{

    EnableSegmentSelection = true,

    EnableSeriesSelection = true

};

chart.Behaviors.Add(selection);

ScatterSeries series1 = new ScatterSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    Label = "2010",

    SegmentSelectionBrush = new SolidColorBrush(Colors.Green),

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0x4A))

};

ScatterSeries series2 = new ScatterSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2011",

    Label = "2011",

    SegmentSelectionBrush = new SolidColorBrush(Colors.Green),

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77))

};

chart.Series.Add(series1);

chart.Series.Add(series2);

{% endhighlight %}

{% endtabs %}

![Series selection support in UWP Chart](Interactive-Features_images/Interactive-Features_img36.jpeg)

N>By default the segment selection is true, so for selecting series you have to set the [`EnableSegmentSelection`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSelectionBehavior.html#Syncfusion_UI_Xaml_Charts_ChartSelectionBehavior_EnableSegmentSelection) property to false.

### Selection mode

[`SfChart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html) provides support to select using mouse move or mouse click. By default the selection will take place in mouse click. The selection mode can be defined using [`SelectionMode`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSelectionBehavior.html#Syncfusion_UI_Xaml_Charts_ChartSelectionBehavior_SelectionMode) property for segment and series selection.

The following code snippet demonstrates the selection mode using [`MouseMove`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SelectionMode.html#Syncfusion_UI_Xaml_Charts_SelectionMode_MouseMove).

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartSelectionBehavior SelectionMode="MouseMove" EnableSeriesSelection="True">

</syncfusion:ChartSelectionBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartSelectionBehavior selection = new ChartSelectionBehavior()
{

    SelectionMode = Syncfusion.UI.Xaml.Charts.SelectionMode.MouseMove,

    EnableSeriesSelection = true

};

chart.Behaviors.Add(selection);

{% endhighlight %}

{% endtabs %}

### Selection style

[`SfChart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html) allows you to select single or multiple segment /series using [`SelectionStyle`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSelectionBehavior.html#Syncfusion_UI_Xaml_Charts_ChartSelectionBehavior_SelectionStyle) property. By default the [`SelectionStyle`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSelectionBehavior.html#Syncfusion_UI_Xaml_Charts_ChartSelectionBehavior_SelectionStyle) is [`Single`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SelectionStyle.html#Syncfusion_UI_Xaml_Charts_SelectionStyle_Single).

The following code snippet demonstrates multiple segment selection.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartSelectionBehavior SelectionStyle="Multiple" EnableSegmentSelection="True">

</syncfusion:ChartSelectionBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartSelectionBehavior selection = new ChartSelectionBehavior()
{

    SelectionStyle = SelectionStyle.Multiple,

    EnableSegmentSelection = true

};

chart.Behaviors.Add(selection);

{% endhighlight %}

{% endtabs %}

![Selection style support in UWP Chart](Interactive-Features_images/Interactive-Features_img37.jpeg)


### Changing cursor while selection

[`SelectionCursor`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSelectionBehavior.html#Syncfusion_UI_Xaml_Charts_ChartSelectionBehavior_SelectionCursor) property allows you to define the cursor when mouse is hovered over the segment with segment or series selection enabled.

The following code snippet demonstrates hand cursor in segment selection.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartSelectionBehavior SelectionCursor="Hand"  EnableSegmentSelection="True">

</syncfusion:ChartSelectionBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartSelectionBehavior selection = new ChartSelectionBehavior()
{

    SelectionCursor = Cursors.Hand,

    EnableSegmentSelection = true

};

chart.Behaviors.Add(selection);

{% endhighlight %}

{% endtabs %}

![Changing cursor while selection support in UWP Chart](Interactive-Features_images/Interactive-Features_img38.jpeg)


### Adornment Selection:

[`SfChart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html) provides selection for adornments by defining [`HighlightOnSelection`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase.html#Syncfusion_UI_Xaml_Charts_ChartAdornmentInfoBase_HighlightOnSelection) property which allows you to select the segment or series with the corresponding adornments.

**HighlightOnSelection**

**Segment selection**

The following code example demonstrates the segment selection with adornments 

{% tabs %}

{% highlight xaml %}

<syncfusion:ColumnSeries Interior="#4A4A4A"

ItemsSource="{Binding Demands}" XBindingPath="Demand"

SegmentSelectionBrush="Green"

YBindingPath="Year2010">

<syncfusion:ColumnSeries.AdornmentsInfo>

<syncfusion:ChartAdornmentInfo UseSeriesPalette="True" ShowConnectorLine="True"

ConnectorHeight="30" ShowLabel="True" HighlightOnSelection="True">

</syncfusion:ChartAdornmentInfo>

</syncfusion:ColumnSeries.AdornmentsInfo>

{% endhighlight %}

{% highlight c# %}

ChartSelectionBehavior selection = new ChartSelectionBehavior()
{

    EnableSegmentSelection = true

};

chart.Behaviors.Add(selection);

ColumnSeries series = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    SegmentSelectionBrush = new SolidColorBrush(Colors.Green),

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0x4A))

};

ChartAdornmentInfo adornmentInfo = new ChartAdornmentInfo()
{

    ShowLabel = true,

    ShowConnectorLine = true,

    HighlightOnSelection = true,

    UseSeriesPalette = true,

    ConnectorHeight = 30

};

series.AdornmentsInfo = adornmentInfo;

chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Segments selection with adornments in UWP Chart](Interactive-Features_images/Interactive-Features_img39.jpeg)

**Series selection**

The following code example demonstrates the series selection with adornments 

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartSelectionBehavior EnableSegmentSelection="False" 

EnableSeriesSelection="True"/>

</syncfusion:SfChart.Behaviors>

<syncfusion:SplineSeries ItemsSource="{Binding Demands}" SeriesSelectionBrush="Green"

XBindingPath="Demand" 

YBindingPath="Year2010">

<syncfusion:SplineSeries.AdornmentsInfo>

<syncfusion:ChartAdornmentInfo Symbol="Ellipse"

ShowMarker="True"

HighlightOnSelection="True">                                            

</syncfusion:ChartAdornmentInfo>

</syncfusion:SplineSeries.AdornmentsInfo>

</syncfusion:SplineSeries>

<syncfusion:SplineSeries Label="2010" Interior="#4A4A4A" 

ItemsSource="{Binding Demands}" SeriesSelectionBrush="Green"

XBindingPath="Demand"

YBindingPath="Year2011">

<syncfusion:SplineSeries.AdornmentsInfo>

<syncfusion:ChartAdornmentInfo Symbol="Ellipse"

ShowMarker="True"

HighlightOnSelection="True">

</syncfusion:ChartAdornmentInfo>

</syncfusion:SplineSeries.AdornmentsInfo>

</syncfusion:SplineSeries>

{% endhighlight %}

{% highlight c# %}

ChartSelectionBehavior selection = new ChartSelectionBehavior()
{

    EnableSegmentSelection = false,

    EnableSeriesSelection = true

};

chart.Behaviors.Add(selection);

SplineSeries series1 = new SplineSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    SeriesSelectionBrush = new SolidColorBrush(Colors.Green)

};

ChartAdornmentInfo adornmentInfo = new ChartAdornmentInfo()
{

    ShowMarker = true,

    Symbol = ChartSymbol.Ellipse

};

series1.AdornmentsInfo = adornmentInfo;

SplineSeries series2 = new SplineSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2011",

    SeriesSelectionBrush = new SolidColorBrush(Colors.Green),

    Interior = new SolidColorBrush(Color.FromRgb(0x4A,0x4A,0x4A))

};

ChartAdornmentInfo adornmentInfo1 = new ChartAdornmentInfo()
{

    ShowMarker = true,

    Symbol = ChartSymbol.Ellipse,

    HighlightOnSelection = true

};

series2.AdornmentsInfo = adornmentInfo1;

chart.Series.Add(series1);

chart.Series.Add(series2);

{% endhighlight %}

{% endtabs %}

![Series selection with adornments in UWP Chart](Interactive-Features_images/Interactive-Features_img40.jpeg)


### Events

The following events are available in [`SfChart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html) for [`ChartSelectionBehavior`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSelectionBehavior.html),

* [`SelectionChanging`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartBase.html#Syncfusion_UI_Xaml_Charts_ChartBase_SelectionChanging)- Occurs when selection changing in chart area.
* [`SelectionChanged`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartBase.html#Syncfusion_UI_Xaml_Charts_ChartBase_SelectionChanged)- Occurs when selection changed in chart area. 


## Resizable Scrollbar

The resizable scrollbar is a type of scrollbar that can be resized within the track area by adjusting the scrolling thumbs. In the SfChart, a resizable scrollbar is used for zooming and panning across different chart segments.

### Adding scrollBar to the axis

[`EnableScrollBar`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartAxisBase2D.html#Syncfusion_UI_Xaml_Charts_ChartAxisBase2D_EnableScrollBar) property allows you to add the scrollbar for the particular axis. The following code snippet illustrates the scrollbar in the primary axis.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.PrimaryAxis>

<syncfusion:CategoryAxis EnableScrollBar="True" />

</syncfusion:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis()
{

    EnableScrollBar = true

};

{% endhighlight %}

{% endtabs %}

![Adding scrollbar to axis in UWP Chart](Interactive-Features_images/Interactive-Features_img41.jpeg)


**Deferred scrolling**

[`SfChart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html) provides support to suspend the value updates for every thumb values. This can be done using [`DeferredScrolling`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartAxisBase2D.html#Syncfusion_UI_Xaml_Charts_ChartAxisBase2D_DeferredScrolling) property in chart axis.The following code snippet demonstrates the deferred scrolling.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.PrimaryAxis>

<syncfusion:CategoryAxis EnableScrollBar="True" DeferredScrolling="True"/>

</syncfusion:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis()
{

    EnableScrollBar = true,

    DeferredScrolling = true,

};

{% endhighlight %}

{% endtabs %}

**Resizing the scrollbar**

[`SfChart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html) allows you to resize the scrollbar using [`EnableScrollBarResizing`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartAxisBase2D.html#Syncfusion_UI_Xaml_Charts_ChartAxisBase2D_EnableScrollBarResizing) property to true. By default the [`EnableScrollBarResizing`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartAxisBase2D.html#Syncfusion_UI_Xaml_Charts_ChartAxisBase2D_EnableScrollBarResizing) property is true. The following code example and image demonstrates scrollbar without resizing option.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.PrimaryAxis>

<syncfusion:CategoryAxis EnableScrollBar="True" EnableScrollBarResizing="False"/>

</syncfusion:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis()
{

    EnableScrollBar = true,

    EnableScrollBarResizing = false,

};

{% endhighlight %}

{% endtabs %}

![Resizing the scrollbar in UPW Chart](Interactive-Features_images/Interactive-Features_img42.jpeg)


### Scrollbar for touch mode

Scrollbar provides a touch mode style by enabling [`EnableTouchMode`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartAxisBase2D.html#Syncfusion_UI_Xaml_Charts_ChartAxisBase2D_EnableTouchMode) property to true as in the below code snippet.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.PrimaryAxis>

<syncfusion:CategoryAxis EnableScrollBar="True" EnableTouchMode="True"/>

</syncfusion:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis()
{

    EnableScrollBar = true,

    EnableTouchMode = true

};

{% endhighlight %}

{% endtabs %}

![Scrollbar for touch mode support in UWP Chart](Interactive-Features_images/Interactive-Features_img43.jpeg)


**Thumb label**

In touch mode while resizing or dragging the scrollbar to view thumb labels the [`ThumbLabelVisibility`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartAxis.html#Syncfusion_UI_Xaml_Charts_ChartAxis_ThumbLabelVisibility) is set to true.

The following code example demonstrates the thumb labels in scrollbar.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.PrimaryAxis>

<syncfusion:CategoryAxis EnableScrollBar="True" ThumbLabelVisibility="Visible" EnableTouchMode="True"/>

</syncfusion:SfChart.PrimaryAxis>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis()
{

    EnableScrollBar = true,

    EnableTouchMode = true,

    ThumbLabelVisibility = Visibility.Visible

};

{% endhighlight %}

{% endtabs %}

![Thumb label for scrollbar in UWP Chart](Interactive-Features_images/Interactive-Features_img44.jpeg)


**ThumbLabelTemplate**

[`ThumbLabelTemplate`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartAxis.html#Syncfusion_UI_Xaml_Charts_ChartAxis_ThumbLabelTemplate) property provides the custom template for the scroll bar thumb

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart x:Name="chart">

    <syncfusion:SfChart.Resources>

        <DataTemplate x:Key="labelTemplate">

            <Grid>

                <Border BorderBrush="Black" Background="Pink" 
                                
                        BorderThickness="2">

                    <TextBlock Text="{Binding}" FontSize="15"/>

                </Border>

            </Grid>

        </DataTemplate>

    </syncfusion:SfChart.Resources>

    <syncfusion:SfChart.PrimaryAxis>

        <syncfusion:CategoryAxis EnableTouchMode="True" EnableScrollBar="True"
                                         
                                 ThumbLabelVisibility="Visible"
                                         
                                 ThumbLabelTemplate="{StaticResource labelTemplate}"/>

    </syncfusion:SfChart.PrimaryAxis>

</syncfusion:SfChart>

{% endhighlight %}

{% highlight c# %}

chart.PrimaryAxis = new CategoryAxis()
{

    EnableTouchMode = true,

    EnableScrollBar = true,

    ThumbLabelVisibility = Visibility.Visible,

    ThumbLabelTemplate = chart.Resources["labelTemplate"] as DataTemplate

};

{% endhighlight %}

{% endtabs %}

![Label template support for scrollbar thumb in UWP Chart](Interactive-Features_images/Interactive-Features_img45.jpeg)

## CrossHair

[`ChartCrossHairBehavior`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartCrossHairBehavior.html) is used to view the values at mouse point or touch contact point. By moving these lines horizontally, you can get the X values and by moving these lines vertically, you can get the Y values.

### Adding CrossHairBehavior to SfChart

You can create an instance [`ChartCrossHairBehavior`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartCrossHairBehavior.html) and add it to the [`Behaviors`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html#Syncfusion_UI_Xaml_Charts_SfChart_Behaviors) collection.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartCrossHairBehavior />

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartCrossHairBehavior behavior = new ChartCrossHairBehavior();

chart.Behaviors.Add(behavior);

{% endhighlight %}

{% endtabs %}

To view the axis labels then set the [`ShowTrackBallInfo`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartAxis.html#Syncfusion_UI_Xaml_Charts_ChartAxis_ShowTrackBallInfo) property to true as in the below code snippet.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.PrimaryAxis>

<syncfusion:CategoryAxis  ShowTrackBallInfo="True"/>

</syncfusion:SfChart.PrimaryAxis>

<syncfusion:SfChart.SecondaryAxis>

<syncfusion:NumericalAxis  ShowTrackBallInfo="True"/>

</syncfusion:SfChart.SecondaryAxis>

{% endhighlight %}

{% highlight c# %}

ChartCrossHairBehavior behavior = new ChartCrossHairBehavior();

chart.Behaviors.Add(behavior);

chart.PrimaryAxis = new CategoryAxis()
{

    ShowTrackBallInfo = true

};

chart.SecondaryAxis = new NumericalAxis()
{

    ShowTrackBallInfo = true

};

{% endhighlight %}

{% endtabs %}

![Cross hair support in UWP Chart](Interactive-Features_images/Interactive-Features_img46.jpeg)


Cross hair is composed of the following parts.

1. Vertical and horizontal line.

2. Axis Labels

### Vertical and Horizontal Line

If you add [`ChartCrossHairBehavior`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartCrossHairBehavior.html) to chart you can see horizontal and vertical lines.The horizontal and vertical lines can be customized using [`HorizontalLineStyle`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartCrossHairBehavior.html#Syncfusion_UI_Xaml_Charts_ChartCrossHairBehavior_HorizontalLineStyle) and [`VerticalLineStyle`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartCrossHairBehavior.html#Syncfusion_UI_Xaml_Charts_ChartCrossHairBehavior_VerticalLineStyle) properties.

**HorizontalLineStyle**

The following code snippet demonstrates the line style for horizontal line in cross hair.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart x:Name="chart">

    <syncfusion:SfChart.Resources>

        <Style TargetType="Line" x:Key="lineStyle">

            <Setter Property="Stroke" Value="Green"></Setter>

            <Setter Property="StrokeThickness" Value="1"></Setter>

        </Style>
                
    </syncfusion:SfChart.Resources>

    <syncfusion:SfChart.Behaviors>

        <syncfusion:ChartCrossHairBehavior HorizontalLineStyle="{StaticResource lineStyle}"/>

    </syncfusion:SfChart.Behaviors>

</syncfusion:SfChart>

{% endhighlight %}

{% highlight c# %}

ChartCrossHairBehavior crosshair = new ChartCrossHairBehavior()
{

    HorizontalLineStyle = chart.Resources["lineStyle"] as Style

};

chart.Behaviors.Add(crosshair);

{% endhighlight %}

{% endtabs %}

![Vertical and horizontal line for cross hair in UWP Chart](Interactive-Features_images/Interactive-Features_img47.jpeg)


**VerticalLineStyle**

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart x:Name="chart">

    <syncfusion:SfChart.Resources>

        <Style TargetType="Line" x:Key="lineStyle">

            <Setter Property="StrokeDashArray" Value="10,5"/>

            <Setter Property="Stroke" Value="Red"/>

             <Setter Property="StrokeThickness" Value="1"/>

        </Style>
                
    </syncfusion:SfChart.Resources>

     <syncfusion:SfChart.Behaviors>

                <syncfusion:ChartCrossHairBehavior VerticalLineStyle="{StaticResource lineStyle}"/>

    </syncfusion:SfChart.Behaviors>

</syncfusion:SfChart>

{% endhighlight %}

{% highlight c# %}

ChartCrossHairBehavior crosshair = new ChartCrossHairBehavior()
{

    VerticalLineStyle = chart.Resources["lineStyle"] as Style

};

chart.Behaviors.Add(crosshair);

{% endhighlight %}

{% endtabs %}

![Cross hair line style in UWP Chart](Interactive-Features_images/Interactive-Features_img48.jpeg)


### Horizontal axis label

The vertical line in contact with the x axes shows axis label. The horizontal axis label can be aligned using [`HorizontalAxisLabelAlignment`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartCrossHairBehavior.html#Syncfusion_UI_Xaml_Charts_ChartCrossHairBehavior_HorizontalAxisLabelAlignment) property.

Axis Label can be aligned by Near, Far, Center, Auto and None Options.

[`Auto`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartAlignment.html#Syncfusion_UI_Xaml_Charts_ChartAlignment_Auto) –Axis label is aligned in Near/Far positions based on the movement of vertical line.

[`Far`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartAlignment.html#Syncfusion_UI_Xaml_Charts_ChartAlignment_Far)-Axis label is positioned far from the position of vertical line in cross hair.

[`Near`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartAlignment.html#Syncfusion_UI_Xaml_Charts_ChartAlignment_Near)- Axis label is near to the position of trackball.

[`Center`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartAlignment.html#Syncfusion_UI_Xaml_Charts_ChartAlignment_Center)-Axis label is aligned to the center of the vertical line. By default the axis label will positioned in center.

The following image demonstrates the horizontal axis label positioned center to the vertical line.

![Axis label alignment support for cross hair in UWP Chart](Interactive-Features_images/Interactive-Features_img49.jpeg)


**Far**

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartCrossHairBehavior HorizontalAxisLabelAlignment="Far ">

</syncfusion:ChartCrossHairBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartCrossHairBehavior behavior = new ChartCrossHairBehavior()
{

    HorizontalAxisLabelAlignment = ChartAlignment.Far

};

chart.Behaviors.Add(behavior);

{% endhighlight %}

{% endtabs %}

![Axis label alignment support for cross hair in UWP Chart](Interactive-Features_images/Interactive-Features_img50.jpeg)


**Near**

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartCrossHairBehavior HorizontalAxisLabelAlignment="Near ">

</syncfusion:ChartCrossHairBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartCrossHairBehavior behavior = new ChartCrossHairBehavior()
{

    HorizontalAxisLabelAlignment = ChartAlignment.Near

};

chart.Behaviors.Add(behavior);

{% endhighlight %}

{% endtabs %}

![Axis label alignment support for cross hair in UWP Chart](Interactive-Features_images/Interactive-Features_img51.jpeg)


### Vertical axis label

Vertical axis label is displayed when the horizontal line in contact with x axis.The label can be aligned using [`VerticalAxisLabelAlignment`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartCrossHairBehavior.html#Syncfusion_UI_Xaml_Charts_ChartCrossHairBehavior_VerticalAxisLabelAlignment) property.

Axis Label can be aligned by [`Near`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartAlignment.html#Syncfusion_UI_Xaml_Charts_ChartAlignment_Near), [`Far`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartAlignment.html#Syncfusion_UI_Xaml_Charts_ChartAlignment_Far), [`Center`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartAlignment.html#Syncfusion_UI_Xaml_Charts_ChartAlignment_Center) and [`Auto`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartAlignment.html#Syncfusion_UI_Xaml_Charts_ChartAlignment_Auto) Options.

The following image demonstrates the horizontal axis label positioned center to the vertical line.

![Axis label alignment support for cross hair in UWP Chart](Interactive-Features_images/Interactive-Features_img52.jpeg)


**Near**

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartCrossHairBehavior VerticalAxisLabelAlignment="Near">

</syncfusion:ChartCrossHairBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartCrossHairBehavior behavior = new ChartCrossHairBehavior()
{

    VerticalAxisLabelAlignment = ChartAlignment.Near

};

chart.Behaviors.Add(behavior);

{% endhighlight %}

{% endtabs %}

![Axis label alignment support for cross hair in UWP Chart](Interactive-Features_images/Interactive-Features_img53.jpeg)

**Far**

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartCrossHairBehavior VerticalAxisLabelAlignment="Far"  >

</syncfusion:ChartCrossHairBehavior>

</syncfusion:SfChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

ChartCrossHairBehavior behavior = new ChartCrossHairBehavior()
{

    VerticalAxisLabelAlignment = ChartAlignment.Far

};

chart.Behaviors.Add(behavior);

{% endhighlight %}

{% endtabs %}

![Axis label alignment support for cross hair in UWP Chart](Interactive-Features_images/Interactive-Features_img54.jpeg)






 
