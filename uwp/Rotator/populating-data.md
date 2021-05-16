---
layout : post
title: Data Binding in UWP Rotator control | Syncfusion
description: Learn here all about Data Binding support in Syncfusion UWP Rotator (SfRotator) control and more.
platform : UWP
control : Rotator 
documentation : ug
---

# Data Binding in UWP Rotator (SfRotator)

## Adding RotatorItem to the control

SfRotatorItem can be populated with a collection of image data using `ItemsSource` property.

{% highlight Xaml %}

	<Page
	x:Class="Rotator.MainPage"
	xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
	xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
	xmlns:local="using:Rotator"
	xmlns:syncfusion="using:Syncfusion.UI.Xaml.Rotator">
	
	<Page.DataContext>
			<local:RotatorData/>
	</Page.DataContext>
	
	<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">
		<syncfusion:SfRotator x:Name="rotator" ItemsSource="{Binding Items}">
		<syncfusion:SfRotator.ItemTemplate>
					<DataTemplate>
						<Image Source="{Binding ImageURL}" />
					</DataTemplate>
				</syncfusion:SfRotator.ItemTemplate>
		</syncfusion:SfRotator>
	
	</Grid> 
	
	</Page>

{% endhighlight %}

{% highlight C# %}

	public class RotatorData : INotifyPropertyChanged
		{
			private ObservableCollection<ImageData> items;
			public ObservableCollection<ImageData> Items
			{
				get { return items; }
				set { items = value; }
			}
			public RotatorData()
			{
				Items = new ObservableCollection<SfRotatorItem>();

				Items.Add(new SfRotatorItem() { Content = new Button() { Height = 100, Width = 100, Content = "Hi", Background = new SolidColorBrush(Color.FromArgb(255, 200, 150, 130)), FontSize = 25 }, Text = "The Agile Succinctly" });
				Items.Add(new SfRotatorItem() { Content = new Image() { Source = new BitmapImage(new Uri("ms-appx:///Assets/Delphi.jpg", UriKind.RelativeOrAbsolute)) }, Text = "The Delphi Succinctly" });
				Items.Add(new SfRotatorItem() { Content = new Image() { Source = new BitmapImage(new Uri("ms-appx:///Assets/NancyFX.jpg", UriKind.RelativeOrAbsolute)) }, Text = "The NancyFX Succinctly" });
				Items.Add(new SfRotatorItem() { Content = new Image() { Source = new BitmapImage(new Uri("ms-appx:///Assets/Roslyn.jpg", UriKind.RelativeOrAbsolute)) }, Text = "The Roslyn Succinctly" });
				Items.Add(new SfRotatorItem() { Content = new Image() { Source = new BitmapImage(new Uri("ms-appx:///Assets/Spark.jpg", UriKind.RelativeOrAbsolute)) }, Text = "The Spark Succinctly" });
				Items.Add(new SfRotatorItem() { Content = new Image() { Source = new BitmapImage(new Uri("ms-appx:///Assets/SQL.jpg", UriKind.RelativeOrAbsolute)) }, Text = "The SQL Succinctly" });
				Items.Add(new SfRotatorItem() { Content = new Image() { Source = new BitmapImage(new Uri("ms-appx:///Assets/T4.jpg", UriKind.RelativeOrAbsolute)) }, Text = "The T4 Succinctly" });
			}
		}

{% endhighlight %}
