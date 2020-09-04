---
layout: post
title: Columns | DataGrid Control for UWP | Syncfusion
description: This section explains about the columns manipulation and customization in Syncfusion UWP DataGrid (SfDataGrid) control
platform: uwp
control: SfDataGrid
documentation: ug
---

# Columns in UWP DataGrid (SfDataGrid)

SfDataGrid allows you to add or remove columns using [SfDataGrid.Columns](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_Columns) property. You can choose the columns to be added from built-in column types or you can create your own column and add to the `SfDataGrid.Columns`. 

Below are the built-in column types supported in SfDataGrid. Each column has its own properties to handle different types of data.

<table>
<tr>
<th>
Column Type
</th>
<th>
Description
</th>
</tr>
<tr>
<td>
{{'[GridTextColumn](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridTextColumn.html)'| markdownify }}
</td>
<td>
Use to display the string data. 
</td>
</tr>
<tr>
<td>
{{'[GridNumericColumn](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridNumericColumn.html)'| markdownify }}
</td>
<td>
Use to display the numeric data.
</td>
</tr>
<tr>
<td>
{{'[GridDateTimeColumn](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridDateTimeColumn.html)'| markdownify }}
</td>
<td>
Use to display the date time value 
</td>
</tr>
<tr>
<td>
{{'[GridComboBoxColumn](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridComboBoxColumn.html)'| markdownify }}
</td>
<td>
Use to display the IEnumerable data using ComboBox.
</td>
</tr>
<tr>
<td>
{{'[GridCheckBoxColumn](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCheckBoxColumn.html)'| markdownify }}
</td>
<td>
Use to display the boolean type data
</td>
</tr>
<tr>
<td>
{{'[GridImageColumn](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridImageColumn.html)'| markdownify }}
</td>
<td>
Use to display the image in each row.
</td>
</tr>
<tr>
<td>
{{'[GridHyperlinkColumn](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridHyperlinkColumn.html)'| markdownify }}
</td>
<td>
Use to display the <code>Uri</code> data
</td>
</tr>
<tr>
<td>
{{'[GridTemplateColumn](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridTemplateColumn.html)'| markdownify }}
</td>
<td>
Use to display the custom template-specified content.
</td>
</tr>
<tr>
<td>
{{'[GridUnboundColumn](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridUnBoundColumn.html)'| markdownify }}
</td>
<td>
Use to display custom information of each record.
</td>
</tr>
<tr>
<td>
{{'[GridMultiColumnDropDownList](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridMultiColumnDropDownList.html)'| markdownify }}
</td>
<td>
Use to display the IEnumerable data using SfMultiColumnDropdownControl.
</td>
</tr>
<tr>
<td>
{{'[GridUpDownColumn](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridUpDownColumn.html)'| markdownify }}
</td>
<td>
Use to display the numeric values .
</td>
</tr>
</table>

## Defining Columns

You can let the SfDataGrid to create columns or you can manually define columns to be displayed. Below sections explains both ways,
 
1. Automatically generating columns
2. Manually define columns

### Automatically generating columns

The automatic column generation based on properties of data object can be enabled or disabled by setting [SfDataGrid.AutoGenerateColumns](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_AutoGenerateColumns). Default value is `true`.

Columns are generated based on type of property. For example, `GridNumericColumn` is added for `int` type property. 

Below are table shows data type and its column type. For remaining types, `GridTextColumn` will be added.
  
<table>
<tr>
<th>
Data Type
</th>
<th>
Column
</th>
</tr>
<tr>
<td>
string, object, dynamic
</td>
<td>
GridTextColumn
</td>
</tr>
<tr>
<td>
int, float, double, decimal and also it’s nullable
</td>
<td>
GridNumericColumn
</td>
</tr>
<tr>
<td>
DateTime, DateTimeOffset and also it’s nullable
</td>
<td>
GridDateTimeColumn
</td>
</tr>
<tr>
<td>
Uri, Uri?
</td>
<td>
GridHyperLinkColumn
</td>
</tr>
<tr>
<td>
bool, bool?
</td>
<td>
GridCheckBoxColumn
</td>
</tr>
<tr>
<td>
TimeSpan, TimeSpan?
</td>
<td>
GridTimeSpanColumn
</td>
</tr>
</table>

N> The order of columns in the collection will determine the order of that they will appear in SfDataGrid.

#### AutoGenerateColumns with different modes

Column auto generation is controlled using [SfDataGrid.AutoGenerateColumnsMode](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_AutoGenerateColumnsMode) property.
 
The `SfDataGrid.AutoGenerateColumnsMode` includes the following modes.

<table>
<tr>
<th>
Mode
</th>
<th>
Behavior
</th>
<th>
When ItemsSource changed
</th>
</tr>
<tr>
<td>
Reset
</td>
<td>
Generates the columns based on the properties defined in the underlying data object.
</td>
<td>
Keeps the columns added manually. 
Clears the columns which are auto generated before and creates new columns based on new ItemsSource.
</td>
</tr>
<tr>
<td>
RetainOld
</td>
<td>
Generates the columns based on the properties defined in the underlying data object if the columns are not defined explicitly.
</td>
<td>
The same columns will be maintained when changing ItemsSource also. So filtering, sorting and grouping settings will be maintained.
</td>
</tr>
<tr>
<td>
ResetAll
</td>
<td>
Generates the columns based on the properties defined in the underlying data object.
</td>
<td>
Clear all the columns including the columns defined manually and creates new columns based on new ItemsSource.
</td>
</tr>
<tr>
<td>
None
</td>
<td>
Columns will not be generated.
</td>
<td>
Keeps old columns in DataGrid.Columns collection.
</td>
</tr>
</table>

#### Auto generating CustomType Property
Custom type properties in data object can be auto-generated by setting [AutoGenerateColumnsForCustomType](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_AutoGenerateColumnsForCustomType) property as true. Default value is false.
Custom type properties will be auto-generated through [AutoGenerateColumnsModeForCustomType](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_AutoGenerateColumnsModeForCustomType) property.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid ItemsSource="{Binding Source}" AllowEditing="True" 
                               AllowFiltering="True" x:Name="dataGrid" 
							   AutoGenerateColumnsForCustomType="True"
                               AllowSorting="True" AddNewRowInitiating="dataGrid_AddNewRowInitiating" 
                               AutoGenerateColumnsModeForCustomType="Both"
                               GridCopyOption="CopyData" GridPasteOption="PasteData"
                               AddNewRowPosition="FixedTop" FilterRowPosition="FixedTop" 
                               ShowGroupDropArea="True" 
                               ColumnSizer="Star" >
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
this.dataGrid.AutoGenerateColumnsForCustomType = true;
this.dataGrid.AutoGenerateColumnsModeForCustomType = AutoGenerateColumnsModeForCustomType.Parent;             
{% endhighlight %}
{% endtabs %}

