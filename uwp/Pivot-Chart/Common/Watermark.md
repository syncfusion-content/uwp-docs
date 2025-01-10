---
layout: post
title: Watermark in UWP Pivot Chart control | Syncfusion
description: Learn here all about Watermark support in Syncfusion® UWP Pivot Chart (SfPivotChart) control and more.
platform: UWP
control: SfPivotChart
documentation: ug
---

# Watermark in UWP Pivot Chart (SfPivotChart)

The SfPivotChart supports watermark that is used to add text or images to the chart area. The major application of watermark is to define the copyright information of users it belongs to.

## Text watermark

You can add a text as watermark in the chart background by using the `Content` property of `PivotChartWatermark` instance.

The following code snippet explains how to set the custom text as watermark.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart x:Name="PivotChart1" ItemSource="{Binding ProductSalesData}" PivotAxis="{Binding PivotAxis}"
                         PivotLegend="{Binding PivotLegend}" PivotCalculations="{Binding PivotCalculations}">
            <syncfusion:SfPivotChart.Watermark>
                <syncfusion:PivotChartWatermark HorizontalAlignment="Center" VerticalAlignment="Center" HorizontalContentAlignment="Center" VerticalContentAlignment="Center">
                    <syncfusion:PivotChartWatermark.Content>
                        <TextBlock Text="Syncfusion" FontSize="28" Opacity="0.5"/>
                    </syncfusion:PivotChartWatermark.Content>
                </syncfusion:PivotChartWatermark>
            </syncfusion:SfPivotChart.Watermark>
</syncfusion:SfPivotChart>

{% endhighlight %}

{% highlight c# %}

PivotChart1.Watermark = new PivotChartWatermark();
PivotChart1.Watermark.Content = new TextBlock() { Text = "Syncfusion", FontSize = 28, Opacity = 0.5 };
PivotChart1.Watermark.HorizontalAlignment = HorizontalAlignment.Center;
PivotChart1.Watermark.VerticalAlignment = VerticalAlignment.Center;

{% endhighlight %}

{% highlight vb %}

Dim watermark As New PivotChartWatermark()
watermark.Content = New Windows.UI.Xaml.Controls.TextBlock() With { _
	Key .Text = "Syncfusion", _
	Key .FontSize = 28, _
	Key .Opacity = 0.5 _
}
watermark.HorizontalAlignment = HorizontalAlignment.Center
watermark.VerticalAlignment = VerticalAlignment.Center
PivotChart1.Watermark = watermark

{% endhighlight %}

{% endtabs %}

![relationalTextWaterMark](Watermark_images/relationalTextWaterMark.png)

## Image watermark

You can also set images as watermark as shown in the following code snippet.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart x:Name="PivotChart1" ItemSource="{Binding ProductSalesData}" PivotAxis="{Binding PivotAxis}"
                         PivotLegend="{Binding PivotLegend}" PivotCalculations="{Binding PivotCalculations}">
            <syncfusion:SfPivotChart.Watermark>
                <syncfusion:PivotChartWatermark HorizontalAlignment="Center" VerticalAlignment="Center" HorizontalContentAlignment="Center" VerticalContentAlignment="Center">
                    <syncfusion:PivotChartWatermark.Content>
                        <Image Source="ms-appx:///Resources/SyncfusionLogo.jpg" Opacity="0.5"/>
                    </syncfusion:PivotChartWatermark.Content>
                </syncfusion:PivotChartWatermark>
            </syncfusion:SfPivotChart.Watermark>
</syncfusion:SfPivotChart>

{% endhighlight %}

{% highlight c# %}

PivotChartWatermark watermark = new PivotChartWatermark();
watermark.Content = new Windows.UI.Xaml.Controls.Image() { Opacity = 0.7, Source = new BitmapImage(new System.Uri("ms-appx:///Resources/SyncfusionLogo.jpg", System.UriKind.Absolute)) };
watermark.HorizontalAlignment = HorizontalAlignment.Center;
watermark.VerticalAlignment = VerticalAlignment.Center;
PivotChart1.Watermark = watermark;

{% endhighlight %}

{% highlight vb %}

Dim watermark As New PivotChartWatermark()
watermark.Content = New Windows.UI.Xaml.Controls.Image() With { _
	Key .Opacity = 0.7, _
	Key .Source = New BitmapImage(New System.Uri("ms-appx:///Resources/SyncfusionLogo.jpg", System.UriKind.Absolute)) _
}
watermark.HorizontalAlignment = HorizontalAlignment.Center
watermark.VerticalAlignment = VerticalAlignment.Center
PivotChart1.Watermark = watermark

{% endhighlight %}

{% endtabs %}

![relationalWaterMark](Watermark_images/relationalWaterMark.png)
