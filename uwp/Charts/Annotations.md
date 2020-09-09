---
layout: post
title: Annotations | SfChart | uwp | Syncfusion
description: Explains the chart annotations, positioning the annotation, customizing the annotation and the types present in the annotation.
platform: uwp
control: SfChart
documentation: ug
---
# Annotations in UWP Charts (SfChart)

[`SfChart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html) supports [`Annotations`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html#Syncfusion_UI_Xaml_Charts_SfChart_Annotations), which allows you to mark the specific area of interest in the chart area. You can draw custom shapes, also text and images can be added using [`Annotations`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html#Syncfusion_UI_Xaml_Charts_SfChart_Annotations). 

The following annotations are supported in [`SfChart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html)

* [Text Annotation](#Text_Annotation)
* [Shape Annotation](#Shape_Annotation)
* [Image Annotation](#Image_Annotation)

## Adding Annotation


You can create an instance for any type of Annotation and add it to [`Annotations`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.AnnotationCollection.html) collection. Here for instance, the [`EllipseAnnotation`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.EllipseAnnotation.html) is added.

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Annotations>

<syncfusion:EllipseAnnotation  X1="2.5" Y1="1500" 

Text="Ellipse Annotation"                                            

X2="3.6" Y2="1680" >

</syncfusion:EllipseAnnotation>            

</syncfusion:SfChart.Annotations>

{% endhighlight %}

{% highlight c# %}

EllipseAnnotation annotation=new EllipseAnnotation()
{

    X1 = 2.5, Y1 = 1500,

    X2 = 3.6, Y2 = 1680,

    Text = "Ellipse Annotation"

};

chart.Annotations.Add(annotation);

{% endhighlight %}

{% endtabs %}

![Annotation support in UWP Chart](Annotation_images/Annotation_img1.jpeg)


## Positioning the Annotation

[`Annotations`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html#Syncfusion_UI_Xaml_Charts_SfChart_Annotations) can be positioned in plot area based on [`X1`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_x1) and [`Y1`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_y1)  properties and for image and shape annotations you need to specify [`X2`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_x2) and [`Y2`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_y2) properties. These X and Y values can be specified with axis units or pixel units and this can be identified using [`CoordinateUnit`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_CoordinateUnit) property.

**Positioning** **based** **on** **CoordinateUnit** **as** **Axis**

To position based on axis you need to set the X1 and Y1, X2 and Y2 (if needed) properties based on the primary and secondary axis range values and [`CoordinateUnit`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_CoordinateUnit) as [`Axis`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.CoordinateUnit.html). 

**Positioning** **based** **on** **CoordinateUnit** **as** **Pixels**

To position based on the pixel values you have to set the [`CoordinateUnit`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_CoordinateUnit) as [`Pixels`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.CoordinateUnit.html) and the pixel values in X1 and Y1, X2 and Y2 properties in Annotation.

**Adding** **Annotation** **for** **MultipleAxes**

You can also add annotation for a particular axis when there is multiple axes using [`XAxisName`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_XAxisName) and [`YAxisName`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_YAxisName) properties as in the below code snippet.

{% tabs %}

{% highlight xaml %}

<Chart:SfChart>

<Chart:SfChart.RowDefinitions>

<Chart:ChartRowDefinition></Chart:ChartRowDefinition>

<Chart:ChartRowDefinition></Chart:ChartRowDefinition>

</Chart:SfChart.RowDefinitions>

<Chart:SfChart.PrimaryAxis>

<Chart:CategoryAxis/>

</Chart:SfChart.PrimaryAxis>

<Chart:SfChart.SecondaryAxis>

<Chart:NumericalAxis  

x:Name="FirstYAxis"                                         

Chart:ChartBase.Row="0"/>

</Chart:SfChart.SecondaryAxis>      

<Chart:SfChart.Annotations>

<Chart:HorizontalLineAnnotation X1="-0.5" X2="3.5"

Stroke="DarkGray"

StrokeThickness="2" 

LineCap="Arrow"

CanDrag="True" CanResize="True"

YAxisName="FirstYAxis"

Y1="500">                    

</Chart:HorizontalLineAnnotation>               

<Chart:RectangleAnnotation  X1="0.6" CanDrag="True" CanResize="True"                                

X2="2.2" Y2="1500" Y1="1800" 

Stroke="DarkGray"

Fill="LightGray"

Opacity="0.5"

YAxisName="SecondYAxis">            

</Chart:RectangleAnnotation>

</Chart:SfChart.Annotations>

<Chart:ColumnSeries  Label="2011" Interior="#777777"

ItemsSource="{Binding Demands}" 

XBindingPath="Demand"      

YBindingPath="Year2011"/>

<Chart:ScatterSeries  Interior="#777777" ItemsSource="{Binding Demands}" 

XBindingPath="Demand"  YBindingPath="Year2010">

<Chart:ScatterSeries.YAxis>

<Chart:NumericalAxis x:Name="SecondYAxis"    

LabelTemplate="{StaticResource label}" TickLineSize="5" 

MajorTickLineStyle="{StaticResource tick}" Minimum="0" Maximum="2000" Interval="500"                                              

AxisLineStyle="{StaticResource axis}" ShowGridLines="False"

Chart:ChartBase.Row="1"></Chart:NumericalAxis>

</Chart:ScatterSeries.YAxis>

</Chart:ScatterSeries>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();

chart.RowDefinitions.Add(new ChartRowDefinition());

chart.RowDefinitions.Add(new ChartRowDefinition());

chart.PrimaryAxis = new CategoryAxis();

chart.SecondaryAxis = new NumericalAxis();

ChartBase.SetRow(chart.SecondaryAxis, 0);

HorizontalLineAnnotation annotation = new HorizontalLineAnnotation()
{

    X1 = -0.5, Y1 = 500,

    X2 = 3.5,

    Stroke = new SolidColorBrush(Colors.DarkGray),

    StrokeThickness = 2,

    LineCap = LineCap.Arrow,

    CanDrag = true,

    CanResize = true,

    YAxisName = "FirstYAxis"

};

RectangleAnnotation annotation1 = new RectangleAnnotation()
{

    X1 = 0.6,Y1 = 1500,

    X2 = 2.2,Y2=1800,

    Stroke = new SolidColorBrush(Colors.DarkGray),

    Fill = new SolidColorBrush(Colors.LightGray),

    StrokeThickness = 2,

    Opacity = 0.5,

    CanDrag = true,

    CanResize = true,

    YAxisName = "SecondYAxis"

};

chart.Annotations.Add(annotation);

chart.Annotations.Add(annotation1);

ColumnSeries columnSeries = new ColumnSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2011",

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77))

};

ScatterSeries scatterSeries = new ScatterSeries()
{

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2010",

    Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77))

};

