---
layout: post
title: Getting Started with UWP DataGrid control | Syncfusion®
description: Learn here about getting started with Syncfusion® UWP DataGrid (SfDataGrid) control, its elements and more.
platform: uwp
control: SfDataGrid
documentation: ug
---

# Getting Started with UWP DataGrid (SfDataGrid)

The SfDataGrid control for Universal Windows Platform is used to display collection of data in rows and columns. It includes editing and data shaping features (Sorting, grouping, filtering and etc) that allows the end users to easily manage the data.
 
Following are the key features of SfDataGrid control,

* **Data binding** – Supports to bind different types of data sources.
* **Selection** – Support for row and also cell selection.
* **Editing** – Interactive support to edit with different column types.
* **Columns** – Support for various column types including unbound columns
* **Sorting** – Interactive support to sort the data in SfDataGrid.
* **Grouping** – Interactive support to group the data in SfDataGrid.
* **Summaries** – Extensive support to show concise information about the individual data columns or groups of rows.
* **Filtering** – Interactive support for filtering data as like in Excel.
* **Validation** – Support to validate the data on errors.
* **Data virtualization** – Support for different modes of data virtualization such as paging, incremental loading.
* **Master-Detail View**– Support to display relational data using hierarchies. 
* **Printing and Exporting** – Support to print and also export the data to Excel, PDF.
* **Styling** – Extensive support for customizing styles of cells and rows in SfDataGrid.
* **Stacked Headers** - Extensive support to show multiple headers called stacked headers.
* **Unbound rows** – Support to display unbound rows.
* **Touch support** – Complete support for resizing, drag-drop column, sorting, filtering, grouping and etc. in touch.

## Assembly deployment

The following list of assemblies needs to be added as reference to use SfDataGrid control in any application,

