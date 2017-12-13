---
layout: post
title: Relational Getting Started | SfPivotGrid | UWP | Syncfusion
description: Getting Started of SfPivotGrid Control with Relational Data
platform: UWP
control: SfPivotGrid
documentation: ug
---

# Getting Started

This section explains about the steps required to create a simple SfPivotGrid control that is bound to relational data sources such as IList, IEnumerable, etc.

## Control initialization

SfPivotGrid control can be initialized and added to an application through the following ways:

1. Through designer
2. Through XAML
3. Through code-behind

## Adding control through designer

Open Visual Studio IDE and navigate to *File > New > Project > Universal > Blank APP(Universal Windows)* under windows option inside the Visual C# Templates to create a new UWP application.

N> After creating the UWP application, select the `Properties` under the project shown in the solution explorer and change the target version of the application as **Windows 10 (10.0; Build 10240)**.

Now, select toolbox options from the view menu and it will appear inside the VisualStudio IDE. From the toolbox, select SfPivotGrid control under “Syncfusion Controls for UWP XAML” group, then drag and drop it into the designer section of the MainPage.xaml file.

Finally, name the added SfPivotGrid control as “PivotGrid1” in MainPage.xaml to refer it in code-behind as follows:

{% tabs %}

{% highlight xaml %}

<PivotGrid:SfPivotGrid x:Name="PivotGrid1"/>

{% endhighlight %}

{% endtabs %}

## Adding control through XAML

Open Visual Studio IDE and navigate to *File > New > Project > Universal > Blank APP(Universal Windows)* under windows option inside the Visual C# Templates to create a new UWP application.

Then, name the project as "SfPivotGridDemo" while creating the application to access the project later.

To add SfPivotGrid control manually in XAML, the following assembly references must be added in the project:

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

You can find these libraries under the following location.

&lt;Installed Drive&gt;:\Program Files (x86)\Syncfusion\Essential Studio\\&lt;Version&gt;\Assemblies for Universal Windows\10.0

Or else, the SfPivotGrid control can be added to the project by choosing SDK reference as follows:

Right-click the **References** and select *Add Reference > Universal Windows > Extensions > Syncfusion Controls for UWP XAML*.

Now, add the following namespace in the MainPage.xaml file.

{% tabs %}

{% highlight xaml %}

xmlns:syncfusion="using:Syncfusion.UI.Xaml.PivotGrid"

{% endhighlight %}

{% endtabs %}

Then, initialize the SfPivotGrid control inside the grid by using the specified namespace and name the control as “PivotGrid1”.

{% tabs %}

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

{% endtabs %}

## Adding control through code-behind

Open Visual Studio IDE and navigate to *File > New > Project > Universal > Blank APP(Universal Windows)* under windows option inside the Visual C# Templates to create a new UWP application.

Then, name the project as "SfPivotGridDemo" while creating the application to access the project later.

To add SfPivotGrid control manually in code-behind, the following assembly references must be added in the project.

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

You can find these libraries under the following location:

&lt;Installed Drive&gt;:\Program Files (x86)\Syncfusion\Essential Studio\\&lt;Version&gt;\Assemblies for Universal Windows\10.0

Or else, the SfPivotGrid control can be added to the project by choosing SDK reference as follows:

Right-click the **References** and select *Add Reference > Universal Windows > Extensions > Syncfusion Controls for UWP XAML*.

Now, open the MainPage.xaml file, and include name for the grid as “Root_Grid” to refer it in code-behind.

{% tabs %}

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

{% endtabs %}

Add the namespace - "Syncfusion.UI.Xaml.PivotGrid" in the MainPage.xaml.cs file. Then initialize the SfPivotGrid control and assign a name for it as "PivotGrid1". You can add the control in the parent grid as follows:

{% tabs %}

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

{% highlight vb %}

Imports Windows.UI.Xaml.Controls
Imports Syncfusion.UI.Xaml.PivotGrid

