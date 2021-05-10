---
layout: post
title: Sparkline Types in UWP Sparkline control | Syncfusion
description: Learn here all about Sparkline Types support in Syncfusion UWP Sparkline (SfSparkline) control and more.
platform: uwp
control: SfSparkline
documentation: ug
---
# Sparkline Types in UWP Sparkline (SfSparkline)

## Line Sparkline

Line sparkline rendered using polyline and the following code is used to create line sparkline.

{% tabs %}

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

{% highlight c# %}

SfLineSparkline sparkline = new SfLineSparkline()
{

	ItemsSource = new SparkViewModel().UsersList,

	YBindingPath = "NoOfUsers"

};

{% endhighlight %}

{% endtabs %}

![Line Sparkline](Sparkline-Types_images/SparklineTypes_img1.jpeg)


## Column Sparkline

Column sparkline used to visualize the raw data as a rectangle and following code is used to create column sparkline.

{% tabs %}

{%highlight xaml%}

<Syncfusion:SfColumnSparkline 
	
Interior="#4a4a4a" BorderBrush="DarkGray"    

BorderThickness="1" ItemsSource="{Binding UsersList}" 

YBindingPath="NoOfUsers">

</Syncfusion:SfColumnSparkline >

{%endhighlight%}

{% highlight c# %}

SfColumnSparkline sparkline = new SfColumnSparkline()
{

	ItemsSource = new SparkViewModel().UsersList,

	YBindingPath = "NoOfUsers"

};

{% endhighlight %}

{% endtabs %}

![Column Sparkline](Sparkline-Types_images/SparklineTypes_img2.jpeg)


## Area Sparkline

An area sparkline is a line sparkline with the area between its points and the horizontal axis colored in. The following code is used to create an area sparkline. All line sparkline features are applicable for area sparklines.

{% tabs %}

{%highlight xaml%}

<Syncfusion:SfAreaSparkline  

Interior="#4a4a4a" BorderBrush="DarkGray"     

BorderThickness="1" ItemsSource="{Binding UsersList}"   

YBindingPath="NoOfUsers">

</Syncfusion:SfAreaSparkline >

{%endhighlight%}

{% highlight c# %}

SfAreaSparkline sparkline = new SfAreaSparkline()
{

	ItemsSource = new SparkViewModel().UsersList,

	YBindingPath = "NoOfUsers"

};

{% endhighlight %}

{% endtabs %}

![Area Sparkline](Sparkline-Types_images/SparklineTypes_img3.jpeg)


## Win-Loss Sparkline

A win-loss sparkline renders as column segments and shows positive, negative, and neutral values.

{% tabs %}

{%highlight xaml%}

<Syncfusion:SfWinLossSparkline Interior="#4a4a4a" BorderBrush="DarkGray"    

BorderThickness="1" 

x:Name="sparkline" ItemsSource="{Binding Match}"   

YBindingPath="Result" >

</Syncfusion:SfWinLossSparkline>

{%endhighlight%}

{% highlight c# %}

SfWinLossSparkline sparkline = new SfWinLossSparkline()
{

	ItemsSource = new SparkViewModel().Match,

	YBindingPath = "Result"

};

{% endhighlight %}

{% endtabs %}

![WinLoss Sparkline](Sparkline-Types_images/SparklineTypes_img4.jpeg)
