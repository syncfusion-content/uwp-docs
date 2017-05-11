---
layout: post
title: Marker Customization
description: Marker Customization
platform: uwp
control: SfSparkline
documentation: ug
---
# Marker Customization

We can customize the markers by initializing the marker template selector class, and we can differentiate the first, last, high, low, negative points.

* [`FirstPointBrush`](http://help.syncfusion.com/cr/cref_files/uwp/sfchart/index.html#frlrfSyncfusionUIXamlChartsSegmentTemplateSelectorClassFirstPointBrushTopic.html) – Gets or sets the brush to paint the first point of the sparkline.
* [`LastPointBrush`](http://help.syncfusion.com/cr/cref_files/uwp/sfchart/frlrfSyncfusionUIXamlChartsSegmentTemplateSelectorClassLastPointBrushTopic.html) – Gets or sets the brush to paint the last point of the sparkline.
* [`LowPointBrush`](http://help.syncfusion.com/cr/cref_files/uwp/sfchart/frlrfSyncfusionUIXamlChartsSegmentTemplateSelectorClassLowPointBrushTopic.html) – Gets or sets the brush to paint the low point of the sparkline.
* [`HighPointBrush`](http://help.syncfusion.com/cr/cref_files/uwp/sfchart/index.html#frlrfSyncfusionUIXamlChartsSegmentTemplateSelectorClassHighPointBrushTopic.html) – Gets or sets the brush to paint the high point of the sparkline.
* [`NegativePointBrush`](http://help.syncfusion.com/cr/cref_files/uwp/sfchart/frlrfSyncfusionUIXamlChartsSegmentTemplateSelectorClassNegativePointBrushTopic.html) – Gets or sets the brush to paint the negative point of the sparkline.
* [`MarkerHeight`](http://help.syncfusion.com/cr/cref_files/uwp/sfchart/frlrfSyncfusionUIXamlChartsMarkerTemplateSelectorClassMarkerHeightTopic.html) – Gets or sets the height of the marker.
* [`MarkerWidth`](http://help.syncfusion.com/cr/cref_files/uwp/sfchart/frlrfSyncfusionUIXamlChartsMarkerTemplateSelectorClassMarkerWidthTopic.html) – Gets or sets the width of the marker.
* [`MarkerBrush`](http://help.syncfusion.com/cr/cref_files/uwp/sfchart/frlrfSyncfusionUIXamlChartsMarkerTemplateSelectorClassMarkerBrushTopic.html) – Gets or sets the brush to paint the markers of the sparkline.
* [`MarkerTemplate`](http://help.syncfusion.com/cr/cref_files/uwp/sfchart/frlrfSyncfusionUIXamlChartsMarkerTemplateSelectorClassMarkerTemplateTopic.html) – Gets or sets the data template to sparkline marker.

{% tabs %}

{% highlight xaml %}

<Syncfusion:SfLineSparkline  Interior="#4a4a4a" 
                                         
                             BorderBrush="DarkGray"
                                    
                             MarkerVisibility="Visible"   
                                         
                             BorderThickness="1" 
                                         
                             ItemsSource="{Binding UsersList}"    
                                         
                             YBindingPath="NoOfUsers">

<Syncfusion:SfLineSparkline.MarkerTemplateSelector>

<Syncfusion:MarkerTemplateSelector  FirstPointBrush="Yellow"

                                    LastPointBrush="Green"

                                    LowPointBrush="Red"

                                    MarkerHeight="15"

                                    MarkerWidth="15"

                                    MarkerBrush="DeepSkyBlue"

                                    NegativePointBrush="Blue"

                                    HighPointBrush="Purple">

</Syncfusion:MarkerTemplateSelector>

</Syncfusion:SfLineSparkline.MarkerTemplateSelector>

</Syncfusion:SfLineSparkline >

{% endhighlight %}

{% highlight c# %}

SfLineSparkline sparkline = new SfLineSparkline()
{

	ItemsSource = new SparkViewModel().Data,

	YBindingPath = "Day",

	MarkerVisibility = Visibility.Visible,

	Interior = new SolidColorBrush(Colors.Gray),

    BorderBrush = new SolidColorBrush(Colors.DarkGray),

    BorderThickness = new Thickness(1)

};

SegmentTemplateSelector selector = new SegmentTemplateSelector()
{

	FirstPointBrush = new SolidColorBrush(Colors.Yellow),

	LastPointBrush = new SolidColorBrush(Colors.Yellow),

	HighPointBrush = new SolidColorBrush(Colors.Red),

	MarkerHeight = 15,

    MarkerWidth = 15,

    MarkerBrush = new SolidColorBrush(Colors.DeepSkyBlue),

    NegativePointBrush = new SolidColorBrush(Colors.Blue),

    HighPointBrush = new SolidColorBrush(Colors.Purple),

};

sparkline.MarkerTemplateSelector = selector;

{% endhighlight %}

{% endtabs %}


![Marker Customization](Marker-Customization_images/MarkerCustomization_img1.jpeg)


**Marker Template**

You can customize default appearence of the marker symbol by using the MarkerTemplate property in the sparkline.

{% tabs %}

{% highlight xaml %}

<Grid.Resources>

    <DataTemplate x:Key="markerTemplate">

        <Grid>

            <Ellipse Height="15" Width="15" 
                                             
                     Fill="LightGoldenrodYellow"
                                             
                     Stroke="Black" StrokeDashArray="1,1" 
                                             
                     StrokeThickness="1" />

            <Ellipse Height="12" Width="12" Fill="Blue" Stroke="Black"   
                                             
                     StrokeDashArray="1,1" 
                                             
                     StrokeThickness="1"/>

        </Grid>

    </DataTemplate>
            
</Grid.Resources>

<Syncfusion:SfLineSparkline Interior="#4a4a4a"  

                            BorderBrush="DarkGray"
                                        
                            MarkerVisibility="Visible"   

                            BorderThickness="1"
                                        
                            ItemsSource="{Binding UsersList}"  

                            YBindingPath="NoOfUsers">

        <Syncfusion:SfLineSparkline.MarkerTemplateSelector>

                <Syncfusion:MarkerTemplateSelector MarkerTemplate="{StaticResource markerTemplate}"/>

         </Syncfusion:SfLineSparkline.MarkerTemplateSelector>

</Syncfusion:SfLineSparkline>

{% endhighlight %}

{% highlight c# %}

SfLineSparkline sparkline = new SfLineSparkline()
{

	ItemsSource = new SparkViewModel().Data,

	YBindingPath = "Day",

	MarkerVisibility = Visibility.Visible,

	Interior =new SolidColorBrush(Colors.Gray),

	BorderBrush = new SolidColorBrush(Colors.DarkGray),

	BorderThickness = new Thickness (1)

};

MarkerTemplateSelector selector = new MarkerTemplateSelector()
{

	MarkerTemplate = grid.Resources["markerTemplate"] as DataTemplate

};

sparkline.MarkerTemplateSelector = selector;

{% endhighlight %}

{% endtabs %}

![MarkerTemplate](Marker-Customization_images/MarkerCustomization_img2.jpeg)


