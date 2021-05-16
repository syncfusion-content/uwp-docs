---
layout: post
title: Scales in UWP Radial Gauge control | Syncfusion
description: Learn here all about Scales support in Syncfusion UWP Radial Gauge (SfCircularGauge) control and more.
platform: uwp
control: SfCircularGauge
documentation: ug
---
# Scales in UWP Radial Gauge (SfCircularGauge)

Scales contain a collection of [`CircularScale`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gauges.CircularScale.html) elements, which integrate labels, tick marks, and a rim to customize the basic look and feel of the circular gauge.

## Scale

The [`CircularScale`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gauges.CircularScale.html) contains sub elements such as rim, ticks, labels, ranges, and pointers. They define the radius, start angle, sweep direction, sweep angle, overall minimum and maximum values, frequency of labels, and tick marks. A scale will have multiple ranges.

A range is a visual element, which begins and ends at the specified values within a [`CircularScale`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gauges.CircularScale.html). A range will have one or more pointers to point out the values in a scale.

{% tabs %}

{% highlight xml %}

    <gauge:SfCircularGauge>

     <gauge:SfCircularGauge.Scales>

    <gauge:CircularScale Radius="150" RimStroke="#39B2C6" RimStrokeThickness="8"

     TickStroke="#BEBEBE" LabelStroke="#9E9E9E" SmallTickStroke="#BEBEBE" />

     </gauge:SfCircularGauge.Scales>

     </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

SfCircularGauge sfCircularGauge = new SfCircularGauge();

CircularScale circularScale = new CircularScale();

circularScale.Radius = 150;

circularScale.RimStroke = new SolidColorBrush(Color.FromArgb(0xff, 0x57, 0xb2, 0xc6));

circularScale.TickStroke = new SolidColorBrush(Color.FromArgb(0xff, 0xc1, 0xc1, 0xc1));

circularScale.SmallTickStroke = new SolidColorBrush(Color.FromArgb(0xff, 0xc1, 0xc1, 0xc1));

circularScale.RimStrokeThickness = 8;

circularScale.LabelStroke = new SolidColorBrush(Color.FromArgb(0xff, 0x99, 0x99, 0x99));

sfCircularGauge.Scales.Add(circularScale);

{% endhighlight %}

{% endtabs %}

![Circular Scale Image](Scales_images/Scales_img1.png)

## Setting start and end values for scale

