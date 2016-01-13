---
layout: post
title: Linear Gauge Elements | SfLinearGauge | uwp | Syncfusion
description: Linear Gauge Elements 
platform: uwp
control: SfLinearGauge
documentation: ug
---

# Getting Started

This section explains you the steps required to configure the **SfLinearauge** and also explains the steps to add basic elements of **SfLinearauge** through various API’s available within it.

## Configuring SfLinearGauge

SfLinearGauge exists in the following assembly and namespace.

**Assembly**: Syncfusion.SfGauge.UWP

**Namespace**: Syncfusion.UI.Xaml.Gauges

{% highlight xml %}

    <Gauges:SfLinearGauge/>

{% endhighlight %}

Run the above code and now the default SfLinearGauge can be displays as follows. In order to customize scales and other SfLinearGauge elements, you have to add the respecting element to SfLinearGauge.

![](Getting-Started_images/Getting-Started_img.png)

As you can see now in the above image, the SfLinearGauge displays its default elements. To customize the basic look and feel of the SfLinearGauge you have to add respective elements to SfLinearGauge, which will be explained in the next section.

## Configuring LinearScale 

You can configure the LinearScale elements by making use of following API’s available in SfLinearGauge.

They are:

* ScaleDirection
* ScaleBarStroke
* ScaleBarSize
* ScaleBarLength
* ScaleBarBorderThickness
* Interval
* Minimum
* Maximum

{% tabs %}
{% highlight xaml %}

              <Gauges:SfLinearGauge Name="linearGauge" Orientation="Horizontal">
            <Gauges:SfLinearGauge.MainScale>
                <Gauges:LinearScale ScaleDirection="Forward"
                                    ScaleBarStroke="White" 
                                    ScaleBarSize="20" 
                                    ScaleBarLength="350"
                                    ScaleBarBorderThickness="1"
                                    Interval="10"
                                    Minimum="0" Maximum="100">
                </Gauges:LinearScale>
            </Gauges:SfLinearGauge.MainScale>
        </Gauges:SfLinearGauge> 

{% endhighlight %}

{% highlight c# %}

            SfLinearGauge lineargauge = new SfLinearGauge();
            lineargauge.Orientation = Orientation.Horizontal;
            LinearScale _mainScale = new LinearScale();
            _mainScale.ScaleDirection = LinearScaleDirection.Forward;
            _mainScale.ScaleBarStroke = new SolidColorBrush(Colors.White);
            _mainScale.ScaleBarSize = 20;
            _mainScale.ScaleBarLength = 350;
            _mainScale.ScaleBarBorderThickness = new Thickness(1);
            _mainScale.Interval = 10;
            _mainScale.Minimum = 0;
            _mainScale.Maximum = 100;
            lineargauge.MainScale = _mainScale;
            this.Grid.Children.Add(lineargauge);

{% endhighlight %}
{% endtabs %}

![](Getting-Started_images/Getting-Started_img1.jpeg)

## Adding Ranges 

You can add ranges to SfLinearGauge by creating **LinearRange** collection using **Ranges**.

{% tabs %}
{% highlight xaml %}

     <Gauges:SfLinearGauge>
            <Gauges:SfLinearGauge.MainScale>
                <Gauges:LinearScale>
                    <Gauges:LinearScale.Ranges>
                        <Gauges:LinearRange StartValue="0" EndValue="35" 
                                            StartWidth="25" EndWidth="10" 
                                            RangeOffset="5" RangeOpacity="1"
                                            RangeStroke="Green"/>
                        <Gauges:LinearRange StartValue="65" EndValue="100" 
                                            StartWidth="10" EndWidth="25" 
                                            RangeOffset="5" RangeOpacity="1"
                                            RangeStroke="Red"/>
                    </Gauges:LinearScale.Ranges>
                </Gauges:LinearScale>
            </Gauges:SfLinearGauge.MainScale>
        </Gauges:SfLinearGauge>


{% endhighlight %}

{% highlight c# %}

           SfLinearGauge lineargauge = new SfLinearGauge();
           LinearScale _mainScale = new LinearScale();
           _mainScale.Ranges.Add(new LinearRange()
           {
               StartValue = 0,
               EndValue = 35,
               StartWidth = 25,
               EndWidth = 10,
               RangeOffset = 5,
               RangeOpacity = 1,
               RangeStroke = new SolidColorBrush(Colors.Green)
           });
           _mainScale.Ranges.Add(new LinearRange() 
           { 
               StartValue = 65,
               EndValue = 100, 
               StartWidth = 10, 
               EndWidth = 25,
               RangeOffset = 5,
               RangeOpacity = 1,
               RangeStroke = new SolidColorBrush(Colors.Red) 
           });
           lineargauge.MainScale = _mainScale;
           this.Grid.Children.Add(lineargauge);

{% endhighlight %}
{% endtabs %}

![](Getting-Started_images/Getting-Started_img2.jpeg)

## Adding Pointers 

You can also add Pointers to SfLinearGauge to point a values on the scale.

{% tabs %}
{% highlight xaml %}

      <Gauges:SfLinearGauge Name="linearGauge">
            <Gauges:SfLinearGauge.MainScale>
                <Gauges:LinearScale>
                    <Gauges:LinearScale.Pointers>
                        <Gauges:LinearPointer Value="40" PointerType="BarPointer" />
                        <Gauges:LinearPointer Value="40" PointerType="SymbolPointer"/>
                    </Gauges:LinearScale.Pointers>
                </Gauges:LinearScale>
            </Gauges:SfLinearGauge.MainScale>
        </Gauges:SfLinearGauge>

{% endhighlight %}

{% highlight c# %}

           SfLinearGauge lineargauge = new SfLinearGauge();
           LinearScale _mainScale = new LinearScale();
           _mainScale.Pointers.Add(new LinearPointer()
           {
               Value = 40,
               PointerType = LinearPointerType.BarPointer
           });
           _mainScale.Pointers.Add(new LinearPointer()
           {
               Value = 40,
               PointerType = LinearPointerType.SymbolPointer,
               SymbolPointerPosition = LinearSymbolPointersPosition.Above
           });
           lineargauge.MainScale = _mainScale;
           this.Grid.Children.Add(lineargauge);

{% endhighlight %}
{% endtabs %}

![](Getting-Started_images/Getting-Started_img3.jpeg)
