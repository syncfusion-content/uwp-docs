---
layout: post
title: DataBinding in UWP Charts control | Syncfusion
description: Learn all about DataBinding support in Syncfusion® UWP Charts (SfChart) control, its functionality, and more
platform: uwp
control: SfChart
documentation: ug
---

# DataBinding in UWP Charts (SfChart)

[`SfChart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html) offers [`ItemsSource`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_ItemsSource) property to bind various datasource ranges from simple collection property to complex properties.

### Binding a simple collection to the chart

{% tabs %}

{% highlight xaml %}

<syncfusion:SfChart >

<syncfusion:LineSeries

ItemsSource="{Binding Demands}"

XBindingPath="Demand"

YBindingPath="Year2010">

</syncfusion:LineSeries>

</syncfusion:SfChart>

{% endhighlight %}

{% highlight C# %}

SfChart chart = new SfChart();

LineSeries lineSeries = new LineSeries()
{

      ItemsSource = new ViewModel().Demands,

      XBindingPath = "Demand",

      YBindingPath = "Year2010",

};

chart.Series.Add(lineSeries);


public class GoldDemand

{

      public string Demand { get; set; }



      public double Year2010 { get; set; }



      public double Year2011 { get; set; }

}



public sealed partial class MainPage : Page

{

public MainPage()

{

      this.InitializeComponent();

      this.Demands = new ObservableCollection<GoldDemand>

      {

      new GoldDemand() {Demand = "Jewelry", Year2010 = 1998.0, Year2011 = 2361.2},

      new GoldDemand() {Demand = "Electronics", Year2010 = 1284.0, Year2011 = 1328.0},

      new GoldDemand() {Demand = "Research", Year2010 = 1090.5, Year2011 = 1032.0},

      new GoldDemand() {Demand = "Investment", Year2010 = 1643.0, Year2011 = 1898.0},

      new GoldDemand() {Demand = "Bank Purchases", Year2010 = 987.0, Year2011 = 887.0},



      new GoldDemand() {Demand = "Others", Year2010 = 1090.5, Year2011 = 1032.0},

      new GoldDemand() {Demand = "Investment", Year2010 = 1643.0, Year2011 = 1898.0},

      new GoldDemand() {Demand = "Bank Purchases", Year2010 = 987.0, Year2011 = 887.0},



      new GoldDemand() {Demand = "Electronics", Year2010 = 1284.0, Year2011 = 1328.0},

      new GoldDemand() {Demand = "Research", Year2010 = 1090.5, Year2011 = 1032.0},

      new GoldDemand() {Demand = "Investment", Year2010 = 1643.0, Year2011 = 1898.0},

      new GoldDemand() {Demand = "Bank Purchases", Year2010 = 987.0, Year2011 = 887.0}

      };



      DataContext = this;

}

public ObservableCollection<GoldDemand> Demands { get; set; }  }

{% endhighlight %}

{% endtabs %}


### Binding complex property to the chart

The complex property binding feature enables you to access nested object reference property values to render the chart segment. 

{% tabs %}

{% highlight xaml %}

<syncfusion:LineSeries ItemsSource="{Binding  DataWithMultipleData}" XBindingPath="StadiumObject.CupDetailsObj.CupName" YBindingPath="StadiumObject.NumberSeats" /> 

{% endhighlight %}

{% highlight C# %}

SfChart chart = new SfChart();

StadiumDetails stadiumDetails = new StadiumDetails();

LineSeries series = new LineSeries()
{

      ItemsSource = new ViewModel().DataWithMultipleData,

      XBindingPath = "stadiumDetails.CupDetailsObj.CupName",

      YBindingPath = "stadiumDetails.NumberSeats",

      Interior = new SolidColorBrush(Color.FromRgb(0xBC, 0xBC, 0xBC))

};

chart.Series.Add(series);

public class StadiumDetails

{

      public string PlaceName { get; set; }

      public int NumberSeats { get; set; }

      public int Price { get; set; }

      public CupDetails CupDetailsObj { get; set; }

}



public class CupDetails

{

      public string CupName { get; set; }

}

public class DataPointWithMultipleData

{

      public string Name { get; set; }

      public StadiumDetails StadiumObject { get; set; }

}

{% endhighlight %}

{% endtabs %}

### Binding array property to the chart

The [`SfChart`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SfChart.html) supports array values for the [`XBindingPath`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_XBindingPath) and [`YBindingPath`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.XYDataSeries.html#Syncfusion_UI_Xaml_Charts_XyDataSeries_YBindingPath). [`XBindingPath`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_XBindingPath) and [`YBindingPath`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.XYDataSeries.html#Syncfusion_UI_Xaml_Charts_XyDataSeries_YBindingPath) are bound with the property name in the corresponding index value. You can bind the same property with different index values.

The following code example demonstrates how to bind the array values for the [`XBindingPath`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_XBindingPath) and [`YBindingPath`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.XYDataSeries.html#Syncfusion_UI_Xaml_Charts_XyDataSeries_YBindingPath).

{% tabs %}

{% highlight xaml %}

<chart:SfChart>

      <chart:ColumnSeries x:Name="series" ItemsSource="{Binding Brands}"

                          XBindingPath="Brand[1]" YBindingPath="Count[0]" >

      </chart:ColumnSeries>

</chart:SfChart>


{% endhighlight %}

{% highlight C# %}

public class Model

{

      public string[] Brand { get; set; }

      public double[] Count { get; set; }

}

public class ViewModel

{

   public ViewModel()

   {

      Brands = new ObservableCollection<Model>();

      Brands.Add(new Model() { Brand = new string[] { "Reebok", "Adidas" }, Count 

= new  double[] { 34, 23 } });

      Brands.Add(new Model() { Brand = new string[] { "Benz", "Audi" }, Count 

=  new double[] { 50, 20 } });

      Brands.Add(new Model() { Brand = new string[] { "iPhone", "Nokia" }, Count 

= new double[] { 24, 30 } });

      Brands.Add(new Model() { Brand = new string[] { "Lenovo", "Acer" }, Count 

= new double[] { 38, 23 } });

      Brands.Add(new Model() { Brand = new string[] { "Fastrack", "Titan" },Count 

= new double[] { 27, 29 } });

   }

   public ObservableCollection<Model> Brands { get; set; }

}

private void CreateChart()

{

   ViewModel view = new ViewModel();

   SfChart chart = new SfChart();

   ColumnSeries series = new ColumnSeries();

   series.ItemsSource = view.Brands;

   series.XBindingPath = "Brand[1]";

   series.YBindingPath = "Count[0]";

   chart.Series.Add(series);

   grid.Children.Add(chart);

}


{% endhighlight %}


{% endtabs %}

### Listening Property Changes

You can notify the [`XBindingPath`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_XBindingPath) and [`YBindingPath`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.XYDataSeries.html#Syncfusion_UI_Xaml_Charts_XyDataSeries_YBindingPath) properties changes by setting [`ListenPropertyChange`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_ListenPropertyChange) as true as shown in the below code snippet.

{% tabs %}

{% highlight xaml %}

<chart:ScatterSeries ScatterWidth="20" ScatterHeight="20"  Label="Coal" ListenPropertyChange="True"

ItemsSource="{Binding EnergyProductions}" Interior="#BCBCBC"

XBindingPath="ID" YBindingPath="Coal">

</chart:ScatterSeries>

{% endhighlight %}

{% highlight c# %}


      
      public partial class MainWindow : Window
      {
     
     
            public MainWindow()
            {
                  InitializeComponent();
            }

            private void Button_Click_1(object sender, RoutedEventArgs e)
            {
                  // When you click on the button, the changes to XBindingPath and YBindingPath are updated in the output
                  viewmodel.EnergyProductions[1].ID = "1001";
                  viewmodel.EnergyProductions[1].Coal = 500;
            }
      }


      public class Model : INotifyPropertyChanged
      {
            private string id;
            public string ID
            {
                  get
                  {
                        return id;
                  }
                  set
                  {
                        id = value;
                        OnPropertyChanged(nameof(ID));
                  }
            }

            private string coal;
            public string Coal
            {
                  get
                  {
                        return coal;
                  }
                  set
                  {
                        coal = value;
                        OnPropertyChanged(nameof(Coal));
                  }
            }

            public event PropertyChangedEventHandler PropertyChanged;

            private void OnPropertyChanged(string propertyName)
            {
                  if (PropertyChanged != null)
                  {
                        PropertyChanged(this, new PropertyChangedEventArgs(propertyName));
                  }
            }
      }


{% endhighlight %}

{% endtabs %}

Also, when enabling this property of the series, you need to implement INotifyPropertyChanged in the underlying business model class to make the chart listen to the property changes of your data object.

N>By default, the property change was disabled. So the dynamic updates will not get reflect in chart. You need to enable this property.