<table>
<tr>
<th>
Required assemblies
</th>
<th>
Description
</th>
</tr>
<tr>
<td>
Syncfusion.Data.UWP
</td>
<td>
Syncfusion.Data.UWP assembly contains fundamental and base classes for <code>[CollectionViewAdv](https://help.syncfusion.com/cr/uwp/Syncfusion.Data.CollectionViewAdv.html)</code> which is responsible for data processing operations handled in SfDataGrid.
</td>
</tr>
<tr>
<td>
Syncfusion.SfGrid.UWP
</td>
<td>
Syncfusion.SfGrid.UWP assembly contains classes that handles all UI operations of SfDataGrid. SfDataGrid control present <code>Syncfusion.UI.Xaml.Grid</code> namespace.
</td>
</tr>
<tr>
<td>
Syncfusion.SfInput.UWP
</td>
<td>
Syncfusion.SfInput.UWP contains various editor controls (such as SfNumericTextBox, SfDateTimeEdit and etc) which are used in SfDataGrid. 
</td>
</tr>
<tr>
<td>
Syncfusion.SfShared.UWP
</td>
<td>
Syncfusion.SfShared.UWP is dependent assembly for Syncfusion.SfInput.UWP.  
</td>
</tr>
</table>

In order to use export to excel and export to PDF functionalities of SfDataGrid control, add the reference to following assemblies,

<table>
<tr>
<th>
Optional Assemblies
</th>
<th>
Description
</th>
</tr>
<tr>
<td>
Syncfusion.SfGridConverter.UWP
</td>
<td>
Syncfusion.SfGridConverter.UWP contains static extension classes for exporting SfDataGrid to excel and PDF in <code>Syncfusion.UI.Xaml.Grid.Converter</code> namespace.
</td>
</tr>
<tr>
<td>
Syncfusion.XlsIO.UWP
</td>
<td>
Syncfusion.XlsIO.Base.UWP contains fundamental and base classes for creating and manipulating excel files.
</td>
</tr>
<tr>
<td>
Syncfusion.Pdf.UWP
</td>
<td>
Syncfusion.Pdf.UWP contains fundamental and base classes for creating PDF.
</td>
</tr>
</table>

You can refer [here](https://help.syncfusion.com/uwp/system-requirements) to know the assemblies installation location on your machine.     

## Creating simple application with SfDataGrid

In this walk through, you will create WPF application that contains SfDataGrid control. 

1. [Creating project](#creating-the-project)
2. [Adding control via Designer](#adding-control-via-designer)
3. [Adding control manually in XAML](#adding-control-manually-in-xaml)
4. [Adding control manually in C#](#adding-control-manually-in-c)
5. [Creating Data Model for application](#creating-data-model-for-sample-application)
6. [Binding to Data](#binding-to-data)
7. [Defining Columns](#defining-columns)
8. [Selection](#selection)
9. [Sorting, Grouping, and Filtering](#sorting-grouping-and-filtering)
10. [Editing](#editing)

### Creating the project

Create new Universal Windows Platform project in Visual Studio to display SfDataGrid with data objects.

### Adding control via Designer

SfDataGrid control can be added to the application by dragging it from Toolbox and dropping it in Designer view. The required assembly references will be added automatically.

![Adding control via Designer](Getting-Started_images/Getting-Started_img1.png)



### Adding control manually in XAML

In order to add control manually in XAML, do the below steps,

1. Add the below required assembly references to the project,

    * Syncfusion.Data.UWP
    * Syncfusion.SfGrid.UWP
    * Syncfusion.SfInput.UWP
    * Syncfusion.SfShared.UWP

2. Import SfDataGrid control namespace **Syncfusion.UI.Xaml.Grid** in XAML page.

3. Declare SfDataGrid control in XAML page.

{% tabs %}
{% highlight xaml %}
<Page x:Class="GettingStarted.MainPage"
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
      xmlns:local="using:GettingStarted"
      xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
      xmlns:syncfusion="using:Syncfusion.UI.Xaml.Grid"
      mc:Ignorable="d">
    <Grid>
        <syncfusion:SfDataGrid x:Name="dataGrid" />
    </Grid>  
  
</Page>
{% endhighlight %}
{% endtabs %}

### Adding control manually in C\#

In order to add control manually in C#, do the below steps,

1. Add the below required assembly references to the project,

    * Syncfusion.Data.UWP
    * Syncfusion.SfGrid.UWP
    * Syncfusion.SfInput.UWP
    * Syncfusion.SfShared.UWP

2. Import SfDataGrid namespace **Syncfusion.UI.Xaml.Grid**.

3. Create SfDataGrid control instance and add it to the Page.

{% tabs %}
{% highlight c# %}
using Syncfusion.UI.Xaml.Grid;
namespace GettingStarted
{
    /// <summary>
    /// An empty page that can be used on its own or navigated to within a Frame.
    /// </summary>

    public sealed partial class MainPage : Page
    {

        public MainPage()
        {
            this.InitializeComponent();
            SfDataGrid dataGrid = new SfDataGrid();
            Root_Grid.Children.Add(dataGrid);
        }
    }
}
{% endhighlight %}
{% endtabs %}

### Creating Data Model for sample application

SfDataGrid is a data-bound control. So before create binding to the control, you must create data model for Application.

1. Create data object class named **OrderInfo** and declare properties as shown below,

{% tabs %}
{% highlight c# %}
public class OrderInfo
{
    int orderID;
    string customerId;
    string country;
    string customerName;
    string shippingCity;

    public int OrderID
    {
        get { return orderID; }
        set { orderID = value; }
    }

    public string CustomerID
    {
        get { return customerId; }
        set { customerId = value; }
    }

    public string CustomerName
    {
        get { return customerName; }
        set { customerName = value; }
    }

    public string Country
    {
        get { return country; }
        set { country = value; }
    }

    public string ShipCity
    {
        get { return shippingCity; }
        set { shippingCity = value; }
    }

    public OrderInfo(int orderId, string customerName, string country, string customerId, string shipCity)
    {
        this.OrderID = orderId;
        this.CustomerName = customerName;
        this.Country = country;
        this.CustomerID = customerId;
        this.ShipCity = shipCity;
    }
}
{% endhighlight %}
{% endtabs %}

N> If you want your data object (OrderInfo class) to automatically reflect property changes, then the object must implement **INotifyPropertyChanged** interface.

2.Create a **ViewModel** class with Orders property and Orders property is initialized with several data objects in constructor. 

{% tabs %}
{% highlight c# %}
public class ViewModel
{
    private ObservableCollection<OrderInfo> _orders;

    public ObservableCollection<OrderInfo> Orders
    {
        get { return _orders; }
        set { _orders = value; }
    }

    public ViewModel()
    {
        _orders = new ObservableCollection<OrderInfo>();
        this.GenerateOrders();
    }

    private void GenerateOrders()
    {
        _orders.Add(new OrderInfo(1001, "Maria Anders", "Germany", "ALFKI", "Berlin"));
        _orders.Add(new OrderInfo(1002, "Ana Trujillo", "Mexico", "ANATR", "Mexico D.F."));
        _orders.Add(new OrderInfo(1003, "Antonio Moreno", "Mexico", "ANTON", "Mexico D.F."));
        _orders.Add(new OrderInfo(1004, "Thomas Hardy", "UK", "AROUT", "London"));
        _orders.Add(new OrderInfo(1005, "Christina Berglund", "Sweden", "BERGS", "Lula"));
        _orders.Add(new OrderInfo(1006, "Hanna Moos", "Germany", "BLAUS", "Mannheim"));
        _orders.Add(new OrderInfo(1007, "Frederique Cite aux", "France", "BLONP", "Strasbourg"));
        _orders.Add(new OrderInfo(1008, "Martin", "Spain", "BOLID", "Madrid"));
        _orders.Add(new OrderInfo(1009, "Laurence", "France", "BONAP", "Marseille"));
        _orders.Add(new OrderInfo(1010, "Elizabeth Lincoln", "Canada", "BOTTM", "Tsawassen"));
    }
}

{% endhighlight %}
{% endtabs %}

### Binding to Data

To bind the SfDataGrid to data, set the [SfDataGrid.ItemsSource](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_ItemsSource) property to an **IEnumerable** implementation. Each row in SfDataGrid is bound to an object in data source and each column in SfDataGrid bound to a property in data object.

Bind the collection created in previous step to `SfDataGrid.ItemsSource` property in XAML by setting ViewModel as DataContext.

{% tabs %}
{% highlight xml %}
<Page x:Class="GettingStarted.MainPage"
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
      xmlns:local="using:GettingStarted"
      xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
      xmlns:syncfusion="using:Syncfusion.UI.Xaml.Grid"
      mc:Ignorable="d">
    <Page.DataContext>
        <local:ViewModel />
    </Page.DataContext>
    <Grid>
        <syncfusion:SfDataGrid x:Name="dataGrid"
                               AutoGenerateColumns="True"
                               ItemsSource="{Binding Orders}" />
    </Grid>
</Page>
{% endhighlight %}
{% endtabs %}

In another way, set the `SfDataGrid.ItemsSource` property in C# as follows,

{% tabs %}
{% highlight c# %}
ViewModel viewModel = new ViewModel();
dataGrid.ItemsSource = viewModel.Orders;
{% endhighlight %}
{% endtabs %}

Now, run the application and you can expect the see the below output,

![Binding to Data](Getting-Started_images/Getting-Started_img2.png)



## Defining Columns

By default, the SfDataGrid control generates the columns automatically when value assigned to [SfDataGrid.ItemsSource](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_ItemsSource) property. The type of the column generated depends on the type of data in the column and the attribute of the property the column bound with. 

The following table lists the column types and it’s constraints for auto column generation.

<table>
<tr>
<th>
Generated Column Type
</th>
<th>
Data Type / Attribute
</th>
</tr>
<tr>
<td>
GridTextColumn
</td>
<td>
Property of type String and any other type apart from below specified cases.
</td>
</tr>
<tr>
<td>
GridNumericColumn
</td>
<td>
Property of type Int or Double
</td>
</tr>   
<tr>
<td>
GridDateTimeColumn
</td>
<td>
Property of type DateTime
</td>
</tr>
<tr>
<td>
GridCheckBoxColumn
</td>
<td>
Property of type Bool
</td>
</tr>
</table>

When columns are auto-generated, you can handle the [SfDataGrid.AutoGeneratingColumn](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event to customize or cancel the columns before they are added to the SfDataGrid. 

You can prevent the automatic column generation by setting SfDataGrid.AutoGenerateColumns property to `false`. When [SfDataGrid.AutoGenerateColumns](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_AutoGenerateColumns) property is `false`, you have to define the columns to be displayed as below,

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"  
                       ItemsSource="{Binding Orders}" 
                       AutoGenerateColumns="False">
                       
    <syncfusion:SfDataGrid.Columns>
        <syncfusion:GridTextColumn MappingName="CustomerID"/>
        <syncfusion:GridTextColumn MappingName="CustomerName"/>
    </syncfusion:SfDataGrid.Columns>
    
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
SfDataGrid dataGrid = new SfDataGrid();
dataGrid.AutoGenerateColumns = false;
dataGrid.Columns.Add(new GridTextColumn() { MappingName = "CustomerID" });
dataGrid.Columns.Add(new GridTextColumn() { MappingName = "CustomerName" });
{% endhighlight %}
{% endtabs %}

Below are the list of column types provided in SfDataGrid.

<table>
<tr>
<th>
Column Type
</th>
<th>
Comments
</th>
</tr>
<tr>
<td>
GridTextColumn
</td>
<td>
Represents SfDataGrid column that hosts textual content in its cells.
</td>
</tr>
<tr>
<td>
GridNumericColumn
</td>
<td>
Represents SfDataGrid column that hosts {{'[SfNumericTextBox](https://help.syncfusion.com/uwp/numeric-textbox/overview)'| markdownify}} controls in its cells which is used to format and display Numeric values.
</td>
</tr>
<tr>
<td>
GridDateTimeColumn
</td>
<td>
Represents SfDataGrid column that hosts {{'[SfDatePicker](https://help.syncfusion.com/uwp/datepicker/overview)'| markdownify}} controls in its cells which is used to display and format DateTime values.
</td>
</tr>
<tr>
<td>
GridComboBoxColumn
</td>
<td>
Represents SfDataGrid column that hosts <code>ComboBox</code> controls in its cells.
</td>
</tr>
<tr>
<td>
GridCheckBoxColumn
</td>
<td>
Represents SfDataGrid column that hosts <code>CheckBox</code> controls in its cells.
</td>
</tr>
<tr>
<td>
GridImageColumn
</td>
<td>
Represents SfDataGrid column that hosts <code>Image</code> controls in its cells.
</td>
</tr>
<tr>
<td>
GridHyperlinkColumn
</td>
<td>
Represents SfDataGrid column that hosts <code>HyperlinkButton</code> controls in its cells.
</td>
</tr>
<tr>
<td>
GridTemplateColumn
</td>
<td>
Represents SfDataGrid column that hosts template-specified content in its cells
</td>
</tr>
<tr>
<td>
GridUnboundColumn
</td>
<td>
Represents SfDataGrid column that hosts textual or template-specified content which are not actually bound with data object of row.
</td>
</tr>
<tr>
<td>
GridMultiColumnDropdownList
</td>
<td>
Represents SfDataGrid column that hosts <code> SfMultiColumnDropDownControl</code> in its cells.
</td>
</tr>
<tr>
<td>
GridUpDownColumn
</td>
<td>
Represents SfDataGrid column that hosts <code> SfNumericUpDown</code> in its cells.
</td>
</tr>
</table>

## Selection

By default, the entire row is selected when a user clicks a cell in a SfDataGrid. You can set the [SfDataGrid.SelectionMode](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_SelectionMode) property to specify whether a user can select single row or cell, or multiple rows or cells.  Set the [SfDataGrid.SelectionUnit](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_SelectionUnit) property to specify whether rows can be selected, or cells can selected.

When `SelectionUnit` is `Row`, you can get information about the rows that are selected using [SfDataGrid.SelectedItem](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_SelectedItem) and [SfDataGrid.SelectedItems](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_SelectedItems) properties. 

When `SfDataGrid.SelectionUnit` is `Cell`, you can get information about the cells that are selected by calling [SfDataGrid.GetSelectedCells](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_GetSelectedCells) method.

You can handle the selection operations with the help of [SfDataGrid.SelectionChanging](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_SelectionChanging) and [SfDataGrid.SelectionChanged](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_SelectionChanged) events of SfDataGrid.

## Sorting, Grouping, and Filtering

### Sorting

By default, you can sort columns in a SfDataGrid by clicking the column header. You can configure the sorting by setting [SfDataGrid.SortColumnDescriptions](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_SortColumnDescriptions) property as below,

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"  ItemsSource="{Binding Orders}" >
    <syncfusion:SfDataGrid.SortColumnDescriptions>
        <syncfusion:SortColumnDescription ColumnName="CustomerName"/>
    </syncfusion:SfDataGrid.SortColumnDescriptions>
    
</syncfusion:SfDataGrid>
{% endhighlight %}
{% endtabs %}


![Sorting](Getting-Started_images/Getting-Started_img3.png)



You can customize sorting by handling the [SfDataGrid.SortColumnsChanging](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_SortColumnsChanging) and [SfDataGrid.SortColumnsChanged](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_SortColumnsChanged) events. To cancel the default sort, set the Cancel property to true in `SfDataGrid.SortColumnsChanging` event. 

{% tabs %}
{% highlight c# %}
this.dataGrid.SortColumnsChanging += dataGrid_SortColumnsChanging;

void dataGrid_SortColumnsChanging(object sender, GridSortColumnsChangingEventArgs e)
{

    if (e.AddedItems[0].ColumnName == "CustomerName")
        e.Cancel = true;
}
{% endhighlight %}
{% endtabs %}

### Grouping

Grouping can be enabled by setting [SfDataGrid.ShowGroupDropArea](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_ShowGroupDropArea) property, where you can group by dragging the column header and dropping it in the GroupDropArea over the column headers. You can configure the grouping by setting [SfDataGrid.GroupColumnDescriptions](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_GroupColumnDescriptions) property as below,

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"  ItemsSource="{Binding Orders}" > 
    <syncfusion:SfDataGrid.GroupColumnDescriptions>
        <syncfusion:GroupColumnDescription ColumnName="CustomerName"/>
    </syncfusion:SfDataGrid.GroupColumnDescriptions>
    
</syncfusion:SfDataGrid>
{% endhighlight %}
{% endtabs %}

![Grouping](Getting-Started_images/Getting-Started_img4.png)



### Filtering

Filtering can be enabled by setting [SfDataGrid.AllowFiltering](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_AllowFiltering) property to `true`, where you can open advanced filter UI by clicking the Filter icon in column header and filter the SfDataGrid. You can customize the filtering operations by handling [SfDataGrid.FilterChanging](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_FilterChanging) and [SfDataGrid.FilterChanged](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_FilterChanged) events.

![Filtering](Getting-Started_images/Getting-Started_img5.png)



## Editing

Editing can be enabled by setting [SfDataGrid.AllowEditing](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_AllowEditing) property to `true`. Set [SfDataGrid.AllowDeleting](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_AllowDeleting) property to specify whether user can delete rows by pressing <kbd>Delete</kbd> key. 

Set [SfDataGrid.AddNewRowPosition](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_AddNewRowPosition) property to enable additional row either `Top` or `Bottom` of SfDataGrid, where user can enter new items into the blank row. Adding new row adds an item to the [SfDataGrid.ItemsSource](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_ItemsSource). 

You can customize the editing operations by handling [SfDataGrid.CurrentCellBeginEdit](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_CurrentCellBeginEdit) and [SfDataGrid.CurrentCellEndEdit](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_CurrentCellEndEdit) events.
