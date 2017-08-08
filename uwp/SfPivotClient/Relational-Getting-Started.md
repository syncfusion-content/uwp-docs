---
layout: post
title: Relational Getting Started with SfPivotClient control for UWP
description: Relational Getting Started with SfPivotClient control for UWP
platform: uwp
control: SfPivotClient
documentation: ug
---

# Getting Started  

This section covers the information required to create a simple SfPivotClient control bound to Relational data source such as IList, IEnumerable.etc.,

### Control Initialization

SfPivotClient control can be initialized and added to an application through the following ways:

1. Through designer
2. Through XAML
3. Through code-behind

## Adding Control through Designer

Open Visual Studio IDE and navigating to *File > New > Project > Universal > Blank APP(Universal Windows)* under Windows option inside the Visual C# Templates to create a new UWP application.

N> Once the UWP application is created, select **"Properties"** under the project shown in Solution Explorer and change the Target Version of the application as **"Windows 10 (10.0; Build 10240)".**

Now select Toolbox options from View menu and it will appear inside the VisualStudio IDE. From the toolbox select SfPivotClient control under “Syncfusion Controls for UWP XAML” group, then drag and drop it into the designer section of MainPage.xaml file.

Finally name the added SfPivotClient control as “PivotClient1” in MainPage.xaml to refer it in code-behind as follows:

{% highlight xaml %}

<PivotClient:SfPivotClient x:Name="PivotClient1"/>

{% endhighlight %}

## Adding Control through XAML

Open Visual Studio IDE and navigating to *File > New > Project > Universal > Blank APP(Universal Windows)* under Windows option inside the Visual C# Templates to create a new UWP application.

Then name the project as "SfPivotClientDemo" while creating the application to access the project later.

In order to add SfPivotClient control manually in XAML, the following assembly references must be added into the project.
	
 * Syncfusion.SfPivotClient.UWP
 * Syncfusion.SfPivotGrid.UWP
 * Syncfusion.SfPivotChart.UWP
 * Syncfusion.SfPivotGridConverter.UWP
 * Syncfusion.SfPivotChartConverter.UWP
 * Syncfusion.SfPivotShared.UWP
 * Syncfusion.Olap.UWP
 * Syncfusion.PivotAnalysis.UWP
 * Syncfusion.Data.UWP
 * Syncfusion.SfCellGrid.UWP
 * Syncfusion.SfGrid.UWP
 * Syncfusion.SfGridCommon.UWP
 * Syncfusion.SfShared.UWP
 * Syncfusion.SfInput.UWP
 * Syncfusion.SfBusyIndicator.UWP
 * Syncfusion.SfChart.UWP
 * Syncfusion.SfColorPickers.UWP
 * Syncfusion.SfTabControl.UWP

You can find these libraries under following location.

&lt;Installed Drive&gt;:\Program Files (x86)\Syncfusion\Essential Studio\\&lt;Version&gt;\Assemblies for Universal Windows\10.0\

Or else, the SfPivotClient control can be added to the project by choosing SDK reference as follows:

Right click on **References** and select *Add Reference > Universal Windows > Extensions > Syncfusion Controls for UWP XAML*. 
 
Now add the following namespace in MainPage.xaml file.

{% highlight xaml %}

xmlns:syncfusion="using:Syncfusion.UI.Xaml.PivotClient"

{% endhighlight %}

Then initialize the SfPivotClient control inside the Grid by using the specified namespace and name the control as “PivotClient1”.

{% highlight xaml %}

<Page
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:local="using:SfPivotClientDemo"
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
    x:Class="SfPivotClientDemo.MainPage"
    xmlns:syncfusion="using:Syncfusion.UI.Xaml.PivotClient"
    mc:Ignorable="d">

    <Grid Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">
        <syncfusion:SfPivotClient x:Name="PivotClient1"/>
    </Grid>
</Page>

{% endhighlight %}

## Adding Control through Code-Behind

