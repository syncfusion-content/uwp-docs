---
layout: post
title: Scale | SfLinearGauge | uwp | Syncfusion
description: Scale 
platform: uwp
control: SfLinearGauge
documentation: ug
---

# Scale

The **MainScale** is a linear scale that integrates ticks, labels and scale bar to specify the basic look and feel of the linear gauge. It defines the overall minimum and maximum values, as well as the frequency of labels and ticks through the interval of the scale. It can contain multiple ranges within a scale. It also contains one or more pointers to point out the measures of the linear scale. 

## Customizing MainScale

The range of the main scale can be mentioned by **Minimum** and **Maximum** of the linear scale with defined **Interval**. The width and height of the linear scale is customized by using the **ScaleBarLength** and **ScaleBarSize** properties respectively. The border thickness of the linear scale is changed by using the **ScaleBarBorderThickness** Property. The direction of the linear scale is personalized by setting the **ScaleDirection** property of the linear scale.

{% tabs %}
{% highlight xaml %}

        <Gauges:SfLinearGauge Name="linearGauge">
            <Gauges:SfLinearGauge.MainScale>
                <Gauges:LinearScale ScaleDirection="Forward"
                                    ScaleBarStroke="Black" 
                                    ScaleBarSize="20" 
                                    ScaleBarLength="350"
                                    ScaleBarBorderThickness="1"
                                         Interval="1"
                                    Minimum="0" Maximum="10">
                </Gauges:LinearScale>
            </Gauges:SfLinearGauge.MainScale>
        </Gauges:SfLinearGauge>

{% endhighlight %}

{% highlight c# %}

            SfLinearGauge lineargauge = new SfLinearGauge();
            LinearScale _mainScale = new LinearScale();
            _mainScale.ScaleDirection = LinearScaleDirection.Forward;
            _mainScale.ScaleBarStroke = new SolidColorBrush(Colors.Black);
            _mainScale.ScaleBarSize = 20;
            _mainScale.ScaleBarLength = 350;
            _mainScale.ScaleBarBorderThickness = new Thickness(1);
            _mainScale.Interval = 1;
            _mainScale.Minimum = 0;
            _mainScale.Maximum = 10;
            lineargauge.MainScale = _mainScale;
            this.Grid.Children.Add(lineargauge);

{% endhighlight %}
{% endtabs %}

![](Scale_images/Scale_img1.jpeg)


