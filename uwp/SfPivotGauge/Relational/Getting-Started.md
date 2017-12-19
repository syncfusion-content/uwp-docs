---
layout: post
title: Relational Getting Started with SfPivotGauge control for UWP
description: Relational Getting Started with SfPivotGauge control for UWP
platform: uwp
control: SfPivotGauge
documentation: ug
---

# Getting Started

This section explains the steps required to create a simple SfPivotGauge control bound to Relational data source such as IList, IEnumerable.etc.,

### Control Initialization

SfPivotGauge control can be initialized and added to an application through the following ways:

1. Through designer
2. Through XAML
3. Through code-behind

## Adding Control through Designer

Open Visual Studio IDE and navigating to *File > New > Project > Universal > Blank APP(Universal Windows)* under Windows option inside the Visual C# Templates to create a new UWP application.

N> Once the UWP application is created, select **"Properties"** under the project shown in Solution Explorer and change the Target Version of the application as **"Windows 10 (10.0; Build 10240)".**

Now select Toolbox options from View menu and it will appear inside the VisualStudio IDE. From the toolbox select SfPivotGauge control under “Syncfusion Controls for UWP XAML” group, then drag and drop it into the designer section of MainPage.xaml file.

Finally name the added SfPivotGauge control as “PivotGauge1” in MainPage.xaml to refer it in code-behind as follows:

{% tabs %}

{% highlight xaml %}

<PivotGauge:SfPivotGauge x:Name="PivotGauge1"/>

{% endhighlight %}

{% endtabs %}

## Adding Control through XAML

Open Visual Studio IDE and navigating to *File > New > Project > Universal > Blank APP(Universal Windows)* under Windows option inside the Visual C# Templates to create a new UWP application.

Then, name the project as "SfPivotGaugeDemo" while creating the application to access the project later.

In order to add SfPivotGauge control manually in XAML, the following assembly references must be added in the project.

* Syncfusion.SfPivotGauge.UWP
* Syncfusion.SfGauge.UWP
* Syncfusion.Data.UWP
* Syncfusion.Olap.UWP
* Syncfusion.PivotAnalysis.UWP

You can find these libraries under following location.

{Installed Drive}:\Program Files (x86)\Syncfusion\Essential Studio\\&lt;Version&gt;\Assemblies for Universal Windows\10.0

Or else, the SfPivotGauge control can be added to the project by choosing SDK reference as follows:

Right click on **References** and select Add Reference > Universal Windows > Extensions > Syncfusion Controls for UWP XAML.

Now add the following namespace in MainPage.xaml file.

{% tabs %}

{% highlight xaml %}

xmlns:syncfusion="using:Syncfusion.UI.Xaml.PivotGauge"

{% endhighlight %}

{% endtabs %}

Then initialize the SfPivotGauge control inside the Gauge by using the specified namespace and name the control as “PivotGauge1”.

{% tabs %}

{% highlight xaml %}

<Page
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:local="using:SfPivotGaugeDemo"
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
    x:Class="SfPivotGaugeDemo.MainPage"
    xmlns:syncfusion="using:Syncfusion.UI.Xaml.PivotGauge"
    mc:Ignorable="d">

    <Grid Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">
        <syncfusion:SfPivotGauge x:Name="PivotGauge1"/>
    </Grid>
</Page>

{% endhighlight %}

{% endtabs %}

## Adding Control through Code-Behind

Open Visual Studio IDE and navigating to *File > New > Project > Universal > Blank APP(Universal Windows)* under Windows option inside the Visual C# Templates to create a new UWP application.

Then, name the project as "SfPivotGaugeDemo" while creating the application to access the project later.

In order to add SfPivotGauge control manually in code-behind, the following assembly references must be added in the project.

* Syncfusion.SfPivotGauge.UWP
* Syncfusion.SfGauge.UWP
* Syncfusion.Data.UWP
* Syncfusion.Olap.UWP
* Syncfusion.PivotAnalysis.UWP

You can find these libraries under following location.

{Installed Drive}:\Program Files (x86)\Syncfusion\Essential Studio\\&lt;Version&gt;\Assemblies for Universal Windows\10.0

Or else, the SfPivotGauge control can be added to the project by choosing SDK reference as follows:

Right click on **References** and select Add Reference > Universal Windows > Extensions > Syncfusion Controls for UWP XAML.

Now open the MainPage.xaml file, and include name for the Gauge as “Root_Gauge” to refer it in code-behind.

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

    <Grid Background="{ThemeResource ApplicationPageBackgroundThemeBrush}" x:Name="Root_Grid">
    </Grid>
</Page>

{% endhighlight %}

{% endtabs %}

Next add the namespace - "Syncfusion.UI.Xaml.PivotGauge" in MainPage.xaml.cs file. Then initialize the SfPivotGauge control and assign a name for it as "PivotGauge1". Then add the control in parent Gauge as follows.

{% tabs %}