The `AutoGenerateColumnsModeForCustomType` includes the following modes.

<table>
<tr>
<th>
Mode
</th>
<th>
Behavior
</th>
</tr>
<tr>
<td>
<code>Both</code>
</td>
<td>
Specifies that the columns for both the custom type and its inner properties will be auto generated.
</td>
</tr>
<tr>
<td>
<code>Child</code>
</td>
<td>
Specifies that the columns for all inner properties of custom type column will be auto generated. 
</td>
</tr>
<tr>
<td>
<code>Parent</code>
</td>
<td>
Specifies that the column for only the custom type will be auto generated.
</td>
</tr>
</table>

You can download the sample demo [here](https://github.com/SyncfusionExamples/how-to-auto-generate-columns-for-custom-type-properties-in-uwp-and-wpf-datagrid) .

#### Customize auto-generated columns

You can customize or cancel the generated column by handling [AutoGeneratingColumn](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event.
 
`AutoGeneratingColumn` event occurs when the individual column is auto-generated for public and non-static property of underlying data object.

{% tabs %}
{% highlight c# %}
this.dataGrid.AutoGeneratingColumn += dataGrid_AutoGeneratingColumn;

void dataGrid_AutoGeneratingColumn(object sender, AutoGeneratingColumnArgs e)
{
}
{% endhighlight %}
{% endtabs %}

[AutoGeneratingColumnArgs](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.AutoGeneratingColumnArgs.html) provides the information about the auto-generated column to the `AutoGeneratingColumn` event. [AutoGeneratingColumnArgs.Column](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.AutoGeneratingColumnArgs.html#Syncfusion_UI_Xaml_Grid_AutoGeneratingColumnArgs_Column) property returns the newly created column.

##### Cancel column generation for particular property

You can cancel the specific column adding to the DataGrid by handling `AutoGeneratingColumn` event.

In the below code, column generation for `OrderID` property is canceled by setting `Cancel` property to `true`.
 
{% tabs %}
{% highlight c# %}
this.dataGrid.AutoGeneratingColumn += dataGrid_AutoGeneratingColumn;

void dataGrid_AutoGeneratingColumn(object sender, AutoGeneratingColumnArgs e)
{

    if (e.Column.MappingName == "OrderID")
        e.Cancel = true;
}
{% endhighlight %}
{% endtabs %}

##### Changing column type

You can change the type of column adding to SfDataGrid by setting the instance of column you want to add in ` AutoGeneratingColumn` event.
 
In the below code, column type for `UnitPrice` property is changed to `GridTextColumn` by setting instance of GridTextColumn to `Column` property.
 
{% tabs %}
{% highlight c# %}
this.dataGrid.AutoGeneratingColumn += dataGrid_AutoGeneratingColumn;

void dataGrid_AutoGeneratingColumn(object sender, AutoGeneratingColumnArgs e)
{

    if (e.Column.MappingName == "UnitPrice")
    {

        if (e.Column is GridNumericColumn)
        {
            e.Column = new GridTextColumn() { MappingName = "UnitPrice", HeaderText = "Unit Price" };
        }       
    }
}     
{% endhighlight %}
{% endtabs %}

##### Changing property settings

You can change the column properties in `AutoGeneratingColumn` event handler. 

{% tabs %}
{% highlight c# %}
this.dataGrid.AutoGeneratingColumn += dataGrid_AutoGeneratingColumn;

void dataGrid_AutoGeneratingColumn(object sender, AutoGeneratingColumnArgs e)
{

    if(e.Column.MappingName=="OrderID")
    {
        e.Column.AllowEditing = false;
        e.Column.AllowSorting = true;
        e.Column.AllowFiltering = true;
        e.Column.AllowGrouping = false;
        e.Column.AllowFocus = true;
        e.Column.AllowResizing = false;
        e.Column.ColumnSizer = GridLengthUnitType.Auto;
        e.Column.AllowDragging = true;        
    }
}
{% endhighlight %}
{% endtabs %}

#### Setting template to auto-generated column

You can set [GridColumn.HeaderTemplate](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridColumnBase.html#Syncfusion_UI_Xaml_Grid_GridColumnBase_HeaderTemplate) and [GridColumn.CellTemplate](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridColumnBase.html#Syncfusion_UI_Xaml_Grid_GridColumnBase_CellTemplate) properties for auto-generated column in `AutoGeneratingColumn` event handler.
 
{% tabs %}
{% highlight xaml %}
<Page.Resources>
    <DataTemplate x:Key="headerTemplate">
        <TextBlock Text="The product has been purchased by the following OrderID" TextWrapping="Wrap" />
    </DataTemplate>
        
</Page.Resources>
{% endhighlight %}
{% endtabs %}


{% tabs %}
{% highlight c# %}
this.dataGrid.AutoGeneratingColumn += dataGrid_AutoGeneratingColumn;

void dataGrid_AutoGeneratingColumn(object sender, AutoGeneratingColumnArgs e)
{

    if (e.Column.MappingName == "OrderID")
    {
        e.Column.HeaderTemplate = this.FindResource("headerTemplate") as DataTemplate;
    }
}
{% endhighlight %}
{% endtabs %}

Below screenshot shows the customized header template loaded on the header of OrderID column.

![Setting template to auto-generated column](Columns_images/Columns_img1.png)

#### Data Annotations with AutoGenerateColumns

SfDataGrid support to generate the columns based on built-in [Data Annotation Attributes](https://msdn.microsoft.com/en-us/library/mt185499.aspx). 

Data Annotations ignored, when the `AutoGenerateColumns` is set to `False`.

##### Exclude column

You can skip the column generation using `AutoGenerateField` property to `false`.

{% tabs %}
{% highlight c# %}
[Display(AutoGenerateField = false, Description = "OrderID field is not generated in UI")]

public int OrderID
{
    get { return orderID; }
    set { orderID = value; }
}
{% endhighlight %}
{% endtabs %}

##### Filtering

You can enable filtering automatically for the field using `Display.AutoGenerateFilter` property.

{% tabs %}
{% highlight c# %}
[Display(AutoGenerateFilter = true, Description = "Filter enabled for CustomerID column")]

public string CustomerID
{
    get { return customerId; }
    set { customerId = value; }
}
{% endhighlight %}
{% endtabs %}

##### Editing
 
You can change the value of the property using `Editable` attribute.

{% tabs %}
{% highlight c# %}
[Editable(true)]

public string Country
{
    get { return country; }
    set { country = value; }
}
{% endhighlight %}
{% endtabs %}

##### Change the HeaderText of column

You can customize header text of column using `Display.Name` property.

{% tabs %}
{% highlight c# %}
[Display(Name="Name of the Customer",Description="CustomerName is necessary for identification ")]

public string CustomerName
{
    get { return customerName; }
    set { customerName = value; }
}
{% endhighlight %}
{% endtabs %}

##### Change the order of the columns

You can change the columns order using `DisplayAttribute.Order` property.

{% tabs %}
{% highlight c# %}
[Display(Order=0)]
public int OrderID
{
    get { return orderID; }
    set { orderID = value; }
}

[Display(Order=-1)]
public string CustomerID
{
    get { return customerId; }
    set { customerId = value; }
}
{% endhighlight %}
{% endtabs %}

The OrderID and CustomerID column rearranged based on specified order.

![Change the order of the columns](Columns_images/Columns_img2.png)

### Manually defining columns

SfDataGrid control allows you to define the columns manually by adding desired column to the [SfDataGrid.Columns](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_Columns) collection.
 
{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       AutoGenerateColumns="False"
                       ItemsSource="{Binding Orders}">

    <syncfusion:SfDataGrid.Columns>

        <syncfusion:GridTextColumn HeaderText="Order ID" MappingName="OrderID" />

        <syncfusion:GridTextColumn HeaderText="Customer ID" MappingName="CustomerID" />

        <syncfusion:GridTextColumn HeaderText="Customer Name" 

MappingName="CustomerName" />

    </syncfusion:SfDataGrid.Columns>

</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
this.dataGrid.Columns.Add(new GridTextColumn() { HeaderText = "Order ID", MappingName = "OrderID" });
this.dataGrid.Columns.Add(new GridTextColumn() { HeaderText = "Customer ID", MappingName = "CustomerID" });
this.dataGrid.Columns.Add(new GridTextColumn() { HeaderText = "Customer Name", MappingName = "CustomerName" });
this.dataGrid.Columns.Add(new GridTextColumn() { HeaderText = "Country", MappingName = "Country" });
this.dataGrid.Columns.Add(new GridNumericColumn() { HeaderText = "Unit Price", MappingName = "UnitPrice" });             
{% endhighlight %}
{% endtabs %}

You can refer more information about handling the column level operations for manually defined columns in Column types section.

## Column manipulation

You can get the columns (added or auto-generated) from [SfDataGrid.Columns](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_Columns) property.
 
### Adding column

You can add column at runtime by adding instance of column to `SfDataGrid.Columns` property.

{% tabs %}
{% highlight c# %}
this.dataGrid.Columns.Add(new GridTextColumn() { HeaderText = "Order ID", MappingName = "OrderID" });
{% endhighlight %}
{% endtabs %}

### Accessing column

You can access the column through its column index or `GridColumn.MappingName` from the SfDataGrid.Columns collection.

{% tabs %}
{% highlight c# %}
GridColumn column = this.dataGrid.Columns[1];
//OR
GridColumn column = this.dataGrid.Columns["OrderID"];
{% endhighlight %}
{% endtabs %}

### Clearing or Removing Column

You can remove all the columns by clearing the `SfDataGrid.Columns` property.

{% tabs %}
{% highlight c# %}
this.dataGrid.Columns.Clear();
{% endhighlight %}
{% endtabs %}

You can remove a column using `Remove` and `RemoveAt` methods.

{% tabs %}
{% highlight c# %}
dataGrid.Columns.Remove(column);
//OR
dataGrid.Columns.RemoveAt(1);
{% endhighlight %}
{% endtabs %}

You can also remove the column under one stacked column from StackedHeaderRow.

{% tabs %}
{% highlight c# %}
var childColumns = this.dataGrid.StackedHeaderRows[1].StackedColumns[0].ChildColumns.Split(',');

foreach (var name in childColumns)
{
    var column = dataGrid.Columns[name];
    if (column == null)
        continue;
    dataGrid.Columns.Remove(column);
}
{% endhighlight %}
{% endtabs %}

## Resizing Columns

SfDataGrid allows to resize the columns like in excel by resizing column header. This can be enabled or disabled by setting [SfDataGrid.AllowResizingColumns](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_AllowResizingColumns) or [GridColumn.AllowResizing](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridColumn.html#Syncfusion_UI_Xaml_Grid_GridColumn_AllowResizing) property.
 
N> Resizing considers MinWidth and MaxWidth of column.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid  x:Name="dataGrid"
                        AllowResizingColumns="True"
                        AutoGenerateColumns="True"
                        ItemsSource="{Binding Orders}" />
{% endhighlight %}
{% endtabs %}

You can change the column width by click and dragging the resizing cursor at the edge of column header. The resizing cursor appears when you hover the grid line exists between two columns.
 
![Resizing Columns](Columns_images/Columns_img3.png)

### Hidden column resizing

SfDataGrid shows indication for hidden columns in column header and also allows end-users to resize the hidden columns when setting [SfDataGrid.AllowResizingHiddenColumns](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_AllowResizingHiddenColumns) property to `true`.

![Hidden column resizing](Columns_images/Columns_img4.png)

### Disable resizing

You can cancel resizing of particular column by setting [GridColumn.AllowResizing](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridColumn.html#Syncfusion_UI_Xaml_Grid_GridColumn_AllowResizing) property to `false`. In another way, you can cancel the resizing by handling [SfDataGrid.ResizingColumns](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event. The `ResizingColumns` event occurs when you start dragging by resizing cursor on headers.
 
[ResizingColumnsEventArgs](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.ResizingColumnsEventArgs.html) of `ResizingColumns` provides information about the columns’s index and width.

{% tabs %}
{% highlight c# %}
this.dataGrid.ResizingColumns += dataGrid_ResizingColumns;

void dataGrid_ResizingColumns(object sender, ResizingColumnsEventArgs e)
{    
    if(e.ColumnIndex == 1)            
        e.Cancel = true;         
}
{% endhighlight %}
{% endtabs %}

### Identify resizing of the column gets completed

SfDataGrid allows you to identify the progress of the resizing of columns through [ResizingColumnsEventArgs.Reason](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.ResizingColumnsEventArgs.html#Syncfusion_UI_Xaml_Grid_ResizingColumnsEventArgs_Reason) property. You can get the width of the column after resizing completed by getting [ResizingColumnsEventArgs.Width](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.ResizingColumnsEventArgs.html#Syncfusion_UI_Xaml_Grid_ResizingColumnsEventArgs_Width) when `ResizingColumnsEventArgs.Reason` is [ColumnResizingReason.Resized](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.ColumnResizingReason.html) in [ResizingColumns](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event.

{% tabs %}
{% highlight c# %}
this.dataGrid.ResizingColumns += OnResizingColumns;

void OnResizingColumns(object sender, ResizingColumnsEventArgs e)
{
    if (e.Reason == Syncfusion.UI.Xaml.Grid.ColumnResizingReason.Resized)
    {
        var resizedWidth = e.Width;
    }
}
{% endhighlight %}
{% endtabs %}

## Column drag and drop

You can allow end-users to rearrange the columns by drag and drop the column headers by setting [SfDataGrid.AllowDraggingColumns](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_AllowDraggingColumns) to `true`.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid  x:Name="dataGrid"
                        AllowDraggingColumns="True"
                        AutoGenerateColumns="True"
                        ItemsSource="{Binding Orders}" />
{% endhighlight %}
{% endtabs %}


![Column drag and drop](Columns_images/Columns_img5.png)



You can enable or disable dragging on particular column using [GridColumn.AllowDragging](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridColumn.html#Syncfusion_UI_Xaml_Grid_GridColumn_AllowDragging) property.

{% tabs %}
{% highlight xaml %}
<syncfusion:GridTextColumn  AllowDragging="False"
                            HeaderText="Order ID"
                            MappingName="OrderID" />
{% endhighlight %}
{% endtabs %}

### Disable column reordering

You can cancel the particular column dragging by handling [SfDataGrid.QueryColumnDragging](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html). `QueryColumnDragging` event occurs when you start dragging the column header. [QueryColumnDraggingEventArgs](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.QueryColumnDraggingEventArgs.html) of `QueryColumnDragging` event provides information about the column triggered this event.
 
`QueryColumnDraggingEventArgs.From` property returns the index of column triggered this event. `QueryColumnDraggingEventArgs.To` property returns the index where you try to drop the column. `QueryColumnDraggingEventArgs.Reason` returns column dragging details by `QueryColumnDraggingReason`.

{% tabs %}
{% highlight c# %}
this.dataGrid.QueryColumnDragging += dataGrid_QueryColumnDragging;

void dataGrid_QueryColumnDragging(object sender, QueryColumnDraggingEventArgs e)
{
    var column = dataGrid.Columns[e.From];
    
    if (column.MappingName == "CustomerName" && e.Reason == QueryColumnDraggingReason.Dropping)
    {
        e.Cancel = true;
    }
}
{% endhighlight %}
{% endtabs %}

### Drag and drop customization 

The drag-and-drop operations can be changed by overriding the virtual methods of [GridColumnDragDropController](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridColumnDragDropController.html) class and assigning it to `SfDataGrid.GridColumnDragDropController`.
 
{% tabs %}
{% highlight c# %}
this.dataGrid.GridColumnDragDropController = new CustomDragDropController(dataGrid);

public class CustomDragDropController:GridColumnDragDropController
{
    public CustomDragDropController(SfDataGrid dataGrid) : base(dataGrid)
    {
    }

    //Returns whether the popup showed its header or not.
    public override bool CanShowPopup(GridColumn column)
    {
        return base.CanShowPopup(column);
    }

    //Get the corresponding GridRegion at a given point.
    public override GridRegion PointToGridRegion(Point point)
    {
        return base.PointToGridRegion(point);
    }

    //Occurs when the GridColumn.Hidden property value changed.
    protected override void OnColumnHiddenChanged(GridColumn column)
    {
        base.OnColumnHiddenChanged(column);
    }

    //Occurs when the popup content is created.
    protected override UIElement CreatePopupContent(GridColumn column)
    {
        return base.CreatePopupContent(column);
    }

    //Occurs when the popup content is dropped on DataGrid.
    protected override void PopupContentDroppedOnGrid(Point point)
    {
        base.PopupContentDroppedOnGrid(point);
    }

    //Occurs when the popup content is dropped on header row.
    protected override void PopupContentDroppedOnHeaderRow(int oldIndex, int newColumnIndex)
    {
        base.PopupContentDroppedOnHeaderRow(oldIndex, newColumnIndex);
    }

    //Occurs when the popup content is dropped.
    protected override void OnPopupContentDropped(Point point, Point pointOverGrid)
    {
        base.OnPopupContentDropped(point, pointOverGrid);
    }

    //Occurs when the popup content is dropped on GroupDropArea
    protected override void PopupContentDroppedOnGroupDropArea(GridColumn column)
    {
        base.PopupContentDroppedOnGroupDropArea(column);
    }

    //Occurs when the popup content position changed.
    protected override void OnPopupContentPositionChanged(double HorizontalDelta, double VerticalDelta, Point mousePoint, Point mousePointOverGrid)
    {
        base.OnPopupContentPositionChanged(HorizontalDelta, VerticalDelta, mousePoint, mousePointOverGrid);
    }      
}
{% endhighlight %}
{% endtabs %}

### Disabling drag & drop between frozen and non-frozen columns

By default, the columns re-ordering performed between any column regions of columns. You can cancel the dropping action between the frozen and non-frozen columns by handling [SfDataGrid.QueryColumnDragging](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event.

{% tabs %}
{% highlight c# %}
this.dataGrid.QueryColumnDragging += dataGrid_QueryColumnDragging;

void dataGrid_QueryColumnDragging(object sender, QueryColumnDraggingEventArgs e)
{    
    if (e.Reason == QueryColumnDraggingReason.Dropping)
    {
        var frozenColIndex = this.dataGrid.FrozenColumnCount + this.dataGrid.ResolveToStartColumnIndex();

        if (e.From < frozenColIndex && e.To > frozenColIndex - 1)
            e.Cancel = true;
       
        if (e.From > frozenColIndex && e.To < frozenColIndex ||(e.From == frozenColIndex && e.To < frozenColIndex))
            e.Cancel = true;
    }
}
{% endhighlight %}
{% endtabs %}


N> FrozenColumnCount and FooterColumnCount should be lesser than the number of Columns that can be displayed in View.

## Freezing Columns 

You can freeze the columns in view at the left and right side like in excel by setting [SfDataGrid.FrozenColumnCount](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_FrozenColumnCount) and [SfDataGrid.FooterColumnCount](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_FooterColumnCount) properties.
 
{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid  x:Name="dataGrid"
                        AutoGenerateColumns="False"
                        FrozenColumnCount="2"
                        ItemsSource="{Binding Orders}"/>
{% endhighlight %}
{% endtabs %}


![Freezing Columns ](Columns_images/Columns_img6.png)

### Limitations

1. SfDataGrid has support to freeze the number of columns from the left or right. There is no support to freeze a specific column.

## Stacked Headers

SfDataGrid supports additional unbound header rows known as `stacked header rows` that span across the DataGrid columns using [StackedHeaderRows](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.StackedHeaderRows.html). You can group one or more columns under each stacked header.

Each [StackedHeaderRow](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.StackedHeaderRow.html) contains the [StackedColumns](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.StackedHeaderRow.html#Syncfusion_UI_Xaml_Grid_StackedHeaderRow_StackedColumns) where each [StackedColumn](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.StackedColumn.html) contains a number of child columns. `StackedColumn.ChildColumns` property returns the columns which are grouped under the stacked header row. The `StackedColumn.MappingName` is a unique name used for mapping a specific child columns grouped under the same stacked header row whereas, the `StackedColumn.HeaderText` returns the text that displays in stacked header row.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"         
                        ItemsSource="{Binding Orders}">
                        
    <syncfusion:SfDataGrid.StackedHeaderRows>
    
        <syncfusion:StackedHeaderRow>
        
            <syncfusion:StackedHeaderRow.StackedColumns>
                <syncfusion:StackedColumn ChildColumns="OrderID,CustomerID,CustomerName,ShipCity,Country" HeaderText="Sales Details" MappingName="SalesDetails"/>
            </syncfusion:StackedHeaderRow.StackedColumns>
            
        </syncfusion:StackedHeaderRow>
        
        <syncfusion:StackedHeaderRow>
        
            <syncfusion:StackedHeaderRow.StackedColumns>
            
                <syncfusion:StackedColumn ChildColumns="OrderID" HeaderText="Order Details" MappingName="OrderDetails"/>
                <syncfusion:StackedColumn ChildColumns="CustomerID,CustomerName" HeaderText="Customer Details" MappingName="CustomerDetails"/>
                <syncfusion:StackedColumn ChildColumns="ShipCity,Country" HeaderText="Shipping Details" MappingName="ShippingDetails"/>
                
            </syncfusion:StackedHeaderRow.StackedColumns>
            
        </syncfusion:StackedHeaderRow>
        
    </syncfusion:SfDataGrid.StackedHeaderRows>
    
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
var stackedHeaderRow = new StackedHeaderRow();
stackedHeaderRow.StackedColumns.Add(new StackedColumn() { ChildColumns = "OrderID" + "," + "CustomerID" + "," + "CustomerName" + "," + "ShipCity" + "," + "Country", HeaderText = "Sales Details" , MappingName="SalesDetails"  });
dataGrid.StackedHeaderRows.Add(stackedHeaderRow);
            
var stackedHeaderRow1 = new StackedHeaderRow();
stackedHeaderRow1.StackedColumns.Add(new StackedColumn() { ChildColumns = "OrderID", HeaderText = "Order Details" , MappingName="OrderDetails"  });            
stackedHeaderRow1.StackedColumns.Add(new StackedColumn() { ChildColumns = "CustomerID" + "," + "CustomerName", HeaderText = "Customer Details" , MappingName="CustomerDetails"  });
stackedHeaderRow1.StackedColumns.Add(new StackedColumn() { ChildColumns = "ShipCity" + "," + "Country", HeaderText = "Shipping Details" , MappingName="ShippingDetails"  });
dataGrid.StackedHeaderRows.Add(stackedHeaderRow1);
{% endhighlight %}
{% endtabs %}


![Stacked Headers](Columns_images/Columns_img7.png)

You can also add the stacked headers using `GroupName` property of [Data Annotations Display attributes](https://msdn.microsoft.com/en-us/library/system.componentmodel.dataannotations.displayattribute.aspx).
 
{% tabs %}
{% highlight c# %}
public class OrderInfo
{
    private int orderID;
    private string customerId;
    private string country;
    private string customerName;
    private string shippingCity;
        
    public int OrderID
    {
        get { return orderID; }
        set { orderID = value; }
    }

    [Display(GroupName = "Customer Details")]
    public string CustomerID
    {
        get { return customerId; }
        set { customerId = value; }
    }

    [Display(GroupName = "Customer Details")]        
    public string CustomerName
    {
        get { return customerName; }
        set { customerName = value; }
    }

    [Display(GroupName = "Shipping Details")]
    public string Country
    {
        get { return country; }
        set { country = value; }
    }

    [Display(GroupName = "Shipping Details")]
    public string ShipCity
    {
        get { return shippingCity; }
        set { shippingCity = value; }
    }
}
{% endhighlight %}
{% endtabs %}


![stacked headers using GroupName property](Columns_images/Columns_img8.png)

### Adding ChildColumns

You can add the child columns in particular stacked header directly.

{% tabs %}
{% highlight c# %}
var childColumn = this.dataGrid.StackedHeaderRows[1].StackedColumns[0].ChildColumns;
this.dataGrid.StackedHeaderRows[1].StackedColumns[0].ChildColumns = childColumn + "," + "OrderDate" + "," + "Discount";
{% endhighlight %}
{% endtabs %}

### Removing ChildColumns

Similarly, you can remove the child columns from particular stacked header directly.

{% tabs %}
{% highlight c# %}
var removingColumns = this.dataGrid.StackedHeaderRows[0].StackedColumns[0].ChildColumns.Split(',').ToList<string>();
   
string childColumns = string.Empty;

foreach(var stackedColumnName in removingColumns.ToList())
{
    if (stackedColumnName.Equals("OrderID"))
    {
        removingColumns.Remove(stackedColumnName);
    }
    
    else
        childColumns = childColumns + stackedColumnName + ",";
}

this.dataGrid.StackedHeaderRows[0].StackedColumns[0].ChildColumns = childColumns;
{% endhighlight %}
{% endtabs %}

### Changing stacked header row height

You can change the height of StackedHeaderRows by using [VisualContainer.RowHeights](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.VisualContainer.html#Syncfusion_UI_Xaml_Grid_VisualContainer_RowHeights) property.

{% tabs %}
{% highlight c# %}
using Syncfusion.UI.Xaml.Grid.Helpers;

var visualContainer = dataGrid.GetVisualContainer();            
int count = dataGrid.StackedHeaderRows.Count;

for (int i = 0; i < count; i++)
{               
    visualContainer.RowHeights[i] = 50;
}            

visualContainer.InvalidateMeasure();
{% endhighlight %}
{% endtabs %}

You can also change the height of stacked header rows using [SfDataGrid.QueryRowHeight](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event.
 
{% tabs %}
{% highlight c# %}
using Syncfusion.UI.Xaml.Grid;

this.dataGrid.QueryRowHeight += dataGrid_QueryRowHeight;

void dataGrid_QueryRowHeight(object sender, Syncfusion.UI.Xaml.Grid.QueryRowHeightEventArgs e)
{
    if(e.RowIndex <this.dataGrid.GetHeaderIndex())
    {
        e.Height = 50;
        e.Handled = true;
    }
}
{% endhighlight %}
{% endtabs %}

## Column Sizing

SfDataGrid allows you to set the column widths based on certain logic using [SfDataGrid.ColumnSizer](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_ColumnSizer) or [GridColumn.ColumnSizer](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridColumn.html#Syncfusion_UI_Xaml_Grid_GridColumn_ColumnSizer) property. 

Below is the list of predefined column sizing options available.

<table>
<tr>
<th>
Type
</th>
<th>
Column width
</th>
</tr>
<tr>
<td>
Star
</td>
<td>
Divides the total width equally for columns. 
</td>
</tr>
<tr>
<td>
Auto
</td>
<td>
Calculates the width of column based on header and cell contents. So that header and cell contents are not truncated.  
</td>
</tr>
<tr>
<td>
AutoWithLastColumnFill
</td>
<td>
Applies <code>GridLengthUnitType.Auto</code> width to all the columns except last column which is visible and the remaining width from total width of SfDataGird is set to last column.
</td>
</tr>
<tr>
<td>
 AutoLastColumnFill
</td>
<td>
Applies <code>GridLengthUnitType.Auto</code> width to all the columns except last column which is visible and sets the maximum between last column auto spacing width and remaining width to last column.
</td>
</tr>
<tr>
<td>
SizeToCells
</td>
<td>
Calculates the width of column based on cell contents. So that cell contents are not truncated.  
</td>
</tr>
<tr>
<td>
SizeToHeader
</td>
<td>
Calculates the width of column based on header content. So that header content is not truncated.  
</td>
</tr>
<tr>
<td>
None
</td>
<td>
Default column width or defined width set to column.
</td>
</tr>
</table>


N> ColumnSizer will not work when the column width defined explicitly. ColumnSizer calculates column width based on `MinWidth` and `MaxWidth` properties.

Below code, applies `GridLengthUnitType.Star` to equally set width for `SfDataGrid.Columns`.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid  x:Name="dataGrid"
                        AutoGenerateColumns="True"
                        ColumnSizer="Star"
                        ItemsSource="{Binding Orders}" />
{% endhighlight %}
{% endtabs %}


![Column Sizing](Columns_images/Columns_img9.png)


N> The `GridColumn.ColumnSizer` takes higher priority than the `SfDataGrid.ColumnSizer`.

### Fill remaining width for any column instead of last column when ColumnSizer is AutoLastColumnFill or AutoWithLastColumnFill 

In SfDataGrid while setting SfDataGrid.ColumnSizer as AutoLastColumnFill or AutoWithLastColumnFill remaining width is applied to last column. You can apply the remaining width to specific column by setting [GridColumn.ColumnSizer](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridColumn.html#Syncfusion_UI_Xaml_Grid_GridColumn_ColumnSizer) property as like below.

{% tabs %}
{% highlight xaml %}
<Syncfusion:SfDataGrid x:Name="datagrid"                                      
                       ColumnSizer="AutoWithLastColumnFill"
                       ItemsSource="{Binding OrderInfoCollection }">
            <Syncfusion:SfDataGrid.Columns>
                <Syncfusion:GridTextColumn MappingName="OrderID" HeaderText="OrderID" ColumnSizer="AutoLastColumnFill"/>
                <Syncfusion:GridTextColumn MappingName="CustomerID" HeaderText="CustomerID" />
                <Syncfusion:GridTextColumn MappingName="CustomerName" HeaderText="CustomerName"/>
                <Syncfusion:GridTextColumn MappingName="Country" HeaderText="Country"/>
                <Syncfusion:GridTextColumn MappingName="ShipCity" HeaderText="ShipCity"/>
            </Syncfusion:SfDataGrid.Columns>
</Syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
this.datagrid.ColumnSizer = GridLengthUnitType.AutoLastColumnFill;
this.datagrid.Columns["OrderID"].ColumnSizer = GridLengthUnitType.AutoWithLastColumnFill;
{% endhighlight %}
{% endtabs %}

![Fill remaining width for any column instead of last column when ColumnSizer is AutoLastColumnFill](Columns_images/Columns_img12.png)

### Refreshing ColumnSizer at runtime

You can refresh the `ColumnSizer` at runtime by calling [SfDataGrid.GridColumnSizer.Refresh](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridColumnSizer.html#Syncfusion_UI_Xaml_Grid_GridColumnSizer_Refresh) method. 

SfDataGrid support to recalculates the column auto width by calling reset methods of `GridColumnSizer`. [GridColumnSizer.ResetAutoCalculationforAllColumns](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.ColumnSizerBase-1.html#Syncfusion_UI_Xaml_Grid_ColumnSizerBase_1_ResetAutoCalculationforAllColumns) method reset widths to all columns. [GridColumnSizer.ResetAutoCalculation](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.ColumnSizerBase-1.html#Syncfusion_UI_Xaml_Grid_ColumnSizerBase_1_ResetAutoCalculation_Syncfusion_UI_Xaml_Grid_GridColumnBase_) method reset the width to particular column.

N> The `GridColumnSizer.ResetAutoCalculationforAllColumns` or `GridColumnSizer.ResetAutoCalculation` methods applicable for Auto, AutoWithLastColumnFill, AutoLastColumnFill, SizeToCells types.

For example, you can refresh all the column’s width based on the cell contents of newly added records at runtime.
 
{% tabs %}
{% highlight c# %}
var viewModel = this.dataGrid.DataContext as ViewModel;

viewModel.Orders.Add(new OrderInfo(11, "BLFKI", "Maria Joseph Anders"));

this.dataGrid.GridColumnSizer.ResetAutoCalculationforAllColumns();

this.dataGrid.GridColumnSizer.Refresh();             
{% endhighlight %}
{% endtabs %}

### Resetting column width to apply ColumnSizer

When the width of the column is explicitly defined or column is resized, then column width is not changed based on `GridColumnSizer`. You can reset [GridColumn.Width](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridColumnBase.html#Syncfusion_UI_Xaml_Grid_GridColumnBase_Width) by setting `double.NaN` to apply column width based on column sizer.

{% tabs %}
{% highlight c# %}
foreach (var column in dataGrid.Columns)
{
    if (!double.IsNaN(column.Width))
        column.Width = double.NaN;
}

this.dataGrid.GridColumnSizer.Refresh();             
{% endhighlight %}
{% endtabs %}


### Customizing built-in column sizing logic

SfDataGrid process column sizing operations in [GridColumnSizer](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridColumnSizer.html) class. You can customize the column sizing operations by overriding `GridColumnSizer` and set it to ` SfDataGrid.GridColumnSizer`.

{% tabs %}
{% highlight c# %}
this.dataGrid.GridColumnSizer = new GridColumnSizerExt(dataGrid);

public class GridColumnSizerExt:GridColumnSizer
{
    public GridColumnSizerExt(SfDataGrid dataGrid)
        :base(dataGrid)
    {

    }    
        
    // Calculate Width for column when ColumnSizer is SizeToCells.        
    protected override double CalculateCellWidth(GridColumn column, bool setWidth = true)
    {
        return base.CalculateCellWidth(column, setWidth);
    }
    
    //Calculate Width for the column when ColumnSizer is SizeToHeader
    protected override double CalculateHeaderWidth(GridColumn column, bool setWidth = true)
    {
        return base.CalculateHeaderWidth(column, setWidth);
    }    
}
{% endhighlight %}
{% endtabs %}

### Auto width calculation based on font settings

By default, the ColumnSizer calculates column’s width based on fixed `FontSize`, `FontFamily`, `Margin`, `SortIconWidth`, `FilterIconWidth`. You can change the calculation by customized settings.

#### Changing Sort and Filter Icon width

You can change the filter icon and sort icon widths for column width calculation by setting [GridColumnSizer.SortIconWidth](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.ColumnSizerBase-1.html#Syncfusion_UI_Xaml_Grid_ColumnSizerBase_1_SortIconWidth) and [GridColumnSizer.FilterIconWidth](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridColumnSizer.html#Syncfusion_UI_Xaml_Grid_GridColumnSizer_FilterIconWidth) properties.

{% tabs %}
{% highlight c# %}
dataGrid.GridColumnSizer.SortIconWidth = 20;
dataGrid.GridColumnSizer.FilterIconWidth = 20;
{% endhighlight %}
{% endtabs %}

#### Changing Font settings for SfDataGrid

You can change the `font settings` for column width calculation by setting [GridColumnSizer.FontSize](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.ColumnSizerBase-1.html#Syncfusion_UI_Xaml_Grid_ColumnSizerBase_1_FontSize), [GridColumnSizer.FontFamily](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.ColumnSizerBase-1.html#Syncfusion_UI_Xaml_Grid_ColumnSizerBase_1_FontFamily) and [GridColumnSizer.Margin](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.ColumnSizerBase-1.html#Syncfusion_UI_Xaml_Grid_ColumnSizerBase_1_Margin) properties.  These settings will be considered for all columns.

{% tabs %}
{% highlight c# %}
this.dataGrid.GridColumnSizer.FontSize = 10.0;
this.dataGrid.GridColumnSizer.FontFamily = new FontFamily("TimesNewRoman");
this.dataGrid.GridColumnSizer.Margin = new Thickness(9, 3, 1, 3);
{% endhighlight %}
{% endtabs %}

#### Changing Font settings for one Column

You can change the `font setting` for one column width calculation using [GridColumnSizer.SetFontFamily](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.ColumnSizerBase-1.html#Syncfusion_UI_Xaml_Grid_ColumnSizerBase_1_SetFontFamily_Syncfusion_UI_Xaml_Grid_GridColumnBase_Windows_UI_Xaml_Media_FontFamily_), [GridColumnSizer.SetFontSize](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.ColumnSizerBase-1.html#Syncfusion_UI_Xaml_Grid_ColumnSizerBase_1_SetFontSize_Syncfusion_UI_Xaml_Grid_GridColumnBase_System_Double_) and [GridColumnSizer.SetMargin](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.ColumnSizerBase-1.html#Syncfusion_UI_Xaml_Grid_ColumnSizerBase_1_SetMargin_Syncfusion_UI_Xaml_Grid_GridColumnBase_Windows_UI_Xaml_Thickness_) static methods of `GridColumnSizer` to `GridColumn`.
 
{% tabs %}
{% highlight c# %}
var gridColumn = this.dataGrid.Columns[0];
GridColumnSizer.SetFontFamily(gridColumn, new FontFamily("TimesNewRoman"));
GridColumnSizer.SetFontSize(gridColumn, 10.0);
GridColumnSizer.SetMargin(gridColumn, new Thickness(9, 3, 1, 3));
{% endhighlight %}
{% endtabs %}

### Star column sizer ratio support

You can customize the `ColumnSizer.Star` width calculation logic by overriding [SetStarWidth](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridColumnSizer.html#Syncfusion_UI_Xaml_Grid_GridColumnSizer_SetStarWidth_System_Double_System_Collections_Generic_IEnumerable_Syncfusion_UI_Xaml_Grid_GridColumn__) method of `GridColumnSizer`.

For example, you can calculate the column width, with specified ratios instead of dividing equal width for all columns in Star calculation using `ColumnRatio` attached property.

{% tabs %}
{% highlight c# %}
public static class StarRatio
{
    public static int GetColumnRatio(DependencyObject obj)
    {
        return (int)obj.GetValue(ColumnRatioProperty);
    }

    public static void SetColumnRatio(DependencyObject obj, int value)
    {
        obj.SetValue(ColumnRatioProperty, value);
    }

    public static readonly DependencyProperty ColumnRatioProperty = DependencyProperty.RegisterAttached("ColumnRatio", typeof(int), typeof(StarRatio), new PropertyMetadata(1, null));
}
{% endhighlight %}
{% endtabs %}

Below code to define the star width calculation based on the `ColumnRatio`.

{% tabs %}
{% highlight c# %}
//Assign the customized GridColumnSizerExt to SfDataGrid.GridColumnSizer
this.dataGrid.GridColumnSizer = new GridColumnSizerExt(dataGrid);

public class GridColumnSizerExt : GridColumnSizer
{
    public GridColumnSizerExt(SfDataGrid grid)
        : base(grid)
    {
    }

    protected override void SetStarWidth(double remainingColumnWidth, IEnumerable<GridColumn> remainingColumns)
    {
        var removedColumn = new List<GridColumn>();

        var columns = remainingColumns.ToList();

        var totalRemainingStarValue = remainingColumnWidth;

        double removedWidth = 0;

        bool isRemoved;

        while (columns.Count > 0)
        {
            isRemoved = false;

            removedWidth = 0;

            var columnsCount = 0;

            foreach (var data in columns)
            {
                columnsCount += StarRatio.GetColumnRatio(data);
            }

            double starWidth = Math.Floor((totalRemainingStarValue / columnsCount));

            var column = columns.First();

            starWidth *= StarRatio.GetColumnRatio(column);

            double computedWidth = SetColumnWidth(column, starWidth);

            if (starWidth != computedWidth && starWidth > 0)
            {
                isRemoved = true;

                columns.Remove(column);

                foreach (var remColumn in removedColumn)
                {
                    if (!columns.Contains(remColumn))
                    {
                        removedWidth += remColumn.ActualWidth;
                        columns.Add(remColumn);
                    }
                }

                removedColumn.Clear();

                totalRemainingStarValue += removedWidth;
            }

            totalRemainingStarValue = totalRemainingStarValue - computedWidth;

            if (!isRemoved)
            {
                columns.Remove(column);

                if (!removedColumn.Contains(column))
                    removedColumn.Add(column);
            }
        }
    }
}
{% endhighlight %}
{% endtabs %}

Below code uses the `ColumnRatio` to apply the defined star width for each column.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       ItemsSource="{Binding Orders}"  
                       ColumnSizer="Star"
                       AutoGenerateColumns="False">
                       
    <syncfusioSSn:SfDataGrid.Columns>
        <syncfusion:GridTextColumn  HeaderText="Order ID"
                                    MappingName="OrderID"
                                    local:StarRatio.ColumnRatio="1" />
                                    
        <syncfusion:GridTextColumn  HeaderText="Customer ID"
                                    MappingName="CustomerID"
                                    local:StarRatio.ColumnRatio="2" />
                                    
        <syncfusion:GridTextColumn  HeaderText="Customer Name"
                                    MappingName="CustomerName"
                                    local:StarRatio.ColumnRatio="3" />
 </syncfusion:SfDataGrid.Columns>
 
</syncfusion:SfDataGrid>
{% endhighlight %}
{% endtabs %}


![Star column sizer ratio support](Columns_images/Columns_img10.png)

### Change the width of GridComboBoxColumn based on it’s ItemsSource

By default, the `ColumnSizer` calculates auto width based on the column content. You can change the auto width calculation for `GridComboBoxColumn` based on its items source by overriding the [CalculateCellWidth](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridColumnSizer.html#Syncfusion_UI_Xaml_Grid_GridColumnSizer_CalculateCellWidth_Syncfusion_UI_Xaml_Grid_GridColumn_System_Boolean_) virtual method.

Below code creates `CustomColumnSizer` to change the width of `GridComboboxColumn` and set to `SfDataGrid.GridColumnSizer`.

{% tabs %}
{% highlight c# %}
this.dataGrid.GridColumnSizer = new CustomColumnSizer(this.dataGrid);

public class CustomColumnSizer : GridColumnSizer
{
    public CustomColumnSizer(SfDataGrid grid)
        : base(grid)
    {
    }

    protected override double CalculateCellWidth(GridColumn column, bool setWidth = true)
    {
        //Customizing width calculation for GridComboBoxColumn
        if (column is GridComboBoxColumn)
        {
            //Get the width of the corresponding GridColumn
            double colWidth = column.Width;

            //Get the Source collection from the corresponding GridComboBoxColumn items source
            var source = (column as GridComboBoxColumn).ItemsSource;

            //Initialize the below field for storing length                
            string maximumComboItemsText = string.Empty;

            //Get the column width and row height
            var clientSize = new Size(colWidth, DataGrid.RowHeight);

            //Calculate the maximum length for each combo box items and store maximum length
            foreach (var comboItems in source)
            {
                string comboItemText = (string)comboItems;
                if (maximumComboItemsText.Length < comboItemText.Length)
                    maximumComboItemsText = comboItemText;
            }

            //Get the size for maximum ComboBoxItems's text and returned the measured width as a column width of that column
            var measureSize = MeasureText(clientSize, maximumComboItemsText, column, null, GridQueryBounds.Width);
            
            return measureSize.Width;
        }
        //Default column width calculation performed other than GridComboBoxColumn
        return base.CalculateCellWidth(column, setWidth);
    }
}
{% endhighlight %}
{% endtabs %}

## Binding column properties with ViewModel

SfDataGrid provides MVVM support for binding `GridColumn` properties with ViewModel properties.
 
{% tabs %}
{% highlight c# %}
public class ViewModel
{
    private bool _allowFiltering =true;
    public bool AllowFiltering
    {
        get { return _allowFiltering; }
        set { _allowFiltering = value; }
    }
}
{% endhighlight %}
{% endtabs %}

Below code, binds the `ViewModel.AllowFiltering` property to `GridColumn.AllowFiltering` property.

{% tabs %}
{% highlight xaml %}
<Page.Resources>
    <local:ViewModel x:Key="viewModel" />
</Page.Resources>

<syncfusion:GridTextColumn  AllowFiltering="{Binding AllowFiltering,
                                                    Source={StaticResource viewModel}}"
                            HeaderText="Order ID"
                            MappingName="OrderID" /> 
{% endhighlight %}
{% endtabs %}


![Binding column properties with ViewModel](Columns_images/Columns_img11.png)