Open Visual Studio IDE and navigating to *File > New > Project > Universal > Blank APP(Universal Windows)* under Windows option inside the Visual C# Templates to create a new UWP application.

Then name the project as "SfPivotClientDemo" while creating the application to access the project later.

In order to add SfPivotClient control manually in code-behind, the following assembly references must be added into the project.

 * Syncfusion.SfPivotClient.UWP
 * Syncfusion.SfPivotGrid.UWP
 * Syncfusion.SfPivotChart.UWP
 * Syncfusion.SfPivotGridConverter.UWP
 * Syncfusion.SfPivotChartConverter.UWP
 * Syncfusion.SfPivotShared.UWP
 * Syncfusion.Olap.UWP
 * Syncfusion.PivotAnalysis.UWP
 * Syncfusion.Data.UWP
 * Syncfusion.SfCellGrid.UWP
 * Syncfusion.SfGrid.UWP
 * Syncfusion.SfGridCommon.UWP
 * Syncfusion.SfShared.UWP
 * Syncfusion.SfInput.UWP
 * Syncfusion.SfBusyIndicator.UWP
 * Syncfusion.SfChart.UWP
 * Syncfusion.SfColorPickers.UWP
 * Syncfusion.SfTabControl.UWP

You can find these libraries under the following location.

&lt;Installed Drive&gt;:\Program Files (x86)\Syncfusion\Essential Studio\\&lt;Version&gt;\Assemblies for Universal Windows\10.0

Or else, the SfPivotClient control can be added to the project by choosing SDK reference as follows:

Right click on **References** and select *Add Reference > Universal Windows > Extensions > Syncfusion Controls for UWP XAML*.

Now open the MainPage.xaml file and include name for the Grid as “Root_Grid” to refer it in code-behind.

{% highlight xaml %}

<Page
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:local="using:SfPivotClientDemo"
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
    x:Class="SfPivotClientDemo.MainPage"
    mc:Ignorable="d">

    <Grid Background="{ThemeResource ApplicationPageBackgroundThemeBrush}" x:Name="Root_Grid">
    </Grid>
</Page>

{% endhighlight %}

Add the namespace - "Syncfusion.UI.Xaml.PivotClient" in MainPage.xaml.cs file. Then initialize the SfPivotClient control and add it into the parent Grid as follows.

