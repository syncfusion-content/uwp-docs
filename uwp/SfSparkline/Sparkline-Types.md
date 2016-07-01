---
layout: post
title: Types of Sparkline
description: Types of Sparkline
platform: uwp
control: SfSparkline
documentation: ug
---
# Sparkline Types

## Line Sparkline

Line sparkline rendered using polyline and the following code is used to create line sparkline.

{%highlight xaml%}

<Grid.DataContext>

<local:UsersViewModel/>

</Grid.DataContext>

<Syncfusion:SfLineSparkline Interior="#4a4a4a"  

BorderBrush="DarkGray" BorderThickness="1"                 

ItemsSource="{Binding UsersList}" 

YBindingPath="NoOfUsers">

</Syncfusion:SfLineSparkline >

{%endhighlight%}

![Line Sparkline](Sparkline-Types_images/SparklineTypes_img1.jpeg)


## Column Sparkline

Column sparkline used to visualize the raw data as a rectangle and following code is used to create column sparkline.

{%highlight xaml%}

<Syncfusion:SfColumnSparkline 
	
Interior="#4a4a4a" BorderBrush="DarkGray"    

BorderThickness="1" ItemsSource="{Binding UsersList}" 

YBindingPath="NoOfUsers">

</Syncfusion:SfColumnSparkline >

{%endhighlight%}

![Column Sparkline](Sparkline-Types_images/SparklineTypes_img2.jpeg)


## Area Sparkline

An area sparkline is a line sparkline with the area between its points and the horizontal axis colored in. The following code is used to create an area sparkline. All line sparkline features are applicable for area sparklines.

{%highlight xaml%}

<Syncfusion:SfAreaSparkline  

Interior="#4a4a4a" BorderBrush="DarkGray"     

BorderThickness="1" ItemsSource="{Binding UsersList}"   

YBindingPath="NoOfUsers">

</Syncfusion:SfAreaSparkline >

{%endhighlight%}

![Area Sparkline](Sparkline-Types_images/SparklineTypes_img3.jpeg)


## Win-Loss Sparkline

A win-loss sparkline renders as column segments and shows positive, negative, and neutral values.

{%highlight xaml%}

<Syncfusion:SfWinLossSparkline Interior="#4a4a4a" BorderBrush="DarkGray"    

BorderThickness="1" 

x:Name="sparkline" ItemsSource="{Binding Match}"   

YBindingPath="Result" >

</Syncfusion:SfWinLossSparkline>

{%endhighlight%}

![WinLoss Sparkline](Sparkline-Types_images/SparklineTypes_img4.jpeg)
