---
layout: post
title: Sorting in SfDataGrid
description: How to sort the data in SfDataGrid
platform: uwp
control: SfDataGrid
documentation: ug
---


# Sorting

SfDataGrid allows you to sort the data against one or more columns either in ascending or descending order. When sorting is applied, the rows are rearranged based on sort criteria. You can allow users to sort the data by touching or clicking the column header using `SfDataGrid.AllowSorting` property to `true`.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       AllowSorting="True"
                       ItemsSource="{Binding Orders}">
{% endhighlight %}
{% highlight c# %}
dataGrid.AllowSorting = true;
{% endhighlight %}
{% endtabs %}

In another way, you can enable or disable the sorting for particular column by setting the `GridColumn.AllowSorting` property.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid  x:Name="dataGrid"
                        AllowSorting="False"
                        AutoGenerateColumns="False"
                        ItemsSource="{Binding Orders}">

    <syncfusion:SfDataGrid.Columns>
        <syncfusion:GridTextColumn AllowSorting="True" MappingName="OrderID" />
        <syncfusion:GridTextColumn AllowSorting="False" MappingName="CustomerID" />
        <syncfusion:GridTextColumn AllowSorting="False" MappingName="CustomerName" />
        <syncfusion:GridTextColumn AllowSorting="True" MappingName="Country" />
        <syncfusion:GridTextColumn AllowSorting="True" MappingName="ShipCity" />
    </syncfusion:SfDataGrid.Columns>

</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
this.dataGrid.Columns["OrderID"].AllowSorting = true;
this.dataGrid.Columns["CustomerID"].AllowSorting = false;
{% endhighlight %}
{% endtabs %}


N> The `GridColumn.AllowSorting` takes higher priority than `SfDataGrid.AllowSorting` property.

End users can sort the column by clicking column header cell. Once the columns get sorted, the sort indicator will be displayed on the right side of the column header.

![](Sorting_images/Sorting_img1.png)


## Sort column in double click

By default, column gets sorted when column header clicked. You can change this behavior to sort the column in double click action by setting `SfDataGrid.SortClickAction` property to `DoubleClick`.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid  x:Name="dataGrid"
                        AllowSorting="True"
                        AutoGenerateColumns="True"
                        ItemsSource="{Binding Orders}"
                        SortClickAction="DoubleClick" />
{% endhighlight %}
{% highlight c# %}
this.dataGrid.SortClickAction = SortClickAction.DoubleClick;
{% endhighlight %}
{% endtabs %}

## Sorting order

By default, the data is sorted in ascending or descending order when clicking column header. You can rearrange the data to its initial order from descending, when clicking column header by setting `SfDataGrid.AllowTriStateSorting` property.

Following are the sequence of sorting orders when clicking column header,
 
* Sorts the data in ascending order

* Sorts the data in descending order
 
* Clears the sorting and records displayed in its initial order

## Multi column sorting

SfDataGrid control allows you sort more than one column, where sorting is applied one column against other columns. 

To apply sorting on multiple columns, user have to click the column header by pressing the <kbd>Ctrl</kbd> key.

In the below screen shot, the OrderID column sorted. Then the `CustomerName` column is sorted against the `OrderID` data by clicking column header by pressing &lt;kbd&gt;Ctrl&lt;/kbd&gt; key. The sorting state of `OrderID` column is preserved and `CustomerName` column sorted against `OrderID` column.  

![](Sorting_images/Sorting_img2.png)

### Display sort order
It is also possible to display sorted order of columns in header by setting `SfDataGrid.ShowSortNumbers` property to `true`. 
{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid  x:Name="dataGrid"
                        AllowSorting="True"        
                        ShowSortNumbers="True"
                        ItemsSource="{Binding Orders}" />
{% endhighlight %}
{% highlight c# %}
this.dataGrid.ShowSortNumbers = true;
{% endhighlight %}
{% endtabs %}

![](Sorting_images/Sorting_img3.png)

## Programmatic sorting

You can sort the data programmatically by adding or removing the `SortColumnDescription` in `SfDataGrid.SortColumnDescriptions` property.
 
N> `SfDataGrid.SortColumnChanging` and `SfDataGrid.SortColumnChanged` events are not raised when the data sorted programmatically through `SfDataGrid.SortColumnDescriptions`.

### Adding sort columns

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid  x:Name="dataGrid"
                        AutoExpandGroups="True"
                        AutoGenerateColumns="True"
                        ItemsSource="{Binding Orders}"
                        ShowGroupDropArea="True">

    <syncfusion:SfDataGrid.SortColumnDescriptions>

        <syncfusion:SortColumnDescription ColumnName="OrderID" SortDirection="Ascending" />

        <syncfusion:SortColumnDescription ColumnName="CustomerName" SortDirection="Descending" />

    </syncfusion:SfDataGrid.SortColumnDescriptions>

</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
this.dataGrid.SortColumnDescriptions.Add(new SortColumnDescription() { ColumnName = "OrderID", SortDirection = ListSortDirection.Ascending });

this.dataGrid.SortColumnDescriptions.Add(new SortColumnDescription() { ColumnName = "CustomerName", SortDirection = ListSortDirection.Descending });
{% endhighlight %}
{% endtabs %}

### Removing sort columns

You can unsort the data by removing the corresponding `SortColumnDescription` from the `SfDataGrid.SortColumnDescriptions` property.

{% tabs %}
{% highlight c# %}
var sortColumnDescription = this.dataGrid.SortColumnDescriptions.FirstOrDefault(col => col.ColumnName == "OrderID");

if (sortColumnDescription!=null)
{  
    this.dataGrid.SortColumnDescriptions.Remove(sortColumnDescription);
}
{% endhighlight %}
{% endtabs %}

### Clear sorting

You can clear sorting, by clearing the `SfDataGrid.SortColumnDescriptions`.

{% tabs %}
{% highlight c# %}
this.dataGrid.SortColumnDescriptions.Clear();
{% endhighlight %}
{% endtabs %}

## Custom sorting

SfDataGrid allows you to sort the columns based on the custom logic. The custom sorting can be applied by adding the `SortComparer` instance to `SfDataGrid.SortComparers`.
 
The `SortComparer` have the following properties,

`PropertyName` - Gets or sets the name of the column to apply custom sorting.

`Comparer` - Gets or sets the custom comparer in which you can code to compare the data using custom logic.

You can implement `ISortDirection` interface in comparer to get the sort direction. So you can apply different custom logics for ascending and descending.
 
Follow the below steps to add custom comparer to sort using custom logic,

#### Define custom comparer with custom sort logic

In the below code snippet, CustomerName property is compared based on its string length, instead of default string comparison.
  
{% tabs %}
{% highlight c# %}
public class CustomComparer : IComparer<object>, ISortDirection
{
    private ListSortDirection _SortDirection;
    public ListSortDirection SortDirection
    {
        get { return _SortDirection; }            
        set { _SortDirection = value; }            
    }

    public int Compare(object x, object y)
    {
        int namX;

        int namY;

        //While data object passed to comparer
        if (x.GetType() == typeof(OrderInfo))
        {
            namX = ((OrderInfo)x).CustomerName.Length;
            namY = ((OrderInfo)y).CustomerName.Length;
        }

        //While sorting groups
        else if (x.GetType() == typeof(Group))
        {
            //Calculating the group key length
            namX = ((Group)x).Key.ToString().Length;
            namY = ((Group)y).Key.ToString().Length;
        }

        else
        {
            namX = x.ToString().Length;
            namY = y.ToString().Length;
        }

        //returns the comparison result based in SortDirection.
        if (namX.CompareTo(namY) > 0)
            return SortDirection == ListSortDirection.Ascending ? 1 : -1;

        else if (namX.CompareTo(namY) == -1)
            return SortDirection == ListSortDirection.Ascending ? -1 : 1;

        else
            return 0;
    }
}
{% endhighlight %}
{% endtabs %}

#### Adding custom comparer to SfDataGrid

Custom comparer can be added to `SfDataGrid.SortComparers` property. `SortComparers` maintains custom comparers and the custom comparer gets called when corresponding column gets sorted by clicking column header or programmatically.
 
{% tabs %}
{% highlight xaml %}
xmlns:Linq="using:Syncfusion.Data"

<Page.Resources>
    <local:CustomComparer x:Key="comparer" />
</Page.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid" ItemsSource="{Binding Orders}">

    <syncfusion:SfDataGrid.SortComparers>
        <Linq:SortComparer Comparer="{StaticResource comparer}" PropertyName="CustomerName" />
    </syncfusion:SfDataGrid.SortComparers>

    <syncfusion:SfDataGrid.SortColumnDescriptions>
        <syncfusion:SortColumnDescription ColumnName="CustomerName" SortDirection="Ascending" />
    </syncfusion:SfDataGrid.SortColumnDescriptions>

</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
this.dataGrid.SortComparers.Add(new SortComparer() { Comparer = new CustomComparer(), PropertyName = "CustomerName" });
{% endhighlight %}
{% endtabs %}

Sorting `CustomerName` column sorts the data using custom comparer availabe in `SfDataGrid.SortComparers`.

![](Sorting_images/Sorting_img4.png)

## Sorting the underlying collection 

SfDataGrid sorts the records in UI and maintains in its internal CollectionView and it will not change the order of data in underlying collection. You can get sorted data from `SfDataGrid.View.Records` when groups are not in place and `SfDataGrid.View.TopLevelGroup.DisplayElements` when grouping in place.
 
If you want to sort the underlying collection when sorting takes place, then this can be achieved by handling `SfDataGrid.SortColumnChanged` event.
 
{% tabs %}
{% highlight c# %}
this.dataGrid.SortColumnsChanged += DataGrid_SortColumnsChanged;                          

void DataGrid_SortColumnsChanged(object sender, GridSortColumnsChangedEventArgs e)
{
    var viewModel = this.DataContext as ViewModel;

    IEnumerable<OrderInfo> OrderedSource = viewModel.Orders;

    foreach (var sortColumn in this.dataGrid.View.SortDescriptions)
    {
        var columnName = sortColumn.PropertyName;

        if (sortColumn.Direction == ListSortDirection.Ascending)
            OrderedSource = OrderedSource.OrderBy(source => GetOrderSource(source, columnName));

        else
            OrderedSource = OrderedSource.OrderByDescending(source => GetOrderSource(source, columnName));
    }
}


using System.Reflection;

private object GetOrderSource(OrderInfo source, string name)
{
    var propInfo = source.GetType().GetRuntimeProperty(name);

    if (propInfo != null)
        // Get the current sort column value
        return propInfo.GetValue(source);

    return null;
}
{% endhighlight %}
{% endtabs %}

## Handling events

### SortColumnChanging event

`SfDataGrid.SortColumnChanging` event occurs while sorting the columns by clicking column header. `GridSortColumnsChangingEventArgs` has following members which provides information for `SortColumnChanging` event.

`Action`– Gets the action triggered this event.
 
`Cancel`– Setting value to `true`, cancels the triggered action.
 
`AddedItems` - Gets the list of new `SortColumnDescription’s` that are added.

`RemovedItems`- Gets the list of `SortColumnDescription’s` that are removed.
 
`CancelScroll` - Gets or sets a value that indicates, whether scroll and bring SelectedItem in view after sorting takes place.

You can prevent sorting for the particular column through `GridSortColumnsChangingEventArgs.Cancel` property of `SortColumnChanging` event.

{% tabs %}
{% highlight c# %}
this.dataGrid.SortColumnsChanging += DataGrid_SortColumnsChanging;

void DataGrid_SortColumnsChanging(object sender, GridSortColumnsChangingEventArgs e)
{
    if (e.AddedItems[0].ColumnName == "OrderID")
    {
        e.Cancel = true;
    }
}
{% endhighlight %}
{% endtabs %}

### SortColumnChanged event

`SfDataGrid.SortColumnChanged` event occurs when the sorting is applied to the column. `GridSortColumnsChangedEventArgs` provides information for `SortColumnChanged` event.
