---
layout: post
title: Annotation | SfPivotChart | UWP | Syncfusion
description: Annotation
platform: UWP
control: SfPivotChart
documentation: ug
---

# Annotations

SfPivotChart supports annotations that allows you to mark the specific area of interest in the chart area. You can draw custom shapes, specify a text note and add images with the help of annotations.

You can add annotation by using the property of `Annotations` in SfPivotChart. Using this property, varieties of annotations can be added to the chart control. Following are the different types of annotations that are supported by SfPivotChart.

* Text Annotation
* Image Annotation
* Rectangle Annotation
* Ellipse Annotation
* Line Annotation
* Horizontal Line Annotation
* Vertical Line Annotation

## Text Annotation

Text annotations are used to add simple text representation in the chart area of SfPivotChart. The following code snippet shows how to add text annotation to the SfPivotChart.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.Annotations>
<syncfusion:PivotChartAnnotation AnnotationType="TextAnnotation" Text="Text Annotation" X1="2" Y1="150" FontFamily="Times New Roman" FontSize="16" FontWeight="Bold" FontStretch="ExtraExpanded" FontStyle="Italic"/>
</syncfusion:SfPivotChart.Annotations>

{% endhighlight %}

{% highlight c# %}

var annotation = new PivotChartAnnotation();
annotation.AnnotationType = PivotChartAnnotationType.TextAnnotation;
annotation.Text = "Text Annotation";
annotation.X1 = 2;
annotation.Y1 = 150;
annotation.FontFamily = new FontFamily("Times New Roman");
annotation.FontSize = 16;
annotation.FontWeight = FontWeights.Bold;
annotation.FontStretch = FontStretch.ExtraExpanded;
annotation.FontStyle = FontStyle.Italic;
PivotChart1.Annotations.Add(annotation);

{% endhighlight %}

{% highlight vb %}

Dim annotation = New PivotChartAnnotation()
annotation.AnnotationType = PivotChartAnnotationType.TextAnnotation
annotation.Text = "Text Annotation"
annotation.X1 = 2
annotation.Y1 = 150
annotation.FontFamily = New FontFamily("Times New Roman")
annotation.FontSize = 16
annotation.FontWeight = FontWeights.Bold
annotation.FontStretch = FontStretch.ExtraExpanded
annotation.FontStyle = FontStyle.Italic
PivotChart1.Annotations.Add(annotation)

{% endhighlight %}

{% endtabs %}

![](Annotations_images/textAnnotation.png)

**Rotating Text Annotation**

Text annotation can be rotated by using the property of `Angle`. The below code snippet illustrates about rotating the text annotation.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart1.Annotations>
<syncfusion:PivotChartAnnotation AnnotationType="TextAnnotation" Text="Text Annotation" X1="2" Y1="150" Angle="22" FontFamily="Times New Roman" FontSize="16" FontWeight="Bold" FontStretch="ExtraExpanded" FontStyle="Italic"/>
</syncfusion:SfPivotChart1.Annotations>

{% endhighlight %}

{% highlight c# %}

var annotation = new PivotChartAnnotation();
annotation.AnnotationType = PivotChartAnnotationType.TextAnnotation;
annotation.Text = "Text Annotation";
annotation.X1 = 2;
annotation.Y1 = 150;
annotation.FontFamily = new FontFamily("Times New Roman");
annotation.FontSize = 16;
annotation.FontWeight = FontWeights.Bold;
annotation.FontStretch = FontStretch.ExtraExpanded;
annotation.FontStyle = FontStyle.Italic;
annotation.Angle = 22;
PivotChart1.Annotations.Add(annotation);

{% endhighlight %}

{% highlight vb %}

Dim annotation = New PivotChartAnnotation()
annotation.AnnotationType = PivotChartAnnotationType.TextAnnotation
annotation.Text = "Text Annotation"
annotation.X1 = 2
annotation.Y1 = 150
annotation.FontFamily = New FontFamily("Times New Roman")
annotation.FontSize = 16
annotation.FontWeight = FontWeights.Bold
annotation.FontStretch = FontStretch.ExtraExpanded
annotation.FontStyle = FontStyle.Italic
annotation.Angle = 22
PivotChart1.Annotations.Add(annotation)

{% endhighlight %}

{% endtabs %}

![](Annotations_images/rotatedTextAnnotation.png)

**Editing Text Annotation**

The text annotation added in the chart area type can be edited by enabling the property of `EnableEditing`. The following code snippet demonstrates the editing of the text annotation.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.Annotations>
<syncfusion:PivotChartAnnotation AnnotationType="TextAnnotation" Text="Text Annotation" X1="2" Y1="150" EnableEditing="True" FontFamily="Times New Roman" FontSize="16" FontWeight="Bold" FontStretch="ExtraExpanded" FontStyle="Italic"/>
</syncfusion:SfPivotChart.Annotations>

{% endhighlight %}

{% highlight c# %}

var annotation = new PivotChartAnnotation();
annotation.AnnotationType = PivotChartAnnotationType.TextAnnotation;
annotation.Text = "Text Annotation";
annotation.X1 = 2;
annotation.Y1 = 150;
annotation.FontFamily = new FontFamily("Times New Roman");
annotation.FontSize = 16;
annotation.FontWeight = FontWeights.Bold;
annotation.FontStretch = FontStretch.ExtraExpanded;
annotation.FontStyle = FontStyle.Italic;
annotation.EnableEditing = true;
PivotChart1.Annotations.Add(annotation);

{% endhighlight %}

{% highlight vb %}

Dim annotation = New PivotChartAnnotation()
annotation.AnnotationType = PivotChartAnnotationType.TextAnnotation
annotation.Text = "Text Annotation"
annotation.X1 = 2
annotation.Y1 = 150
annotation.FontFamily = New FontFamily("Times New Roman")
annotation.FontSize = 16
annotation.FontWeight = FontWeights.Bold
annotation.FontStretch = FontStretch.ExtraExpanded
annotation.FontStyle = FontStyle.Italic
annotation.EnableEditing = True
PivotChart1.Annotations.Add(annotation)

{% endhighlight %}

{% endtabs %}

![](Annotations_images/editTextAnnotation.png)

## Image Annotation

SfPivotChart allows to add image annotation to the specific chart are by mentioning the `AnnotationType` as `ImageAnnotation`. The following code snippet shows how to add image annotation to SfPivotChart.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.Annotations>
    <syncfusion:PivotChartAnnotation AnnotationType="ImageAnnotation" ImageSource="ms-appx:///Assets/anchor.jpg" X1="1" X2="1.5" Y1="50" Y2="100"/>
</syncfusion:SfPivotChart.Annotations>

{% endhighlight %}

{% highlight c# %}

var annotation = new PivotChartAnnotation();
annotation.AnnotationType = PivotChartAnnotationType.ImageAnnotation;
annotation.ImageSource = "ms-appx:///Assets/anchor.jpg";
annotation.X1 = 1;
annotation.Y1 = 50;
annotation.X2 = 1.5;
annotation.Y2 = 100;
PivotChart1.Annotations.Add(annotation);

{% endhighlight %}

{% highlight vb %}

Dim annotation = New PivotChartAnnotation()
annotation.AnnotationType = PivotChartAnnotationType.ImageAnnotation
annotation.ImageSource = "ms-appx:///Assets/anchor.jpg"
annotation.X1 = 1
annotation.Y1 = 50
annotation.X2 = 1.5
annotation.Y2 = 100
PivotChart1.Annotations.Add(annotation)

{% endhighlight %}

{% endtabs %}

![](Annotations_images/imageAnnotation.png)

**Rotating Image Annotation**

Image annotation can be rotated by using the property of `Angle`. The below code snippet illustrates about rotating the image annotation.

{% tabs %}

{% highlight xaml %}
<syncfusion:SfPivotChart.Annotations>
    <syncfusion:PivotChartAnnotation AnnotationType="ImageAnnotation" Angle="22" ImageSource="ms-appx:///Assets/anchor.jpg" X1="1" X2="1.5" Y1="50" Y2="100"/>
</syncfusion:SfPivotChart.Annotations>>

{% endhighlight %}

{% highlight c# %}

var annotation = new PivotChartAnnotation();
annotation.AnnotationType = PivotChartAnnotationType.ImageAnnotation;
annotation.ImageSource = "ms-appx:///Assets/anchor.jpg";
annotation.X1 = 1;
annotation.Y1 = 50;
annotation.X2 = 1.5;
annotation.Y2 = 100;
annotation.Angle = 22;
PivotChart1.Annotations.Add(annotation);

{% endhighlight %}

{% highlight vb %}

Dim annotation = New PivotChartAnnotation()
annotation.AnnotationType = PivotChartAnnotationType.ImageAnnotation
annotation.ImageSource = "ms-appx:///Assets/anchor.jpg"
annotation.X1 = 1
annotation.Y1 = 50
annotation.X2 = 1.5
annotation.Y2 = 100
annotation.Angle = 22
PivotChart1.Annotations.Add(annotation)

{% endhighlight %}

{% endtabs %}

![](Annotations_images/rotatedImageAnnotation.png)

## Line Annotation

Line annotation draws a line over the specific chart area. The following code snippet specifies about adding line annotation to SfPivotChart.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.Annotations>
<syncfusion:PivotChartAnnotation AnnotationType="LineAnnotation" LineCap="Arrow" X1="1" Y1="30" X2="2" Y2="300" Stroke="Orange" StrokeThickness="3" StrokeDashCap="Square" StrokeLineJoin="Round"/>
</syncfusion:SfPivotChart.Annotations>

{% endhighlight %}

{% highlight c# %}

var annotation = new PivotChartAnnotation();
annotation.AnnotationType = PivotChartAnnotationType.LineAnnotation;
annotation.LineCap = LineCap.Arrow;
annotation.X1 = 1;
annotation.Y1 = 30;
annotation.X2 = 2;
annotation.Y2 = 300;
annotation.Stroke = new SolidColorBrush(Colors.Orange);
annotation.StrokeThickness = 3;
annotation.StrokeDashCap = PenLineCap.Square;
annotation.StrokeLineJoin = PenLineJoin.Round;
PivotChart1.Annotations.Add(annotation);

{% endhighlight %}

{% highlight vb %}

Dim annotation = New PivotChartAnnotation()
annotation.AnnotationType = PivotChartAnnotationType.LineAnnotation
annotation.LineCap = LineCap.Arrow
annotation.X1 = 1
annotation.Y1 = 30
annotation.X2 = 2
annotation.Y2 = 300
annotation.Stroke = New SolidColorBrush(Colors.Orange)
annotation.StrokeThickness = 3
annotation.StrokeDashCap = PenLineCap.Square
annotation.StrokeLineJoin = PenLineJoin.Round
PivotChart1.Annotations.Add(annotation)

{% endhighlight %}

{% endtabs %}

![](Annotations_images/lineAnnotation.png)

## Horizontal Line Annotation

Horizontal Line Annotation draws a horizontal line over the chart area. The following code snippet demonstrates the horizontal line annotation.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.Annotations>
<syncfusion:PivotChartAnnotation AnnotationType="HorizontalLineAnnotation" LineCap="Arrow" X1="0" X2="2" Y1="100" Stroke="LawnGreen" StrokeThickness="3" StrokeDashCap="Square" StrokeLineJoin="Round"/>
</syncfusion:SfPivotChart.Annotations>

{% endhighlight %}

{% highlight c# %}

var annotation = new PivotChartAnnotation();
annotation.AnnotationType = PivotChartAnnotationType.HorizontalLineAnnotation;
annotation.LineCap = LineCap.Arrow;
annotation.X1 = 1;
annotation.X2 = 2;
annotation.Y1 = 100;
annotation.Stroke = new SolidColorBrush(Colors.LawnGreen);
annotation.StrokeThickness = 3;
annotation.StrokeDashCap = PenLineCap.Square;
annotation.StrokeLineJoin = PenLineJoin.Round;
PivotChart1.Annotations.Add(annotation);

{% endhighlight %}

{% highlight vb %}

Dim annotation = New PivotChartAnnotation()
annotation.AnnotationType = PivotChartAnnotationType.HorizontalLineAnnotation
annotation.LineCap = LineCap.Arrow
annotation.X1 = 1
annotation.X2 = 2
annotation.Y1 = 100
annotation.Stroke = New SolidColorBrush(Colors.LawnGreen)
annotation.StrokeThickness = 3
annotation.StrokeDashCap = PenLineCap.Square
annotation.StrokeLineJoin = PenLineJoin.Round
PivotChart1.Annotations.Add(annotation)

{% endhighlight %}

{% endtabs %}

![](Annotations_images/horizontalLineAnnotation.png)

## Vertical Line Annotation

Vertical Line Annotation draws a vertical line over the chart area. The following code snippet specifies the vertical line annotation.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.Annotations>
<syncfusion:PivotChartAnnotation AnnotationType="VerticalLineAnnotation" LineCap="Arrow" X1="1" Y1="55" Y2="300" Stroke="BrulyWood" StrokeThickness="3" StrokeDashCap="Square" StrokeLineJoin="Round"/>
</syncfusion:SfPivotChart.Annotations>

{% endhighlight %}

{% highlight c# %}

var annotation = new PivotChartAnnotation();
annotation.AnnotationType = PivotChartAnnotationType.VerticalLineAnnotation;
annotation.LineCap = LineCap.Arrow;
annotation.X1 = 1;
annotation.Y1 = 55;
annotation.Y2 = 300;
annotation.Stroke = new SolidColorBrush(Colors.Orange);
annotation.StrokeThickness = 3;
annotation.StrokeDashCap = PenLineCap.Square;
annotation.StrokeLineJoin = PenLineJoin.Round;
PivotChart1.Annotations.Add(annotation);

{% endhighlight %}

{% highlight vb %}

Dim annotation = New PivotChartAnnotation()
annotation.AnnotationType = PivotChartAnnotationType.VerticalLineAnnotation
annotation.LineCap = LineCap.Arrow
annotation.X1 = 1
annotation.Y1 = 55
annotation.Y2 = 300
annotation.Stroke = New SolidColorBrush(Colors.Orange)
annotation.StrokeThickness = 3
annotation.StrokeDashCap = PenLineCap.Square
annotation.StrokeLineJoin = PenLineJoin.Round
PivotChart1.Annotations.Add(annotation)

{% endhighlight %}

{% endtabs %}

![](Annotations_images/verticalLineAnnotation.png)

## Rectangle Annotation

Rectangle Annotation draws a rectangle over the chart area. The following code snippet specifies how to add rectangle annotation to the chart.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.Annotations>
<syncfusion:PivotChartAnnotation AnnotationType="RectangleAnnotation" X1="1" X2="2" Y1="85" Y2="120" Fill="Red" Opacity="0.6"/>
</syncfusion:SfPivotChart.Annotations>

{% endhighlight %}

{% highlight c# %}

var annotation = new PivotChartAnnotation();
annotation.AnnotationType = PivotChartAnnotationType.RectangleAnnotation;
annotation.X1 = 1;
annotation.X2 = 2;
annotation.Y1 = 85;
annotation.Y2 = 120;
annotation.Fill = new SolidColorBrush(Colors.Red);
annotation.Opacity = 0.6;
PivotChart1.Annotations.Add(annotation);

{% endhighlight %}

{% highlight vb %}

Dim annotation = New PivotChartAnnotation()
annotation.AnnotationType = PivotChartAnnotationType.RectangleAnnotation
annotation.X1 = 1
annotation.X2 = 2
annotation.Y1 = 85
annotation.Y2 = 120
annotation.Fill = New SolidColorBrush(Colors.Red)
annotation.Opacity = 0.6
PivotChart1.Annotations.Add(annotation)

{% endhighlight %}

{% endtabs %}

![](Annotations_images/rectangleAnnotation.png)

## Ellipse Annotation

Ellipse Annotation draws an ellipse over the chart area. The following code snippet illustrates about adding ellipse annotation.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.Annotations>
<syncfusion:PivotChartAnnotation AnnotationType="EllipseAnnotation" X1="1" X2="2" Y1="85" Y2="120" Fill="Green" Opacity="0.6"/>
</syncfusion:SfPivotChart.Annotations>

{% endhighlight %}

{% highlight c# %}

var annotation = new PivotChartAnnotation();
annotation.AnnotationType = PivotChartAnnotationType.EllipseAnnotation;
annotation.X1 = 1;
annotation.X2 = 2;
annotation.Y1 = 85;
annotation.Y2 = 120;
annotation.Fill = new SolidColorBrush(Colors.Green);
annotation.Opacity = 0.6;
PivotChart1.Annotations.Add(annotation);

{% endhighlight %}

{% highlight vb %}

Dim annotation = New PivotChartAnnotation()
annotation.AnnotationType = PivotChartAnnotationType.EllipseAnnotation
annotation.X1 = 1
annotation.X2 = 2
annotation.Y1 = 85
annotation.Y2 = 120
annotation.Fill = New SolidColorBrush(Colors.Green)
annotation.Opacity = 0.6
PivotChart1.Annotations.Add(annotation)

{% endhighlight %}

{% endtabs %}

![](Annotations_images/ellipseAnnotation.png)

## Positioning Annotations

Annotations can be positioned in the SfPivotChart based on `X1` and `Y1` properties and for image and shape (Line, Ellipse, Rectangle, Horizontal Line and Vertical Line) annotations you need to specify `X2` and `Y2` properties. These X and Y values can be specified with axis units or pixel units and this can be identified by using `CoordinateUnit` property.

**CoordinateUnit as Axis**

To position the annotation based on axis values, you have to set the *CoordinateUnit* as *Pixels* and the values specified in `X1` and `Y1`, `X2` and `Y2` (if needed) are considered based on primary and secondary axis range values.

**CoordinateUnit as Pixels**

To position the annotation based on pixel values, you have to set the *CoordinateUnit* as *Pixels* and the values specified in `X1` and `Y1`, `X2` and `Y2` (if needed) are considered based on pixels.

## Dragging & Resizing Annotations

The annotations can be dragged and resized by enabling the properties of `CanDrag` and `CanDrop` as specified in the below code snippet.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart.Annotations>
<syncfusion:PivotChartAnnotation AnnotationType="EllipseAnnotation" X1="1" X2="2" Y1="85" Y2="120" CanDrag="True" CanResize="True" DraggingMode="All" ResizingMode="All" Fill="Green" Opacity="0.6"/>
</syncfusion:SfPivotChart.Annotations>

{% endhighlight %}

{% highlight c# %}

var annotation = new PivotChartAnnotation();
annotation.AnnotationType = PivotChartAnnotationType.EllipseAnnotation;
annotation.X1 = 1;
annotation.X2 = 2;
annotation.Y1 = 85;
annotation.Y2 = 120;
annotation.Fill = new SolidColorBrush(Colors.Green);
annotation.Opacity = 0.6;
annotation.CanDrag = true;
annotation.CanResize = true;
annotation.DraggingMode = AxisMode.All;
annotation.ResizingMode = AxisMode.All;
PivotChart1.Annotations.Add(annotation);

{% endhighlight %}

{% highlight vb %}

Dim annotation = New PivotChartAnnotation()
annotation.AnnotationType = PivotChartAnnotationType.EllipseAnnotation
annotation.X1 = 1
annotation.X2 = 2
annotation.Y1 = 85
annotation.Y2 = 120
annotation.Fill = New SolidColorBrush(Colors.Green)
annotation.Opacity = 0.6
annotation.CanDrag = True
annotation.CanResize = True
annotation.DraggingMode = AxisMode.All
annotation.ResizingMode = AxisMode.All
PivotChart1.Annotations.Add(annotation)

{% endhighlight %}

{% endtabs %}

![](Annotations_images/resizing_Dragging_Annotations.png)

A demo sample is located in the below location:

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\Samples\UWP\SampleBrowser\PivotChart\PivotChart\View\Annotations.xaml