NumericalAxis axis = new NumericalAxis()
{

    Minimum = 0,

    Maximum = 2000,

    Interval = 500,

    ShowGridLines = false,

    TickLineSize = 5,

    LabelTemplate = chart.Resources["labelTemplate"] as DataTemplate,

    MajorTickLineStyle = chart.Resources["lineStyle1"] as Style,

    AxisLineStyle = chart.Resources["lineStyle2"] as Style

};

ChartBase.SetRow(axis, 1);

scatterSeries.YAxis = axis;

chart.Series.Add(columnSeries);

chart.Series.Add(scatterSeries);

{% endhighlight %}

{% endtabs %}

![Multiple axis support for annotation in UWP Chart](Annotation_images/Annotation_img2.jpeg)


## Aligning the Annotation

You can align the annotation horizontally and vertically from its actual plotting position using the `HorizontalAlignment` and `VerticalAlignment` properties as in the following code sample.

{% highlight xaml %}

<syncfusion:SfChart.Annotations>                    

<syncfusion:RectangleAnnotation  X1="0.6" 

HorizontalAlignment="Left"

VerticalAlignment="Bottom"

X2="2.2"                                                

Y2="1500"                                                

Y1="1800"                                                 

Stroke="DarkGray"

Fill="LightGray"

Opacity="0.5">            

</syncfusion:RectangleAnnotation>

</syncfusion:SfChart.Annotations>

{% endhighlight %}

In the following image, you can see the rectangle annotation aligned to the bottom left from its actual position in the chart area.

![Alignment support for annotations in UWP Chart](Annotation_images/Annotation_img3.jpeg)


## Text Annotation

[`TextAnnotations`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.TextAnnotation.html) are used to add simple text in specific points over the chart area.

### Rotate the Text Annotation