{% highlight c# %}

using Windows.UI.Xaml.Controls;
using Syncfusion.UI.Xaml.PivotClient;

namespace SfPivotClientDemo
{
    /// <summary>
    /// An empty page that can be used on its own or navigated to within a Frame.
    /// </summary>
    public sealed partial class MainPage : Page
    {
        public MainPage()
        {
            this.InitializeComponent();
            SfPivotClient PivotClient = new SfPivotClient();
            PivotClient.Name = "PivotClient1";
            Root_Grid.Children.Add(PivotClient);
        }
    }
}

{% endhighlight %}

## Adding Relational data source to SfPivotClient Control

Right-click on the project in the solution explorer and select *Add -> New Folder* and then name the folder as **"Model"**.

Then create a new class file by right-click on the project in the solution explorer and select *Add -> New Item -> Class*. In "Add New Item" window, provide the name of the class as ProductSales.cs and click **OK**.

The ItemSource for the SfPivotClient control will be initialized in this file. Please refer the below code sample.

{% highlight c# %}

public class ProductSales
{
    /// <summary>
    /// Gets or sets the product values from item source.
    /// </summary>
    public string Product { get; set; }
    /// <summary>
    /// Gets or sets the date values from item source.
    /// </summary>
    public string Date { get; set; }
    /// <summary>
    /// Gets or sets the country values from item source.
    /// </summary>
    public string Country { get; set; }
    /// <summary>
    /// Gets or sets the state values from item source.
    /// </summary>
    public string State { get; set; }
    /// <summary>
    /// Gets or sets the quantity values from item source.
    /// </summary>
    public int Quantity { get; set; }
    /// <summary>
    /// Gets or sets the amount values from item source.
    /// </summary>
    public double Amount { get; set; }
    /// <summary>
    /// Returns the collection of objects from item source.
    /// </summary>
    /// <returns></returns>
    public static ProductSalesCollection GetSalesData()
    {
      /// Geography
      string[] countries = new string[] { "Australia", "Canada", "France", "Germany", "United States" };
      string[] ausStates = new string[] { "New South Wales", "Queensland", "South Australia", "Tasmania", "Victoria" };
      string[] canadaStates = new string[] { "Alberta", "British Columbia", "Brunswick", "Manitoba", "Ontario", "Quebec" };
      string[] franceStates = new string[] { "Charente-Maritime", "Essonne", "Garonne (Haute)", "Gers", };
      string[] germanyStates = new string[] { "Bayern", "Brandenburg", "Hamburg", "Hessen", "Nordrhein-Westfalen", "Saarland" };
      string[] ukStates = new string[] { "England" };
      string[] ussStates = new string[] { "New York", "North Carolina", "Alabama", "California", "Colorado", "New Mexico", "South Carolina" };

      /// Time
      string[] dates = new string[] { "FY 2005", "FY 2006", "FY 2007", "FY 2008", "FY 2009" };

      /// Products
      string[] products = new string[] { "Bike", "Car" };
      Random r = new Random(123345345);

      int numberOfRecords = 2000;
      ProductSalesCollection listOfProductSales = new ProductSalesCollection();
      for (int i = 0; i < numberOfRecords; i++)
      {
        ProductSales sales = new ProductSales();
        sales.Country = countries[r.Next(1, countries.GetLength(0))];
        sales.Quantity = r.Next(1, 12);
        /// 1 percent discount for 1 quantity
        double discount = (sales.Quantity) * (double.Parse(sales.Quantity.ToString()) / 100);
        sales.Amount = (sales.Quantity) - discount;
        sales.Date = dates[r.Next(r.Next(dates.GetLength(0) + 1))];
        sales.Product = products[r.Next(r.Next(products.GetLength(0) + 1))];

        switch (sales.Country)
        {
          case "Australia":
          {
           sales.State = ausStates[r.Next(ausStates.GetLength(0))];
           break;
          }
         case "Canada":
          {
           sales.State = canadaStates[r.Next(canadaStates.GetLength(0))];
           break;
          }
         case "France":
          {
           sales.State = franceStates[r.Next(franceStates.GetLength(0))];
           break;
          }
         case "Germany":
          {
           sales.State = germanyStates[r.Next(germanyStates.GetLength(0))];
           break;
          }
         case "United States":
          {
           sales.State = ussStates[r.Next(ussStates.GetLength(0))];
           break;
          }
        }
       listOfProductSales.Add(sales);
      }

     return listOfProductSales;
    }

    public class ProductSalesCollection : List<ProductSales>
    {
    }
}
    
{% endhighlight %}

Above mentioned GetSalesData method is used to get the collection that needs to be populated in the SfPivotClient control. Now we need to bind the collection to the SfPivotClient control as its ItemSource. It can be done through XAML or code-behind.

Right-click on the project in the solution explorer and select *Add -> New Folder* and then name the folder as **"ViewModel"**.

Then create a new class file by right-click on the project in the solution explorer and select *Add -> New Item -> Class*. In "Add New Item" window, provide the name of the class as ViewModel.cs and click **OK**.

The ItemSource for the SfPivotClient control will be defined in this file. Please refer the below code sample.

{% highlight c# %}

public class ViewModel
{

    #region Private Fields

    /// <summary>
    /// Gets or sets the item source for SfPivotClient control.
    /// </summary>
    private object productSalesData;

    #endregion

    #region Public Properties

    public object ProductSalesData
    {
      get
      {
       this.productSalesData = this.productSalesData ?? Model.ProductSales.GetSalesData();
       return this.productSalesData;
      }
      set { this.productSalesData = value; }
    }     
    #endregion    
}
    
{% endhighlight %}

### Binding ItemSource, defining PivotItems and PivotComputations to SfPivotClient through XAML

If you need to initialize the ItemSource through XAML, DataContext is used. Please refer the following code.

{% highlight xaml %}

<Page
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:local="using:SfPivotClientDemo"
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
    xmlns:pivots="using:Syncfusion.PivotAnalysis.UWP"
    xmlns:viewModel="using:SfPivotClientDemo.ViewModel"
    x:Class="SfPivotClientDemo.MainPage"
    xmlns:syncfusion="using:Syncfusion.UI.Xaml.PivotClient"
    mc:Ignorable="d">

    <Grid Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">
      <Grid.DataContext>
             <viewModel:ViewModel/>
        </Grid.DataContext>
        <syncfusion:SfPivotClient x:Name="PivotClient1" ItemsSource="{Binding ProductSalesData}">
         <syncfusion:SfPivotClient.PivotRows>
            <pivots:PivotItem FieldCaption="Product" FieldMappingName="Product" TotalHeader="Total"/>
            <pivots:PivotItem FieldCaption="Date" FieldMappingName="Date" TotalHeader="Total"/>
         </syncfusion:SfPivotClient.PivotRows>
         <syncfusion:SfPivotClient.PivotColumns>
            <pivots:PivotItem FieldCaption="Country" FieldMappingName="Country" TotalHeader="Total"/>
         </syncfusion:SfPivotClient.PivotColumns>
         <syncfusion:SfPivotClient.PivotCalculations>
            <pivots:PivotComputationInfo FieldCaption="Amount" FieldName="Amount" Format="C" SummaryType="DoubleTotalSum"/>
            <pivots:PivotComputationInfo FieldCaption="Quantity" FieldName="Quantity" Format="#,##" SummaryType="Count"/>
         </syncfusion:SfPivotClient.PivotCalculations>
         </syncfusion:SfPivotClient>
    </Grid>
</Page>

{% endhighlight %}

### Binding ItemSource, defining PivotItems and PivotComputations to SfPivotClient through code-behind

If you need to initialize the ItemSource through code-behind, please refer the below code snippet.

{% highlight c# %}

using Windows.UI.Xaml.Controls;
using Syncfusion.PivotAnalysis.UWP;
using Syncfusion.UI.Xaml.PivotClient;

namespace SfPivotClientDemo
{
    /// <summary>
    /// An empty page that can be used on its own or navigated to within a Frame.
    /// </summary>
    public sealed partial class MainPage : Page
    {
        public MainPage()
        {
            this.InitializeComponent();
            SfPivotClient pivotClient = new SfPivotClient();
            pivotClient.Name = "PivotClient1";
            Root_Grid.Children.Add(PivotClient);
            pivotClient.ItemsSource = ProductSales.GetSalesData()
            // Adding PivotRows to the Control
            pivotClient.PivotRows.Add(new Syncfusion.PivotAnalysis.UWP.PivotItem { FieldMappingName = "Product", TotalHeader = "Total" });
            pivotClient.PivotRows.Add(new Syncfusion.PivotAnalysis.UWP.PivotItem { FieldMappingName = "Date", TotalHeader = "Total" });

            // Adding PivotColumns to the Control
            pivotClient.PivotColumns.Add(new Syncfusion.PivotAnalysis.UWP.PivotItem { FieldMappingName = "Country", TotalHeader = "Total" });

            // Adding PivotCalculations to the Control
            pivotClient.PivotCalculations.Add(new PivotComputationInfo { FieldName = "Amount", Format = "C", SummaryType = SummaryType.DoubleTotalSum });
            pivotClient.PivotCalculations.Add(new PivotComputationInfo { FieldName = "Quantity", Format = "#,##", SummaryType = SummaryType.Count });
        }
    }
}

{% endhighlight %}

**Run** the application, the following output will be generated.

![](GettingStarted_images/Relational.png) 