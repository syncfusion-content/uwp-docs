---
layout: post
title: Transform axis value to pixel value | SfChart | Winrt | Syncfusion
description: Learn how to transform axis values to pixel values and vice versa in SfChart using ValueToPoint and PointToValue utility methods.
platform: uwp
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

## See Also

- [How to get Axis Range in UWP chart?](https://support.syncfusion.com/kb/article/9505/how-to-get-axis-range-in-uwp-chart)