The [`StartValue`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gauges.CircularScale.html#Syncfusion_UI_Xaml_Gauges_CircularScale_StartValue)  and [`EndValue`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gauges.CircularScale.html#Syncfusion_UI_Xaml_Gauges_CircularScale_EndValue)  properties allow you to set the start and end values for a scale.

{% tabs %}

{% highlight xml %}

    <gauge:SfCircularGauge>

    <gauge:SfCircularGauge.Scales>

     <gauge:CircularScale StartValue="-30" EndValue="50" Radius="150" RimStroke="#39B2C6" RimStrokeThickness="8"

    TickStroke="#BEBEBE" LabelStroke="#9E9E9E" SmallTickStroke="#BEBEBE">

    <gauge:CircularScale.Pointers>

    <gauge:CircularPointer NeedlePointerVisibility="Collapsed"/>

    </gauge:CircularScale.Pointers>

    </gauge:CircularScale>

    </gauge:SfCircularGauge.Scales>

    </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

SfCircularGauge sfCircularGauge = new SfCircularGauge();

CircularScale circularScale = new CircularScale();

circularScale.Radius = 150;

circularScale.StartValue = -30;

circularScale.EndValue = 50;

circularScale.RimStroke = new SolidColorBrush(Color.FromArgb(0xff, 0x57, 0xb2, 0xc6));

circularScale.TickStroke = new SolidColorBrush(Color.FromArgb(0xff, 0xc1, 0xc1, 0xc1));

circularScale.SmallTickStroke = new SolidColorBrush(Color.FromArgb(0xff, 0xc1, 0xc1, 0xc1));

circularScale.RimStrokeThickness = 8;

circularScale.LabelStroke = new SolidColorBrush(Color.FromArgb(0xff, 0x99, 0x99, 0x99));

CircularPointer circularPointer = new CircularPointer();

circularPointer.NeedlePointerVisibility = Windows.UI.Xaml.Visibility.Collapsed;

circularScale.Pointers.Add(circularPointer);

sfCircularGauge.Scales.Add(circularScale);

{% endhighlight %}

{% endtabs %}

![Circular Scale Start And End Image](Scales_images/Scales_img2.png)

## Setting start and sweep angles for scale

The [`StartAngle`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gauges.CircularScale.html#Syncfusion_UI_Xaml_Gauges_CircularScale_StartAngle)   and [`SweepAngle`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gauges.CircularScale.html#Syncfusion_UI_Xaml_Gauges_CircularScale_SweepAngle)  properties allow you to set the start and end angles for a scale.

{% tabs %}

{% highlight xml %}

    <gauge:SfCircularGauge>

    <gauge:SfCircularGauge.Scales>

    <gauge:CircularScale StartAngle="185" SweepAngle="270" Radius="150" RimStroke="#39B2C6" RimStrokeThickness="8"

    TickStroke="#BEBEBE" LabelStroke="#9E9E9E" SmallTickStroke="#BEBEBE">

    <gauge:CircularScale.Pointers>

    <gauge:CircularPointer NeedlePointerVisibility="Collapsed"/>

    </gauge:CircularScale.Pointers>

    </gauge:CircularScale>

    </gauge:SfCircularGauge.Scales>

    </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

SfCircularGauge sfCircularGauge = new SfCircularGauge();

CircularScale circularScale = new CircularScale();

circularScale.Radius = 150;

circularScale.StartAngle = 185;

circularScale.SweepAngle = 270;

circularScale.RimStroke = new SolidColorBrush(Color.FromArgb(0xff, 0x57, 0xb2, 0xc6));

circularScale.TickStroke = new SolidColorBrush(Color.FromArgb(0xff, 0xc1, 0xc1, 0xc1));

circularScale.SmallTickStroke = new SolidColorBrush(Color.FromArgb(0xff, 0xc1, 0xc1, 0xc1));

circularScale.RimStrokeThickness = 8;

circularScale.LabelStroke = new SolidColorBrush(Color.FromArgb(0xff, 0x99, 0x99, 0x99));

CircularPointer circularPointer = new CircularPointer();

circularPointer.NeedlePointerVisibility = Windows.UI.Xaml.Visibility.Collapsed;

circularScale.Pointers.Add(circularPointer);

sfCircularGauge.Scales.Add(circularScale);

{% endhighlight %}

{% endtabs %}

![Circular Scale Start And End Angle Image](Scales_images/Scales_img3.png)


## Setting interval for scale

The [`Interval`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gauges.CircularScale.html#Syncfusion_UI_Xaml_Gauges_CircularScale_Interval)  property allows you to set the interval for a scale.

{% tabs %}

{% highlight xml %}

    <gauge:SfCircularGauge>

    <gauge:SfCircularGauge.Scales>

    <gauge:CircularScale StartValue="0" EndValue="500" Interval="100" Radius="150" RimStroke="#39B2C6" 
    
    RimStrokeThickness="8"

    TickStroke="#BEBEBE" LabelStroke="#9E9E9E" SmallTickStroke="#BEBEBE">

    <gauge:CircularScale.Pointers>

    <gauge:CircularPointer NeedlePointerVisibility="Collapsed"/>

    </gauge:CircularScale.Pointers>

    </gauge:CircularScale>

    </gauge:SfCircularGauge.Scales>

    </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

SfCircularGauge sfCircularGauge = new SfCircularGauge();

CircularScale circularScale = new CircularScale();

circularScale.Radius = 150;

circularScale.StartValue = 0;

circularScale.EndValue = 500;

circularScale.Interval = 100;

circularScale.RimStroke = new SolidColorBrush(Color.FromArgb(0xff, 0x57, 0xb2, 0xc6));

circularScale.TickStroke = new SolidColorBrush(Color.FromArgb(0xff, 0xc1, 0xc1, 0xc1));

circularScale.SmallTickStroke = new SolidColorBrush(Color.FromArgb(0xff, 0xc1, 0xc1, 0xc1));

circularScale.RimStrokeThickness = 8;

circularScale.LabelStroke = new SolidColorBrush(Color.FromArgb(0xff, 0x99, 0x99, 0x99));

CircularPointer circularPointer = new CircularPointer();

circularPointer.NeedlePointerVisibility = Windows.UI.Xaml.Visibility.Collapsed;

circularScale.Pointers.Add(circularPointer);

sfCircularGauge.Scales.Add(circularScale);

{% endhighlight %}

{% endtabs %}

![Circular Scale Interval Image](Scales_images/Scales_img4.png)

## Setting auto interval for scale

By default, the interval value is calculated by 10. By using the [`EnableAutoInterval`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gauges.CircularScale.html#Syncfusion_UI_Xaml_Gauges_CircularScale_EnableAutoInterval) property, you can set auto interval based on the start and end values.

{% tabs %}

{% highlight xml %}

    <gauge:SfCircularGauge>

    <gauge:SfCircularGauge.Scales>

    <gauge:CircularScale StartValue="0" EndValue="1000" EnableAutoInterval="true"  Radius="150" RimStroke="#39B2C6" 
    
    RimStrokeThickness="8"

    TickStroke="#BEBEBE" LabelStroke="#9E9E9E" SmallTickStroke="#BEBEBE">

    <gauge:CircularScale.Pointers>

    <gauge:CircularPointer NeedlePointerVisibility="Collapsed"/>

    </gauge:CircularScale.Pointers>

    </gauge:CircularScale>

    </gauge:SfCircularGauge.Scales>

    </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

           SfCircularGauge sfCircularGauge = new SfCircularGauge();

            CircularScale circularScale = new CircularScale();

            circularScale.Radius = 150;

            circularScale.StartValue = 0;

            circularScale.EndValue = 1000;

            circularScale.EnableAutoInterval = true;

            circularScale.RimStroke = new SolidColorBrush(Color.FromArgb(0xff, 0x57, 0xb2, 0xc6));

            circularScale.TickStroke = new SolidColorBrush(Color.FromArgb(0xff, 0xc1, 0xc1, 0xc1));

            circularScale.SmallTickStroke = new SolidColorBrush(Color.FromArgb(0xff, 0xc1, 0xc1, 0xc1));

            circularScale.RimStrokeThickness = 8;

            circularScale.LabelStroke = new SolidColorBrush(Color.FromArgb(0xff, 0x99, 0x99, 0x99));

            CircularPointer circularPointer = new CircularPointer();

            circularPointer.NeedlePointerVisibility = Windows.UI.Xaml.Visibility.Collapsed;

            circularScale.Pointers.Add(circularPointer);

            sfCircularGauge.Scales.Add(circularScale);

{% endhighlight %}

{% endtabs %}

![Circular Scale Auto Interval Image](Scales_images/Scales_img5.png)

## Setting scale direction for scale

The [`SweepDirection`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gauges.CircularScale.html#Syncfusion_UI_Xaml_Gauges_CircularScale_SweepDirection) property allows you to render the gauge scale in either clockwise or counterclockwise direction.

{% tabs %}

{% highlight xml %}

    <gauge:SfCircularGauge>

    <gauge:SfCircularGauge.Scales>

    <gauge:CircularScale StartValue="0" EndValue="100" SweepDirection="Counterclockwise"  Radius="150" 
    
    RimStroke="#39B2C6" RimStrokeThickness="8"

    TickStroke="#BEBEBE" LabelStroke="#9E9E9E" SmallTickStroke="#BEBEBE">

    <gauge:CircularScale.Pointers>

    <gauge:CircularPointer NeedlePointerVisibility="Collapsed"/>

    </gauge:CircularScale.Pointers>

    </gauge:CircularScale>

    </gauge:SfCircularGauge.Scales>

    </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

            SfCircularGauge sfCircularGauge = new SfCircularGauge();

            CircularScale circularScale = new CircularScale();

            circularScale.Radius = 150;

            circularScale.StartValue = 0;

            circularScale.EndValue = 100;

            circularScale.SweepDirection = SweepDirection.Counterclockwise;

            circularScale.RimStroke = new SolidColorBrush(Color.FromArgb(0xff, 0x57, 0xb2, 0xc6));

            circularScale.TickStroke = new SolidColorBrush(Color.FromArgb(0xff, 0xc1, 0xc1, 0xc1));

            circularScale.SmallTickStroke = new SolidColorBrush(Color.FromArgb(0xff, 0xc1, 0xc1, 0xc1));

            circularScale.RimStrokeThickness = 8;

            circularScale.LabelStroke = new SolidColorBrush(Color.FromArgb(0xff, 0x99, 0x99, 0x99));

            CircularPointer circularPointer = new CircularPointer();

            circularPointer.NeedlePointerVisibility = Windows.UI.Xaml.Visibility.Collapsed;

            circularScale.Pointers.Add(circularPointer);

            sfCircularGauge.Scales.Add(circularScale);

{% endhighlight %}

{% endtabs %}

![Circular Scale Direction Image](Scales_images/Scales_img6.png)

## Setting multiple scales for circular gauge

You can add multiple scales to the same circular gauge and customize all the scales in a [`Scales`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gauges.SfCircularGauge.html#Syncfusion_UI_Xaml_Gauges_SfCircularGauge_Scales)  collection.

{% tabs %}

{% highlight xml %}

    <Grid Background="Black">

    <gauge:SfCircularGauge SpacingMargin="0.7">

    <gauge:SfCircularGauge.Scales>

    <gauge:CircularScale Radius="175" TickStroke="White" SmallTickStroke="White" LabelStroke="White">

    <gauge:CircularScale.Ranges>

    <gauge:CircularRange  StartValue="0" 

    EndValue="60"  Stroke="#B0B0B0"  StrokeThickness="5" />

    <gauge:CircularRange  StartValue="60" 

    EndValue="100" Stroke="#C1252C" StrokeThickness="5"/>

    </gauge:CircularScale.Ranges>

    <gauge:CircularScale.Pointers>

    <gauge:CircularPointer Value="30" 

    PointerType="SymbolPointer"  Symbol="InvertedArrow"   SymbolPointerWidth="30" 

    SymbolPointerHeight="20"    SymbolPointerStroke="Green"  SymbolPointerBorderBrush="Green"/>

    </gauge:CircularScale.Pointers>

    </gauge:CircularScale>

    <gauge:CircularScale Radius="90" TickStroke="White" SmallTickStroke="White" LabelStroke="White">

    <gauge:CircularScale.Ranges>

    <gauge:CircularRange  StartValue="0"   EndValue="60"  Stroke="#B0B0B0"  StrokeThickness="5" />

    <gauge:CircularRange  StartValue="60"    EndValue="100"   Stroke="#C1252C" StrokeThickness="5"/>

    </gauge:CircularScale.Ranges>

    <gauge:CircularScale.Pointers>

    <gauge:CircularPointer Value="30" PointerType="NeedlePointer" NeedlePointerStroke="#C1252C"/>

    </gauge:CircularScale.Pointers>

    </gauge:CircularScale>

    </gauge:SfCircularGauge.Scales>

    </gauge:SfCircularGauge>

    </Grid>

{% endhighlight %}

{% highlight c# %}

this.Background = new SolidColorBrush(Colors.Black);

SfCircularGauge circularGauge = new SfCircularGauge();

CircularScale scale1 = new CircularScale();

scale1.TickStroke = new SolidColorBrush(Colors.White);

scale1.LabelStroke = new SolidColorBrush(Colors.White);

scale1.SmallTickStroke = new SolidColorBrush(Colors.White);

scale1.Radius = 175;

CircularScale scale2 = new CircularScale();

scale2.TickStroke = new SolidColorBrush(Colors.White);

scale2.LabelStroke = new SolidColorBrush(Colors.White);

scale2.SmallTickStroke = new SolidColorBrush(Colors.White);

scale2.Radius = 90;

CircularRange circularRange = new CircularRange();

circularRange.StartValue = 0;

circularRange.EndValue = 60;

circularRange.Stroke = new SolidColorBrush(Color.FromArgb(0xFF, 0xB0, 0xB0, 0xB0));

circularRange.StrokeThickness = 5;

scale1.Ranges.Add(circularRange);

CircularRange circularRange1 = new CircularRange();

circularRange1.StartValue = 60;

circularRange1.EndValue = 100;

circularRange1.Stroke = new SolidColorBrush(Color.FromArgb(0xFF, 0xC1, 0x25, 0x2C));

circularRange1.StrokeThickness = 5;

scale1.Ranges.Add(circularRange1);

CircularPointer circularPointer = new CircularPointer();

circularPointer.Value = 30;

circularPointer.PointerType = PointerType.SymbolPointer;

circularPointer.Symbol = Syncfusion.UI.Xaml.Gauges.Symbol.InvertedArrow;

circularPointer.SymbolPointerWidth = 30;

circularPointer.SymbolPointerHeight = 20;

circularPointer.SymbolPointerStroke = new SolidColorBrush(Colors.Green);

circularPointer.SymbolPointerBorderBrush = new SolidColorBrush(Colors.Green);

scale1.Pointers.Add(circularPointer);

CircularRange circularRange2 = new CircularRange();

circularRange2.StartValue = 0;

circularRange2.EndValue = 60;

circularRange2.Stroke = new SolidColorBrush(Color.FromArgb(0xFF, 0xB0, 0xB0, 0xB0));

circularRange2.StrokeThickness = 5;

scale2.Ranges.Add(circularRange2);

CircularRange circularRange3 = new CircularRange();

circularRange3.StartValue = 60;

circularRange3.EndValue = 100;

circularRange3.Stroke = new SolidColorBrush(Color.FromArgb(0xFF, 0xC1, 0x25, 0x2C));

circularRange3.StrokeThickness = 5;

scale2.Ranges.Add(circularRange3);

CircularPointer circularPointer2 = new CircularPointer();

circularPointer2.Value = 30;

circularPointer2.PointerType = PointerType.NeedlePointer;

circularPointer2.NeedlePointerStroke = new SolidColorBrush(Color.FromArgb(0xFF, 0xC1, 0x25, 0x2C));

scale2.Pointers.Add(circularPointer2);

circularGauge.Scales.Add(scale1);

circularGauge.Scales.Add(scale2);

{% endhighlight %}

{% endtabs %}

![Circular Scale Maximum Labels Image](Scales_images/Scales_img7.png)

## Calculate radius and center based on angle

This feature is used to automatically adjust the radius and center of a circular gauge based on the `StartAngle` and `SweepAngle` properties by enable the `IsCenterAligned` property of gauge.

N> Default value of the IsCenterAligned property is false. To enable the center align feature, you need to set Ticks, Labels and Range position as Custom and set IsCenterAligned as true.

{% tabs %}

{% highlight xaml %}

         <gauge:SfCircularGauge Height="500" IsCenterAligned="True" Width="500" >
            <gauge:SfCircularGauge.Scales>
                <gauge:CircularScale  EnableAutoAngle="True" 
                    StartAngle="181" 
                    SweepAngle="180" 
                    StartValue="0" 
                    EndValue="1000"
                    SymbolPointerOffset="1"
                    Interval="500" 
                    RangePointerOffset="0"
                    RimStroke="LightGray"
                    EnableAutoInterval="True"
                    RimStrokeThickness="15"  
                    TickStroke="#BEBEBE" 
                    LabelStroke="Black"
                     FontSize="20"
                    SmallTickStroke="#BEBEBE">
                    <gauge:CircularScale.Pointers>
                        <gauge:CircularPointer PointerType="NeedlePointer" Value="500"  NeedleLengthFactor="0.5" NeedlePointerType="Triangle" PointerCapDiameter="15" PointerCapStroke="#007DD1" BorderBrush="#007DD1"  NeedlePointerStroke="#424242" />
                        <gauge:CircularPointer RangeCap="Both" PointerType="RangePointer" Value="1000" RangePointerStroke="Brown" RangePointerStrokeThickness="15"/>
                        <gauge:CircularPointer PointerType="SymbolPointer" Value="300" Symbol="InvertedArrow" SymbolPointerBorderBrush="Brown" SymbolPointerStroke="Brown" SymbolPointerHeight="30"  SymbolPointerWidth="30"  />
                    </gauge:CircularScale.Pointers>
                </gauge:CircularScale>
            </gauge:SfCircularGauge.Scales>
        </gauge:SfCircularGauge>
   

{% endhighlight %}

{% highlight c# %}

           SfCircularGauge sfCircularGauge = new SfCircularGauge();
            sfCircularGauge.Height = 500;
            sfCircularGauge.Width = 500;
            sfCircularGauge.IsCenterAligned = true;
            CircularScale circularScale = new CircularScale();
            circularScale.EnableAutoAngle = true;
            circularScale.StartAngle = 180;
            circularScale.SweepAngle = 180;
            circularScale.StartValue = 0;
            circularScale.EndValue = 1000;
            circularScale.SymbolPointerOffset = 1;
            circularScale.Interval = 500;
            circularScale.RangePointerOffset = 0;
            circularScale.RimStroke = new SolidColorBrush(Colors.LightGray);
            circularScale.EnableAutoInterval = true;
            circularScale.RimStrokeThickness = 15;
            circularScale.TickStroke = new SolidColorBrush(Colors.LightGray);
            circularScale.LabelStroke = new SolidColorBrush(Colors.Black);
            circularScale.FontSize = 20;
            circularScale.SmallTickStroke = new SolidColorBrush(Colors.LightGray);
            CircularPointer circularPointer = new CircularPointer();
            circularPointer.PointerType = PointerType.NeedlePointer;
            circularPointer.Value = 500;
            circularPointer.NeedleLengthFactor = 0.5;
            circularPointer.NeedlePointerType = NeedlePointerType.Triangle;
            circularPointer.PointerCapDiameter = 15;
            circularPointer.PointerCapStroke = new SolidColorBrush(Colors.Blue);
            circularPointer.NeedlePointerStroke = new SolidColorBrush(Colors.Black);
            circularScale.Pointers.Add(circularPointer);
            CircularPointer circularPointer1 = new CircularPointer();
            circularPointer1.RangeCap = RangeCap.Both;
            circularPointer1.PointerType = PointerType.RangePointer;
            circularPointer1.Value = 1000;
            circularPointer1.RangePointerStrokeThickness = 15;
            circularPointer1.RangePointerStroke = new SolidColorBrush(Colors.Brown);
            circularScale.Pointers.Add(circularPointer1);
            CircularPointer circularPointer2 = new CircularPointer();
            circularPointer2.PointerType = PointerType.SymbolPointer;
            circularPointer2.Value = 300;
            circularPointer2.Symbol = Syncfusion.UI.Xaml.Gauges.Symbol.InvertedArrow;
            circularPointer2.SymbolPointerBorderBrush = new SolidColorBrush(Colors.Brown);
            circularPointer2.SymbolPointerStroke = new SolidColorBrush(Colors.Brown);
            circularPointer2.SymbolPointerWidth = 30;
            circularPointer2.SymbolPointerHeight = 30;
            circularScale.Pointers.Add(circularPointer2);
            sfCircularGauge.Scales.Add(circularScale);
			
{% endhighlight %}

{% endtabs %}

![Center Aligned SfCircularGauge image](Scales_images/iscenteraligned.jpg)

