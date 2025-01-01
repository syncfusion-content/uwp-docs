---
layout: post
title: Transform axis value to pixel value and vice versa | SfChart | Winrt | Syncfusion
description: transform axis value to pixel value and vice versa
platform: wpf
control: SfChart
documentation: ug
---

# Transform axis value to pixel value and vice versa

[`SfChart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html) offers two utility methods for converting your data points into pixel values (device coordinates).

* ValueToPoint(ChartAxis axis, double value)
* PointToValue(ChartAxis axis, Point point)


{% highlight c# %}


private void LineChart_MouseMove(object sender, MouseEventArgs e)

        {

            Point mousePoint = new Point

            {

                X = e.GetPosition(LineChart).X - LineChart.SeriesClipRect.Left,

                Y = e.GetPosition(LineChart).Y - LineChart.SeriesClipRect.Top

            };



           // Converts mouse co-ordinate points into a value related to ChartAxis.



            double xValue = this.LineChart.PointToValue(this.LineChart.PrimaryAxis, mousePoint);

            double yValue = this.LineChart.PointToValue(this.LineChart.SecondaryAxis, mousePoint);





            // Converts the data point value of the chart to Chart coordinate.

            double chartPointX = this.LineChart.ValueToPoint(this.LineChart.PrimaryAxis, xValue);

            double chartPointY = this.LineChart.ValueToPoint(this.LineChart.SecondaryAxis, yValue);



        }

		
{% endhighlight %}