{% highlight c# %}

using Windows.UI.Xaml.Controls;
using Syncfusion.UI.Xaml.PivotGauge;

namespace SfPivotGaugeDemo
{
    /// <summary>
    /// An empty page that can be used on its own or navigated to within a Frame.
    /// </summary>
    public sealed partial class MainPage: Page
    {
        public MainPage()
        {
            this.InitializeComponent();
            SfPivotGauge pivotGauge = new SfPivotGauge();
            pivotGauge.Name = "PivotGauge1";
            Root_Grid.Children.Add(pivotGauge);
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
            pivotGauge.Name = "PivotGauge1"
            Root_Grid.Children.Add(pivotGauge)
        End Sub
    End Class
End Namespace

{% endhighlight %}

{% endtabs %}

## Adding Relational Data Source to SfPivotGauge

Right-click on the project in the solution explorer and select *Add -> New Folder* and then name the folder as **"ViewModel"**.

Then create a new class file by right-click on the project in the solution explorer and select *Add -> New Item -> Class*. In "Add New Item" window, provide the name of the class as ProductSales.cs and click **OK**.

The ItemSource for the SfPivotGauge control will be initialized in this file. Please refer the below code sample.

{% tabs %}

{% highlight c# %}

public class ProductSales
{
    public string Product { get; set; }
    public string Date { get; set; }
    public string Country { get; set; }
    public double Amount { get; set; }

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

    Public Property Product As String

    Public Property Date As String

    Public Property Country As String

    Public Property Amount As Double

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

Above mentioned GetSalesData method is used to get the collection that needs to be populated in the SfPivotGauge control. Now we need to bind the collection to the SfPivotGauge control as its ItemSource. It can be done through XAML or code-behind.

### Binding ItemSource, Defining PivotItems and PivotComputations to SfPivotGauge through XAML

If you need to initialize the ItemSource through XAML, DataContext is used. Please refer the following code.

{% tabs %}

{% highlight xaml %}

<Page
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:local="using:SfPivotGaugeDemo"
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
    xmlns:syncfusion="using:Syncfusion.UI.Xaml.PivotGauge"
    xmlns:pivots="using:Syncfusion.PivotAnalysis.UWP"
    xmlns:viewModel="using:SfPivotGaugeDemo.ViewModel"
    x:Class="SfPivotGaugeDemo.MainPage"
    mc:Ignorable="d">

    <Grid Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">
        <Grid.DataContext>
             <viewModel:ProductSales/>
        </Grid.DataContext>
        <syncfusion:SfPivotGauge x:Name="PivotGauge1" ItemSource="{Binding ProductSalesData}">
            <syncfusion:SfPivotGauge.PivotRows>
                <pivots:PivotItem FieldCaption="Product" FieldMappingName="Product" TotalHeader="Total"/>
                <pivots:PivotItem FieldCaption="Date" FieldMappingName="Date" TotalHeader="Total"/>
            </syncfusion:SfPivotGauge.PivotRows>
            <syncfusion:SfPivotGauge.PivotColumns>
                <pivots:PivotItem FieldCaption="Country" FieldMappingName="Country" TotalHeader="Total"/>
            </syncfusion:SfPivotGauge.PivotColumns>
            <syncfusion:SfPivotGauge.PivotCalculations>
                <pivots:PivotComputationInfo FieldCaption="Amount" FieldName="Amount" Format="C" SummaryType="DoubleTotalSum"/>
            </syncfusion:SfPivotGauge.PivotCalculations>
         </syncfusion:SfPivotGauge>
    </Grid>
</Page>

{% endhighlight %}

{% endtabs %}

### Binding ItemSource, Defining PivotItems and PivotComputations to SfPivotGauge through Code-Behind

If you need to initialize the ItemSource through code-behind, please refer the below code snippet.

{% tabs %}

{% highlight c# %}

using Windows.UI.Xaml.Controls;
using Syncfusion.UI.Xaml.PivotGauge;
using Syncfusion.PivotAnalysis.UWP;

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
            pivotGauge.Name = "PivotGauge1";
            Root_Grid.Children.Add(pivotGauge);
            pivotGauge.ItemSource = ProductSales.GetSalesData();
            // Adding PivotRows to the Control
            pivotGauge.PivotRows.Add(new Syncfusion.PivotAnalysis.UWP.PivotItem { FieldMappingName = "Product", TotalHeader = "Total" });
            pivotGauge.PivotRows.Add(new Syncfusion.PivotAnalysis.UWP.PivotItem { FieldMappingName = "Date", TotalHeader = "Total" });

            // Adding PivotColumns to the Control
            pivotGauge.PivotColumns.Add(new Syncfusion.PivotAnalysis.UWP.PivotItem { FieldMappingName = "Country", TotalHeader = "Total" });

            // Adding PivotCalculations to the Control
            pivotGauge.PivotCalculations.Add(new PivotComputationInfo { FieldName = "Amount", Format = "C", SummaryType = SummaryType.DoubleTotalSum });
        }
    }
}

{% endhighlight %}

{% highlight vb %}

Imports Windows.UI.Xaml.Controls
Imports Syncfusion.UI.Xaml.PivotGauge
Imports Syncfusion.PivotAnalysis.UWP

Namespace SfPivotGaugeDemo

    Public NotInheritable Partial Class MainPage
        Inherits Page

        Public Sub New()
            Me.InitializeComponent()
            Dim pivotGauge As SfPivotGauge = New SfPivotGauge()
            pivotGauge.Name = "PivotGauge1"
            Root_Grid.Children.Add(pivotGauge)
            pivotGauge.ItemSource = ProductSales.GetSalesData()
            pivotGauge.PivotRows.Add(New Syncfusion.PivotAnalysis.UWP.PivotItem With {.FieldMappingName = "Product", .TotalHeader = "Total"})
            pivotGauge.PivotRows.Add(New Syncfusion.PivotAnalysis.UWP.PivotItem With {.FieldMappingName = "Date", .TotalHeader = "Total"})
            pivotGauge.PivotColumns.Add(New Syncfusion.PivotAnalysis.UWP.PivotItem With {.FieldMappingName = "Country", .TotalHeader = "Total"})
            pivotGauge.PivotCalculations.Add(New PivotComputationInfo With {.FieldName = "Amount", .Format = "C", .SummaryType = SummaryType.DoubleTotalSum})
        End Sub
    End Class
End Namespace

{% endhighlight %}

{% endtabs %}

**Run** the application, the following output will be generated.

![](Getting-Started_images/Relational.png)