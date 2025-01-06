---
layout: post
title: Adornments in UWP Pivot Chart control | Syncfusion
description: Learn here all about Adornments support in Syncfusion® UWP Pivot Chart (SfPivotChart) control and more.
platform: UWP
control: SfPivotChart
documentation: ug
---

# Adornments in UWP Pivot Chart (SfPivotChart)

Adornments are used to display data values of a chart segment with custom formatting options. The data point values (x,y) can be formatted by using the `AdornmentsInfo` property of the SfPivotChart. You can initialize the adornments as specified in the following code snippet.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.AdornmentsInfo>
    <syncfusion:PivotChartAdornmentsInfo/>
</syncfusion:SfPivotChart.AdornmentsInfo>

{% endhighlight %}

{% highlight c# %}

PivotChartAdornmentsInfo adornmentsInfo = new PivotChartAdornmentsInfo();
PivotChart1.AdornmentsInfo = adornmentsInfo;

{% endhighlight %}

{% highlight vb %}

Dim adornmentsInfo As New PivotChartAdornmentsInfo()
PivotChart1.AdornmentsInfo = adornmentsInfo

{% endhighlight %}

{% endtabs %}

Each adornment can be represented by the following components:

* Marker: Displays a symbol at the data point (x,y).
* Label: Displays segmented label content at the data point (x,y).
* Connector line: Connects a label element to a data point (x,y) using a line.

## Marker

To enable a marker in adornments, the `ShowMarker` property is used. By default, no symbol is shown in adornments unless the desired symbol is specified.

The following code snippet demonstrates how to show cross-type markers in adornments.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.AdornmentsInfo>
    <syncfusion:PivotChartAdornmentsInfo ShowMarker="True" Symbol="Cross"/>
</syncfusion:SfPivotChart.AdornmentsInfo>

{% endhighlight %}

{% highlight c# %}

PivotChartAdornmentsInfo adornmentsInfo = new PivotChartAdornmentsInfo();
adornmentsInfo.ShowMarker = true;
adornmentsInfo.Symbol = ChartSymbol.Cross;
PivotChart1.AdornmentsInfo = adornmentsInfo;

{% endhighlight %}

{% highlight vb %}

Dim adornmentsInfo As New PivotChartAdornmentsInfo()
adornmentsInfo.ShowMarker = True
adornmentsInfo.Symbol = ChartSymbol.Cross
PivotChart1.AdornmentsInfo = adornmentsInfo

{% endhighlight %}

{% endtabs %}

![default_MarkerAdornments](Adornments_images/default_MarkerAdornments.png)

### Customizing marker appearance

The marker's size can be customized using the `SymbolHeight` and `SymbolWidth` properties; its appearance can be customized using the `SymbolInterior` and `SymbolStroke` properties respectively.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.AdornmentsInfo>
    <syncfusion:PivotChartAdornmentsInfo ShowMarker="True" Symbol="Ellipse" SymbolStroke="Red" SymbolInterior="White" 
                                         SymbolHeight="15" SymbolWidth="15"/>
</syncfusion:SfPivotChart.AdornmentsInfo>

{% endhighlight %}

{% highlight c# %}

PivotChartAdornmentsInfo adornmentsInfo = new PivotChartAdornmentsInfo();
adornmentsInfo.ShowMarker = true;
adornmentsInfo.Symbol = ChartSymbol.Ellipse;
adornmentsInfo.Stroke = new SolidColorBrush(Colors.Red);
adornmentsInfo.Stroke = new SolidColorBrush(Colors.White);
adornmentsInfo.SymbolHeight = 15;
adornmentsInfo.SymbolWeight = 15;
PivotChart1.AdornmentsInfo = adornmentsInfo;

{% endhighlight %}

{% highlight vb %}

Dim adornmentsInfo As New PivotChartAdornmentsInfo()
adornmentsInfo.ShowMarker = True
adornmentsInfo.Symbol = ChartSymbol.Ellipse
adornmentsInfo.Stroke = New SolidColorBrush(Colors.Red)
adornmentsInfo.Stroke = New SolidColorBrush(Colors.White)
adornmentsInfo.SymbolHeight = 15
adornmentsInfo.SymbolWeight = 15
PivotChart1.AdornmentsInfo = adornmentsInfo

{% endhighlight %}

{% endtabs %}

![symbolSize_MarkerAdornments](Adornments_images/symbolSize_MarkerAdornments.png)

### Custom marker

You can specify a custom template to create your own symbols by using the `SymbolTemplate` property as shown in the following code snippet.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.AdornmentsInfo>
    <syncfusion:PivotChartAdornmentsInfo ShowMarker="True" Symbol="Custom">
        <syncfusion:PivotChartAdornmentsInfo.SymbolTemplate>
            <DataTemplate>
                <Image Source="ms-appx:///Assets/Clover.ico" Height="15" Width="15"/>
            </DataTemplate>
        </syncfusion:PivotChartAdornmentsInfo.SymbolTemplate>
    </syncfusion:PivotChartAdornmentsInfo>
</syncfusion:SfPivotChart.AdornmentsInfo>

{% endhighlight %}

{% highlight c# %}

PivotChartAdornmentsInfo adornmentsInfo = new PivotChartAdornmentsInfo();
adornmentsInfo.ShowMarker = true;
adornmentsInfo.Symbol = ChartSymbol.Custom;
adornmentsInfo.SymbolTemplate = Resources["CustomSymbol"] as DataTemplate;
PivotChart1.AdornmentsInfo = adornmentsInfo;

{% endhighlight %}

{% highlight vb %}

Dim adornmentsInfo As New PivotChartAdornmentsInfo()
adornmentsInfo.ShowMarker = True
adornmentsInfo.Symbol = ChartSymbol.Custom
adornmentsInfo.SymbolTemplate = TryCast(Resources("CustomSymbol"), DataTemplate)
PivotChart1.AdornmentsInfo = adornmentsInfo

{% endhighlight %}

{% endtabs %}

![symbolTemplate_MarkerAdornments](Adornments_images/symbolTemplate_MarkerAdornments.png)

## Label

A label in the adornments can be enabled by using the `ShowLabel` property. The label specifies the text value of the data point (x,y) based on the chart segment. The following code snippet illustrates how to enable labels in adornments.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.AdornmentsInfo>
    <syncfusion:PivotChartAdornmentsInfo ShowLabel="True"/>
</syncfusion:SfPivotChart.AdornmentsInfo>

{% endhighlight %}

{% highlight c# %}

PivotChartAdornmentsInfo adornmentsInfo = new PivotChartAdornmentsInfo();
adornmentsInfo.ShowLabel = true;
PivotChart1.AdornmentsInfo = adornmentsInfo;

{% endhighlight %}

{% highlight vb %}

Dim adornmentsInfo As New PivotChartAdornmentsInfo()
adornmentsInfo.ShowLabel = True
PivotChart1.AdornmentsInfo = adornmentsInfo

{% endhighlight %}

{% endtabs %}

![default_LabelAdornments](Adornments_images/default_LabelAdornments.png)

### Defining label content

By using the `SegmentLabelContent` property, you can define the values to be displayed as labels for data point segments in the SfPivotChart. The label content can be specified as one of the following values:

**XValue**

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.AdornmentsInfo>
    <syncfusion:PivotChartAdornmentsInfo ShowLabel="True" SegmentLabelContent="XValue"/>
</syncfusion:SfPivotChart.AdornmentsInfo>

{% endhighlight %}

{% highlight c# %}

PivotChartAdornmentsInfo adornmentsInfo = new PivotChartAdornmentsInfo();
adornmentsInfo.ShowLabel = true;
adornmentsInfo.SegmentLabelContent = LabelContent.XValue;
PivotChart1.AdornmentsInfo = adornmentsInfo;

{% endhighlight %}

{% highlight vb %}

Dim adornmentsInfo As New PivotChartAdornmentsInfo()
adornmentsInfo.ShowLabel = True
adornmentsInfo.SegmentLabelContent = LabelContent.XValue
PivotChart1.AdornmentsInfo = adornmentsInfo

{% endhighlight %}

{% endtabs %}

![xValueContent_LabelAdornments](Adornments_images/xValueContent_LabelAdornments.png)

**Percentage**

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.AdornmentsInfo>
    <syncfusion:PivotChartAdornmentsInfo ShowLabel="True" SegmentLabelContent="Percentage"/>
</syncfusion:SfPivotChart.AdornmentsInfo>

{% endhighlight %}

{% highlight c# %}

PivotChartAdornmentsInfo adornmentsInfo = new PivotChartAdornmentsInfo();
adornmentsInfo.ShowLabel = true;
adornmentsInfo.SegmentLabelContent = LabelContent.Percentage;
PivotChart1.AdornmentsInfo = adornmentsInfo;

{% endhighlight %}

{% highlight vb %}

Dim adornmentsInfo As New PivotChartAdornmentsInfo()
adornmentsInfo.ShowLabel = True
adornmentsInfo.SegmentLabelContent = LabelContent.Percentage
PivotChart1.AdornmentsInfo = adornmentsInfo

{% endhighlight %}

{% endtabs %}

![percentageContent_LabelAdornments](Adornments_images/percentageContent_LabelAdornments.png)

**YofTot**

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.AdornmentsInfo>
    <syncfusion:PivotChartAdornmentsInfo ShowLabel="True" SegmentLabelContent="YofTot"/>
</syncfusion:SfPivotChart.AdornmentsInfo>

{% endhighlight %}

{% highlight c# %}

PivotChartAdornmentsInfo adornmentsInfo = new PivotChartAdornmentsInfo();
adornmentsInfo.ShowLabel = true;
adornmentsInfo.SegmentLabelContent = LabelContent.YofTot;
PivotChart1.AdornmentsInfo = adornmentsInfo;

{% endhighlight %}

{% highlight vb %}

Dim adornmentsInfo As New PivotChartAdornmentsInfo()
adornmentsInfo.ShowLabel = True
adornmentsInfo.SegmentLabelContent = LabelContent.YofTot
PivotChart1.AdornmentsInfo = adornmentsInfo

{% endhighlight %}

{% endtabs %}

![yOfTotalContent_LabelAdornments](Adornments_images/yOfTotalContent_LabelAdornments.png)

**DateTime**

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.AdornmentsInfo>
    <syncfusion:PivotChartAdornmentsInfo ShowLabel="True" SegmentLabelContent="DateTime"/>
</syncfusion:SfPivotChart.AdornmentsInfo>

{% endhighlight %}

{% highlight c# %}

PivotChartAdornmentsInfo adornmentsInfo = new PivotChartAdornmentsInfo();
adornmentsInfo.ShowLabel = true;
adornmentsInfo.SegmentLabelContent = LabelContent.DateTime;
PivotChart1.AdornmentsInfo = adornmentsInfo;

{% endhighlight %}

{% highlight vb %}

Dim adornmentsInfo As New PivotChartAdornmentsInfo()
adornmentsInfo.ShowLabel = True
adornmentsInfo.SegmentLabelContent = LabelContent.DateTime
PivotChart1.AdornmentsInfo = adornmentsInfo

{% endhighlight %}

{% endtabs %}

![dateTimeContent_labelAdornments](Adornments_images/dateTimeContent_labelAdornments.png)

**LabelContentPath**

By default, the Y value of the SfPivotChart point in the provided chart segment can be displayed in the label's text. You can also define other specific label values by defining the `LabelTemplate` property. This property returns the adornment value for chart segments that are being rendered.

The following code sample demonstrates displaying string values from the x-axis.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.AdornmentsInfo>
    <syncfusion:PivotChartAdornmentsInfo ShowLabel="True" SegmentLabelContent="LabelContentPath">
        <syncfusion:PivotChartAdornmentsInfo.LabelTemplate>
            <DataTemplate>
                <Border CornerRadius="3" BorderThickness="1"
                        Background="{Binding Converter={StaticResource CustomAdornmentConverter}, ConverterParameter=Background}"
                        BorderBrush="{Binding Converter={StaticResource CustomAdornmentConverter}, ConverterParameter=BorderBrush}">
                    <TextBlock FontSize="12" Height="20" Foreground="White" FontWeight="Medium" Margin="5 0"
                               Text="{Binding Converter={StaticResource CustomAdornmentConverter}}"
                               HorizontalAlignment="Center" VerticalAlignment="Center"/>
                </Border>
            </DataTemplate>
        </syncfusion:PivotChartAdornmentsInfo.LabelTemplate>
    </syncfusion:PivotChartAdornmentsInfo>
</syncfusion:SfPivotChart.AdornmentsInfo>

{% endhighlight %}

{% highlight C# %}

public class CustomAdornmentConverter : IValueConverter
{
    public object Convert(object value, Type targetType, object parameter, string language)
    {
        if (value is Syncfusion.UI.Xaml.Charts.ChartPieAdornment)
        {
            var adornment = value as Syncfusion.UI.Xaml.Charts.ChartPieAdornment;
            (adornment.Series as Syncfusion.UI.Xaml.Charts.PieSeries).PieCoefficient = 0.5;
            if (parameter != null)
            {
                SolidColorBrush interior = (adornment.Interior as SolidColorBrush);
                if (parameter.ToString() == "Background")
                    return new SolidColorBrush(Color.FromArgb(200, interior.Color.R, interior.Color.G, interior.Color.B));
                else
                    return interior;
            }
            else
            {
                var label = string.Empty;
                double totalValues = 0d;
                if (adornment != null)
                {
                    label = (adornment.Item as Syncfusion.UI.Xaml.PivotChart.PivotChartPoint).BindingX;
                    if (adornment.Series.ItemsSource != null)
                    {
                        foreach (var item in adornment.Series.ItemsSource)
                            totalValues += (item as Syncfusion.UI.Xaml.PivotChart.PivotChartPoint).BindingY;
                    }
                    label += " - (" + Math.Round(((adornment.Item as Syncfusion.UI.Xaml.PivotChart.PivotChartPoint).BindingY / totalValues) * 100, 2).ToString() + "%" + ")";
                }
                return label;
            }
        }
        return null;
    }

    public object ConvertBack(object value, Type targetType, object parameter, string language)
    {
        return null;
    }
}

{% endhighlight %}

{% highlight vb %}

Public Class CustomAdornmentConverter
	Implements IValueConverter
	Public Function Convert(value As Object, targetType As Type, parameter As Object, language As String) As Object
		If TypeOf value Is Syncfusion.UI.Xaml.Charts.ChartPieAdornment Then
			Dim adornment = TryCast(value, Syncfusion.UI.Xaml.Charts.ChartPieAdornment)
			TryCast(adornment.Series, Syncfusion.UI.Xaml.Charts.PieSeries).PieCoefficient = 0.5
			If parameter IsNot Nothing Then
				Dim interior As SolidColorBrush = TryCast(adornment.Interior, SolidColorBrush)
				If parameter.ToString() = "Background" Then
					Return New SolidColorBrush(Color.FromArgb(200, interior.Color.R, interior.Color.G, interior.Color.B))
				Else
					Return interior
				End If
			Else
				Dim label = String.Empty
				Dim totalValues As Double = 0.0
				If adornment IsNot Nothing Then
					label = TryCast(adornment.Item, Syncfusion.UI.Xaml.PivotChart.PivotChartPoint).BindingX
					If adornment.Series.ItemsSource IsNot Nothing Then
						For Each item As var In adornment.Series.ItemsSource
							totalValues += TryCast(item, Syncfusion.UI.Xaml.PivotChart.PivotChartPoint).BindingY
						Next
					End If
					label += " - (" + Math.Round((TryCast(adornment.Item, Syncfusion.UI.Xaml.PivotChart.PivotChartPoint).BindingY / totalValues) * 100, 2).ToString() + "%" + ")"
				End If
				Return label
			End If
		End If
		Return Nothing
	End Function

	Public Function ConvertBack(value As Object, targetType As Type, parameter As Object, language As String) As Object
		Return Nothing
	End Function
End Class

{% endhighlight %}

{% endtabs %}

![labelTemplate_LabelAdornments](Adornments_images/labelTemplate_LabelAdornments.png)

### Rotating labels

The labels in the adornments can be rotated to a specific angle using the `LabelRotationAngle` property. The following code snippet demonstrates how to rotate the labels.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.AdornmentsInfo>
    <syncfusion:PivotChartAdornmentsInfo ShowLabel="True" LabelRotationAngle="60"/>
</syncfusion:SfPivotChart.AdornmentsInfo>

{% endhighlight %}

{% highlight c# %}

PivotChartAdornmentsInfo adornmentsInfo = new PivotChartAdornmentsInfo();
adornmentsInfo.ShowLabel = true;
adornmentsInfo.LabelRotationAngle = 60;
PivotChart1.AdornmentsInfo = adornmentsInfo;

{% endhighlight %}

{% highlight vb %}

Dim adornmentsInfo As New PivotChartAdornmentsInfo()
adornmentsInfo.ShowLabel = True
adornmentsInfo.LabelRotationAngle = 60
PivotChart1.AdornmentsInfo = adornmentsInfo

{% endhighlight %}

{% endtabs %}

![labelRotation_LabelAdornments](Adornments_images/labelRotation_LabelAdornments.png)

### Customizing label appearance

The following code snippet illustrates how to customize the appearance of labels in adornments.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.AdornmentsInfo>
    <syncfusion:PivotChartAdornmentsInfo ShowLabel="True" AdornmentsPosition="Top" BorderBrush="Red" BorderThickness="2" Margin="2"
                                         FontStyle="Italic" FontSize="14" Foreground="Black" FontFamily="Times New Roman"/>
</syncfusion:SfPivotChart.AdornmentsInfo>

{% endhighlight %}

{% highlight c# %}

PivotChartAdornmentsInfo adornmentsInfo = new PivotChartAdornmentsInfo();
adornmentsInfo.ShowLabel = true;
adornmentsInfo.AdornmentsPosition = AdornmentsPosition.Top;
adornmentsInfo.BorderBrush = new SolidColorBrush(Colors.Red);
adornmentsInfo.BorderThickness = new Thickness(2);
adornmentsInfo.Margin = new Thickness(2);
adornmentsInfo.FontStyle = FontStyle.Italic;
adornmentsInfo.FontSize = 14;
adornmentsInfo.Foreground = new SolidColorBrush(Colors.Black);
adornmentsInfo.FontFamily = new FontFamily("Times New Roman");
PivotChart1.AdornmentsInfo = adornmentsInfo;

{% endhighlight %}

{% highlight vb %}

Dim adornmentsInfo As New PivotChartAdornmentsInfo()
adornmentsInfo.ShowLabel = True
adornmentsInfo.AdornmentsPosition = AdornmentsPosition.Top
adornmentsInfo.BorderBrush = New SolidColorBrush(Colors.Red)
adornmentsInfo.BorderThickness = New Thickness(2)
adornmentsInfo.Margin = New Thickness(2)
adornmentsInfo.FontStyle = FontStyle.Italic
adornmentsInfo.FontSize = 14
adornmentsInfo.Foreground = New SolidColorBrush(Colors.Black)
adornmentsInfo.FontFamily = New FontFamily("Times New Roman")
PivotChart1.AdornmentsInfo = adornmentsInfo

{% endhighlight %}

{% endtabs %}

![customizedLabel_LabelAdornments](Adornments_images/customizedLabel_LabelAdornments.png)

### Applying series brush

The series color palette can be applied to the background of the labels in adornments by enabling the `UseSeriesPalette` property.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.AdornmentsInfo>
    <syncfusion:PivotChartAdornmentsInfo ShowLabel="True" UseSeriesPalette="True"/>
</syncfusion:SfPivotChart.AdornmentsInfo>

{% endhighlight %}

{% highlight c# %}

PivotChartAdornmentsInfo adornmentsInfo = new PivotChartAdornmentsInfo();
adornmentsInfo.ShowLabel = true;
adornmentsInfo.UseSeriesPalette = true;
PivotChart1.AdornmentsInfo = adornmentsInfo;

{% endhighlight %}

{% highlight vb %}

Dim adornmentsInfo As New PivotChartAdornmentsInfo()
adornmentsInfo.ShowLabel = True
adornmentsInfo.UseSeriesPalette = True
PivotChart1.AdornmentsInfo = adornmentsInfo

{% endhighlight %}

{% endtabs %}

![useSeriesPalette_LabelAdornments](Adornments_images/useSeriesPalette_LabelAdornments.png)

### Formatting labels

The content of the labels in adornments can be set to a desired format by using the `SegmentLabelFormat` property. The following code snippet illustrates how to format an adornment label to decimal digits.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.AdornmentsInfo>
    <syncfusion:PivotChartAdornmentsInfo ShowLabel="True" SegmentLabelFormat="0.00"/>
</syncfusion:SfPivotChart.AdornmentsInfo>

{% endhighlight %}

{% highlight c# %}

PivotChartAdornmentsInfo adornmentsInfo = new PivotChartAdornmentsInfo();
adornmentsInfo.ShowLabel = true;
adornmentsInfo.SegmentLabelFormat = "0.00";
PivotChart1.AdornmentsInfo = adornmentsInfo;

{% endhighlight %}

{% highlight vb %}

Dim adornmentsInfo As New PivotChartAdornmentsInfo()
adornmentsInfo.ShowLabel = True
adornmentsInfo.SegmentLabelFormat = "0.00"
PivotChart1.AdornmentsInfo = adornmentsInfo

{% endhighlight %}

{% endtabs %}

![labelFormat_LabelAdornments](Adornments_images/labelFormat_LabelAdornments.png)

## Connector line

A connector line can be added to the adornments through the `ShowConnectorLine` property. It can be customized by using the `ConnectorHeight` and `ConnectorRotationAngle` properties as follows.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.AdornmentsInfo>
    <syncfusion:PivotChartAdornmentsInfo ShowLabel="True" ShowConnectorLine="True" ConnectorHeight="20" ConnectorRotationAngle="45"/>
</syncfusion:SfPivotChart.AdornmentsInfo>

{% endhighlight %}

{% highlight c# %}

PivotChartAdornmentsInfo adornmentsInfo = new PivotChartAdornmentsInfo();
adornmentsInfo.ShowLabel = true;
adornmentsInfo.ShowConnectorLine = true;
adornmentsInfo.ConnectorHeight = 20;
adornmentsInfo.ConnectorRotationAngle = 45;
PivotChart1.AdornmentsInfo = adornmentsInfo;

{% endhighlight %}

{% highlight vb %}

Dim adornmentsInfo As New PivotChartAdornmentsInfo()
adornmentsInfo.ShowLabel = True
adornmentsInfo.ShowConnectorLine = True
adornmentsInfo.ConnectorHeight = 20
adornmentsInfo.ConnectorRotationAngle = 45
PivotChart1.AdornmentsInfo = adornmentsInfo

{% endhighlight %}

{% endtabs %}

![connectorLine_LabelAdornments](Adornments_images/connectorLine_LabelAdornments.png)

### Styling connector line

You can define your own style for the connector line by using the `ConnectorLineStyle` property.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.AdornmentsInfo>
    <syncfusion:PivotChartAdornmentsInfo ShowLabel="True" ShowConnectorLine="True" ConnectorHeight="20">
        <syncfusion:PivotChartAdornmentsInfo.ConnectorLineStyle>
            <Style TargetType="Path">
                <Setter Property="StrokeDashArray" Value="10,7,5"/>
                <Setter Property="StrokeThickness" Value="2"/>
                <Setter Property="Stroke" Value="Red"/>
            </Style>
        </syncfusion:PivotChartAdornmentsInfo.ConnectorLineStyle>
    </syncfusion:PivotChartAdornmentsInfo>
</syncfusion:SfPivotChart.AdornmentsInfo>

{% endhighlight %}

{% highlight c# %}

PivotChartAdornmentsInfo adornmentsInfo = new PivotChartAdornmentsInfo();
adornmentsInfo.ShowLabel = true;
adornmentsInfo.ShowConnectorLine = true;
adornmentsInfo.ConnectorHeight = 20;
adornmentsInfo.ConnectorLineStyle = Resources["CustomLineStyle"] as Style;
PivotChart1.AdornmentsInfo = adornmentsInfo;

{% endhighlight %}

{% highlight vb %}

Dim adornmentsInfo As New PivotChartAdornmentsInfo()
adornmentsInfo.ShowLabel = True
adornmentsInfo.ShowConnectorLine = True
adornmentsInfo.ConnectorHeight = 20;
adornmentsInfo.ConnectorLineStyle = TryCast(Resources("CustomLineStyle"), Style)
PivotChart1.AdornmentsInfo = adornmentsInfo

{% endhighlight %}

{% endtabs %}

![styledConnectorLine_LabelAdornments](Adornments_images/styledConnectorLine_LabelAdornments.png)

## Positioning adornments

The adornments can be positioned with respect to chart segment by using the `AdornmentsPosition` property. The positions are:

* `Top`: Positions the adornment at the top edge point of the chart segment.
* `Bottom`: Positions the adornment at the bottom edge point of the chart segment.
* `TopAndBottom`: Positions the adornment at the center point of the chart segment.

The following code snippet explains how the adornments are placed at the center position.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.AdornmentsInfo>
    <syncfusion:PivotChartAdornmentsInfo ShowLabel="True" FontSize="16" AdornmentsPosition="TopAndBottom"/>
</syncfusion:SfPivotChart.AdornmentsInfo>

{% endhighlight %}

{% highlight c# %}

PivotChartAdornmentsInfo adornmentsInfo = new PivotChartAdornmentsInfo();
adornmentsInfo.ShowLabel = true;
adornmentsInfo.FontSize = 16;
adornmentsInfo.AdornmentsPosition = AdornmentsPosition.TopAndBottom;
PivotChart1.AdornmentsInfo = adornmentsInfo;

{% endhighlight %}

{% highlight vb %}

Dim adornmentsInfo As New PivotChartAdornmentsInfo()
adornmentsInfo.ShowLabel = True
adornmentsInfo.FontSize = 16
adornmentsInfo.AdornmentsPosition = AdornmentsPosition.TopAndBottom
PivotChart1.AdornmentsInfo = adornmentsInfo

{% endhighlight %}

{% endtabs %}

![positioningLabel_LabelAdornments](Adornments_images/positioningLabel_LabelAdornments.png)

A label in adornments can be aligned by using the `HorizontalAlignment` and `VerticalAlignment` properties as explained in the following code snippet.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.AdornmentsInfo>
    <syncfusion:PivotChartAdornmentsInfo ShowLabel="True" HorizontalAlignment="Right" VerticalAlignment="Center"/>
</syncfusion:SfPivotChart.AdornmentsInfo>

{% endhighlight %}

{% highlight c# %}

PivotChartAdornmentsInfo adornmentsInfo = new PivotChartAdornmentsInfo();
adornmentsInfo.ShowLabel = true;
adornmentsInfo.HorizontalAlignment = HorizontalAlignment.Right;
adornmentsInfo.VerticalAlignment = VerticalAlignment.Center;
PivotChart1.AdornmentsInfo = adornmentsInfo;

{% endhighlight %}

{% highlight vb %}

Dim adornmentsInfo As New PivotChartAdornmentsInfo()
adornmentsInfo.ShowLabel = True
adornmentsInfo.HorizontalAlignment = HorizontalAlignment.Right
adornmentsInfo.VerticalAlignment = VerticalAlignment.Center
PivotChart1.AdornmentsInfo = adornmentsInfo

{% endhighlight %}

{% endtabs %}

![alignedLabel_LabelAdornments](Adornments_images/alignedLabel_LabelAdornments.png)

The SfPivotChart supports positioning a label in adornments, depending upon the selected chart type, using the `LabelPosition` property. The following code snippet defines positioning the label based on the `Auto` position.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart x:Name="PivotChart1" ItemSource="{Binding ProductSalesData}" PivotAxis="{Binding PivotAxis}" 
                         PivotLegend="{Binding PivotLegend}" PivotCalculations="{Binding PivotCalculations}" ChartType="Spline">
    <syncfusion:SfPivotChart.AdornmentsInfo>
        <syncfusion:PivotChartAdornmentsInfo ShowLabel="True" LabelPosition="Auto"/>
    </syncfusion:SfPivotChart.AdornmentsInfo>
</syncfusion:SfPivotChart>>

{% endhighlight %}

{% highlight c# %}

PivotChartAdornmentsInfo adornmentsInfo = new PivotChartAdornmentsInfo();
adornmentsInfo.ShowLabel = true;
adornmentsInfo.LabelPosition = AdornmentsLabelPosition.Auto;
PivotChart1.AdornmentsInfo = adornmentsInfo;

{% endhighlight %}

{% highlight vb %}

Dim adornmentsInfo As New PivotChartAdornmentsInfo()
adornmentsInfo.ShowLabel = True
adornmentsInfo.LabelPosition = AdornmentsLabelPosition.Auto
PivotChart1.AdornmentsInfo = adornmentsInfo

{% endhighlight %}

{% endtabs %}

![autoAlignedLabel_LabelAdornments](Adornments_images/autoAlignedLabel_LabelAdornments.png)

A demo sample is located in the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\Samples\UWP\SampleBrowser\PivotChart\PivotChart\View\Adornments.xaml
