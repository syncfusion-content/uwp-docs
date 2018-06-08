---
layout: post
title: LoadMore 
description: Handle numerous item in SfCarousel using LoadMore
platform: uwp
control: SfCarousel
documentation: ug
---

# LoadMore

Virtualization can be achieved by using the Load more concept. This support is used to handle the numerous items in the carousel control. A particular items are maintained in the view port based on the `LoadMoreItemsCount` property. The LoadMore view is added after the last item in the collection of carousel view. When tapping the LoadMore view, the next set of items in the collection can be added to the carousel.

The following properties are used to achieve this support:

*	`AllowLoadMore`

*	`LoadMoreItemsCount`

*	`LoadMoreView`

## AllowLoadMore

By enabling the `AllowLoadMore` property, the LoadMore support works in the carousel view. 

N>The default value of the `AllowLoadMore` property is false.

{% tabs %}

{% highlight xaml %}

<Page
	x:Class="LoadMoreUWP.MainPage"
	xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
	xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
	xmlns:local="using:LoadMoreUWP"
	xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
	xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
	xmlns:layout="using:Syncfusion.UI.Xaml.Controls.Layout"
	mc:Ignorable="d">

		<Page.DataContext>
		<local:CarouselViewModel/>
		</Page.DataContext>

		<Page.Resources>
			<ResourceDictionary>
				<DataTemplate x:Key="itemTemplate">
					<Image Source="{Binding Image}" 
					Height="100" 
					Width="100"/>
				</DataTemplate>
			</ResourceDictionary>
		</Page.Resources>

	<Page.Content>
		<layout:SfCarousel x:Name="carousel"
		ItemTemplate="{StaticResource itemTemplate}"
		ItemsSource="{Binding ImageCollection}"
		ItemHeight="200"
		ItemWidth="200"
		ItemSpace="2"
		AllowLoadMore="True"
		VisualMode="LinearMode">
	</layout:SfCarousel>
	</Page.Content>
</Page>

{% endhighlight %}

{% highlight c# %}

 //Enable load more in SfCarousel

carousel.AllowLoadMore = true;

{% endhighlight %}

{% endtabs %}

## LoadMoreItemsCount

Number of items can be maintained in the carousel control by using the `LoadMoreItemsCount` property. By using the `LoadMoreItemsCount` property, numerous items can be separated. 

N>The default value of the `LoadMoreItemsCount` property is 3.

{% tabs %}

{% highlight xaml %}

<Page
	x:Class="LoadMoreUWP.MainPage"
	xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
	xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
	xmlns:local="using:LoadMoreUWP"
	xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
	xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
	xmlns:layout="using:Syncfusion.UI.Xaml.Controls.Layout"
	mc:Ignorable="d">

		<Page.DataContext>
		<local:CarouselViewModel/>
		</Page.DataContext>

		<Page.Resources>
			<ResourceDictionary>
				<DataTemplate x:Key="itemTemplate">
					<Image Source="{Binding Image}" 
					Height="100" 
					Width="100"/>
				</DataTemplate>
			</ResourceDictionary>
		</Page.Resources>

	<Page.Content>
		<layout:SfCarousel x:Name="carousel"
		ItemTemplate="{StaticResource itemTemplate}"
		ItemsSource="{Binding ImageCollection}"
		ItemHeight="200"
		ItemWidth="200"
		ItemSpace="2"
		LoadMoreItemsCount="5"
		AllowLoadMore="True"
		VisualMode="LinearMode">
	</layout:SfCarousel>
	</Page.Content>
</Page>

{% endhighlight %}

{% highlight c# %}

 //Enable load more in SfCarousel

carousel.LoadMoreItemsCount = true;

{% endhighlight %}

{% endtabs %}

Custom view can be passed instead of the LoadMore label by using the `LoadMoreView` property. 

{% tabs %}

{% highlight xaml %}

<layout:SfCarousel.LoadMoreView>
	<Grid
		Background="#FFFFFFFF">
		<TextBlock
		Text="Load More..."
		FontSize="14"
		Foreground="#FF000000"
		FontWeight="Bold"
		HorizontalAlignment="Center"
		VerticalAlignment="Center"/>
	</Grid>
</layout:SfCarousel.LoadMoreView>

{% endhighlight %}

{% highlight c# %}

SfCarousel carousel = new SfCarousel();

Grid grid = new Grid();

grid.Background = new SolidColorBrush(Colors.White);

TextBlock textblock = new TextBlock();

textblock.Text = "Load More...";

textblock.FontSize = 14;

textblock.Foreground = new SolidColorBrush(Colors.Black);

textblock.HorizontalAlignment = HorizontalAlignment.Center;

textblock.VerticalAlignment = VerticalAlignment.Center;

grid.Children.Add(textblock);

carousel.LoadMoreView = grid;

{% endhighlight %}

{% endtabs %}

![](SfCarousel-images/LoadMore.png)

You can find the complete Load More sample from this [link.](http://www.syncfusion.com/downloads/support/directtrac/general/ze/LoadMoreUWP1495601504)