The [`Angle`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.TextAnnotation.html#Syncfusion_UI_Xaml_Charts_TextAnnotation_Angle) property is used to get or set the angle for rotating the Annotation. The following code example demonstrate the rotation feature for [`TextAnnotation`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.TextAnnotation.html).

{% highlight xaml %}

<syncfusion:SfChart.Annotations>

<syncfusion:TextAnnotation  CoordinateUnit="Axis"                                           

Text="Annotation"

HorizontalAlignment="Stretch"

VerticalAlignment="Stretch"

FontWeight="Bold"

Foreground="Black"

Angle="90"

X1="3.5" Y1="500" >

</syncfusion:TextAnnotation>

</syncfusion:SfChart.Annotations>

{% endhighlight %}

{% highlight C# %}

{% endhighlight %}

![Rotation support for text annotation in UWP Chart](Annotation_images/Annotation_img4.jpeg)


### Editing Text Annotation

[`SfChart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html) provides you with an editing option for the text in any annotations. When text annotation is enabled editing, if we click the text annotation it switches to edit mode which provide easy way of customizing the text at run time. You can enable the editing mode in TextAnnotation using [`EnableEditing`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_EnableEditing) property.

The following code example and screenshot demonstrate [`TextAnnotation`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.TextAnnotation.html) while editing the text.

{% highlight xaml %}

<syncfusion:SfChart.Annotations>

<syncfusion:TextAnnotation  CoordinateUnit="Axis"                                           

Text="Annotation"

EnableEditing="True"

HorizontalAlignment="Stretch"

VerticalAlignment="Stretch"

FontWeight="Bold"

Foreground="Black"

Angle="90"

X1="3.5" Y1="500" >

</syncfusion:TextAnnotation>

</syncfusion:SfChart.Annotations>

{% endhighlight %}

![Editing text annotation support in UWP Chart](Annotation_images/Annotation_img5.jpeg)


## Shape Annotation

[`ShapeAnnotation`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html) allows you to add annotations in the form of shapes such as rectangle, ellipse,horizontal line and vertical line  at the specific area of interest, in the chart area.

* [`EllipseAnnotation`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.EllipseAnnotation.html)- Used to draw a circle or an ellipse over the chart area.
* [`RectangleAnnotation`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.RectangleAnnotation.html)- Used to draw a rectangle over the chart area.
* [`VerticalLineAnnotation`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.VerticalLineAnnotation.html)- Used to draw a vertical line across the chart area.
* [`HorizontalLineAnnotation`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.HorizontalLineAnnotation.html) - Used to add a horizontal line across the chart area.

The following API’s are commonly used in all ShapeAnnotation:

* [`Fill`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_Fill) - Represents the brush inside the Shape Annotation.

* [`X2`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_x2)  - Represents the X2 Coordinate of the Shape Annotation.

* [`Y2`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_y2) - Represents the Y2 Coordinate of the Shape Annotation.

* [`CanDrag`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_CanDrag) - A Boolean value that represent to drag the Annotation.

* [`CanResize`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_CanResize)  - A Boolean value that represent to resize the Annotation.


### Customization options for LineAnnotation


**GrabExtent** 

[`GrabExtent`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.LineAnnotation.html#Syncfusion_UI_Xaml_Charts_LineAnnotation_GrabExtent) property of [`LineAnnotation`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.LineAnnotation.html) allows user to extent the hit visible area, while performing dragging and resizing. We need to set the desired pixel value for [`GrabExtent`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.LineAnnotation.html#Syncfusion_UI_Xaml_Charts_LineAnnotation_GrabExtent) property and it can be set as shown in the below code example:

{% tabs %}

{% highlight xml %}

<syncfusion:SfChart.Annotations>
 
<syncfusion:LineAnnotation X1="0" X2="3" Y1="1500" Y2="1500"     
                               GrabExtent="10" 
                               Stroke="DarkGray" CanDrag="True"   
                               CanResize="True"/>
     
</syncfusion:SfChart.Annotations>

{% endhighlight %}

{% highlight c# %}

LineAnnotation annotation = new LineAnnotation()
            {
                X1 = 0,
                X2 = 3,
                Y1 = 1500,
                Y2 = 1500,
                CanDrag = true,
                Stroke = new SolidColorBrush(Colors.DarkGray),
                CanResize = true,
                GrabExtent = 10
            };
            
chart.Annotations.Add(annotation);


{% endhighlight %}

{% endtabs %}

![Customizing line annotation support in UWP Chart](Annotation_images/GrabExtent.png)


**Toggling** **LineAnnotation** **Visibility**

[`LineAnnotation`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.LineAnnotation.html) by default will be visible. You can also collapse the visibility of the line annotation using [`ShowLine`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.LineAnnotation.html#Syncfusion_UI_Xaml_Charts_LineAnnotation_ShowLine) property.

{% highlight xaml %}

<syncfusion:SfChart.Annotations>

<syncfusion:HorizontalLineAnnotation X1="-0.5" X2="3.5"

Stroke="DarkGray"

StrokeThickness="1"

ShowLine="False"

Fill="LightGray"                                                      

Y1="1500" >                    

</syncfusion:HorizontalLineAnnotation>

<syncfusion:VerticalLineAnnotation  Stroke="DarkGray" StrokeThickness="1"                                                   

X1="1.5" >

</syncfusion:VerticalLineAnnotation>

</syncfusion:SfChart.Annotations>

{% endhighlight %}

![Visibility support for line annotation in UWP Chart](Annotation_images/Annotation_img6.jpeg)


**Displaying** **Axis** **Labels** **for** **LineAnnotation**

[`VerticalLineAnnotation`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.VerticalLineAnnotation.html) and [`HorizontalLineAnnotation`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.HorizontalLineAnnotation.html) also displays the axis labels in which the line is placed. This feature can be enabled by setting [`ShowAxisLabel`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.StraightLineAnnotation.html#Syncfusion_UI_Xaml_Charts_StraightLineAnnotation_ShowAxisLabel) property to true as in the below code snippet.

{% highlight xaml %}

<syncfusion:SfChart.Annotations>

<syncfusion:HorizontalLineAnnotation X1="-0.5" X2="3.5"

Stroke="DarkGray"

StrokeThickness="1"

ShowAxisLabel="True"

Fill="LightGray"                                                      

Y1="1500" >                    

</syncfusion:HorizontalLineAnnotation>

<syncfusion:VerticalLineAnnotation  Stroke="DarkGray" 

StrokeThickness="1"                                                    

ShowAxisLabel="True"

X1="1.5" >

</syncfusion:VerticalLineAnnotation>

</syncfusion:SfChart.Annotations>

{% endhighlight %}

![Displaying axis label for line annotation in UWP Chart](Annotation_images/Annotation_img7.jpeg)


**AxisLabelTemplate**

You can also customize the default appearance of the axis label using [`AxisLabelTemplate`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.StraightLineAnnotation.html#Syncfusion_UI_Xaml_Charts_StraightLineAnnotation_AxisLabelTemplate) property as in the below code snippet.

{% highlight xaml %}

<syncfusion:SfChart.Annotations>

<syncfusion:HorizontalLineAnnotation X1="-0.5" X2="3.5"

Stroke="DarkGray"

StrokeThickness="1"                                                     

ShowAxisLabel="True"                                                                                                       

Y1="1500" >  

<syncfusion:HorizontalLineAnnotation.AxisLabelTemplate>

<DataTemplate>

<Border BorderBrush="DarkGray" 

BorderThickness="1" CornerRadius="5" 

Background="LightGray">

<TextBlock Foreground="Black" 

FontSize="11"

Text="{Binding}">                                    

</TextBlock>

</Border>

</DataTemplate>

</syncfusion:HorizontalLineAnnotation.AxisLabelTemplate>

</syncfusion:HorizontalLineAnnotation>

</syncfusion:SfChart.Annotations>

{% endhighlight %}

![Customizing axis label in UWP Chart](Annotation_images/Annotation_img8.jpeg)


**Adding** **Arrow** **to** **LineAnnotation**

To display single headed arrow you can modify the line annotation by setting [`LineCap`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.LineAnnotation.html#Syncfusion_UI_Xaml_Charts_LineAnnotation_LineCap) property to [`Arrow`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.LineCap.html). By default the [`LineCap`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.LineAnnotation.html#Syncfusion_UI_Xaml_Charts_LineAnnotation_LineCap) property value in none.

![Arrow support for line annotation in UWP Chart](Annotation_images/Annotation_img9.jpeg)

### Adding Text in ShapeAnnotation

For all the annotations like Text, Shape, Image and Line, you can display the text for the annotation using Text property as in the below code snippet.

{% highlight xaml %}

<syncfusion:SfChart.Annotations>

<syncfusion:EllipseAnnotation  X1="2.5" Y1="1500" 

Fill="LightBlue" Text="Annotation"                                               

X2="3.6" Y2="1680" >

</syncfusion:EllipseAnnotation>

</syncfusion:SfChart.Annotations>

{% endhighlight %}

![Customizing text for shape annotation in UWP Chart](Annotation_images/Annotation_img10.jpeg)


### Aligning Text in ShapeAnnotation

The text alignment can be changed using [`HorizontalTextAlignment`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_HorizontalTextAlignment) and [`VerticalTextAlignment`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_VerticalTextAlignment) properties. 

**EllipseAnnotation**

{% highlight xaml %}

<syncfusion:SfChart.Annotations>

<syncfusion:EllipseAnnotation  X1="2.5" Y1="1500" 

HorizontalTextAlignment="Center"

VerticalTextAlignment="Center"

Fill="LightBlue" Text="Annotation"                                               

X2="3.6" Y2="1680" >

</syncfusion:EllipseAnnotation>

</syncfusion:SfChart.Annotations>

{% endhighlight %}

![Alignment support for the text of shape annotation in UWP Chart](Annotation_images/Annotation_img11.jpeg)


**Line** **Annotation**

{% highlight xaml %}

<syncfusion:SfChart.Annotations>

<syncfusion:HorizontalLineAnnotation Text="Line Annotation" 

X1="2" X2="3.5"

Stroke="Black"

StrokeThickness="1"

HorizontalTextAlignment="Center" 

VerticalTextAlignment="Bottom"

Y1="1500" >                    

</syncfusion:HorizontalLineAnnotation>

</syncfusion:SfChart.Annotations>

{% endhighlight %}

![Alignment support for the text of shape annotation in UWP Chart](Annotation_images/Annotation_img12.jpeg)


**Image** **Annotation**

{% highlight xaml %}

<syncfusion:SfChart.Annotations>

<syncfusion:ImageAnnotation  Text="Annotation" 

HorizontalTextAlignment="Center"

VerticalTextAlignment="Top"

ImageSource="Images\Graduate.png"

X1="2.5" Y1="1200" X2="3.6" Y2="1700" >                    

</syncfusion:ImageAnnotation>            

</syncfusion:SfChart.Annotations>

{% endhighlight %}

![Alignment support for the text of shape annotation in UWP Chart](Annotation_images/Annotation_img13.jpeg)

N> [`HorizontalTextAlignment`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_HorizontalTextAlignment) and [`VerticalTextAlignment`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_VerticalTextAlignment) properties are not applicable for [`TextAnnotation`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.TextAnnotation.html).

### Customization of ShapeAnnotation

SfChart allows customization of shape annotation using the following properties.

* [`Stroke`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_Stroke) - Represents the brush for the annotation outline.
* [`StrokeThickness`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_StrokeThickness)- Represents the thickness of the annotation outline.
* [`StrokeDashArray`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_StrokeDashArray)- Represents the DashArray of the annotation stroke.
* [`StrokeDashCap`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_StrokeDashCap)- Represents the DashCap of the annotation stroke.
* [`StrokeDashOffset`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_StrokeDashOffset)- Represents the DashOffset of the annotation stroke.
* [`StrokeStartLineCap`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_StrokeStartLineCap)- Represents the start line cap of the annotation stroke.
* [`StrokeEndLineCap`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_StrokeEndLineCap)- Represents the end line cap of the annotation stroke.
* [`StrokeLineJoin`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_StrokeLineJoin) - Represents the line join of the annotation outline.
* [`StrokeMiterLimit`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_StrokeMiterLimit) - Represents the limit on the ratio of the miter length to half of the annotation shape.

{% highlight xaml %}

<syncfusion:SfChart.Annotations>

<syncfusion:HorizontalLineAnnotation X1="-0.5" X2="3.5"

Stroke="DarkGray"

StrokeThickness="3"

HorizontalTextAlignment="Center" 

VerticalTextAlignment="Bottom"

Fill="LightGray" 

StrokeDashArray="1,1"                                                                                       

StrokeStartLineCap="Square"

StrokeEndLineCap="Square"

StrokeDashCap="Round"

StrokeDashOffset="1.5"

Y1="1500" >                    

</syncfusion:HorizontalLineAnnotation>

</syncfusion:SfChart.Annotations>

{% endhighlight %}

![Shape annotations customization support in UWP Chart](Annotation_images/Annotation_img14.jpeg)


## Image Annotation

[`SfChart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html) provides support to add images as Annotation over the chart area, using the class [ImageAnnotation](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ImageAnnotation.html). 

The following API’s are used in ImageAnnotation

* [`Angle`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ImageAnnotation.html#Syncfusion_UI_Xaml_Charts_ImageAnnotation_Angle)  – An integer value that represents the rotation angle for the text in Annotation.
* [`ImageSource`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ImageAnnotation.html#Syncfusion_UI_Xaml_Charts_ImageAnnotation_ImageSource)  - Represents the source from where the image must be added.
* [`X2`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ImageAnnotation.html#Syncfusion_UI_Xaml_Charts_ImageAnnotation_X2)- Represents the X2 Coordinate of the Annotation.****
* [`Y2`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ImageAnnotation.html#Syncfusion_UI_Xaml_Charts_ImageAnnotation_Y2)- Represents the Y2 Coordinate of the Annotation.****

{% highlight xaml %}

<syncfusion:SfChart.Annotations>

<syncfusion:ImageAnnotation  CoordinateUnit="Axis"     

ImageSource="apple.png"

X1="3" Y1="1200" X2="4" Y2="1450" />

<syncfusion:ImageAnnotation  CoordinateUnit="Axis" ImageSource="Fruit-Banana-01.png"                                            

X1="2" Y1="1000" X2="3" Y2="1400"/>

<syncfusion:ImageAnnotation  CoordinateUnit="Axis" ImageSource="Fruit-Grapes.png"

HorizontalAlignment="Center"

VerticalAlignment="Center"

X1="1" Y1="1350" X2="2" Y2="1750" />

<syncfusion:ImageAnnotation  CoordinateUnit="Axis" ImageSource="Fruit-Strawberry.png"

HorizontalAlignment="Center"

VerticalAlignment="Center"

X1="0" Y1="1350" X2="1" Y2="1600" >

</syncfusion:ImageAnnotation>

</syncfusion:SfChart.Annotations>

{% endhighlight %}

![Image annotation type in UWP Chart](Annotation_images/Annotation_img15.jpeg)


**Rotating** **the** **image** **in** **ImageAnnotation**

{% highlight xaml %}

<syncfusion:SfChart.Annotations>

<syncfusion:ImageAnnotation  Angle="-90" CoordinateUnit="Axis" ImageSource="apple.png"

HorizontalAlignment="Center"

VerticalAlignment="Top"

X1="3" Y1="1300" X2="3.5" Y2="1450" />

<syncfusion:ImageAnnotation  Angle="-90" CoordinateUnit="Axis" ImageSource="Fruit-Banana-01.png"                                            

HorizontalAlignment="Center"

VerticalAlignment="Center"

X1="2" Y1="1000" X2="2.5" Y2="1400"/>

<syncfusion:ImageAnnotation   Angle="-90" CoordinateUnit="Axis" ImageSource="Fruit-Grapes.png"

HorizontalAlignment="Center"

VerticalAlignment="Center"

X1="1" Y1="1350" X2="1.5" Y2="1750" />

<syncfusion:ImageAnnotation   Angle="-90" CoordinateUnit="Axis" ImageSource="Fruit-Strawberry.png"

HorizontalAlignment="Center"

VerticalAlignment="Center"

X1="0" Y1="1350" X2="0.5" Y2="1650" >

</syncfusion:ImageAnnotation>

</syncfusion:SfChart.Annotations>

{% endhighlight %}

![Rotation support for image annotation in UWP Chart](Annotation_images/Annotation_img16.jpeg)


## Interactivity

### ToolTip

[`SfChart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html) provides support to view the tooltip when mouse hovered on the annotation. To view to tooltip you have to enable the [`ShowToolTip`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_ShowToolTip) property. By default for tooltip there is no content, you have to set the content for the tooltip in [`ToolTipContent`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_ToolTipContent) property.

The following code example demonstrates the default tooltip.

{% highlight xaml %}

<chart:SfChart.Annotations>

<syncfusion:EllipseAnnotation  X1="2.5" Y1="1500" 

Stroke="DarkGray" ToolTipContent="Annotation"                                                

Fill="LightGray" ShowToolTip="True"                                               

X2="3.6" Y2="1680">

</syncfusion:EllipseAnnotation>

</syncfusion:SfChart.Annotations>

{% endhighlight %}

![ToolTip support for annotation in UWP Chart](Annotation_images/Annotation_img17.jpeg)


**Position** **the** **Tooltip**

Tooltip can be placed top, bottom, left or right side of the cursor using [`ToolTipPlacement`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_ToolTipPlacement) property. The tooltip by default will be placed in Right. The following code example demonstrates the tooltip placed at the bottom.

{% highlight xaml %}

<syncfusion:SfChart.Annotations>

<syncfusion:EllipseAnnotation  X1="2.5" Y1="1500" 

Stroke="DarkGray" ToolTipContent="Annotation"  

ToolTipPlacement="Bottom"

Fill="LightGray" ShowToolTip="True"                                               

X2="3.6" Y2="1680" >

</syncfusion:EllipseAnnotation>

</syncfusion:SfChart.Annotations>

{% endhighlight %}

![Annotation tooltip positioning support in UWP Chart](Annotation_images/Annotation_img18.jpeg)


**ToolTipTemplate**

The default appearance of the Tooltip can be changed using [`TooltipTemplate`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_ToolTipTemplate) property as in the below code snippet.

{% highlight xaml %}

<syncfusion:SfChart.Annotations>

<syncfusion:EllipseAnnotation  X1="2.5" Y1="1500" 

Stroke="DarkGray"                                                

Fill="LightGray" ShowToolTip="True"                                                                                            

X2="3.6" Y2="1680">

<syncfusion:EllipseAnnotation.ToolTipTemplate>

<DataTemplate>

<Border CornerRadius="5" BorderBrush="DarkGray" 

BorderThickness="1">

<TextBlock FontSize="11" Text="Annotation" 

Foreground="Black">                                    

</TextBlock>

</Border>

</DataTemplate>

</syncfusion:EllipseAnnotation.ToolTipTemplate>

</syncfusion:EllipseAnnotation>

</syncfusion:SfChart.Annotations>

{% endhighlight %}

![Annotation tooltip template support in UWP Chart](Annotation_images/Annotation_img19.jpeg)


### Drag and Resize the Annotation

[`SfChart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html) provides dragging and resizing support for [`ShapeAnnotations`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html).

The following API’s are used for dragging and resizing the annotation

* [`CanDrag`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_CanDrag)- A Boolean value that allows the annotation to drag. 
* [`CanResize`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_CanResize)- A Boolean value that allows the annotation to resize. 
* [`DraggingMode`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_DraggingMode)- Represents the dragging direction for the annotation. 
* [`ResizingMode`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SolidShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_SolidShapeAnnotation_ResizingMode)- Represents the resizing direction for the annotation. 

**Dragging** **the** **Annotation**

The following code example demonstrates the dragging the rectangle annotation.

{% highlight xaml %}

<syncfusion:SfChart.Annotations>                    

<syncfusion:RectangleAnnotation  X1="0.6" CanDrag="True"                                                  

X2="2.2" Y2="1500" 

Y1="1800" 

Stroke="DarkGray"

Fill="LightGray"

Opacity="0.5">            

</syncfusion:RectangleAnnotation>

</syncfusion:SfChart.Annotations>

{% endhighlight %}

![Annotation dragging support in UWP Chart](Annotation_images/Annotation_img20.jpeg)


You can set the [`DraggingMode`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_DraggingMode) as Horizontal which will limit the annotation to be dragged only by horizontally as in the below code snippet.

{% highlight xaml %}

<syncfusion:SfChart.Annotations>                    

<syncfusion:RectangleAnnotation  X1="0.6" CanDrag="True"                                                  

X2="2.2" Y2="1500" 

Y1="1800" 

DraggingMode="Horizontal"

Stroke="DarkGray"

Fill="LightGray"

Opacity="0.5">            

</syncfusion:RectangleAnnotation>

</syncfusion:SfChart.Annotations>

{% endhighlight %}

![Dragging mode support for annotation in UWP Chart](Annotation_images/Annotation_img21.jpeg)


**Resizing** **the** **Annotation**

You can resize the annotation by enabling [`CanResize`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_CanResize) property to True as in the below code snippet.

{% highlight xaml %}

<syncfusion:SfChart.Annotations>                    

<syncfusion:RectangleAnnotation  X1="0.6" 

CanResize="True"

X2="2.2" 

Y2="1500" 

Y1="1800"                                                 

Stroke="DarkGray"

Fill="LightGray"

Opacity="0.5">            

</syncfusion:RectangleAnnotation>

</syncfusion:SfChart.Annotations>

{% endhighlight %}

![Annotation resizing support in UWP Chart](Annotation_images/Annotation_img22.jpeg)

[`ResizingMode`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SolidShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_SolidShapeAnnotation_ResizingMode) allows you to limit the resizing to a particular direction may be horizontal, vertical or both direction. The following code example demonstrates the resizing of annotation along vertical direction.

{% highlight xaml %}

<syncfusion:SfChart.Annotations>                    

<syncfusion:RectangleAnnotation  X1="0.6" 

CanResize="True"

X2="2.2" 

Y2="1500" 

ResizingMode="Vertical"

Y1="1800"                                                 

Stroke="DarkGray"

Fill="LightGray"

Opacity="0.5">            

</syncfusion:RectangleAnnotation>

</syncfusion:SfChart.Annotations>

{% endhighlight %}

![Annotation resizing mode support in UWP Chart](Annotation_images/Annotation_img23.jpeg)


## Annotation Clipping

[`SfChart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html) allows you to clip the annotation if the annotation crosses the boundary by setting [`EnableClipping`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_EnableClipping) property to True as in the below code snippet.

{% highlight xaml %}

<syncfusion:SfChart.Annotations>

<syncfusion:ImageAnnotation  HorizontalTextAlignment="Center"

VerticalTextAlignment="Top"

EnableClipping="True"

ImageSource="Images\Graduate.png"

X1="4" Y1="1200" X2="7" Y2="1700" >                    

</syncfusion:ImageAnnotation>            

</syncfusion:SfChart.Annotations>

{% endhighlight %}

The following screenshot explains that even when x value is provided out of bounds the image annotation is placed inside the chart area.

![Annotation clipping support in UWP Chart](Annotation_images/Annotation_img24.jpeg)


## Customizing Text in Annotation

The text in annotation can be customized using the following API’s

* [`FontSize`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_FontSize)– An int value that represents the font size of the annotation text.
* [`FontFamily`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_FontFamily)– Represents the font family of the annotation text.
* [`FontStyle`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_FontStyle)– Represents the font style of the annotation text.
* [`FontWeight`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_FontWeight)- Represents the font weight of the annotation text.
* [`Foreground`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_Foreground)– Represents the brush value of the annotation text color.
* [`FontStretch`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_FontStretch) - Represents the font stretch for the annotation description.
 
The following code example demonstrates the customization of annotation text.

{% highlight xaml %}

<syncfusion:SfChart.Annotations>

<syncfusion:EllipseAnnotation  X1="2.5" Y1="1500" 

Stroke="DarkGray"   

Text="Annotation"

FontSize="12" Foreground="DarkGray"

FontStyle="Italic" FontWeight="Bold"

Fill="LightGray" ShowToolTip="True"                                                                                            

X2="3.6" Y2="1680">                    

</syncfusion:EllipseAnnotation>

</syncfusion:SfChart.Annotations>

{% endhighlight %}

![Annotation text customization support in UWP Chart](Annotation_images/Annotation_img25.jpeg)

Text can also be customized by setting [`ContentTemplate`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_ContentTemplate) property as in the below code snippet.

{% highlight xaml %}

<syncfusion:SfChart.Annotations>           

<syncfusion:TextAnnotation  CoordinateUnit="Pixel"                                           

X1="266" Y1="4" >

<syncfusion:TextAnnotation.ContentTemplate>

<DataTemplate>

<Border Height="20" Width="80" BorderBrush="Black" CornerRadius="2" Background="LightGray" >

<TextBlock HorizontalAlignment="Center" VerticalAlignment="Center" 

FontFamily="Calibri (Body)"

FontWeight="SemiBold" Foreground="Black" FontSize="12" 

Text="Gold Demand" FontStyle="Italic"></TextBlock>

</Border>

</DataTemplate>

</syncfusion:TextAnnotation.ContentTemplate>

</syncfusion:TextAnnotation>

</syncfusion:SfChart.Annotations>

{% endhighlight %}

![Annotation text customization support in UWP Chart](Annotation_images/Annotation_img26.jpeg)

## Events

[`SfChart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html) provides the following events in [`Annotation`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.Annotation.html).

* [`Selected`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.Annotation.html)- Occurs when the annotation is selected.
* [`UnSelected`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.Annotation.html)- Occurs when annotation is deselected.
* [`DragStarted`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.StraightLineAnnotation.html)- Occurs at the start of the dragging.
* [`DragDelta`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.StraightLineAnnotation.html)- Occurs when the drag takes place.
* [`DragCompleted`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.StraightLineAnnotation.html)- Occurs when the dragging is completed. You can cancel the dragging by using Cancel argument.
* [`PointerPressed`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.Annotation.html) - Occurs when the pointer is pressed, while the mouse pointer is over the annotation.
* [`PointerMoved`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.Annotation.html) - Occurs when the pointer is moved, while the mouse pointer is over the annotation.
* [`PointerReleased`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.Annotation.html) - Occurs when the pointer is released, while the mouse pointer is over the annotation.
