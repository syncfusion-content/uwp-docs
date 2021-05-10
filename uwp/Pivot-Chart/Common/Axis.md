---
layout: post
title: Axis in UWP Pivot Chart control | Syncfusion
description: Learn here all about Axis support in Syncfusion UWP Pivot Chart (SfPivotChart) control and more.
platform: UWP
control: SfPivotChart
documentation: ug
---

# Axis in UWP Pivot Chart (SfPivotChart)

Axis is used to locate a data point inside the chart area. Generally, two axes are required along each direction to locate the data point in the chart, i.e., horizontal and vertical. The vertical axis (y-axis) represents numerical values and the horizontal axis (x-axis) represents categorical values.

## Axis style

The primary axis style can be modified by using the `PrimaryAxisStyle` property and the secondary axis style can be modified by using the `SecondaryAxisStyle` property in the SfPivotChart.

### Grid line style

To customize the grid line of chart axis, you can use the `GridLineStyle` property.

The following code snippet describes how to customize the style of grid lines in the primary axis.

{% tabs %}

{% highlight xaml %}

<Page.Resources>
    <Style x:Key="LineStyle" TargetType="Line">
        <Setter Property="Stroke" Value="Red"/>
        <Setter Property="StrokeDashArray" Value="1,2"/>
    </Style>
</Page.Resources>

<syncfusion:SfPivotChart.PrimaryAxisStyle>
    <syncfusion:PivotChartAxisStyle GridLineStyle="{StaticResource LineStyle}"/>
</syncfusion:SfPivotChart.PrimaryAxisStyle>

{% endhighlight %}

