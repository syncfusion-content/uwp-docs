---
layout: post
title: Relational Getting Started with SfPivotGrid control for UWP
description: Relational Getting Started with SfPivotGrid control for UWP
platform: uwp
control: SfPivotGrid
documentation: ug
---

# Getting Started

This section explains the steps required to create a simple SfPivotGrid control bound to Relational data source such as IList, IEnumerable.etc.,

### Control Initialization

SfPivotGrid control can be initialized and added to an application through the following ways:

1. Through designer
2. Through XAML
3. Through code-behind

## Adding Control through Designer

Open Visual Studio IDE and navigating to *File > New > Project > Universal > Blank APP(Universal Windows)* under Windows option inside the Visual C# Templates to create a new UWP application.

N> Once the UWP application is created, select **"Properties"** under the project shown in Solution Explorer and change the Target Version of the application as **"Windows 10 (10.0; Build 10240)".**

Now select Toolbox options from View menu and it will appear inside the VisualStudio IDE. From the toolbox select SfPivotGrid control under “Syncfusion Controls for UWP XAML” group, then drag and drop it into the designer section of MainPage.xaml file.

Finally name the added SfPivotGrid control as “PivotGrid1” in MainPage.xaml to refer it in code-behind as follows:

{% highlight xaml %}

<PivotGrid:SfPivotGrid x:Name="PivotGrid1"/>

{% endhighlight %}

## Adding Control through XAML

Open Visual Studio IDE and navigating to *File > New > Project > Universal > Blank APP(Universal Windows)* under Windows option inside the Visual C# Templates to create a new UWP application.

Then, name the project as "SfPivotGridDemo" while creating the application to access the project later.

In order to add SfPivotGrid control manually in XAML, the following assembly references must be added in the project.
	
* Syncfusion.SfPivotGrid.UWP
* Syncfusion.SfCellGrid.UWP
* Syncfusion.SfGridCommon.UWP
* Syncfusion.SfShared.UWP
* Syncfusion.SfInput.UWP
* Syncfusion.SfBusyIndicator.UWP
* Syncfusion.SfColorPickers.UWP
* Syncfusion.Olap.UWP
* Syncfusion.PivotAnalysis.UWP
* Syncfusion.Data.UWP

You can find these libraries under following location.

&lt;Installed Drive&gt;:\Program Files (x86)\Syncfusion\Essential Studio\\&lt;Version&gt;\Universal Windows\10.0\SDK\References\CommonConfiguration\neutral\

Or else, the SfPivotGrid control can be added to the project by choosing SDK reference as follows:

Right click on **References** and select *Add Reference > Universal Windows > Extensions > Syncfusion Controls for UWP XAML*.

Now add the following namespace in MainPage.xaml file.

{% highlight xaml %}

xmlns:syncfusion="using:Syncfusion.UI.Xaml.PivotGrid"

{% endhighlight %}

Then initialize the SfPivotGrid control inside the Grid by using the specified namespace and name the control as “PivotGrid1”.

{% highlight xaml %}

<Page
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:local="using:SfPivotGridDemo"
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
    x:Class="SfPivotGridDemo.MainPage"
    xmlns:syncfusion="using:Syncfusion.UI.Xaml.PivotGrid"
    mc:Ignorable="d">

    <Grid Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">
        <syncfusion:SfPivotGrid x:Name="PivotGrid1"/>
    </Grid>
</Page>

{% endhighlight %}

## Adding Control through code-behind

Open Visual Studio IDE and navigating to *File > New > Project > Universal > Blank APP(Universal Windows)* under Windows option inside the Visual C# Templates to create a new UWP application.

Then, name the project as "SfPivotGridDemo" while creating the application to access the project later.

In order to add SfPivotGrid control manually in code-behind, the following assembly references must be added in the project.

* Syncfusion.SfPivotGrid.UWP
* Syncfusion.SfCellGrid.UWP
* Syncfusion.SfGridCommon.UWP
* Syncfusion.SfShared.UWP
* Syncfusion.SfInput.UWP
* Syncfusion.SfBusyIndicator.UWP
* Syncfusion.SfColorPickers.UWP
* Syncfusion.Olap.UWP
* Syncfusion.PivotAnalysis.UWP
* Syncfusion.Data.UWP

You can find these libraries under following location.

&lt;Installed Drive&gt;:\Program Files (x86)\Syncfusion\Essential Studio\\&lt;Version&gt;\Universal Windows\10.0\SDK\References\CommonConfiguration\neutral\

Or else, the SfPivotGrid control can be added to the project by choosing SDK reference as follows:

Right click on **References** and select *Add Reference > Universal Windows > Extensions > Syncfusion Controls for UWP XAML*.

Now open the MainPage.xaml file, and include name for the Grid as “Root_Grid” to refer it in code-behind.

{% highlight xaml %}

<Page
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:local="using:SfPivotGridDemo"
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
    x:Class="SfPivotGridDemo.MainPage"
    mc:Ignorable="d">

    <Grid Background="{ThemeResource ApplicationPageBackgroundThemeBrush}" x:Name="Root_Grid">
    </Grid>
</Page>

{% endhighlight %}

Next add the namespace - "Syncfusion.UI.Xaml.PivotGrid" in MainPage.xaml.cs file. Then initialize the SfPivotGrid control and assign a name for it as "PivotGrid1". Then add the control in parent Grid as follows.

