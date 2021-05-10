---
layout: post
title: Customization in UWP Range Selector control | Syncfusion
description: Learn here all about Customization support in Syncfusion UWP Range Selector (SfDateTimeRangeNavigator) control and more.
platform: uwp
control: SfDateTimeRangeNavigator
documentation: ug
---
# Customization in UWP Range Selector (SfDateTimeRangeNavigator)

## Higher Level Bar Customization

Higher level bar style can be customized using the following properties.

* [`HigherBarGridLineStyle`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfDateTimeRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfDateTimeRangeNavigator_HigherBarGridLineStyle)- Gets or sets the style for upper bar gridlines.

{% tabs %}

{% highlight xaml %}

<Grid.Resources>

    <Style TargetType="Line" x:Key="lineStyle">

        <Setter Property="Stroke" Value="Red"></Setter>

        <Setter Property="StrokeThickness" Value="2"></Setter>

    </Style>

</Grid.Resources>

<syncfusion:SfDateTimeRangeNavigator HigherBarGridLineStyle="{StaticResource lineStyle}"/>

{% endhighlight %}

{% highlight c# %}

SfDateTimeRangeNavigator rangeNavigator = new SfDateTimeRangeNavigator()
{

    HigherBarGridLineStyle = grid.Resources["barStyle"] as Style

};

{% endhighlight %}

{% endtabs %}

![Higher LevelBar Tick Customization](Customization_images/Customization_img1.jpeg)


* [`HigherBarTickLineStyle`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfDateTimeRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfDateTimeRangeNavigator_HigherBarTickLineStyle)- Gets or sets the style for ticklines inside the upper bar.

{% tabs %}

{% highlight xaml %}

<Grid.Resources>

    <Style TargetType="Line" x:Key="lineStyle">

        <Setter Property="Stroke" Value="Red"></Setter>

        <Setter Property="StrokeThickness" Value="2"></Setter>

    </Style>

</Grid.Resources>

<syncfusion:SfDateTimeRangeNavigator HigherBarGridLineStyle="{StaticResource lineStyle}"/>

{% endhighlight %}

{% highlight c# %}

SfDateTimeRangeNavigator rangeNavigator = new SfDateTimeRangeNavigator()
{

    HigherBarTickLineStyle = grid.Resources["barTickStyle"] as Style

};

{% endhighlight %}

{% endtabs %}

![HigherBarTickLineStyle](Customization_images/Customization_img2.jpeg)


* [`HigherLevelBarStyle`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfDateTimeRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfDateTimeRangeNavigator_HigherLevelBarStyle)- Gets or sets the styles for the higher label bar of SfDateTimeRangeNavigator.
* [`HigherLabelStyle`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfDateTimeRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfDateTimeRangeNavigator_HigherLabelStyle)- Gets or sets the higher label style.
* [`SelectedLabelStyle`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.LabelBarStyle.html#Syncfusion_UI_Xaml_Charts_LabelBarStyle_SelectedLabelStyle)- Gets or sets the style for labels in the selected region.
* [`Position`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.LabelBarStyle.html#Syncfusion_UI_Xaml_Charts_LabelBarStyle_Position)- Gets or sets position value which is used to position the upper and lower labels inside or outside. 
* [`SelectedLabelBrush`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.LabelBarStyle.html#Syncfusion_UI_Xaml_Charts_LabelBarStyle_SelectedLabelBrush) – Gets or sets the color of the labels inside the selected region.
* [`LabelHorizontalAlignment`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.LabelBarStyle.html#Syncfusion_UI_Xaml_Charts_LabelBarStyle_LabelHorizontalAlignment)- An attached property of LabelBarStyle, used to align the labels in level bar.
* [`Background`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.LabelBarStyle.html#Syncfusion_UI_Xaml_Charts_LabelBarStyle_Background) – Gets or sets the Background the label bar. 

{% tabs %}

{% highlight xaml %}

<Grid.Resources>

    <Style TargetType="TextBlock" x:Key="labelStyle1">

        <Setter Property="Foreground" Value="White"></Setter>

        <Setter Property="FontStyle" Value="Normal"  ></Setter>

        <Setter Property="FontWeight" Value="Bold"></Setter>

    </Style>

    <Style TargetType="TextBlock" x:Key="labelStyle2">

        <Setter Property="Foreground" Value="Cyan"></Setter>

        <Setter Property="FontStyle" Value="Italic"  ></Setter>

        <Setter Property="FontWeight" Value="Bold"></Setter>

    </Style>

</Grid.Resources>

<chart:SfDateTimeRangeNavigator HigherLabelStyle="{StaticResource labelStyle2}">

    <chart:SfDateTimeRangeNavigator.HigherLevelBarStyle>

        <chart:LabelBarStyle Background="Green" Position="Outside"

                             SelectedLabelBrush="White"

                             LabelHorizontalAlignment="Center"

                            SelectedLabelStyle="{StaticResource labelStyle1}">

        </chart:LabelBarStyle>

    </chart:SfDateTimeRangeNavigator.HigherLevelBarStyle>

</chart:SfDateTimeRangeNavigator>

{% endhighlight %}

{% highlight c# %}

LabelBarStyle barStyle = new LabelBarStyle()
{

    LabelHorizontalAlignment = HorizontalAlignment.Left,

    Background = new SolidColorBrush(Colors.Green),

    Position = BarPosition.Outside,

    SelectedLabelBrush = new SolidColorBrush(Colors.White),

    SelectedLabelStyle = grid.Resources["labelStyle1"] as Style

};

SfDateTimeRangeNavigator rangeNavigator = new SfDateTimeRangeNavigator()
{

    HigherLabelStyle = labelStyle2,

    HigherLevelBarStyle = labelStyle1

};

{% endhighlight %}

{% endtabs %}

The following output is displayed as the result of above code.

![SelectedLabelStyle](Customization_images/Customization_img3.jpeg)


## Lower Level Bar Customization

Lower level bar style can be customized using the following properties.

* [`LowerBarGridLineStyle`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfDateTimeRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfDateTimeRangeNavigator_LowerBarGridLineStyle)- Gets or sets the style for lower bar gridlines.

{% tabs %}

{% highlight xaml %}

<chart:SfDateTimeRangeNavigator.LowerBarGridLineStyle>

 <Grid.Resources>

    <Style TargetType="Line" x:Key="lowerBarStyle">

        <Setter Property="Stroke" Value="Red"></Setter>

        <Setter Property="StrokeThickness" Value="2"></Setter>

    </Style>

</Grid.Resources>

<chart:SfDateTimeRangeNavigator LowerBarGridLineStyle="{StaticResource lowerBarStyle}"/>

{% endhighlight %}

{% highlight c# %}

SfDateTimeRangeNavigator rangeNavigator = new SfDateTimeRangeNavigator()
{

    LowerBarGridLineStyle = grid.Resources["lowerBarStyle"] as Style

};

{% endhighlight %}

{% endtabs %}

![LowerBarGridLineStyle](Customization_images/Customization_img4.jpeg)


* [`LowerBarTickLineStyle`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfDateTimeRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfDateTimeRangeNavigator_LowerBarTickLineStyle)- Gets or sets the style for ticklines in lower bar.

{% tabs %}

{% highlight xaml %}

 <Grid.Resources>

    <Style TargetType="Line" x:Key="lowerBarStyle">

        <Setter Property="Stroke" Value="Red"></Setter>

        <Setter Property="StrokeThickness" Value="2"></Setter>

    </Style>

</Grid.Resources>

<chart:SfDateTimeRangeNavigator LowerBarTickLineStyle="{StaticResource lowerBarStyle}"/>

{% endhighlight %}

{% highlight c# %}

SfDateTimeRangeNavigator rangeNavigator = new SfDateTimeRangeNavigator()
{

    LowerBarTickLineStyle = grid.Resources["lowerBarStyle"] as Style

};

{% endhighlight %}

{% endtabs %}

![LowerBarTickLineStyle](Customization_images/Customization_img5.jpeg)


* [`Minimum`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfDateTimeRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfDateTimeRangeNavigator_Minimum)- Gets or sets the Minimum Starting Range of the SfDateTimeRangeNavigator.
* [`Maximum`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfDateTimeRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfDateTimeRangeNavigator_Maximum)- Gets or sets the Maximum Ending Range of the SfDateTimeRangeNavigator.

{% tabs %}

{% highlight xaml %}

<chart:SfDateTimeRangeNavigator x:Name="RangeNavigator" Width="700" 

                                Height="179"   

                                Minimum="February,2015"

                                Maximum="March,2015"                                  

                                XBindingPath="Date"> 

 </chart:SfDateTimeRangeNavigator>                 

{% endhighlight %}

{% highlight c# %}

SfDateTimeRangeNavigator rangeNavigator = new SfDateTimeRangeNavigator()
{

    ItemsSource = new ViewModel().StockPriceDetails,

    XBindingPath = "Date",

    ViewRangeStart = new DateTime(2015,02,01),

    ViewRangeEnd = new DateTime(2015, 03, 01)

};

{% endhighlight %}

{% endtabs %}

![Customization of SfDateTimeRangeNavigator in UWP](Customization_images/Customization_img6.jpeg)


* [`LowerLevelBarStyle`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfDateTimeRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfDateTimeRangeNavigator_LowerLevelBarStyle)- Gets or sets the styles for the lower label bar of SfDateTimeRangeNavigator.
* [`LowerLabelStyle`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfDateTimeRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfDateTimeRangeNavigator_LowerLabelStyle) – Gets or sets the lower label style.

{% tabs %}

{% highlight xaml %}

<Grid.Resources>

    <Style TargetType="TextBlock" x:Key="labelStyle1">

        <Setter Property="Foreground" Value="White"></Setter>

        <Setter Property="FontStyle" Value="Normal"  ></Setter>

        <Setter Property="FontWeight" Value="Bold"></Setter>

    </Style>

    <Style TargetType="TextBlock" x:Key="labelStyle1">

        <Setter Property="Foreground" Value="Cyan"></Setter>

        <Setter Property="FontStyle" Value="Italic" ></Setter>

        <Setter Property="FontWeight" Value="Bold"></Setter>

    </Style>

</Grid.Resources>

<chart:SfDateTimeRangeNavigator LowerLabelStyle="{StaticResource labelStyle2}">

    <chart:SfDateTimeRangeNavigator.LowerLevelBarStyle>

        <chart:LabelBarStyle Background="Green" Position="Outside"

                             SelectedLabelBrush="White"

                             LabelHorizontalAlignment="Center"

                             SelectedLabelStyle="{StaticResource labelStyle1}"/>

    </chart:SfDateTimeRangeNavigator.LowerLevelBarStyle>

</chart:SfDateTimeRangeNavigator>

{% endhighlight %}

{% highlight c# %}

LabelBarStyle barStyle = new LabelBarStyle()
{

    LabelHorizontalAlignment = HorizontalAlignment.Center,

    Background = new SolidColorBrush(Colors.Green),

    Position = BarPosition.Outside,

    SelectedLabelBrush = new SolidColorBrush(Colors.White),

    SelectedLabelStyle = grid.Resources["labelStyle1"] as Style

};


SfDateTimeRangeNavigator rangeNavigator = new SfDateTimeRangeNavigator()
{

    LowerLevelBarStyle = barStyle,

    LowerLabelStyle = grid.Resources["labelStyle2"] as Style

};

{% endhighlight %}

{% endtabs %}

![LowerLabelStyle](Customization_images/Customization_img7.jpeg)

### Visibility of label bar 
 
SfDateTimeRangeNavigator provides support to customize the visibility of lower bar and upper bar using the `LowerLabelBarVisibility` and `UpperLabelBarVisibility` types.

## Thumb Style Customization

SfDateTimeRangeNavigator provides the following properties to customize the left and right thumb.

* [`LeftThumbStyle`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfDateTimeRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfDateTimeRangeNavigator_LeftThumbStyle)- Gets or sets the thumb style for left thumb.
* [`RightThumbStyle`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfDateTimeRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfDateTimeRangeNavigator_RightThumbStyle)- Gets or sets the right thumb style.
* [`SymbolTemplate`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ThumbStyle.html#Syncfusion_UI_Xaml_Charts_ThumbStyle_SymbolTemplate)- Gets or sets the data template for the symbol.

{% tabs %}

{% highlight xaml %}

<Grid x:Name="grid">

     <Grid.Resources>

        <DataTemplate x:Key="symbolTemplate1">

            <Grid>

                <Border Name="outerBorder" Background="#2a52be"   
                        
                        Height="26" Width="26" Opacity="1"
                            
                        BorderThickness="2" CornerRadius="4"/>

                <Border Name="innerBorder"
                            
                        Background="#e6e6fa" Width="10"                                
                    
                        Height="10" CornerRadius="1" Opacity="1" />

            </Grid>

        </DataTemplate>

        <DataTemplate x:Key="symbolTemplate2">

            <Grid>

                 <Border Name="outerBorder"
                            
                         Background="#2a52be" Height="26"                                 
                            
                         Width="26" Opacity="1" BorderThickness="2" 
                            
                         CornerRadius="4"/>

                <Border Name="innerBorder"
                            
                        Background="#e6e6fa" Height="10"
                            
                        Width="10" CornerRadius="1" Opacity="1" />

            </Grid>

        </DataTemplate>

 </Grid.Resources>

<syncfusion:SfDateTimeRangeNavigator>

        <syncfusion:SfDateTimeRangeNavigator.RightThumbStyle>

            <syncfusion:ThumbStyle SymbolTemplate="{StaticResource symbolTemplate1}"/>

        </syncfusion:SfDateTimeRangeNavigator.RightThumbStyle>

        <syncfusion:SfDateTimeRangeNavigator.LeftThumbStyle>

                <syncfusion:ThumbStyle SymbolTemplate="{StaticResource symbolTemplate2}"/>
            
        </syncfusion:SfDateTimeRangeNavigator.LeftThumbStyle>
            
</syncfusion:SfDateTimeRangeNavigator>
        
</Grid>

{% endhighlight %}

{% highlight c# %}

ThumbStyle thumbStyle1 = new ThumbStyle()
{

    SymbolTemplate = grid.Resources["symbolTemplate1"] as DataTemplate

};

ThumbStyle thumbStyle2 = new ThumbStyle()
{

    SymbolTemplate = grid.Resources["symbolTemplate2"] as DataTemplate

};

SfDateTimeRangeNavigator rangeNavigator = new SfDateTimeRangeNavigator()
{

    ItemsSource = new ViewModel().StockPriceDetails,

    XBindingPath = "Date",

    RightThumbStyle = thumbStyle1,

    LeftThumbStyle = thumbStyle2

};

{% endhighlight %}

{% endtabs %}

![LeftThumbStyle](Customization_images/Customization_img8.jpeg)


* [`LineStyle`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ThumbStyle.html#Syncfusion_UI_Xaml_Charts_ThumbStyle_LineStyle)- Gets or sets the style for the thumb line.

{% tabs %}

{% highlight xaml %}

<Grid x:Name="grid">

<Grid.Resources>

    <Style TargetType="Line" x:Key="lineStyle1">

        <Setter Property="Stroke" Value="Red"></Setter>

        <Setter Property="StrokeThickness" Value="3"></Setter>

        <Setter Property="StrokeDashArray" Value="2,1"></Setter>

    </Style>

    <Style TargetType="Line" x:Key="lineStyle2">

        <Setter Property="Stroke" Value="Red"></Setter>

        <Setter Property="StrokeThickness" Value="3"></Setter>

        <Setter Property="StrokeDashArray" Value="2,1"></Setter>

    </Style>

</Grid.Resources>

<syncfusion:SfDateTimeRangeNavigator>

    <syncfusion:SfDateTimeRangeNavigator.LeftThumbStyle>

        <syncfusion:ThumbStyle LineStyle="{StaticResource lineStyle1}"/>

     </syncfusion:SfDateTimeRangeNavigator.LeftThumbStyle>

    <syncfusion:SfDateTimeRangeNavigator.RightThumbStyle>

        <syncfusion:ThumbStyle LineStyle="{StaticResource lineStyle2}"/>

    </syncfusion:SfDateTimeRangeNavigator.RightThumbStyle>

</syncfusion:SfDateTimeRangeNavigator>

</Grid>

{% endhighlight %}

{% highlight c# %}

ThumbStyle thumbStyle1 = new ThumbStyle()
{

    SymbolTemplate = grid.Resources["symbolTemplate1"] as DataTemplate

};

ThumbStyle thumbStyle2 = new ThumbStyle()
{

    SymbolTemplate = grid.Resources["symbolTemplate2"] as DataTemplate

};

SfDateTimeRangeNavigator rangeNavigator = new SfDateTimeRangeNavigator()
{

    ItemsSource = new ViewModel().StockPriceDetails,

    XBindingPath = "Date",

    RightThumbStyle = thumbStyle1,

    LeftThumbStyle = thumbStyle2

};

{% endhighlight %}

{% endtabs %}

![RightThumbStyle](Customization_images/Customization_img9.jpeg)


## Label Customization

User can also set the Interval which they think suitable for their data, this can be done by using Interval Property and can also set format to the labels.

* [`Intervals`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfDateTimeRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfDateTimeRangeNavigator_Intervals)- Gets or sets intervals collection to render labels of SfDateTimeRangeNavigator.

{% tabs %}

{% highlight xaml %}

<chart:SfDateTimeRangeNavigator x:Name="RangeNavigator" Width="700" Height="179" 

ItemsSource="{Binding StockPriceDetails}"                                          

XBindingPath="Date">

<chart:SfDateTimeRangeNavigator.Intervals>

<chart:Interval x:Name="interval1" 

IntervalType="Month"></chart:Interval>

<chart:Interval x:Name="interval2" 

IntervalType="Week"></chart:Interval>   

</chart:SfDateTimeRangeNavigator.Intervals>

<chart:SfDateTimeRangeNavigator.Content >

<chart:SfLineSparkline ItemsSource="{Binding StockPriceDetails}" 

YBindingPath="High" >

</chart:SfLineSparkline>

</chart:SfDateTimeRangeNavigator.Content>

</chart:SfDateTimeRangeNavigator>   

{% endhighlight %}

{% highlight c# %}

SfLineSparkline sparkline = new SfLineSparkline()
{
    
    ItemsSource = new ViewModel().StockPriceDetails,

    XBindingPath = "Date",

    YBindingPath = "High"

};

SfDateTimeRangeNavigator rangeNavigator = new SfDateTimeRangeNavigator()
{

    ItemsSource = new ViewModel().StockPriceDetails,

    XBindingPath ="Date"

};

rangeNavigator.Intervals.Add(new Interval() { IntervalType = NavigatorIntervalType.Month });

rangeNavigator.Intervals.Add(new Interval() { IntervalType = NavigatorIntervalType.Week });

rangeNavigator.Content = sparkline;

{% endhighlight %}

{% endtabs %}

![Label Customization](Customization_images/Customization_img10.jpeg)


* [`LabelFormatters`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.Interval.html#Syncfusion_UI_Xaml_Charts_Interval_LabelFormatters) - Gets or sets string collection to set the label format for the navigator labels.

The following code illustrates how to set label format.

{% highlight c# %}

interval1.LabelFormatters = new ObservableCollection<string>(); interval1.LabelFormatters.Add("MMMM,yyyy");    
interval2.LabelFormatters = new ObservableCollection<string>(); interval2.LabelFormatters.Add("ddd");

{% endhighlight %}

* [`IntervalType`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.Interval.html#Syncfusion_UI_Xaml_Charts_Interval_IntervalType)- Gets or sets interval type in which the navigator values should be displayed.

Interval has the following types:

* [`Year`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.NavigatorIntervalType.html)
* [`Quarter`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.NavigatorIntervalType.html)
* [`Month`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.NavigatorIntervalType.html)
* [`Week`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.NavigatorIntervalType.html)
* [`Day`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.NavigatorIntervalType.html)
* [`Hour`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.NavigatorIntervalType.html)

The auto timespan format simplifies the visual representation of data while zooming.

