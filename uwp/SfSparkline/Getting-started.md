---
layout: post
title: Getting started for Sparkline
description: Getting started for Sparkline
platform: uwp
control: SfSparkline
documentation: ug
---

# Getting Started

The following section helps you to build your application with SfChart.

## Create a simple sparkline from XAML

### Adding assembly reference

1. Open the Add Reference window from your project.
2. Choose Windows > Extensions > SyncfusionControls for UWP XAML.

![Reference Manager Dialog Windows in Visual Studio](Getting-started_images/GettingStarted_img1a.jpeg)

Add the following namespace in your XAML window.

{% highlight xaml %}
xmlns:syncfusion="using:Syncfusion.UI.Xaml.Charts"
{% endhighlight %}
 
### Add Sparkline from Toolbox

Drag and drop the Sparkline controls from the Toolbox to your application.

![Visual Studio Toolbox](Getting-started_images/GettingStarted_img1.jpeg)

Now the Syncfusion.SfChart.UWP reference is added to the application references and the xmlns namespace code is generated in MainWindow.xaml as below.

![Project Solution Window contains SfChart reference](Getting-started_images/GettingStarted_img2.jpeg)

![Added xmlns:syncfusion="clr-namespace:Syncfusion.UI.Xaml.Charts" in MainWindow](Getting-started_images/GettingStarted_img3.jpeg)

### Initialize the Sparkline

You need to initialize the sparkline represented by the following class of Syncfusion.UI.Xaml.Charts.SfChart,

{%highlight xaml%}

<chart:SfLineSparkline >  

</chart:SfLineSparkline>

{%endhighlight%}
 
### Create a data source

Since the above step will produce only an empty sparkline, we need to add some data to the sparkline for plotting. In this step, let’s create a sample data source.
 
{% highlight C#%}

public class UserProfile

 {

   public DateTime TimeStamp { get; set; }

   public double NoOfUsers { get; set; }

 } 

public class UsersViewModel

 {

 public UsersViewModel()

  {

   this.UsersList = new ObservableCollection<UserProfile>();

   DateTime date = DateTime.Today;

   UsersList.Add(new UserProfile { TimeStamp = date.AddHours(0.5), NoOfUsers = 3000 });

   UsersList.Add(new UserProfile { TimeStamp = date.AddHours(0.5), NoOfUsers = 5000 });

   UsersList.Add(new UserProfile { TimeStamp = date.AddHours(0.5), NoOfUsers = -3000 });

   UsersList.Add(new UserProfile { TimeStamp = date.AddHours(0.5), NoOfUsers = -4000 });

   UsersList.Add(new UserProfile { TimeStamp = date.AddHours(0.5), NoOfUsers = 2000 });

   UsersList.Add(new UserProfile { TimeStamp = date.AddHours(0.5), NoOfUsers = 3000 });  }

 public ObservableCollection<UserProfile> UsersList

  {

    get; set;

  }

 }

{%endhighlight%}

### Applying data to Sparkline
 
We need to add the above UsersViewModel to the DataContext of the sparkline, bind the data source to the ItemsSource property of the SfLineSparkline, and then map the data using YBindingPath .

{%highlight xaml%}

<Grid>

<Grid.DataContext>

<local:UsersViewModel/>

</Grid.DataContext>  
     
<chart:SfLineSparkline  Interior="#4a4a4a" BorderThickness="1" 
                        ItemsSource="{Binding UsersList}" BorderBrush="DarkGray"
                        YBindingPath="NoOfUsers" >                
</chart:SfLineSparkline> 
       
</Grid>

{%endhighlight%}

![Simple SfLineSparkline](Getting-started_images/GettingStarted_img4.jpeg)


## Create a simple sparkline from Code behind(C#/VB)

Some developers prefer code behind as the first approach for development, to create things dynamically. This section helps you create to sparkline from code behind.

### Add Assembly reference

1. Open the Add Reference window from your project.
2. Choose Windows > Extensions > SyncfusionControls for UWP XAML.
3. Add the following namespace in code behind

{% tabs %}

{% highlight c# %}

using Syncfusion.UI.Xaml.Charts;

{% endhighlight  %}

{% highlight vb %}

Imports Syncfusion.UI.Xaml.Charts

{% endhighlight  %}

{% endtabs %}

### Initializing SparkLine

You need to create the instance for the Sparkline as below.

{% tabs %}

{% highlight c# %}

SfLineSparkline linespark = new SfLineSparkline();

{% endhighlight  %}

{% highlight vb %}

Dim linespark As New SfLineSparkline()

{% endhighlight  %}

{% endtabs %}

### Create a data source

Since the above step will produce only an empty sparkline, we need to add some data to the sparkline for plotting. In this step, let’s create a sample data source.
 
{% highlight C#%}

public class UserProfile

 {

   public DateTime TimeStamp { get; set; }

   public double NoOfUsers { get; set; }

 } 

public class UsersViewModel

 {

 public UsersViewModel()

  {

   this.UsersList = new ObservableCollection<UserProfile>();

   DateTime date = DateTime.Today;

   UsersList.Add(new UserProfile { TimeStamp = date.AddHours(0.5), NoOfUsers = 3000 });

   UsersList.Add(new UserProfile { TimeStamp = date.AddHours(0.5), NoOfUsers = 5000 });

   UsersList.Add(new UserProfile { TimeStamp = date.AddHours(0.5), NoOfUsers = -3000 });

   UsersList.Add(new UserProfile { TimeStamp = date.AddHours(0.5), NoOfUsers = -4000 });

   UsersList.Add(new UserProfile { TimeStamp = date.AddHours(0.5), NoOfUsers = 2000 });

   UsersList.Add(new UserProfile { TimeStamp = date.AddHours(0.5), NoOfUsers = 3000 });  }

 public ObservableCollection<UserProfile> UsersList

  {

    get; set;

  }

 }

{%endhighlight%}

### Applying data to Sparkline 

After you have added the sparkline, you need to add ItemSource and YBindingPath APIs, to populate your data in the chart.

 {%highlight C#%}

UsersViewModel viewmodel = new UsersViewModel();
linespark.ItemsSource = viewmodel.UsersList;
linespark.YBindingPath = "NoOfUsers";

{%endhighlight%}
 
The following code example gives the complete set of code for creating sparkline in code behind

{%highlight C#%}

//creating object for viewmodel

UsersViewModel viewmodel = new UsersViewModel();

//assinging the data context for the chart

this.DataContext = viewmodel;

//intializing sparkline

SfLineSparkline linespark = new SfLineSparkline();

//setting itemsource and binding path 

linespark.ItemsSource = viewmodel.UsersList;

linespark.YBindingPath = "NoOfUsers";

//sparkline is customizied by setting the below properties

Color color = (Color)ColorConverter.ConvertFromString("#4a4a4a");

linespark.Interior = new SolidColorBrush(color);

linespark.BorderBrush = new SolidColorBrush(Colors.DarkGray);

linespark.BorderThickness = new Thickness(1);

//adding sparkline to grid

grid.Children.Add(linespark);

{%endhighlight%}

![Simple SfLineSparkline](Getting-started_images/GettingStarted_img4.jpeg)