Namespace SfPivotGridDemo

    Public NotInheritable Partial Class MainPage
        Inherits Page

        Public Sub New()
            Me.InitializeComponent()
            Dim pivotGrid As SfPivotGrid = New SfPivotGrid()
            pivotGrid.Name = "PivotGrid1"
            Root_Grid.Children.Add(pivotGrid)
        End Sub
    End Class
End Namespace

{% endhighlight %}

{% endtabs %}

## Adding relational data source to SfPivotGrid control

Right-click the project in the solution explorer and select *Add > New Folder*, and then name the folder as `ViewModel`.

Create a new class file by right-clicking the project in the solution explorer and select *Add > New Item > Class*. In "Add New Item" window, provide the name of the class as ProductSales.cs and click **OK**.

The ItemSource for the SfPivotGrid control will be initialized in this file. Please refer the below code sample:

{% tabs %}

{% highlight c# %}

public class ProductSales
{
    private object productSalesData;
    public string Product { get; set; }
    public string Date { get; set; }
    public string Country { get; set; }
    public double Amount { get; set; }
     public object ProductSalesData
    {
      get
        {
          this.productSalesData = this.productSalesData ?? ProductSales.GetSalesData();
          return this.productSalesData;
        }
      set { this.productSalesData = (ProductSales.ProductSalesCollection)value; }      
    }
    public static ProductSalesCollection GetSalesData()
    {
        // Geography
        string[] countries = new string[] { "Germany", "Canada", "United States"};

        // Time
        string[] dates = new string[] { "FY 2008", "FY 2009", "FY 2010", "FY 2012" };

        // Products
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

{% highlight vb %}

Public Class ProductSales

    Private productSalesData As Object

    Public Property Product As String

    Public Property Date As String

    Public Property Country As String

    Public Property Amount As Double

    Public Property ProductSalesData As Object
        Get
            Me.productSalesData = If(Me.productSalesData, ProductSales.GetSalesData())
            Return Me.productSalesData
        End Get

        Set(ByVal value As Object)
            Me.productSalesData = CType(value, ProductSales.ProductSalesCollection)
        End Set
    End Property

    Public Shared Function GetSalesData() As ProductSalesCollection
        Dim countries As String() = New String() {"Germany", "Canada", "United States"}
        Dim dates As String() = New String() {"FY 2008", "FY 2009", "FY 2010", "FY 2012"}
        Dim products As String() = New String() {"Bike", "Car"}
        Dim r As Random = New Random(123345)
        Dim numberOfRecords As Integer = 1000
        Dim listOfProductSales As ProductSalesCollection = New ProductSalesCollection()
        For i As Integer = 0 To numberOfRecords - 1
            Dim sales As ProductSales = New ProductSales()
            sales.Country = countries(r.[Next](1, countries.GetLength(0)))
            sales.Amount =(3000 * r.[Next](1, 12))
            sales.Date = dates(r.[Next](r.[Next](dates.GetLength(0) + 1)))
            sales.Product = products(r.[Next](r.[Next](products.GetLength(0) + 1)))
            listOfProductSales.Add(sales)
        Next

        Return listOfProductSales
    End Function

    Public Class ProductSalesCollection
        Inherits List(Of ProductSales)

    End Class
End Class

{% endhighlight %}

{% endtabs %}

Above mentioned GetSalesData method is used to get the collection that needs to be populated in the SfPivotGrid control. Now, you should bind the collection to the SfPivotGrid control as its ItemSource. It can be done through XAML or code-behind.

### Binding ItemSource, defining PivotItems and PivotComputations to SfPivotGrid through XAML

If you need to initialize the ItemSource through XAML, the DataContext is used. Please refer the following code:

{% tabs %}

{% highlight xaml %}

<Page
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:local="using:SfPivotGridDemo"
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
    xmlns:syncfusion="using:Syncfusion.UI.Xaml.PivotGrid"
    xmlns:pivots="using:Syncfusion.PivotAnalysis.UWP"
    xmlns:viewModel="using:SfPivotGridDemo.ViewModel"
    x:Class="SfPivotGridDemo.MainPage"
    mc:Ignorable="d">

    <Grid Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">
        <Grid.DataContext>
             <viewModel:ProductSales/>
        </Grid.DataContext>
        <syncfusion:SfPivotGrid x:Name="PivotGrid1" ItemSource="{Binding ProductSalesData}">
         <syncfusion:SfPivotGrid.PivotRows>
                    <pivots:PivotItem FieldCaption="Product" FieldMappingName="Product" TotalHeader="Total"/>
                    <pivots:PivotItem FieldCaption="Date" FieldMappingName="Date" TotalHeader="Total"/>
                </syncfusion:SfPivotGrid.PivotRows>
                <syncfusion:SfPivotGrid.PivotColumns>
                    <pivots:PivotItem FieldCaption="Country" FieldMappingName="Country" TotalHeader="Total"/>
                </syncfusion:SfPivotGrid.PivotColumns>
                <syncfusion:SfPivotGrid.PivotCalculations>
                    <pivots:PivotComputationInfo FieldCaption="Amount" FieldName="Amount" Format="C" SummaryType="DoubleTotalSum"/>
                </syncfusion:SfPivotGrid.PivotCalculations>
         </syncfusion:SfPivotGrid>
    </Grid>
</Page>

{% endhighlight %}

{% endtabs %}

### Binding ItemSource, defining PivotItems, and PivotComputations to SfPivotGrid through code-behind

If you need to initialize the ItemSource through code-behind, please refer the below code snippet:

{% tabs %}

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
            pivotGrid.ItemSource = ProductSales.GetSalesData();
            // Adding PivotRows to the Control
            pivotGrid.PivotRows.Add(new Syncfusion.PivotAnalysis.UWP.PivotItem { FieldMappingName = "Product", TotalHeader = "Total" });
            pivotGrid.PivotRows.Add(new Syncfusion.PivotAnalysis.UWP.PivotItem { FieldMappingName = "Date", TotalHeader = "Total" });

            // Adding PivotColumns to the Control
            pivotGrid.PivotColumns.Add(new Syncfusion.PivotAnalysis.UWP.PivotItem { FieldMappingName = "Country", TotalHeader = "Total" });

            // Adding PivotCalculations to the Control
            pivotGrid.PivotCalculations.Add(new PivotComputationInfo { FieldName = "Amount", Format = "C", SummaryType = SummaryType.DoubleTotalSum });
        }
    }
}