{% highlight c# %}

PivotChart1.PrimaryAxisStyle.GridLineStyle = Resources["LineStyle"] as Style;

{% endhighlight %}

{% highlight vb %}

PivotChart1.PrimaryAxisStyle.GridLineStyle = TryCast(Resources("LineStyle"), Style)

{% endhighlight %}

{% endtabs %}

![relationalPrimaryAxisGridLineStyle](Axis_images/relationalPrimaryAxisGridLineStyle.png)

The following code snippet describes how to customize the style of gridlines in the secondary axis.

{% tabs %}

{% highlight xaml %}

<Page.Resources>
    <Style x:Key="LineStyle" TargetType="Line">
        <Setter Property="Stroke" Value="Red"/>
        <Setter Property="StrokeDashArray" Value="1,2"/>
    </Style>
</Page.Resources>

<syncfusion:SfPivotChart.SecondaryAxisStyle>
    <syncfusion:PivotChartAxisStyle GridLineStyle="{StaticResource LineStyle}"/>
</syncfusion:SfPivotChart.SecondaryAxisStyle>

{% endhighlight %}

{% highlight c# %}

PivotChart1.SecondaryAxisStyle.GridLineStyle = Resources["LineStyle"] as Style;

{% endhighlight %}

{% highlight vb %}

PivotChart1.SecondaryAxisStyle.GridLineStyle = TryCast(Resources("LineStyle"), Style)

{% endhighlight %}

{% endtabs %}

![relationalSecondaryAxisGridLineStyle](Axis_images/relationalSecondaryAxisGridLineStyle.png)

### Expander style

To customize the expanders of primary axis labels, you should assign the `ExpanderStyle` property in the `PivotChartAxisStyle`. It is applicable only for the primary axis having expanders in labels.

The following code snippet describes how to customize the style of expanders in primary axis labels.

{% tabs %}

{% highlight xaml %}

<Page.Resources>
    <Style x:Key="PrimaryAxisExpanderStyle" TargetType="ToggleButton">
        <Setter Property="Template">
        <Setter.Value>
        <ControlTemplate TargetType="ToggleButton">
            <Grid Visibility="{TemplateBinding Visibility}">
                   <VisualStateManager.VisualStateGroups>
                   <VisualStateGroup x:Name="CommonStates">
                   <VisualState x:Name="Normal"/>
                   <VisualState x:Name="PointerOver"/>
                   <VisualState x:Name="Pressed"/>
                   <VisualState x:Name="Disabled"/>
                   <VisualState x:Name="Checked">
                        <Storyboard>
                            <ObjectAnimationUsingKeyFrames Storyboard.TargetName="ExpandPath" Storyboard.TargetProperty="Data">
                                <DiscreteObjectKeyFrame KeyTime="0">
                                    <DiscreteObjectKeyFrame.Value>
                                        <Geometry>M0,2L0,3 5,3 5,2z</Geometry>
                                    </DiscreteObjectKeyFrame.Value>
                                </DiscreteObjectKeyFrame>
                            </ObjectAnimationUsingKeyFrames>
                        </Storyboard>
                    </VisualState>
                    <VisualState x:Name="CheckedPressed"/>
                    <VisualState x:Name="CheckedDisabled"/>
                    <VisualState x:Name="Indeterminate"/>
                    <VisualState x:Name="IndeterminatePointerOver"/>
                    <VisualState x:Name="IndeterminatePressed"/>
                    <VisualState x:Name="IndeterminateDisabled"/>
                    </VisualStateGroup>
                </VisualStateManager.VisualStateGroups>
                            <Border x:Name="border" HorizontalAlignment="Center"
                                Background="Transparent" BorderBrush="Gray" BorderThickness="1"
                                CornerRadius="1" Height="13" Width="13">
                            <Grid>
                                <Path x:Name="ExpandPath" Data="M0,2L0,3 2,3 2,5 3,5 3,3 5,3 5,2 3,2 3,0 2,0 2,2z"
                                      Fill="#FF333333" Stroke="#FF333333" StrokeThickness="1" HorizontalAlignment="Center"
                                      Stretch="Uniform" Height="7" Width="7" VerticalAlignment="Center"/>
                            </Grid>
                        </Border>
                    </Grid>
                </ControlTemplate>
            </Setter.Value>
        </Setter>
    </Style>
</Page.Resources>

<syncfusion:SfPivotChart x:Name="PivotChart1" OlapDataManager="{Binding OlapDataManager}">
    <syncfusion:SfPivotChart.PrimaryAxisStyle>
        <syncfusion:PivotChartAxisStyle ExpanderStyle="{StaticResource PrimaryAxisExpanderStyle}"/>
    </syncfusion:SfPivotChart.PrimaryAxisStyle>
</syncfusion:SfPivotChart>

{% endhighlight %}

{% highlight c# %}

PivotChart1.PrimaryAxisStyle.ExpanderStyle = Resources["PrimaryAxisExpanderStyle"] as Style;

{% endhighlight %}

{% highlight vb %}

PivotChart1.PrimaryAxisStyle.ExpanderStyle = TryCast(Resources("PrimaryAxisExpanderStyle"), Style)

{% endhighlight %}

{% endtabs %}

![relationalPrimaryAxisExpanderStyle](Axis_images/relationalPrimaryAxisExpanderStyle.png)

### Group line customization

To customize the appearance of group line around primary axis labels, the `GroupLineStroke` and `GroupLineStrokeThickness` properties of `PivotChartAxisStyle` are used. The following code snippet describes how to customize the appearance of group lines in the primary axis.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart x:Name="PivotChart1">
    <syncfusion:SfPivotChart.PrimaryAxisStyle>
        <syncfusion:PivotChartAxisStyle GroupLineStroke="Red" GroupLineStrokeThickness="1.5"/>
    </syncfusion:SfPivotChart.PrimaryAxisStyle>
</syncfusion:SfPivotChart>

{% endhighlight %}

{% highlight c# %}

PivotChart1.PrimaryAxisStyle.GroupLineStroke = new SolidColorBrush((Colors.Red));
PivotChart1.PrimaryAxisStyle.GroupLineStrokeThickness = new Thickness(1.5);

{% endhighlight %}

{% highlight vb %}

PivotChart1.PrimaryAxisStyle.GroupLineStroke = New SolidColorBrush((Colors.Red))
PivotChart1.PrimaryAxisStyle.GroupLineStrokeThickness = New Thickness(1.5)

{% endhighlight %}

{% endtabs %}

![relationalGroupLineStroke](Axis_images/relationalGroupLineStroke.png)

### Label customization

To customize the labels of pivot chart axis, the properties like `LabelFontFamily`, `LabelFontSize`, and `LabelForeground` can be used.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.PrimaryAxisStyle>
    <syncfusion:PivotChartAxisStyle LabelFontFamily="Arial" LabelFontSize="14" LabelForeground="DarkGray"/>
</syncfusion:SfPivotChart.PrimaryAxisStyle>

<syncfusion:SfPivotChart.SecondaryAxisStyle>
    <syncfusion:PivotChartAxisStyle LabelFontFamily="Arial" LabelFontSize="14" LabelForeground="DarkGray"/>
</syncfusion:SfPivotChart.SecondaryAxisStyle>

{% endhighlight %}

{% highlight c# %}

PivotChart1.PrimaryAxisStyle.LabelForeground = new SolidColorBrush(Colors.DarkGray);
PivotChart1.PrimaryAxisStyle.LabelFontFamily = new FontFamily("Arial");
PivotChart1.PrimaryAxisStyle.LabelFontSize = 14d;

PivotChart1.SecondaryAxisStyle.LabelForeground = new SolidColorBrush(Colors.DarkGray);
PivotChart1.SecondaryAxisStyle.LabelFontFamily = new FontFamily("Arial");
PivotChart1.SecondaryAxisStyle.LabelFontSize = 14d;

{% endhighlight %}

{% highlight vb %}

PivotChart1.PrimaryAxisStyle.LabelForeground = New SolidColorBrush(Colors.DarkGray)
PivotChart1.PrimaryAxisStyle.LabelFontFamily = New FontFamily("Arial")
PivotChart1.PrimaryAxisStyle.LabelFontSize = 14.0

PivotChart1.SecondaryAxisStyle.LabelForeground = New SolidColorBrush(Colors.DarkGray)
PivotChart1.SecondaryAxisStyle.LabelFontFamily = New FontFamily("Arial")
PivotChart1.SecondaryAxisStyle.LabelFontSize = 14.0

{% endhighlight %}

{% endtabs %}

![axisLabelStyle](Axis_images/axisLabelStyle.png)

**Label formatting**

To modify the format of axis labels, you should use the `LabelFormat` property. The following code sample describes how to display the ‘%’ symbol in secondary axis labels.

{% highlight xaml %}

<syncfusion:SfPivotChart.SecondaryAxisStyle>
     <syncfusion:PivotChartAxisStyle LabelFormat="00.00%"/>
</syncfusion:SfPivotChart.SecondaryAxisStyle>

{% endhighlight %}

![axisLabelFormat](Axis_images/axisLabelFormat.png)

**Label rotation**

The labels of primary axis and secondary axis can be rotated with the help of `LabelRotationAngle` property in the `PivotChartAxisStyle`. The following code snippet illustrates how to rotate the angle of primary axis labels to -20 degrees.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.PrimaryAxisStyle>
    <syncfusion:PivotChartAxisStyle LabelRotationAngle="-20"/>
</syncfusion:SfPivotChart.PrimaryAxisStyle>

{% endhighlight %}

{% highlight c# %}

PivotChart1.PrimaryAxisStyle.LabelRotationAngle = -20;

{% endhighlight %}

{% highlight vb %}

PivotChart1.PrimaryAxisStyle.LabelRotationAngle = -20

{% endhighlight %}

{% endtabs %}

![axisLabelRotation](Axis_images/axisLabelRotation.png)

## Show/hide axis

The visibility of pivot chart axis can be toggled by setting the `Visibility` property of `PrimaryAxis` or `SecondaryAxis`. The following code snippet shows how to hide the primary axis of the SfPivotChart.

{% tabs %}

{% highlight c# %}

PivotChart1.PrimaryAxis.Visibility = Windows.UI.Xaml.Visibility.Collapsed;
PivotChart1.SecondaryAxis.Visibility = Windows.UI.Xaml.Visibility.Collapsed;

{% endhighlight %}

{% highlight vb %}

PivotChart1.PrimaryAxis.Visibility = Windows.UI.Xaml.Visibility.Collapsed
PivotChart1.SecondaryAxis.Visibility = Windows.UI.Xaml.Visibility.Collapsed

{% endhighlight %}

{% endtabs %}

![axisLabelVisibility](Axis_images/axisLabelVisibility.png)
