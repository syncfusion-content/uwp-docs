---
layout: post
title: Getting Started with UWP Rotator control | Syncfusion
description: Learn here all about getting started with Syncfusion UWP Rotator (SfRotator) control and more.
platform: UWP
control: Rotator
documentation: ug
---

# Getting Started with UWP Rotator (SfRotator)

This section explains you the steps to configure a Rotator control in a real-time scenario and also provides a walk-through on some of the customization features available in Rotator control.

![rotator](images/rotator.png)

## Referencing Essential Studio Components in Your Solution	

After installing Essential Studio for Universal Windows Platform, all the required assemblies can be found in the installation folders, typically

{Syncfusion Installed location}\Essential Studio\syncfusionessentialstudio-version\lib

Eg: C:\Program Files (x86)\Syncfusion\Essential Studio\{{ site.releaseversion }}\lib

## Create your first Rotator in UWP

This section explains how to create a SfRotator that lets you to display image data's and navigate through them.

`SfRotator` is available in the following assembly and namespace:

`Assembly`: Syncfusion.SfRotator.UWP

`Namespace`: Syncfusion.UI.Xaml.Rotator


## How to create a simple Rotator sample

To develop an application with Rotator is simple. The following steps explain how to create and configure its properties.

## Add and Configure the Rotator

* Adding reference to Rotator.

{% highlight c# %}

	using Syncfusion.UI.Xaml.Rotator; 

{% endhighlight %}


* The following code snippet shows how to create `Rotator` using XAML


{% highlight Xaml %}		
	
	<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">
		<syncfusion:SfRotator x:Name="rotator"/>
	</Grid> 


{% endhighlight %}
 
 *The following code snippet shows how to create `Rotator` in code behind

{% highlight c# %}
	
	SfRotator rotator = new SfRotator();   
{% endhighlight %}   
 
##Creating Data Model for sample application

1.Create data object class and declare properties as shown below,

{% highlight C# %}

		 public class ImageData
    		{
        		public string Text { get; set; }
        		public string ImageURL { get; set; }
    		}
			
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
					Items = new ObservableCollection<ImageData>();
	
					Items.Add(new ImageData() { ImageURL = "ms-appx:///Assets/Agile.jpg", Text = "The Agile" });
					Items.Add(new ImageData() { ImageURL = "ms-appx:///Assets/Delphi.jpg", Text = "The Delphi" });
					Items.Add(new ImageData() { ImageURL = "ms-appx:///Assets/NancyFX.jpg", Text = "The NancyFX" });
					Items.Add(new ImageData() { ImageURL = "ms-appx:///Assets/Roslyn.jpg", Text = "The Roslyn" });
					Items.Add(new ImageData() { ImageURL = "ms-appx:///Assets/1.gif", Text = "The Spark" });
					Items.Add(new ImageData() { ImageURL = "ms-appx:///Assets/SQL.jpg", Text = "The SQL" });
					Items.Add(new ImageData() { ImageURL = "ms-appx:///Assets/T4.jpg", Text = "The T4" });
				}
	}


{% endhighlight %}

## Setting ItemsSource

SfRotator items can be populated with a collection of image data using `ItemsSource` property.

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

N> ItemTemplate property of Rotator control is used to customize the contents of rotator items.

