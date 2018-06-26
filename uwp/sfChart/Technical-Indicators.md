---
layout: post
title: Technical Indicators | SfChart | uwp | Syncfusion
description: technical indicators
platform: uwp
control: SfChart
documentation: ug
---

# Technical Indicator

Technical indicators are the base of technical analysis, which is used to determine the future market trends. 

## Adding Technical Indicators to the Chart

Technical indicator merely an another type meta series. The following steps illustrates how to add the technical indicators to the chart:

### Initializing Indicator

Create the instance for any technical indicator and add it to the [`TechnicalIndicators`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.SfChart~TechnicalIndicators.html) collection. 

Here for instance, the [AccumulationDistributionIndicator](#accumulationdistributionindicator) is added.

{% tabs %}

{% highlight xaml %}

<chart:SfChart.TechnicalIndicators>

<chart:AccumulationDistributionIndicator>

</chart:AccumulationDistributionIndicator>

</chart:SfChart.TechnicalIndicators>

{% endhighlight %}

{% highlight c# %}

AccumulationDistributionIndicator indicator = new AccumulationDistributionIndicator();

chart.TechnicalIndicators.Add(indicator);

{% endhighlight %}

{% endtabs %}

### Binding the Data

Next you need to bind the property path for the [`open`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.FinancialTechnicalIndicator~Open.html), [`high`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.FinancialTechnicalIndicator~High.html), [`low`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.FinancialTechnicalIndicator~Low.html) and [`close`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.FinancialTechnicalIndicator~Close.html) along with x value binding property.

{% tabs %}

{% highlight xaml %}

<chart:SfChart.TechnicalIndicators>

<chart:AccumulationDistributionIndicator Open="Open" Close="Close" High="High" Low="Low">                    

</chart:AccumulationDistributionIndicator>

</chart:SfChart.TechnicalIndicators>

{% endhighlight %}

{% highlight c# %}

AccumulationDistributionIndicator indicator = new AccumulationDistributionIndicator()
{

    Open = "Open", Close = "Close",

    High = "High", Low = "Low"

};

chart.TechnicalIndicators.Add(indicator);

{% endhighlight %}

{% endtabs %}

### Specifying the ItemsSource

{% tabs %}

{% highlight xaml %}

<chart:SfChart.TechnicalIndicators>

<chart:AccumulationDistributionIndicator Open="Open" Close="Close" High="High" 

Low="Low"  ItemsSource="{Binding StockPriceDetails}" 

XBindingPath="Date">                    

</chart:AccumulationDistributionIndicator>

</chart:SfChart.TechnicalIndicators>

{% endhighlight %}

{% highlight c# %}

AccumulationDistributionIndicator indicator = new AccumulationDistributionIndicator()
{

    ItemsSource = new ViewModel().StockPriceDetails,

    XBindingPath = "Date",

    Open = "Open", Close = "Close",

    High = "High", Low = "Low"

};

chart.TechnicalIndicators.Add(indicator);

{% endhighlight %}

{% endtabs %}

![](Technical-Indicators_images/overview_1.png)


The following sections covers all the different types of technical indicators available in [`SfChart`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.SfChart.html).

Most of the indicators are having the `Period` and `SignalLineColor` properties as common, in which Period property indicates the moving average period and the SignalLineColor defines the color for the respective indicator line.

## Average True Range

You can define the [`AverageTrueRangeIndicator`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.AverageTrueRangeIndicator.html) using the following code example

{% tabs %}

{% highlight xaml %}

<chart:SfChart.TechnicalIndicators>

<chart:AverageTrueRangeIndicator ItemsSource="{Binding  ViewModel1}"    

Period="3" XBindingPath="Date" Volume="Volume"

SignalLineColor="Black" High="High" Low="Low"

Open="Open" Close="Close"/ >

</chart:SfChart.TechnicalIndicators>

{% endhighlight %}

{% highlight c# %}

AverageTrueRangeIndicator indicator = new AverageTrueRangeIndicator()
{

    ItemsSource = new ViewModel().StockPriceDetails,

    XBindingPath = "Date",

    Open = "Open", Close = "Close",

    High = "High", Low = "Low",

    Volume ="Volume", Period = 3,

    SignalLineColor = new SolidColorBrush(Colors.Black)

};

chart.TechnicalIndicators.Add(indicator);

{% endhighlight %}

{% endtabs %}

![](Technical-Indicators_images/atr.png)


## Simple Average 

The following code example demonstrates the usage of [`SimpleAverageIndicator`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.SimpleAverageIndicator.html).

{% tabs %}

{% highlight xaml %}

<chart:SfChart.TechnicalIndicators>

<chart:SimpleAverageIndicator ItemsSource="{Binding  ViewModel1}"  Period="3"     

SignalLineColor="Black" XBindingPath="Date" 

Volume="Volume"  

High="High" Low="Low" Open="Open" Close="Close" >

</chart:SimpleAverageIndicator >

</chart:SfChart.TechnicalIndicators>

{% endhighlight %}

{% highlight c# %}

SimpleAverageIndicator indicator = new SimpleAverageIndicator()
{

    ItemsSource = new ViewModel().StockPriceDetails,

    XBindingPath = "Date",

    Open = "Open", Close = "Close",

    High = "High", Low = "Low",

    Volume ="Volume", Period = 3,

    SignalLineColor = new SolidColorBrush(Colors.Black)

};

chart.TechnicalIndicators.Add(indicator);

{% endhighlight %}

{% endtabs %}

![](Technical-Indicators_images/sa.png)


## RSI 

The [`Relative Strength Index(RSI)`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.RSITechnicalIndicator.html) indicators are having additional two lines other than signal line, which indicate the overbought and oversold region. 

The [`UpperLineColor`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.RSITechnicalIndicator~UpperLineColor.html) property is used to define the color for the line indicating overbought region and the [`LowerLineColor`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.RSITechnicalIndicator~LowerLineColor.html) property is used to define the color for the line indicating oversold region.

To define the [`RSITechnicalIndicator`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.RSITechnicalIndicator.html), you can use the following code example:

{% tabs %}

{% highlight xaml %}

<chart:SfChart.TechnicalIndicators>

<chart:RSITechnicalIndicator 

ItemsSource="{Binding  ViewModel1}"  Period="3"   

SignalLineColor="Black" XBindingPath="Date" Volume="Volume"  

UpperLineColor="Blue" LowerLineColor="Red"                  

High="High" Low="Low" Open="Open" Close="Close"/>

</chart:SfChart.TechnicalIndicators>

{% endhighlight %}

{% highlight c# %}

RSITechnicalIndicator indicator = new RSITechnicalIndicator()
{

    ItemsSource = new ViewModel().StockPriceDetails,

    XBindingPath = "Date",

    Open = "Open", Close = "Close",

    High = "High", Low = "Low",

    Volume ="Volume", Period = 3,

    SignalLineColor = new SolidColorBrush(Colors.Black),

    UpperLineColor = new SolidColorBrush(Colors.Blue),

    LowerLineColor = new SolidColorBrush(Colors.Red)

};

chart.TechnicalIndicators.Add(indicator);

{% endhighlight %}

{% endtabs %}

![](Technical-Indicators_images/rsi.png)


## Momentum 

This indicator having two lines momentum line and center line. No signal line in this indicator. You can define momentum technical indicator using the following code example.

The [`MomentumLineColor`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.MomentumTechnicalIndicator~MomentumLineColor.html) property and [`CenterLineColor`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.MomentumTechnicalIndicator~CenterLineColor.html) property are used to define the color for the momentum and center line respectively.

{% tabs %}

{% highlight xaml %}

<chart:SfChart.TechnicalIndicators>

<chart:MomentumTechnicalIndicator ItemsSource="{Binding  ViewModel1}"     

Period="3" CenterLineColor="red" XBindingPath="Date"        

Volume="Volume" MomentumLineColor="Black"

High="High" Low="Low" Open="Open" Close="Close"/ >

</chart:SfChart.TechnicalIndicators>

{% endhighlight %}

{% highlight c# %}

MomentumTechnicalIndicator indicator = new MomentumTechnicalIndicator()
{

    ItemsSource = new ViewModel().StockPriceDetails,

    XBindingPath = "Date",

    Open = "Open", Close = "Close",

    High = "High", Low = "Low",

    Volume ="Volume", Period = 3,

    MomentumLineColor = new SolidColorBrush(Colors.Black),

    CenterLineColor = new SolidColorBrush(Colors.Red)

};

chart.TechnicalIndicators.Add(indicator);

{% endhighlight %}

{% endtabs %}

![](Technical-Indicators_images/momentum.png)


## Stochastic 

[`Stochastic`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.StochasticTechnicalIndicator.html) indicator is used to measure the range and momentum of price movements. It contains [`KPeriod`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.StochasticTechnicalIndicator~KPeriod.html) and [`DPeriod`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.StochasticTechnicalIndicator~DPeriod.html) property defining the ‘K’ percentage and ‘D’ percentage respectively.No signal line in this indicator.

The [`UpperLineColor`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.StochasticTechnicalIndicator~UpperLineColor.html), [`LowerLineColor`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.StochasticTechnicalIndicator~LowerLineColor.html) and [`PeriodLineColor`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.StochasticTechnicalIndicator~PeriodLineColor.html) property are used to define the brushes for the Stochastic indicator lines.

You can define stochastic technical indicator using the following code example:

{% tabs %}

{% highlight xaml %}

<chart:SfChart.TechnicalIndicators>

<chart:StochasticTechnicalIndicator ItemsSource="{Binding  ViewModel1}" 

Period="3" SignalLineColor="Black" KPeriod="8" DPeriod="5"

XBindingPath="Date" Volume="Volume" UpperLineColor="Blue"

LowerLineColor="Purple" PeriodLineColor="Red"

High="High" Low="Low" Open="Open" Close="Close"/>

</chart:SfChart.TechnicalIndicators>

{% endhighlight %}

{% highlight c# %}

StochasticTechnicalIndicator indicator = new StochasticTechnicalIndicator()
{

    ItemsSource = new ViewModel().StockPriceDetails,

    XBindingPath = "Date", Volume = "Volume",

    Open = "Open", Close = "Close",

    High = "High", Low = "Low",

    Period = 3,KPeriod = 8,DPeriod = 5,

    SignalLineColor = new SolidColorBrush(Colors.Black),

    PeriodLineColor = new SolidColorBrush(Colors.Red),

    UpperLineColor = new SolidColorBrush(Colors.Blue),

    LowerLineColor = new SolidColorBrush(Colors.Purple)

};

chart.TechnicalIndicators.Add(indicator);

{% endhighlight %}

{% endtabs %}

![](Technical-Indicators_images/stochastic.png)


## Exponential Average

The [`ExponentialAverageIndicator`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ExponentialAverageIndicator.html) is similar to [SimpleAverageIndicator](#_simple-average) and this can be defined using the following code examples.

{% tabs %}

{% highlight xaml %}

<chart:SfChart.TechnicalIndicators>

<chart:ExponentialAverageIndicator  ItemsSource="{Binding  ViewModel1}"    

Period="3" XBindingPath="Date" Volume="Volume"

SignalLineColor="Black" High="High" Low="Low"

Open="Open" Close="Close"/ >

</chart:SfChart.TechnicalIndicators>

{% endhighlight %}

{% highlight c# %}

ExponentialAverageIndicator indicator = new ExponentialAverageIndicator()
{

    ItemsSource = new ViewModel().StockPriceDetails,

    XBindingPath = "Date",

    Open = "Open", Close = "Close",

    High = "High", Low = "Low",

    Volume ="Volume", Period = 3,

    SignalLineColor = new SolidColorBrush(Colors.Black)

};

chart.TechnicalIndicators.Add(indicator);

{% endhighlight %}

{% endtabs %}

![](Technical-Indicators_images/exponential.png)


## Triangular Average 

The [`TriangularAverageIndicator`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.TriangularAverageIndicator.html) can be defined as in the following code example.

{% tabs %}

{% highlight xaml %}

<chart:SfChart.TechnicalIndicators>

<chart:TriangularAverageIndicator  ItemsSource="{Binding  ViewModel1}"    

Period="3" XBindingPath="Date" Volume="Volume"

SignalLineColor="Black" High="High" Low="Low"

Open="Open" Close="Close"/ >

</chart:SfChart.TechnicalIndicators>

{% endhighlight %}

{% highlight c# %}

TriangularAverageIndicator indicator = new TriangularAverageIndicator()
{

    ItemsSource = new ViewModel().StockPriceDetails,

    XBindingPath = "Date",

    Open = "Open", Close = "Close",

    High = "High", Low = "Low",

    Volume ="Volume", Period = 3,

    SignalLineColor = new SolidColorBrush(Colors.Black)

};

chart.TechnicalIndicators.Add(indicator);

{% endhighlight %}

{% endtabs %}

![](Technical-Indicators_images/ta.png)


## Accumulation Distribution 

The following code example help you to add [`AccumulationDistributionIndicator`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.AccumulationDistributionIndicator.html).

{% tabs %}

{% highlight xaml %}

<chart:SfChart.TechnicalIndicators>

<chart:AccumulationDistributionIndicator 

ItemsSource="{Binding  ViewModel1}" 

XBindingPath="Date" Volume="Volume"    

SignalLineColor="Black" High="High" Low="Low" 

Open="Open" Close="Close" >                 

</chart:AccumulationDistributionIndicator >

</chart:SfChart.TechnicalIndicators>

{% endhighlight %}

{% highlight c# %}

AccumulationDistributionIndicator indicator = new AccumulationDistributionIndicator()
{

    ItemsSource = new ViewModel().StockPriceDetails,

    XBindingPath = "Date",

    Open = "Open", Close = "Close",

    High = "High", Low = "Low",

    Volume ="Volume", Period = 3,

    SignalLineColor = new SolidColorBrush(Colors.Black)

};

chart.TechnicalIndicators.Add(indicator);

{% endhighlight %}

{% endtabs %}

![](Technical-Indicators_images/accumulation.png)


## Bollinger Band

This indicator also having [`UpperLineColor`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.BollingerBandIndicator~UpperLineColor.html), [`LowerLineColor`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.BollingerBandIndicator~LowerLineColor.html) and [`SignalLineColor`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.BollingerBandIndicator~SignalLineColor.html) property for defining the brushes for the indicator lines.

You can define the [`BollingerBandIndicator`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.BollingerBandIndicator.html) using the following code example:

{% tabs %}

{% highlight xaml %}

<chart:SfChart.TechnicalIndicators>

<chart:BollingerBandIndicator 

ItemsSource="{Binding  ViewModel1}" Period="3"  

UpperLineColor="Blue" LowerLineColor="Red"

XBindingPath="Date" Volume="Volume" SignalLineColor="Black" 

High="High" Low="Low" Open="Open" Close="Close"/>

</chart:SfChart.TechnicalIndicators>

{% endhighlight %}

{% highlight c# %}

BollingerBandIndicator indicator = new BollingerBandIndicator()
{

    ItemsSource = new ViewModel().StockPriceDetails,

    XBindingPath = "Date",

    Open = "Open", Close = "Close",

    High = "High", Low = "Low",

    Volume ="Volume", Period = 3,

    SignalLineColor = new SolidColorBrush(Colors.Black),

    UpperLineColor = new SolidColorBrush(Colors.Blue),

    LowerLineColor = new SolidColorBrush(Colors.Red)

};

chart.TechnicalIndicators.Add(indicator);

{% endhighlight %}

{% endtabs %}

![](Technical-Indicators_images/bollinger.png)


## MACD 

This is mostly using indicator having [`ShortPeriod`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.MACDTechnicalIndicator~ShortPeriod.html) and [`LongPeriod`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.MACDTechnicalIndicator~LongPeriod.html) for defining the motion of the indicator.

Other than signal line, MACD is having convergence and divergence line. The brushes for these lines can be defined using [`ConvergenceLineColor`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.MACDTechnicalIndicator~ConvergenceLineColor.html) and [`DivergenceLineColor`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.MACDTechnicalIndicator~DivergenceLineColor.html).

Also you can draw line, histogram MACD or both using the [`Type`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.MACDTechnicalIndicator~Type.html) property, which defines the type of MACD to be drawn.

You can define the [`MACDTechnicalIndicator`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.MACDTechnicalIndicator.html) using the following code example:

{% tabs %}

{% highlight xaml %}

<chart:SfChart.TechnicalIndicators>

<chart:MACDTechnicalIndicator ItemsSource="{Binding  ViewModel1}" 

Type="Line"  ShortPeriod="2" Period="3" LongPeriod="6"

ConvergenceLineColor="Red" DivergenceLineColor="Blue"

XBindingPath="Date" Volume="Volume" SignalLineColor="Black" 

High="High" Low="Low" Open="Open" Close="Close" >

</chart:MACDTechnicalIndicator >

</chart:SfChart.TechnicalIndicators>

{% endhighlight %}

{% highlight c# %}

MACDTechnicalIndicator indicator = new MACDTechnicalIndicator()
{

    ItemsSource = new ViewModel().StockPriceDetails,

    XBindingPath = "Date", Volume = "Volume",

    Open = "Open", Close = "Close",

    High = "High", Low = "Low",

    Period = 3, ShortPeriod = 2, LongPeriod = 6,

    Type = MACDType.Line ,

    SignalLineColor = new SolidColorBrush(Colors.Black),

    ConvergenceLineColor = new SolidColorBrush(Colors.Red),

    DivergenceLineColor = new SolidColorBrush(Colors.Blue),

};

chart.TechnicalIndicators.Add(indicator);

{% endhighlight %}

{% endtabs %}

![](Technical-Indicators_images/macd.png)


