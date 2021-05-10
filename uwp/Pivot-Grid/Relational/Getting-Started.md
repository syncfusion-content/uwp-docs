---
layout: post
title: Getting Started with UWP Pivot Grid control | Syncfusion
description: Learn here all about getting started with Syncfusion UWP Pivot Grid (SfPivotGrid) control and more.
platform: UWP
control: SfPivotGrid
documentation: ug
---

# Getting Started with UWP Pivot Grid (SfPivotGrid)

>**Important**
Starting with v16.2.0.x, if you refer to Syncfusion assemblies from trial setup or from the NuGet feed, include a license key in your projects. Refer to this [link](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to learn about registering Syncfusion license key in your UWP application to use the components.

This section explains the steps required to create a simple SfPivotGrid control bound to relational data source such as IList, IEnumerable, etc.

## Initializing SfPivotGrid control

Open Visual Studio IDE and select **File > New > Project** to open the new project dialog.

Select **Installed > Templates > Visual C# > Windows > Universal > Blank APP(Universal Windows)** to create a new UWP application and name the project as "SfPivotGridDemo".

The target version/minimum version dialog appears, in which change the target version of the application as **"Windows 10 (10.0; Build 10240)".**

The SfPivotGrid control can be initialized and added to the application through any of the following ways:

1. Through designer.
2. Through XAML.
3. Through code-behind.

### Adding control through designer

Double-click the MainPage.xaml from the solution explorer to open it in the design view.

Click the toolbox and drag the **SfPivotGrid** control from the “Syncfusion Controls for UWP XAML” group to drop it on the middle of the design canvas.

The SfPivotGrid control will be added to the designer as follows:

![GettingStarted_Designer](Getting-Started_images/Designer.png)

### Adding control through XAML

The SfPivotGrid control can be added to the project by referring assemblies or SDK as described below:

**Assembly reference**

Right-click the project in the solution explorer and select **Add > Reference...** to add the required assemblies. Then, click **Browse** to select the following assemblies from the installed location and click **OK**.

* Syncfusion.Data.UWP
* Syncfusion.Olap.UWP
* Syncfusion.PivotAnalysis.UWP
* Syncfusion.SfBusyIndicator.UWP
* Syncfusion.SfCellGrid.UWP
* Syncfusion.SfColorPickers.UWP
* Syncfusion.SfGrid.UWP
* Syncfusion.SfGridCommon.UWP
* Syncfusion.SfInput.UWP
* Syncfusion.SfPivotGrid.UWP
* Syncfusion.SfShared.UWP

N> You can find these libraries under the following location.
&lt;Installed Drive&gt;:\Program Files (x86)\Syncfusion\Essential Studio\\&lt;Version&gt;\Assemblies for Universal Windows\10.0

**Extension SDK reference**

Right-click the project in the solution explorer and select **Add > Reference... > Universal Windows > Extensions > Syncfusion Controls for UWP XAML**.

After adding the required reference, add the following namespace in the *MainPage.xaml* file.

{% tabs %}

{% highlight xaml %}

xmlns:PivotGrid="using:Syncfusion.UI.Xaml.PivotGrid"

{% endhighlight %}

{% endtabs %}

Then, add the SfPivotGrid control to the grid by using the specified namespace as specified in the following code snippet.

{% tabs %}

{% highlight xaml %}

    <Page
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:local="using:SfPivotGridDemo"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        x:Class="SfPivotGridDemo.MainPage"
        xmlns:PivotGrid="using:Syncfusion.UI.Xaml.PivotGrid"
        mc:Ignorable="d">

        <Grid Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">
            <PivotGrid:SfPivotGrid/>
        </Grid>
    </Page>

{% endhighlight %}

{% endtabs %}

### Adding control through code-behind

The SfPivotGrid control can be added to the project by referring assemblies or SDK.

**Assembly reference**

Right-click the project in the solution explorer and select **Add > Reference...** to add the required assemblies. Then, click **Browse** to select the following assemblies from the installed location and click **OK**.

* Syncfusion.Data.UWP
* Syncfusion.Olap.UWP
* Syncfusion.PivotAnalysis.UWP
* Syncfusion.SfBusyIndicator.UWP
* Syncfusion.SfCellGrid.UWP
* Syncfusion.SfColorPickers.UWP
* Syncfusion.SfGrid.UWP
* Syncfusion.SfGridCommon.UWP
* Syncfusion.SfInput.UWP
* Syncfusion.SfPivotGrid.UWP
* Syncfusion.SfShared.UWP

N> You can find these libraries under the following location.
&lt;Installed Drive&gt;:\Program Files (x86)\Syncfusion\Essential Studio\\&lt;Version&gt;\Assemblies for Universal Windows\10.0

**Extension SDK reference**

Right-click the project in the solution explorer and select **Add > Reference... > Universal Windows > Extensions > Syncfusion Controls for UWP XAML**.

After adding the required reference, open the *MainPage.xaml* file and name the grid as "RootGrid" to refer it in the code-behind.

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

        <Grid Background="{ThemeResource ApplicationPageBackgroundThemeBrush}" x:Name="RootGrid">
        </Grid>
    </Page>

{% endhighlight %}

{% endtabs %}

Open the *MainPage.xaml.cs* file and include the namespace "Syncfusion.UI.Xaml.PivotGrid". Then, initialize the SfPivotGrid control in the constructor and add it to the grid as illustrated below.

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
            RootGrid.Children.Add(pivotGrid);
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
            RootGrid.Children.Add(pivotGrid)
        End Sub
    End Class
End Namespace

{% endhighlight %}

{% endtabs %}

## Binding relational data to SfPivotGrid control

### Creating relational data through view model

After initializing the SfPivotGrid control, right-click the project in the solution explorer and select **Add > New Item... > Class** to create a new class file. Then, name the class as *ProductSalesViewModel* and click **OK**.

The following code snippet illustrates how to define the relational data for the SfPivotGrid.

{% tabs %}

{% highlight c# %}

using System;
using System.Collections.ObjectModel;

namespace SfPivotGridDemo
{
    public class ProductSalesViewModel
    {
        private ProductSalesCollection productSales;

        public ProductSalesCollection ProductSales
        {
            get { return this.productSales; }
            set { this.productSales = value; }
        }

        public ProductSalesViewModel()
        {
            this.productSales = GetSalesData();
        }

        public static ProductSalesCollection GetSalesData()
        {
            // Geography
            string[] countries = new string[] { "Germany", "Canada", "United States" };

            // Time
            string[] dates = new string[] { "FY 2008", "FY 2009", "FY 2010", "FY 2012" };

            // Products
            string[] products = new string[] { "Bike", "Car" };
            Random r = new Random(123345);

            int numberOfRecords = 1000;
            ProductSalesCollection listOfProductSales = new ProductSalesCollection();
            for (int i = 0; i < numberOfRecords; i++)
            {
                ProductSale sales = new ProductSale();
                sales.Country = countries[r.Next(1, countries.GetLength(0))];
                sales.Amount = (3000 * r.Next(1, 12));
                sales.Date = dates[r.Next(r.Next(dates.GetLength(0) + 1))];
                sales.Product = products[r.Next(r.Next(products.GetLength(0) + 1))];
                listOfProductSales.Add(sales);
            }
            return listOfProductSales;
        }
    }

    public class ProductSale
    {
        public string Product { get; set; }
        public string Date { get; set; }
        public string Country { get; set; }
        public double Amount { get; set; }
    }

    public class ProductSalesCollection : ObservableCollection<ProductSale>
    {
    }
}

{% endhighlight %}

{% highlight vb %}

Imports System
Imports System.Collections.ObjectModel

Namespace SfPivotGridDemo

    Public Class ProductSalesViewModel

        Private productSales As ProductSalesCollection

        Public Property ProductSales As ProductSalesCollection
            Get
                Return Me.productSales
            End Get

            Set(ByVal value As ProductSalesCollection)
                Me.productSales = value
            End Set
        End Property

        Public Sub New()
            Me.productSales = GetSalesData()
        End Sub

        Public Shared Function GetSalesData() As ProductSalesCollection
            Dim countries As String() = New String() {"Germany", "Canada", "United States"}
            Dim dates As String() = New String() {"FY 2008", "FY 2009", "FY 2010", "FY 2012"}
            Dim products As String() = New String() {"Bike", "Car"}
            Dim r As Random = New Random(123345)
            Dim numberOfRecords As Integer = 1000
            Dim listOfProductSales As ProductSalesCollection = New ProductSalesCollection()
            For i As Integer = 0 To numberOfRecords - 1
                Dim sales As ProductSale = New ProductSale()
                sales.Country = countries(r.[Next](1, countries.GetLength(0)))
                sales.Amount =(3000 * r.[Next](1, 12))
                sales.Date = dates(r.[Next](r.[Next](dates.GetLength(0) + 1)))
                sales.Product = products(r.[Next](r.[Next](products.GetLength(0) + 1)))
                listOfProductSales.Add(sales)
            Next

            Return listOfProductSales
        End Function
    End Class

    Public Class ProductSale
        Public Property Product As String
        Public Property Date As String
        Public Property Country As String
        Public Property Amount As Double
    End Class

    Public Class ProductSalesCollection
        Inherits ObservableCollection(Of ProductSale)
    End Class
End Namespace

{% endhighlight %}

{% endtabs %}

### Defining item source, pivot columns, pivot rows, and pivot calculations for SfPivotGrid control

Relational data can be bound to SfPivotGrid control by using the `ItemSource` property through any of the following ways:

* Through XAML.
* Through code-behind.

**Through XAML**

The relational data mentioned in the *ProductSalesViewModel* is bound to SfPivotGrid control with the help of `DataContext`. In addition to this, `PivotColumns`, `PivotRows`, and `PivotCalculations` should be assigned to the SfPivotGrid for populating the data.

{% tabs %}

{% highlight xaml %}

    <Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
            xmlns:local="using:SfPivotGridDemo"
            xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
            xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
            xmlns:PivotGrid="using:Syncfusion.UI.Xaml.PivotGrid"
            xmlns:pivot="using:Syncfusion.PivotAnalysis.UWP"
            x:Class="SfPivotGridDemo.MainPage"
            mc:Ignorable="d">

        <Grid Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">
            <Grid.DataContext>
                <local:ProductSalesViewModel/>
            </Grid.DataContext>
            <PivotGrid:SfPivotGrid ItemSource="{Binding ProductSales}">
                <PivotGrid:SfPivotGrid.PivotRows>
                    <pivot:PivotItem FieldCaption="Product" FieldMappingName="Product" TotalHeader="Total"/>
                    <pivot:PivotItem FieldCaption="Country" FieldMappingName="Country" TotalHeader="Total"/>
                </PivotGrid:SfPivotGrid.PivotRows>
                <PivotGrid:SfPivotGrid.PivotColumns>
                    <pivot:PivotItem FieldCaption="Date" FieldMappingName="Date" TotalHeader="Total"/>
                </PivotGrid:SfPivotGrid.PivotColumns>
                <PivotGrid:SfPivotGrid.PivotCalculations>
                    <pivot:PivotComputationInfo FieldCaption="Amount" FieldName="Amount" Format="#.##" SummaryType="DoubleTotalSum"/>
                </PivotGrid:SfPivotGrid.PivotCalculations>
            </PivotGrid:SfPivotGrid>
        </Grid>
    </Page>

{% endhighlight %}

{% endtabs %}

**Through code-behind**

The following code snippet illustrates how to bind the data to SfPivotGrid control in code-behind.

{% tabs %}

{% highlight c# %}

using Windows.UI.Xaml.Controls;
using Syncfusion.PivotAnalysis.UWP;
using Syncfusion.UI.Xaml.PivotGrid;

namespace SfPivotGridDemo
{
    public sealed partial class MainPage : Page
    {
        public MainPage()
        {
            this.InitializeComponent();

            ProductSalesViewModel productSalesViewModel = new ProductSalesViewModel();

            SfPivotGrid pivotGrid = new SfPivotGrid();

            // Assigning ItemSource to PivotGrid
            pivotGrid.ItemSource = productSalesViewModel.ProductSales;

            // Adding PivotColumns to PivotGrid
            pivotGrid.PivotColumns.Add(new Syncfusion.PivotAnalysis.UWP.PivotItem { FieldMappingName = "Product", TotalHeader = "Total" });
            pivotGrid.PivotColumns.Add(new Syncfusion.PivotAnalysis.UWP.PivotItem { FieldMappingName = "Country", TotalHeader = "Country" });

            // Adding PivotRows to PivotGrid
            pivotGrid.PivotRows.Add(new Syncfusion.PivotAnalysis.UWP.PivotItem { FieldMappingName = "Date", TotalHeader = "Date" });

            // Adding PivotCalculations to PivotGrid
            pivotGrid.PivotCalculations.Add(new PivotComputationInfo { FieldName = "Amount", Format = "#.##", SummaryType = SummaryType.DoubleTotalSum });

            RootGrid.Children.Add(pivotGrid);
        }
    }
}

{% endhighlight %}

{% highlight vb %}

Imports Windows.UI.Xaml.Controls
Imports Syncfusion.PivotAnalysis.UWP
Imports Syncfusion.UI.Xaml.PivotGrid

Namespace SfPivotGridDemo
    Public NotInheritable Partial Class MainPage
        Inherits Page
        Public Sub New()
            Me.InitializeComponent()

            Dim productSalesViewModel As New ProductSalesViewModel()

            Dim pivotGrid As New SfPivotGrid()

            ' Assigning ItemSource to PivotGrid
            pivotGrid.ItemSource = productSalesViewModel.ProductSales

            ' Adding PivotColumns to PivotGrid
            pivotGrid.PivotColumns.Add(New Syncfusion.PivotAnalysis.UWP.PivotItem With {.FieldMappingName = "Product", .TotalHeader = "Total"})
            pivotGrid.PivotColumns.Add(New Syncfusion.PivotAnalysis.UWP.PivotItem With {.FieldMappingName = "Country", .TotalHeader = "Country"})

            ' Adding PivotRows to PivotGrid
            pivotGrid.PivotRows.Add(New Syncfusion.PivotAnalysis.UWP.PivotItem With {.FieldMappingName = "Date", .TotalHeader = "Date"})

            ' Adding PivotCalculations to PivotGrid
            pivotGrid.PivotCalculations.Add(New PivotComputationInfo With {.FieldName = "Amount", .Format = "#.##", .SummaryType = SummaryType.DoubleTotalSum})

            RootGrid.Children.Add(pivotGrid)
        End Sub
    End Class
End Namespace

{% endhighlight %}

{% endtabs %}

Finally, run the application to generate the following output.

![GettingStarted-Relational](Getting-Started_images/Relational.png)