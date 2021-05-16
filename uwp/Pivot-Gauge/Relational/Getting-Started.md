---
layout: post
title: Getting Started with UWP Pivot Gauge control | Syncfusion
description: Learn here all about getting started with Syncfusion UWP Pivot Gauge (SfPivotGauge) control and more.
platform: UWP
control: SfPivotGauge
documentation: ug
---

# Getting Started with UWP Pivot Gauge (SfPivotGauge)

>**Important**
To start with v16.2.0.x, if you refer to Syncfusion assemblies from trial setup or NuGet feed, include a license key in your projects. Refer to this [link](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to learn about registering a Syncfusion license key in your UWP application to use the components.

This section explains the steps required to create a simple SfPivotGauge control bound to a relational data source such as IList or IEnumerable.

## Initializing SfPivotGauge control

1. Open Visual Studio IDE and select **File > New > Project** to open the new project dialog.

2. Select **Installed > Templates > Visual C# > Windows > Universal > Blank APP(Universal Windows)** to create a new UWP application and name the project as "SfPivotGaugeDemo".

The target version/minimum version dialog appears, in which you can change the target version of the application as **"Windows 10 (10.0; Build 10240)".**

The SfPivotGauge control can be initialized and added to the application through any of the following ways:

1. Designer.
2. XAML.
3. Code-behind.

### Adding control through designer

1. Double-click the MainPage.xaml from the solution explorer to open it in the design view.

2. Click the toolbox and drag the **SfPivotGauge** control from the “Syncfusion Controls for UWP XAML” group to drop it on the middle of the design canvas.

Now, the SfPivotGauge control will be added to the designer as follows.

![GettingStarted_Designer](Getting-Started_images/Designer.png)

### Adding control through XAML

The SfPivotGauge control can be added to the project by referencing assemblies or SDK.

**Assembly reference**

1. Right-click the project in the solution explorer and select **Add > Reference...** to add the required assemblies.

2. Then, click **Browse** to select the following assemblies from the installed location and click **OK**.

* Syncfusion.Data.UWP
* Syncfusion.Olap.UWP
* Syncfusion.PivotAnalysis.UWP
* Syncfusion.SfBusyIndicator.UWP
* Syncfusion.SfGauge.UWP
* Syncfusion.SfPivotGauge.UWP

N> You can find these libraries under the following location.
&lt;Installed Drive&gt;:\Program Files (x86)\Syncfusion\Essential Studio\\&lt;Version&gt;\Assemblies for Universal Windows\10.0

**Extension SDK reference**

1. Right-click the project in the solution explorer and select **Add > Reference... > Universal Windows > Extensions > Syncfusion Controls for UWP XAML**.

2. After adding the required reference, add the following namespace to the *MainPage.xaml* file.

{% tabs %}

{% highlight xaml %}

xmlns:PivotGauge="using:Syncfusion.UI.Xaml.PivotGauge"

{% endhighlight %}

{% endtabs %}

3. Then, add the SfPivotGauge control to the grid by using the namespace specified in the following code snippet.

{% tabs %}

{% highlight xaml %}

    <Page
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:local="using:SfPivotGaugeDemo"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        x:Class="SfPivotGaugeDemo.MainPage"
        xmlns:PivotGauge="using:Syncfusion.UI.Xaml.PivotGauge"
        mc:Ignorable="d">

        <Grid Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">
            <PivotGauge:SfPivotGauge/>
        </Grid>
    </Page>

{% endhighlight %}

{% endtabs %}

### Adding control through code-behind

The SfPivotGauge control can be added to the project by referencing assemblies or SDK.

**Assembly reference**

1. Right-click the project in the solution explorer and select **Add > Reference...** to add the required assemblies.

2. Click **Browse** to select the following assemblies from the installed location and click **OK**.

* Syncfusion.Data.UWP
* Syncfusion.Olap.UWP
* Syncfusion.PivotAnalysis.UWP
* Syncfusion.SfBusyIndicator.UWP
* Syncfusion.SfGauge.UWP
* Syncfusion.SfPivotGauge.UWP

N> You can find these libraries under the following location.
&lt;Installed Drive&gt;:\Program Files (x86)\Syncfusion\Essential Studio\\&lt;Version&gt;\Assemblies for Universal Windows\10.0

**Extension SDK reference**

1. Right-click the project in the solution explorer and select **Add > Reference... > Universal Windows > Extensions > Syncfusion Controls for UWP XAML**.

2. After adding the required reference, open the *MainPage.xaml* file and name the grid "RootGrid" to refer to it in the code-behind.

{% tabs %}

{% highlight xaml %}

    <Page
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:local="using:SfPivotGaugeDemo"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        x:Class="SfPivotGaugeDemo.MainPage"
        mc:Ignorable="d">

        <Grid Background="{ThemeResource ApplicationPageBackgroundThemeBrush}" x:Name="RootGrid">
        </Grid>
    </Page>

{% endhighlight %}

{% endtabs %}

3. Open the *MainPage.xaml.cs* file and include the namespace "Syncfusion.UI.Xaml.PivotGauge". 

4. Then, initialize the SfPivotGauge control in the constructor and add it to the grid as illustrated below.

{% tabs %}

{% highlight c# %}

using Windows.UI.Xaml.Controls;
using Syncfusion.UI.Xaml.PivotGauge;

namespace SfPivotGaugeDemo
{
    /// <summary>
    /// An empty page that can be used on its own or navigated to within a Frame.
    /// </summary>
    public sealed partial class MainPage : Page
    {
        public MainPage()
        {
            this.InitializeComponent();
            SfPivotGauge pivotGauge = new SfPivotGauge();
            RootGrid.Children.Add(pivotGauge);
        }
    }
}

{% endhighlight %}

{% highlight vb %}

Imports Windows.UI.Xaml.Controls
Imports Syncfusion.UI.Xaml.PivotGauge

Namespace SfPivotGaugeDemo

    Public NotInheritable Partial Class MainPage
        Inherits Page

        Public Sub New()
            Me.InitializeComponent()
            Dim pivotGauge As SfPivotGauge = New SfPivotGauge()
            RootGrid.Children.Add(pivotGauge)
        End Sub
    End Class
End Namespace

{% endhighlight %}

{% endtabs %}

## Binding relational data to SfPivotGauge control

### Creating relational data through view model

5. After initializing the SfPivotGauge control, right-click the project in the solution explorer and select **Add > New Item... > Class** to create a new class file.

6. Then, name the class *ProductSalesViewModel* and click **OK**.

The following code snippet illustrates how to define relational data for the SfPivotGauge.

{% tabs %}

{% highlight c# %}

using System;
using System.Collections.ObjectModel;

namespace SfPivotGaugeDemo
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

Namespace SfPivotGaugeDemo

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

### Defining item sSource, pivot rows, pivot columns and pivot calculations for SfPivotGauge control

Relational data can be bound to SfPivotGauge control by using the `ItemSource` property through the following ways:

* XAML
* Code-behind

**Through XAML**

The relational data mentioned in the *ProductSalesViewModel* is bound to the SfPivotGauge control with the help of `DataContext`. In addition to this, the `PivotRows`, `PivotColumns`, and `PivotCalculations` should be assigned to SfPivotGauge for populating the data.


{% tabs %}

{% highlight xaml %}

    <Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
            xmlns:local="using:SfPivotGaugeDemo"
            xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
            xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
            xmlns:PivotGauge="using:Syncfusion.UI.Xaml.PivotGauge"
            xmlns:pivot="using:Syncfusion.PivotAnalysis.UWP"
            x:Class="SfPivotGaugeDemo.MainPage"
            mc:Ignorable="d">

        <Grid Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">
            <Grid.DataContext>
                <local:ProductSalesViewModel/>
            </Grid.DataContext>
            <PivotGauge:SfPivotGauge ItemSource="{Binding ProductSales}">
                <PivotGauge:SfPivotGauge.PivotRows>
                    <pivot:PivotItem FieldCaption="Product" FieldMappingName="Product" TotalHeader="Total"/>
                    <pivot:PivotItem FieldCaption="Country" FieldMappingName="Country" TotalHeader="Total"/>
                </PivotGauge:SfPivotGauge.PivotRows>
                <PivotGauge:SfPivotGauge.PivotColumns>
                    <pivot:PivotItem FieldCaption="Date" FieldMappingName="Date" TotalHeader="Total"/>
                </PivotGauge:SfPivotGauge.PivotColumns>
                <PivotGauge:SfPivotGauge.PivotCalculations>
                    <pivot:PivotComputationInfo FieldCaption="Amount" FieldName="Amount" Format="#.##" SummaryType="DoubleTotalSum"/>
                </PivotGauge:SfPivotGauge.PivotCalculations>
            </PivotGauge:SfPivotGauge>
        </Grid>
    </Page>

{% endhighlight %}

{% endtabs %}

**Through code-behind**

The following code snippet illustrates how to bind the data to SfPivotGauge control in code-behind.

{% tabs %}

{% highlight c# %}

using Windows.UI.Xaml.Controls;
using Syncfusion.PivotAnalysis.UWP;
using Syncfusion.UI.Xaml.PivotGauge;

namespace SfPivotGaugeDemo
{
    public sealed partial class MainPage : Page
    {
        public MainPage()
        {
            this.InitializeComponent();

            ProductSalesViewModel productSalesViewModel = new ProductSalesViewModel();

            SfPivotGauge pivotGauge = new SfPivotGauge();

            // Assigning ItemSource to PivotGauge
            pivotGauge.ItemSource = productSalesViewModel.ProductSales;

            // Adding PivotColumns to PivotGauge
            pivotGauge.PivotColumns.Add(new Syncfusion.PivotAnalysis.UWP.PivotItem { FieldMappingName = "Product", TotalHeader = "Total" });
            pivotGauge.PivotColumns.Add(new Syncfusion.PivotAnalysis.UWP.PivotItem { FieldMappingName = "Country", TotalHeader = "Country" });

            // Adding PivotRows to PivotGauge
            pivotGauge.PivotRows.Add(new Syncfusion.PivotAnalysis.UWP.PivotItem { FieldMappingName = "Date", TotalHeader = "Date" });

            // Adding PivotCalculations to PivotGauge
            pivotGauge.PivotCalculations.Add(new PivotComputationInfo { FieldName = "Amount", Format = "#.##", SummaryType = SummaryType.DoubleTotalSum });

            RootGrid.Children.Add(pivotGauge);
        }
    }
}

{% endhighlight %}

{% highlight vb %}

Imports Windows.UI.Xaml.Controls
Imports Syncfusion.PivotAnalysis.UWP
Imports Syncfusion.UI.Xaml.PivotGauge

Namespace SfPivotGaugeDemo
    Public NotInheritable Partial Class MainPage
        Inherits Page
        Public Sub New()
            Me.InitializeComponent()

            Dim productSalesViewModel As New ProductSalesViewModel()

            Dim pivotGauge As New SfPivotGauge()

            ' Assigning ItemSource to PivotGauge
            pivotGauge.ItemSource = productSalesViewModel.ProductSales

            ' Adding PivotColumns to PivotGauge
            pivotGauge.PivotColumns.Add(New Syncfusion.PivotAnalysis.UWP.PivotItem With {.FieldMappingName = "Product", .TotalHeader = "Total"})
            pivotGauge.PivotColumns.Add(New Syncfusion.PivotAnalysis.UWP.PivotItem With {.FieldMappingName = "Country", .TotalHeader = "Country"})

            ' Adding PivotRows to PivotGauge
            pivotGauge.PivotRows.Add(New Syncfusion.PivotAnalysis.UWP.PivotItem With {.FieldMappingName = "Date", .TotalHeader = "Date"})

            ' Adding PivotCalculations to PivotGauge
            pivotGauge.PivotCalculations.Add(New PivotComputationInfo With {.FieldName = "Amount", .Format = "#.##", .SummaryType = SummaryType.DoubleTotalSum})

            RootGrid.Children.Add(pivotGauge)
        End Sub
    End Class
End Namespace

{% endhighlight %}

{% endtabs %}

Finally, run the application to generate the following output.

![GettingStarted-Relational](Getting-Started_images/Relational.png)