{% highlight c# %}

using Windows.UI.Xaml.Controls;
using Syncfusion.UI.Xaml.PivotGrid;

namespace SfPivotGridDemo
{
    /// <summary>
    /// An empty page that can be used on its own or navigated to within a Frame.
    /// </summary>
    public sealed partial class MainPage : Page
    {
        public MainPage()
        {
            this.InitializeComponent();
            SfPivotGrid pivotGrid = new SfPivotGrid();
            pivotGrid.Name = "PivotGrid1";
            Root_Grid.Children.Add(pivotGrid);
        }
    }
}

{% endhighlight %}

## Adding Relational data source to SfPivotGrid Control

Right-click on the project in the solution explorer and select *Add -> New Folder* and then name the folder as **"ViewModel"**.

Then create a new class file by right-click on the project in the solution explorer and select *Add -> New Item -> Class*. In "Add New Item" window, provide the name of the class as ProductSales.cs and click **OK**.

The ItemSource for the SfPivotGrid control will be initialized in this file. Please refer the below code sample.

{% highlight c# %}

public class ProductSales
{
    public string Product { get; set; }
    public string Date { get; set; }
    public string Country { get; set; }
    public double Amount { get; set; }
    public static ProductSalesCollection GetSalesData()
    {
        /// Geography
        string[] countries = new string[] { "Germany", "Canada", "United States"};

        /// Time
        string[] dates = new string[] { "FY 2008", "FY 2009", "FY 2010", "FY 2012" };

        /// Products
        string[] products = new string[] { "Bike", "Car" };
        Random r = new Random(123345);

        int numberOfRecords = 1000;
        ProductSalesCollection listOfProductSales = new ProductSalesCollection();
        for (int i = 0; i < numberOfRecords; i++)
        {
            ProductSales sales = new ProductSales();
            sales.Country = countries[r.Next(1, countries.GetLength(0))];
            sales.Amount = (3000 * r.Next(1, 12));
            sales.Date = dates[r.Next(r.Next(dates.GetLength(0) + 1))];
            sales.Product = products[r.Next(r.Next(products.GetLength(0) + 1))];
            listOfProductSales.Add(sales);
        }
        return listOfProductSales;
    }

    public class ProductSalesCollection : List<ProductSales>
    {
    }
}
    
{% endhighlight %}

Above mentioned GetSalesData method is used to get the collection that needs to be populated in the SfPivotGrid control. Now we need to bind the collection to the SfPivotGrid control as its ItemSource. It can be done through XAML or code-behind.

### Binding ItemSource, defining PivotItems and PivotComputations to SfPivotGrid through XAML

If you need to initialize the ItemSource through XAML, DataContext is used. Please refer the following code.

{% highlight xaml %}

<Page
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:local="using:SfPivotGridDemo"
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
    xmlns:pivotGrid="using:Syncfusion.UI.Xaml.PivotGrid"
    xmlns:pivots="using:Syncfusion.PivotAnalysis.UWP"
    xmlns:viewModel="using:SfPivotGridDemo.ViewModel"
    x:Class="SfPivotGridDemo.MainPage"
    mc:Ignorable="d">

    <Grid Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">
        <Grid.DataContext>
             <viewModel:ProductSales/>
        </Grid.DataContext>
        <syncfusion:SfPivotGrid x:Name="PivotGrid1" ItemSource="{Binding ProductSalesData}">
         <pivotGrid:SfPivotGrid.PivotRows>
                    <pivots:PivotItem FieldCaption="Product" FieldMappingName="Product" TotalHeader="Total"/>
                    <pivots:PivotItem FieldCaption="Date" FieldMappingName="Date" TotalHeader="Total"/>
                </pivotGrid:SfPivotGrid.PivotRows>
                <pivotGrid:SfPivotGrid.PivotColumns>
                    <pivots:PivotItem FieldCaption="Country" FieldMappingName="Country" TotalHeader="Total"/>
                </pivotGrid:SfPivotGrid.PivotColumns>
                <pivotGrid:SfPivotGrid.PivotCalculations>
                    <pivots:PivotComputationInfo FieldCaption="Amount" FieldName="Amount" Format="C" SummaryType="DoubleTotalSum"/>
                </pivotGrid:SfPivotGrid.PivotCalculations>
         </pivotGrid:SfPivotGrid>
    </Grid>
</Page>

{% endhighlight %}

### Binding ItemSource, defining PivotItems and PivotComputations to SfPivotGrid through code-behind

If you need to initialize the ItemSource through code-behind, please refer the below code snippet.

{% highlight c# %}

using Windows.UI.Xaml.Controls;
using Syncfusion.UI.Xaml.PivotGrid;
using Syncfusion.PivotAnalysis.UWP;

namespace SfPivotGridDemo
{
    /// <summary>
    /// An empty page that can be used on its own or navigated to within a Frame.
    /// </summary>
    public sealed partial class MainPage : Page
    {
        public MainPage()
        {
            this.InitializeComponent();
            SfPivotGrid pivotGrid = new SfPivotGrid();
            pivotGrid.Name = "PivotGrid1";
            Root_Grid.Children.Add(pivotGrid);
            pivotGrid.ItemSource = ProductSales.GetSalesData()
            // Adding PivotRows to the Control
            this.pivotGrid.PivotRows.Add(new Syncfusion.PivotAnalysis.UWP.PivotItem { FieldMappingName = "Product", TotalHeader = "Total" });
            this.pivotGrid.PivotRows.Add(new Syncfusion.PivotAnalysis.UWP.PivotItem { FieldMappingName = "Date", TotalHeader = "Total" });

            // Adding PivotColumns to the Control
            this.pivotGrid.PivotColumns.Add(new Syncfusion.PivotAnalysis.UWP.PivotItem { FieldMappingName = "Country", TotalHeader = "Total" });

            // Adding PivotCalculations to the Control
            this.pivotGrid.PivotCalculations.Add(new PivotComputationInfo { FieldName = "Amount", Format = "C", SummaryType = SummaryType.DoubleTotalSum });
        }
    }
}

{% endhighlight %}

**Run** the application, the following output will be generated.

![](Getting-Started_images/Relational.png) 