{% endhighlight %}

{% highlight vb %}

Imports Windows.UI.Xaml.Controls
Imports Syncfusion.UI.Xaml.PivotGrid
Imports Syncfusion.PivotAnalysis.UWP

Namespace SfPivotGridDemo

    Public NotInheritable Partial Class MainPage
        Inherits Page

        Public Sub New()
            Me.InitializeComponent()
            Dim pivotGrid As SfPivotGrid = New SfPivotGrid()
            pivotGrid.Name = "PivotGrid1"
            Root_Grid.Children.Add(pivotGrid)
            pivotGrid.ItemSource = ProductSales.GetSalesData()
            pivotGrid.PivotRows.Add(New Syncfusion.PivotAnalysis.UWP.PivotItem With {.FieldMappingName = "Product", .TotalHeader = "Total"})
            pivotGrid.PivotRows.Add(New Syncfusion.PivotAnalysis.UWP.PivotItem With {.FieldMappingName = "Date", .TotalHeader = "Total"})
            pivotGrid.PivotColumns.Add(New Syncfusion.PivotAnalysis.UWP.PivotItem With {.FieldMappingName = "Country", .TotalHeader = "Total"})
            pivotGrid.PivotCalculations.Add(New PivotComputationInfo With {.FieldName = "Amount", .Format = "C", .SummaryType = SummaryType.DoubleTotalSum})
        End Sub
    End Class
End Namespace

{% endhighlight %}

{% endtabs %}

**Run** the application, the following output will be generated.

![](Getting-Started_images/Relational.png)