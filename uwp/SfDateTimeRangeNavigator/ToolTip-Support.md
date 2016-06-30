---
layout: post
title: ToolTip Support 
description: Tooltip Support
platform: uwp
control: SfDateTimeRangeNavigator
documentation: ug
---
# ToolTip Support

DateTimeRangeNavigator control provides ToolTip support for Sliders. Sliders are used to select a particular region of data in the DateTimeRangeNavigator control. ToolTips for sliders show the selected start and end date time values. You can even view exact date values to the precision of milliseconds.

The following properties are used to customize the ToolTip settings for the DateTimeRangeNavigator control.

* [`ShowToolTip`](http://help.syncfusion.com/cr/cref_files/uwp/sfchart/frlrfSyncfusionUIXamlChartsSfDateTimeRangeNavigatorClassShowToolTipTopic.html#)- Gets or sets to show ToolTip.
* [`ToolTipLabelFormat`](http://help.syncfusion.com/cr/cref_files/uwp/sfchart/frlrfSyncfusionUIXamlChartsSfDateTimeRangeNavigatorClassToolTipLabelFormatTopic.html#)-Gets or sets label format for ToolTip.
* [`LeftToolTipTemplate`](http://help.syncfusion.com/cr/cref_files/uwp/sfchart/frlrfSyncfusionUIXamlChartsSfDateTimeRangeNavigatorClassLeftToolTipTemplateTopic.html#)-Gets or sets template for the left side ToolTip.
* [`RightToolTipTemplate`](http://help.syncfusion.com/cr/cref_files/uwp/sfchart/frlrfSyncfusionUIXamlChartsSfDateTimeRangeNavigatorClassRightToolTipTemplateTopic.html#)- Gets or sets template for the right side ToolTip.

Default tool tip template of SfDateTimeRangeNavigator.

![](ToolTip-Support_images/ToolTipSupport_img1.jpeg)


The following code illustrates the customization of tool tip.

{% highlight xaml %}

<chart:SfDateTimeRangeNavigator x:Name="RangeNavigator" Width="700" Height="179"                                      

ItemsSource="{Binding StockPriceDetails}"

ShowToolTip="True" 

ToolTipLabelFormat="yyyy/MMM/dd"  

XBindingPath="Date" >

<chart:SfDateTimeRangeNavigator.LeftToolTipTemplate>

<DataTemplate>                     

<Border BorderBrush="Black" BorderThickness="0.5" Background="SeaGreen"  Width="100" Height="30" CornerRadius="10">

<TextBlock Width="90" VerticalAlignment="Center" HorizontalAlignment="Center" FontSize="15" Foreground="White" Text="{Binding}">

</TextBlock>

</Border>                     

</DataTemplate>

</chart:SfDateTimeRangeNavigator.LeftToolTipTemplate>

<chart:SfDateTimeRangeNavigator.RightToolTipTemplate>

<DataTemplate>

<Border BorderThickness="0.5" BorderBrush="Black" Background="SeaGreen"  Width="100" Height="30" CornerRadius="10">

<TextBlock Width="90" VerticalAlignment="Center" HorizontalAlignment="Center" FontSize="15" Foreground="White" Text="{Binding}">

</TextBlock>

</Border>

</DataTemplate>

</chart:SfDateTimeRangeNavigator.RightToolTipTemplate>

</chart:SfDateTimeRangeNavigator>

{% endhighlight %}

![](ToolTip-Support_images/ToolTipSupport_img2.jpeg)


