---
layout: post
title: Labels | SfLinearGauge | uwp | Syncfusion
description: Labels 
platform: uwp
control: SfLinearGauge
documentation: ug
---

# Labels

`Labels` of the linear scale provide a numeric value to the major ticks that will be specified according to the range of the scale.

## Label color customization

The foreground of the label is customized by setting the [`LabelStroke`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGauge.UWP~Syncfusion.UI.Xaml.Gauges.LinearScale~LabelStroke.html) of the linear scale.

{% tabs %}

{% highlight xml %}

     <gauge:SfLinearGauge>

            <gauge:SfLinearGauge.MainScale>

            <gauge:LinearScale     Interval="10" 
                                   MajorTickStroke="Gray" MajorTickSize="25" 
                                   MinorTickSize="12" LabelSize="15" ScaleBarSize="10"
                                   MinorTickStroke="Gray" LabelStroke="Purple"
                                   MinorTicksPerInterval="3" ScaleBarLength="300">
                
            </gauge:LinearScale>

            </gauge:SfLinearGauge.MainScale>

        </gauge:SfLinearGauge>

{% endhighlight %}

{% highlight c# %}

             SfLinearGauge sfLinearGauge = new SfLinearGauge();

            LinearScale linearScale = new LinearScale();

            linearScale.Interval = 10;

            linearScale.LabelSize = 15;

            linearScale.ScaleBarSize = 10;

            linearScale.MajorTickStroke = new SolidColorBrush(Colors.Gray);

            linearScale.MinorTickStroke = new SolidColorBrush(Colors.Gray);

            linearScale.LabelStroke = new SolidColorBrush(Colors.Purple);

            linearScale.MajorTickSize = 25;

            linearScale.MinorTickSize = 12;

            linearScale.ScaleBarLength = 300;

            linearScale.MinorTicksPerInterval = 3;

            sfLinearGauge.MainScale = linearScale;

{% endhighlight %}

{% endtabs %}

![](Labels_images/Labels_img1.png)

## Label font customization

The label font can be customized using the [`LabelSize`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGauge.UWP~Syncfusion.UI.Xaml.Gauges.LinearScale~LabelSize.html), `FontFamily`, and `FontStyle` properties. 

{% tabs %}

{% highlight xml %}

    <gauge:SfLinearGauge>

            <gauge:SfLinearGauge.MainScale>

            <gauge:LinearScale     Interval="10" FontFamily="Monotype Corsiva" 
                                   FontStyle="Italic"
                                   MajorTickStroke="Gray" MajorTickSize="25" 
                                   MinorTickSize="12" LabelSize="15" ScaleBarSize="10"
                                   MinorTickStroke="Gray" LabelStroke="#424242"
                                   MinorTicksPerInterval="3" ScaleBarLength="300">
                
            </gauge:LinearScale>

            </gauge:SfLinearGauge.MainScale>

        </gauge:SfLinearGauge>

{% endhighlight %}

{% highlight c# %}

            SfLinearGauge sfLinearGauge = new SfLinearGauge();

            LinearScale linearScale = new LinearScale();

            linearScale.Interval = 10;

            linearScale.LabelSize = 15;

            linearScale.FontFamily = new FontFamily("Monotype Corsiva");

            linearScale.FontStyle = Windows.UI.Text.FontStyle.Italic;

            linearScale.ScaleBarSize = 10;

            linearScale.MajorTickStroke = new SolidColorBrush(Colors.Gray);

            linearScale.MinorTickStroke = new SolidColorBrush(Colors.Gray);

            linearScale.LabelStroke = new SolidColorBrush(Color.FromArgb(0xff, 0x42, 0x42, 0x42));

            linearScale.MajorTickSize = 25;

            linearScale.MinorTickSize = 12;

            linearScale.ScaleBarLength = 300;

            linearScale.MinorTicksPerInterval = 3;

            sfLinearGauge.MainScale = linearScale;

{% endhighlight %}

{% endtabs %}

![](Labels_images/Labels_img2.png)

## Setting position for labels

The labels in the scale can be placed above or below the linear scale by choosing the following options available in the [`LabelPosition`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGauge.UWP~Syncfusion.UI.Xaml.Gauges.LinearScale~LabelPosition.html) property. The default value of [`LabelPosition`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGauge.UWP~Syncfusion.UI.Xaml.Gauges.LinearScale~LabelPosition.html) property is below.

1.	Above
2.	Below (Default)

{% tabs %}

{% highlight xml %}

        <gauge:SfLinearGauge>

            <gauge:SfLinearGauge.MainScale>

            <gauge:LinearScale     Interval="10" LabelPosition="Above"
                                   MajorTickStroke="Gray" MajorTickSize="25" 
                                   MinorTickSize="12" LabelSize="15" ScaleBarSize="10"
                                   MinorTickStroke="Gray" LabelStroke="#424242"
                                   MinorTicksPerInterval="3" ScaleBarLength="300">
                
            </gauge:LinearScale>

            </gauge:SfLinearGauge.MainScale>

        </gauge:SfLinearGauge>

{% endhighlight %}

{% highlight c# %}

            SfLinearGauge sfLinearGauge = new SfLinearGauge();

            LinearScale linearScale = new LinearScale();

            linearScale.Interval = 10;

            linearScale.LabelSize = 15;

            linearScale.LabelPosition = LinearLabelsPosition.Above;

            linearScale.ScaleBarSize = 10;

            linearScale.MajorTickStroke = new SolidColorBrush(Colors.Gray);

            linearScale.MinorTickStroke = new SolidColorBrush(Colors.Gray);

            linearScale.LabelStroke = new SolidColorBrush(Color.FromArgb(0xff, 0x42, 0x42, 0x42));

            linearScale.MajorTickSize = 25;

            linearScale.MinorTickSize = 12;

            linearScale.ScaleBarLength = 300;

            linearScale.MinorTicksPerInterval = 3;

            sfLinearGauge.MainScale = linearScale;

{% endhighlight %}

{% endtabs %}

![](Labels_images/Labels_img3.png)

## Setting postfix and prefix for labels

You can postfix and prefix values to the scale labels using the [`LabelPostfix`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGauge.UWP~Syncfusion.UI.Xaml.Gauges.LinearScale~LabelPostfix.html) and [`LabelPrefix`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGauge.UWP~Syncfusion.UI.Xaml.Gauges.LinearScale~LabelPrefix.html) properties, respectively.

### Setting label postfix

The [`LabelPostfix`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGauge.UWP~Syncfusion.UI.Xaml.Gauges.LinearScale~LabelPostfix.html) property allows to postfix the values to scale labels.

{% tabs %}

{% highlight xml %}

       <gauge:SfLinearGauge>

            <gauge:SfLinearGauge.MainScale>

            <gauge:LinearScale    Minimum="0" Maximum="50"  LabelPostfix="%"
                                  Interval="10" 
                                   MajorTickStroke="Gray" MajorTickSize="25" 
                                   MinorTickSize="12" LabelSize="15" ScaleBarSize="10"
                                   MinorTickStroke="Gray" LabelStroke="#424242"
                                   ScaleBarLength="300">
                
            </gauge:LinearScale>

            </gauge:SfLinearGauge.MainScale>

        </gauge:SfLinearGauge>

{% endhighlight %}

{% highlight c# %}

            SfLinearGauge sfLinearGauge = new SfLinearGauge();

            LinearScale linearScale = new LinearScale();

            linearScale.Interval = 10;

            linearScale.LabelSize = 15;

            linearScale.Minimum = 0;

            linearScale.Maximum = 50;

            linearScale.LabelPostfix = "%";

            linearScale.ScaleBarSize = 10;

            linearScale.MajorTickStroke = new SolidColorBrush(Colors.Gray);

            linearScale.MinorTickStroke = new SolidColorBrush(Colors.Gray);

            linearScale.LabelStroke = new SolidColorBrush(Color.FromArgb(0xff, 0x42, 0x42, 0x42));

            linearScale.MajorTickSize = 25;

            linearScale.MinorTickSize = 12;

            linearScale.ScaleBarLength = 300;

            sfLinearGauge.MainScale = linearScale;

{% endhighlight %}

{% endtabs %}

![](Labels_images/Labels_img4.png)

### Setting label prefix

The [`LabelPrefix`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGauge.UWP~Syncfusion.UI.Xaml.Gauges.LinearScale~LabelPrefix.html) property allows to prefix the values to scale labels.

{% tabs %}

{% highlight xml %}

    <gauge:SfLinearGauge>

            <gauge:SfLinearGauge.MainScale>

            <gauge:LinearScale     Minimum="0" Maximum="50"  LabelPrefix="$"
                                   Interval="10" 
                                   MajorTickStroke="Gray" MajorTickSize="25" 
                                   MinorTickSize="12" LabelSize="15" ScaleBarSize="10"
                                   MinorTickStroke="Gray" LabelStroke="#424242" ScaleBarLength="300">
                
            </gauge:LinearScale>

            </gauge:SfLinearGauge.MainScale>

        </gauge:SfLinearGauge>

{% endhighlight %}

{% highlight c# %}

            SfLinearGauge sfLinearGauge = new SfLinearGauge();

            LinearScale linearScale = new LinearScale();

            linearScale.Interval = 10;

            linearScale.LabelSize = 15;

            linearScale.Minimum = 0;

            linearScale.Maximum = 50;

            linearScale.LabelPostfix = "$";

            linearScale.ScaleBarSize = 10;

            linearScale.MajorTickStroke = new SolidColorBrush(Colors.Gray);

            linearScale.MinorTickStroke = new SolidColorBrush(Colors.Gray);

            linearScale.LabelStroke = new SolidColorBrush(Color.FromArgb(0xff, 0x42, 0x42, 0x42));

            linearScale.MajorTickSize = 25;

            linearScale.MinorTickSize = 12;

            linearScale.ScaleBarLength = 300;

            sfLinearGauge.MainScale = linearScale;

{% endhighlight %}

{% endtabs %}

![](Labels_images/Labels_img5.png)

## Setting label offset

The labels can be positioned far away from the ticks using the [`LabelOffset`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGauge.UWP~Syncfusion.UI.Xaml.Gauges.LinearScale~LabelOffset.html) property.

{% tabs %}

{% highlight xml %}

    <gauge:SfLinearGauge>

            <gauge:SfLinearGauge.MainScale>

            <gauge:LinearScale     LabelOffset="15"
                                   MajorTickStroke="Gray" MajorTickSize="25" 
                                   MinorTickSize="12" LabelSize="15" ScaleBarSize="10"
                                   MinorTickStroke="Gray" LabelStroke="#424242" ScaleBarLength="300">
                
            </gauge:LinearScale>

            </gauge:SfLinearGauge.MainScale>

        </gauge:SfLinearGauge>

{% endhighlight %}

{% highlight c# %}

            SfLinearGauge sfLinearGauge = new SfLinearGauge();

            LinearScale linearScale = new LinearScale();

            linearScale.ScaleBarSize = 10;

            linearScale.LabelOffset = 15;

            linearScale.MajorTickStroke = new SolidColorBrush(Colors.Gray);

            linearScale.MinorTickStroke = new SolidColorBrush(Colors.Gray);

            linearScale.LabelStroke = new SolidColorBrush(Color.FromArgb(0xff, 0x42, 0x42, 0x42));

            linearScale.MajorTickSize = 25;

            linearScale.MinorTickSize = 12;

            linearScale.ScaleBarLength = 300;

            sfLinearGauge.MainScale = linearScale;

{% endhighlight %}

{% endtabs %}

![](Labels_images/Labels_img6.png)

## Labels visibility

Labels visibility can be customized using the [`ShowLabels`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGauge.UWP~Syncfusion.UI.Xaml.Gauges.LinearScale~ShowLabels.html) property of linear scale.

{% tabs %}

{% highlight xml %}

    <gauge:SfLinearGauge>

        <gauge:SfLinearGauge.MainScale>

            <gauge:LinearScale     ShowLabels="False"
                                   MajorTickStroke="Gray" MajorTickSize="25" 
                                   MinorTickSize="12" LabelSize="15" ScaleBarSize="10"
                                   MinorTickStroke="Gray" LabelStroke="#424242" ScaleBarLength="300">

            </gauge:LinearScale>

        </gauge:SfLinearGauge.MainScale>

    </gauge:SfLinearGauge>

{% endhighlight %}

{% highlight c# %}

            SfLinearGauge sfLinearGauge = new SfLinearGauge();

            LinearScale linearScale = new LinearScale();

            linearScale.ScaleBarSize = 10;

            linearScale.ShowLabels = false;

            linearScale.MajorTickStroke = new SolidColorBrush(Colors.Gray);

            linearScale.MinorTickStroke = new SolidColorBrush(Colors.Gray);

            linearScale.LabelStroke = new SolidColorBrush(Color.FromArgb(0xff, 0x42, 0x42, 0x42));

            linearScale.MajorTickSize = 25;

            linearScale.MinorTickSize = 12;

            linearScale.ScaleBarLength = 300;

            sfLinearGauge.MainScale = linearScale;

{% endhighlight %}

{% endtabs %}

![](Labels_images/Labels_img7.png)