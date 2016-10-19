---
layout: post
title: Selection support in SfDataGrid
description: How to select the rows or cells in SfDataGrid
platform: uwp
control: SfDataGrid
documentation: ug
---

# Selection

SfDataGrid allows you to select one or more rows or cells. For selecting specific row or group of rows you have to set [SelectionUnit](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfDataGridClassSelectionUnitTopic.html) as [Row](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridSelectionUnitClassTopic.html) and for selecting a specific cell or group of cells you have to set  `SelectionUnit` as [Cell](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridSelectionUnitClassTopic.html) or `Any`. In [SelectionUnit.Any](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridSelectionUnitClassTopic.html) option you can select the row by clicking on row header.

### Current Cell Navigation

Keyboard navigation through the cells and rows is determined based on the [NavigationMode](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfGridBaseClassNavigationModeTopic.html) property. [NavigationMode.Cell](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridNavigationModeClassTopic.html) allows you to navigate between the cells in a row as well as between rows. [NavigationMode.Row](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridNavigationModeClassTopic.html) allows you to navigate only between rows. It is not possible to set [NavigationMode.Row](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridNavigationModeClassTopic.html) when cell selection is enabled (`SelectionUnit` is Cell or Any). 

### Selection Modes

The `SelectionUnit` and `SelectionMode` properties together define the behavior of selection in SfDataGird. If the [SelectionMode](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfGridBaseClassSelectionModeTopic.html) is `Single`, you can able to select single row or cell, and if the SelectionMode is `Extended` or `Multiple`, you can able to select multiple rows or cell, and if you want to disable the selection you need to set SelectionMode as `None`,

{% tabs %}
{% highlight xaml %}

<Syncfusion:SfDataGrid x:Name=”dataGrid”
                       SelectionUnit="Row"
                       NavigationMode="Cell"
                       SelectionMode="Single"
                       ItemsSource="{Binding Orders}">

{% endhighlight %}
{% endtabs %}

![](Selection_images/Selection_img1.png)


### Disable selection for rows and columns

You can disable selection and navigation on particular column by setting [GridColumn.AllowFocus](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridColumnBaseClassAllowFocusTopic.html) property. You can disable selection on particular row or cell or column by handling [CurrentCellActivating](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfDataGridClassCurrentCellActivatingTopic.html) event. 

N> It is not possible to select header rows, table summary rows, unbound rows which are above the table summary row when it’s placed in top and the unbound rows which are below table summary rows when it’s placed in bottom of SfDataGrid. 

## Multiple Row or Cell Selection

The SfDataGrid allows you to select multiple rows or cells by setting [SelectionMode](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfGridBaseClassSelectionModeTopic.html) property as [Extended](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridSelectionModeClassTopic.html) or [Multiple](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridSelectionModeClassTopic.html), where you can select multiple rows or cells by dragging the mouse on SfDataGrid and also using the key modifiers.

While using `Extended`, you can select multiple rows or cells by pressing the key modifiers <kbd>Ctrl</kbd> and <kbd>Shift</kbd>. 

{% tabs %}
{% highlight xaml %}

<syncfusion:SfDataGrid x:Name="dataGrid"
                       SelectionUnit="Cell"
                       NavigationMode="Cell"
                       SelectionMode="Extended"
                       ItemsSource="{Binding Orders}">

{% endhighlight %}
{% endtabs %}

![](Selection_images/Selection_img2.png)

N> When the `SelectionMode` as `Multiple`, you can select or deselect multiple rows and cells by clicking the respective cell or row.  Also in multiple selection pressing navigation keys will move only the current cell and you can select or deselect by pressing <kbd>space</kbd> key.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfDataGrid x:Name="dataGrid"
                       SelectionUnit="Cell"
                       NavigationMode="Cell"
                       SelectionMode="Multiple"
                       ItemsSource="{Binding Orders}">

{% endhighlight %}
{% endtabs %}

![](Selection_images/Selection_img3.png)


## Get Selected Rows and Cells

The [SelectedItem](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfGridBaseClassSelectedItemTopic.html) property returns the data object of the selected row and the [SelectedIndex](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfGridBaseClassSelectedIndexTopic.html) property returns the index of the `SelectedItem` in SfDataGrid. `SelectedItem` denotes the first selected row in multiple selection. 

The [CurrentItem](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfDataGridClassCurrentItemTopic.html) returns the data object that currently has the focus and the [CurrentColumn](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfDataGridClassCurrentColumnTopic.html) denotes the [GridColumn](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridColumnClassTopic.html) that currently has the focus. The [CurrentCellInfo](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfDataGridClassCurrentCellInfoTopic.html) returns an instance [GridCellInfo](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridCellInfoClassTopic.html) which contains the information about the cell that currently has the focus. 

### Row Selection

You can gets all the selected records through [SelectedItems](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfGridBaseClassSelectedItemsTopic.html) property and you can also get all selected rows information through [SfDataGrid.SelectionController.SelectedRows](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridIGridSelectionControllerClassSelectedRowsTopic.html) which is the collection of [GridRowInfo](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridRowInfoClassTopic.html). 

### Cell Selection

You can get all selected cells information through [SfDataGrid.SelectionController.SelectedCells](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridIGridSelectionControllerClassSelectedCellsTopic.html) property which is the collection of `GridSelectedCellsInfo`.

You can get the selected cells as [GridCellInfo](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridCellInfoClassTopic.html) collection by using [GetSelectedCells](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfDataGridClassGetSelectedCellsTopic.html) method.

{% tabs %}
{% highlight c# %}

List<GridCellInfo> selectedCells = this.dataGrid.GetSelectedCells();

{% endhighlight %}
{% endtabs %}

### CurrentItem vs SelectedItem

Both `SelectedItem` and `CurrentItem` returns the same data object when there is single cell or row is selected in SfDataGrid. When you have selected more than one rows or cells, the record that had been selected initially is maintained in `SelectedItem` and the record that currently have focus is maintained in `CurrentItem`. 

## Programmatic selection

### Process selection using properties

You can select a single row or cell by setting `SelectedItem` property or `SelectedIndex` property. 

{% tabs %}
{% highlight c# %}

var recordIndex = this.dataGrid.ResolveToRecordIndex(5);
this.dataGrid.SelectedIndex = recordIndex;

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

var record = this.dataGrid.GetRecordAtRowIndex(6);
this.dataGrid.SelectedItem = record;

{% endhighlight %}
{% endtabs %}

In Row selection, you can select multiple rows by adding data objects to `SelectedItems` property.

{% tabs %}
{% highlight c# %}

var viewModel = this.dataGrid.DataContext as ViewModel;
foreach(var order in viewModel.Orders)
{
    if (order.Country == "Mexico")
    this.dataGrid.SelectedItems.Add(order);
}

{% endhighlight %}
{% endtabs %}

![](Selection_images/Selection_img4.png)


### Process selection using methods

You can select range of rows through [SelectRows](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfDataGridClassSelectRowsTopic.html) method in row selection.

{% tabs %}
{% highlight c# %}

this.dataGrid.SelectRows(3, 7);

{% endhighlight %}
{% endtabs %}

![](Selection_images/Selection_img5.png)


You can select a specific cell by using the [SelectCell](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfDataGridClassSelectCellTopic.html) method in cell selection.

{% tabs %}
{% highlight c# %}

var record = this.dataGrid.GetRecordAtRowIndex(3);
var column = this.dataGrid.Columns[1];
this.dataGrid.SelectCell(record, column);

{% endhighlight %}
{% endtabs %}

![](Selection_images/Selection_img6.png)


You can select a range of cells through [SelectCells](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfDataGridClassSelectCellsTopic.html) method in cell selection.

{% tabs %}
{% highlight c# %}

public MainWindow()
{
    InitializeComponent();
    this.dataGrid.Loaded += dataGrid_Loaded;
    this.dataGrid.SelectionController = new GridSelectionControllerExt(this.dataGrid);
}

private void dataGrid_Loaded(object sender, RoutedEventArgs e)
{
    var firstRecord = this.dataGrid.GetRecordAtRowIndex(3);
    var lastRecord = this.dataGrid.GetRecordAtRowIndex(7);
    var firstColumn = this.dataGrid.Columns[1];
    var lastColumn = this.dataGrid.Columns[3];
    this.dataGrid.SelectCells(firstRecord, firstColumn, lastRecord, lastColumn);
    (this.dataGrid.SelectionController as GridSelectionControllerExt).rowColumnIndex = new RowColumnIndex(7, 3);
    //Updates the PressedRowColumnIndex value in the GridBaseSelectionController.
    (this.dataGrid.SelectionController as GridSelectionControllerExt).UpdatePressedIndex(); 
}

public class GridSelectionControllerExt : GridCellSelectionController
{
    //Overrides the GridCellSelectionController class to update the PressedRowColumnIndex.
    public GridSelectionControllerExt(SfDataGrid datagrid)
        : base(datagrid)
    {
    }

    private RowColumnIndex rowcolumnindex;

    public RowColumnIndex rowColumnIndex
    {
        get { return rowcolumnindex; }
        set { rowcolumnindex = value; }
    }

    //Updates the PressedRowColumnIndex to maintain the ShiftSelection.
    public void UpdatePressedIndex()
    {
        this.isInShiftSelection = true;
        this.PressedRowColumnIndex = rowColumnIndex;
    }
}

{% endhighlight %}
{% endtabs %}

![](Selection_images/Selection_img7.png)


You can select all the rows or cells using [SelectAll](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfDataGridClassSelectAllTopic.html) method.

{% tabs %}
{% highlight c# %}

this.dataGrid.SelectAll();

{% endhighlight %}
{% endtabs %}

### Process Current Cell

When you set the [CurrentItem](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfDataGridClassCurrentItemTopic.html) to particular record, the [CurrentCell](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridCurrentCellManagerClassCurrentCellTopic.html) will be moved to corresponding record when the `SelectionMode` is `Multiple` or `Extended` and the selection will added to the particular record item when the `SelectionMode` is `Single`.

{% tabs %}
{% highlight c# %}

var viewModel = this.dataGrid.DataContext as ViewModel;
this.dataGrid.CurrentItem = viewModel.Orders.FirstOrDefault(order => order.Country == "Spain");

{% endhighlight %}
{% endtabs %}

You can move the `CurrentCell` to a particular rowColumnIndex by using the [MoveCurrentCell](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfDataGridClassMoveCurrentCellTopic.html) method.

{% tabs %}
{% highlight c# %}

this.dataGrid.MoveCurrentCell(new RowColumnIndex(3,2), false);

{% endhighlight %}
{% endtabs %}

### Clear Selection

You can clear the selection by using the [ClearSelection](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfDataGridClassClearSelectionsTopic.html) method. In Row Selection you can also remove the selection by setting null to `SelectedItem` or clearing the `SelectedItems` property.

{% tabs %}
{% highlight c# %}

this.dataGrid.SelectionController.ClearSelections(true);

{% endhighlight %}
{% endtabs %}

You can clear selection on group of cells by using the [UnSelectCells](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfDataGridClassUnSelectCellsTopic.html) method in cell selection.

{% tabs %}
{% highlight c# %}

var firstRecord = this.dataGrid.GetRecordAtRowIndex(3);
var lastRecord = this.dataGrid.GetRecordAtRowIndex(7);
var firstColumn = this.dataGrid.Columns[1];
var lastColumn = this.dataGrid.Columns[3];
this.dataGrid.UnSelectCells(firstRecord, firstColumn, lastRecord, lastColumn);

{% endhighlight %}
{% endtabs %}

You can clear the selection on particular cell by using the [UnSelectCell](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfDataGridClassUnSelectCellTopic.html) method in cell selection.

{% tabs %}
{% highlight c# %}

var removeRecord = this.dataGrid.GetRecordAtRowIndex(5);
var removeColum = this.dataGrid.Columns[2];
this.dataGrid.UnSelectCell(removeRecord, removeColum);

{% endhighlight %}
{% endtabs %}

![](Selection_images/Selection_img8.png)


## Selection in Master-Details View

Master-Details View provides support to select one or more rows or cells in [DetailsViewDataGrid](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridDetailsViewDataGridClassTopic.html). You can’t able to maintain the selection in both ParentDataGrid and `DetailsViewDataGrid`. Selection will be maintained either in ParentDataGrid or in `DetailsViewDataGrid`.

![](Selection_images/Selection_img9.png)


### Getting SelectedDetailsViewDataGrid

You can get the currently selected `DetailsViewDataGrid` by using the [SelectedDetailsViewGrid](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfDataGridClassSelectedDetailsViewGridTopic.html) property of parent DataGrid.

{% tabs %}
{% highlight c# %}

var detailsViewDataGrid = this.dataGrid.SelectedDetailsViewGrid;

{% endhighlight %}
{% endtabs %}

For accessing nested level `SelectedDetailsViewGrid`,

{% tabs %}
{% highlight c# %}

var detailsViewDataGrid = this.dataGrid.SelectedDetailsViewGrid.SelectedDetailsViewGrid;

{% endhighlight %}
{% endtabs %}

### Getting SelectedItem from DetailsViewDataGrid

You can get the selected record of `DetailsViewDataGrid` by using the [SelectedItem](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfGridBaseClassSelectedItemTopic.html) property.

{% tabs %}
{% highlight c# %}

var detailsviewDataGrid = this.datagrid.SelectedDetailsViewGrid;
var SelectedItem = detailsviewDataGrid.SelectedItem;

{% endhighlight %}
{% endtabs %}

You can get the `SelectedItem` while it’s changed using [SelectionChanged](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfDataGridClassSelectionChangedTopic.html) event of [ViewDefinition.DataGrid](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridViewDefinitionClassDataGridTopic.html). 

{% tabs %}
{% highlight xaml %}

<syncfusion:GridViewDefinition RelationalColumn="OrderDetails">
    <syncfusion:GridViewDefinition.DataGrid>
        <syncfusion:SfDataGrid x:Name="FirstDetailsViewGrid" 
                               SelectionChanged="FirstDetailsViewGrid_SelectionChanged">
        </syncfusion:SfDataGrid>
    </syncfusion:GridViewDefinition.DataGrid>
</syncfusion:GridViewDefinition>

{% endhighlight %}



{% highlight c# %}

FirstDetailsViewGrid.SelectionChanged += FirstDetailsViewGrid_SelectionChanged;

private void FirstDetailsViewGrid_SelectionChanged(object sender, Syncfusion.UI.Xaml.Grid.GridSelectionChangedEventArgs e)
{
    var SelectedItem = (e.OriginalSender as DetailsViewDataGrid).SelectedItem;
}

{% endhighlight %}
{% endtabs %}

N> You can get the SelectedIndex and SelectedItems also in selection changed event.

You can refer [here](http://help.syncfusion.com/uwp/sfdatagrid/master-details-view#handling-events-for-detailsviewdatagrid) to wire the events for `ViewDefinition.DataGrid` based on `AutoPopulateRelations` for different levels.

### Get the CurrentItem of DetailsViewDataGrid

You can get the current record of the `DetailsViewDataGrid` by using the `CurrentItem` property.

{% tabs %}
{% highlight c# %}

var detailsviewDataGrid = this.datagrid.SelectedDetailsViewGrid;
var CurrentItem = detailsviewDataGrid.CurrentItem;

{% endhighlight %}
{% endtabs %}


You can get the `CurrentItem` while it’s changed using `SelectionChanged` event of `ViewDefinition.DataGrid`.

{% tabs %}
{% highlight xaml %}

<syncfusion:GridViewDefinition RelationalColumn="OrderDetails">
    <syncfusion:GridViewDefinition.DataGrid>
        <syncfusion:SfDataGrid x:Name="FirstDetailsViewGrid" 
                               SelectionChanged="FirstDetailsViewGrid_SelectionChanged">
        </syncfusion:SfDataGrid>
    </syncfusion:GridViewDefinition.DataGrid>
</syncfusion:GridViewDefinition>

{% endhighlight %}

{% highlight c# %}

FirstDetailsViewGrid.SelectionChanged+=FirstDetailsViewGrid_SelectionChanged;

private void FirstDetailsViewGrid_SelectionChanged(object sender, Syncfusion.UI.Xaml.Grid.GridSelectionChangedEventArgs e)
{
    var SelectedItem = (e.OriginalSender as DetailsViewDataGrid).CurrentItem;
}

{% endhighlight %}
{% endtabs %}

You can refer [here](http://help.syncfusion.com/uwp/sfdatagrid/master-details-view#handling-events-for-detailsviewdatagrid) to wire the events from `ViewDefinition.DataGrid` based on `AutoPopulateRelations` for different levels.

### Get CurrentCell of DetailsViewDataGrid

You can get the `CurrentCell` of `DetailsViewDataGrid` by using the [SelectedDetailsViewGrid](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfDataGridClassSelectedDetailsViewGridTopic.html) property. You can use different events of `ViewDefinition.DataGrid` like [CurrentCellBeginEdit](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfDataGridClassCurrentCellBeginEditTopic.html), [CurrentCellActivated](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfDataGridClassCurrentCellActivatedTopic.html) to get the `CurrentCell`.

{% tabs %}
{% highlight c# %}

var currentCell = this.dataGrid.SelectedDetailsViewGrid.SelectionController.CurrentCellManager.CurrentCell;

{% endhighlight %}
{% endtabs %}

You can get the `CurrentCell` using `CurrentCellBeginEdit` event `ViewDefinition.DataGrid`.

{% tabs %}
{% highlight xaml %}

<syncfusion:GridViewDefinition RelationalColumn="OrderDetails">
    <syncfusion:GridViewDefinition.DataGrid>
        <syncfusion:SfDataGrid x:Name="FirstLevelNestedGrid"                                                   
                               CurrentCellBeginEdit=" FirstLevelNestedGrid_CurrentCellBeginEdit">
        </syncfusion:SfDataGrid>
    </syncfusion:GridViewDefinition.DataGrid>
</syncfusion:GridViewDefinition>

{% endhighlight %}

{% highlight c# %}

this.FirstLevelNestedGrid.CurrentCellBeginEdit += FirstLevelNestedGrid_CurrentCellBeginEdit;
void FirstLevelNestedGrid_CurrentCellBeginEdit(object sender, CurrentCellBeginEditEventArgs args)
{
    var detailsViewDataGrid = args.OriginalSender as DetailsViewDataGrid;
    var currentCell = detailsViewDataGrid.SelectionController.CurrentCellManager.CurrentCell;
}

{% endhighlight %}
{% endtabs %}

You can refer [here](http://help.syncfusion.com/uwp/sfdatagrid/master-details-view#handling-events-for-detailsviewdatagrid) to wire the events from the `ViewDefinition.DataGrid` based on `AutoPopulateRelations` for different levels.

### Programmatic Selection in DetailsViewDataGrid

You can select data objects while loading DetailsViewDataGrid using [DetailsViewLoading](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfDataGridClassDetailsViewLoadingTopic.html) event.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfDataGrid Name="datagrid" 
                       DetailsViewLoading="datagrid_DetailsViewLoading" >
</syncfusion:SfDataGrid>

{% endhighlight %}

{% highlight c# %}

this.datagrid.DetailsViewLoading += datagrid_DetailsViewLoading;

void dataGrid_DetailsViewLoading(object sender, DetailsViewLoadingAndUnloadingEventArgs e)
{
    var record = e.DetailsViewDataGrid.GetRecordAtRowIndex(e.DetailsViewDataGrid.GetFirstDataRowIndex());
    e.DetailsViewDataGrid.SelectedItem = record;
}

{% endhighlight %}
{% endtabs %}

### Getting the parent of DetailsViewDataGrid

You can get the immediate parent of `DetailsViewDataGrid` through [GetParentDataGrid](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridHelpersSelectionHelperClassGetParentDataGridTopic.html) helper method.

{% tabs %}
{% highlight c# %}

using Syncfusion.UI.Xaml.Grid.Helpers;
var parentDataGrid = this.dataGrid.SelectedDetailsViewGrid.GetParentDataGrid();

{% endhighlight %}
{% endtabs %}

You can get the top level DataGrid for the `DetailsViewDataGrid` through the [GetTopLevelParentDataGrid](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridHelpersSelectionHelperClassGetTopLevelParentDataGridTopic.html) helper method.

{% tabs %}
{% highlight c# %}

using Syncfusion.UI.Xaml.Grid.Helpers;
var dataGrid = this.detailsviewdatagrid.GetTopLevelParentDataGrid();

{% endhighlight %}
{% endtabs %}

### Getting the DetailsViewDataGrid based on index

You can get the `DetailsViewDataGrid` based on row index through [GetDetailsViewGrid](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridHelpersSelectionHelperClassGetDetailsViewGridTopic.html) helper method.

{% tabs %}
{% highlight c# %}

var detailsViewDataGrid = this.dataGrid.GetDetailsViewGrid(2);

{% endhighlight %}
{% endtabs %}

You can also get the `DetailsViewDataGrid` based on the record index and relational column name using [GetDetailsViewGrid](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridHelpersSelectionHelperClassGetDetailsViewGridTopic.html) method.

{% tabs %}
{% highlight c# %}

var detailsViewDataGrid = this.dataGrid.GetDetailsViewGrid(0, "ProductDetails");

{% endhighlight %}
{% endtabs %}

### Programmatically expanding and scrolling DetailsViewDataGrid 

You can expand the `DetailsViewDataGrid` programmatically by calling `ExpandDetailsViewAt` method by passing the record index.

{% tabs %}
{% highlight c# %}

int parentRowIndex = 2;
var recordindex = this.datagrid.ResolveToRecordIndex(parentRowIndex);
var record = this.datagrid.View.Records[recordindex];
if (!record.IsExpanded)
this.datagrid.ExpandDetailsViewAt(recordindex);

{% endhighlight %}
{% endtabs %}

If the expanded `DetailsViewDataGrid` is not in view, then you can scroll using [DetailsViewManager.BringIntoView](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridDetailsViewManagerClassBringIntoViewTopic.html) method.

{% tabs %}
{% highlight c# %}

int recordIndex = 20;
datagrid.ExpandDetailsViewAt(recordIndex);
//Get the Details view based upon the recordIndex and Column name
SfDataGrid detailsViewDataGrid = datagrid.GetDetailsViewGrid(recordIndex, "OrderDetails");
//Get the DetailsViewManager using Reflection
var propertyInfo = dataGrid.GetType().GetField("DetailsViewManager", System.Reflection.BindingFlags.Instance | System.Reflection.BindingFlags.NonPublic);
DetailsViewManager detailsViewManager = propertyInfo.GetValue(dataGrid) as DetailsViewManager;
if (detailsViewDataGrid == null)
{
    detailsViewManager.BringIntoView(index);
    detailsViewDataGrid = this.dataGrid.GetDetailsViewGrid(this.dataGrid.ResolveToRecordIndex(recordIndex), " OrderDetails ");
}

{% endhighlight %}
{% endtabs %}

![](Selection_images/Selection_img10.png)


You can get the sample from [here](http://www.syncfusion.com/downloads/support/directtrac/general/DETAIL~1781445470.ZIP).

### Programmatically select the records in DetailsViewDataGrid which is not in view

#### Scrolling to the DetailsViewDataGrid

You can expand the `DetailsViewDataGrid` by using `ExpandDetailsViewAt` helper method. If the `DetailsViewDataGrid` is already expanded, you can use [ScrollInView](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfDataGridClassScrollInViewTopic.html) method to bring it into view. You can also use [DetailsViewManager.BringIntoView](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridDetailsViewManagerClassBringIntoViewTopic.html) method to get the `DetailsViewDataGrid` into view.

{% tabs %}
{% highlight c# %}

//  find DetailsViewDataRow index based on relational column
int index = 0;
foreach (var def in this.dataGrid.DetailsViewDefinition)
{
    if (def.RelationalColumn == "ProductDetails")
    {
        index = this.dataGrid.DetailsViewDefinition.IndexOf(def);
        index = parentRowIndex + index + 1;
    }
}

var rowcolumnIndex = new RowColumnIndex(index, 1);
//Get the DetailsViewDataGrid by passing the corresponding row index and relation name
var detailsViewDataGrid = this.dataGrid.GetDetailsViewGrid(this.dataGrid.ResolveToRecordIndex(parentRowIndex), "ProductDetails");
//if the DetailsViewDataGrid is not already expanded, call BringIntoView method
if (detailsViewDataGrid == null)
{
    detailsViewManager.BringIntoView(index);
    detailsViewDataGrid = this.dataGrid.GetDetailsViewGrid(this.dataGrid.ResolveToRecordIndex(parentRowIndex), "ProductDetails");    
}
else
{
    // if the DetailsViewDataGrid is already expanded, bring that into view
    dataGrid.ScrollInView(rowcolumnIndex);
}

{% endhighlight %}
{% endtabs %}

#### Select the record in the DetailsViewDataGrid

You can select the record of the `DetailsViewDataGrid` programmatically at run time by setting the corresponding child grid record index to the `SfDataGrid.SelectedIndex` property.

{% tabs %}
{% highlight c# %}

detailsViewDataGrid.SelectedIndex = childindex;

{% endhighlight %}
{% endtabs %}

You can get the sample from [here](http://www.syncfusion.com/downloads/support/directtrac/general/SELECT~1638424730.ZIP ).

### Customizing the SelectionController for DetailsViewDataGrid

The `DetailsViewDataGrid` process the selection operations in selection controller. Below are the built-in selection controllers,

[GridSelectionController](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridSelectionControllerClassTopic.html) – Process selection operations when selection unit as row.

[GridCellSelectionController](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridCellSelectionControllerClassTopic.html) – Process selection operations when selection unit as cell or Any.

You can customize the default row selection behavior by overriding `GridSelectionController` class and set it to `DetailsViewDataGrid.SelectionController`.

The below code-snippet explains you about the customization of `GridSelectionController` class.

{% tabs %}
{% highlight c# %}

this.dataGrid.DetailsViewLoading += dataGrid_DetailsViewLoading;
void dataGrid_DetailsViewLoading(object sender, DetailsViewLoadingAndUnloadingEventArgs e)
{
    if (!(e.DetailsViewDataGrid.SelectionController is GridSelectionControllerExt))
    e.DetailsViewDataGrid.SelectionController = new GridSelectionControllerExt (e.DetailsViewDataGrid);
}

public class GridSelectionControllerExt : GridSelectionController
{      
    public GridSelectionControllerExt(SfDataGrid datagrid)
        : base(datagrid)
    { 
    }
}

{% endhighlight %}
{% endtabs %}

## Scrolling Rows or Columns

### Automatic scrolling on Drag Selection

SfDataGrid will scrolls rows and columns automatically when you try to perform the drag selection like in excel. You can enable or disable AutoScrolling by setting the [AutoScroller.AutoScrolling](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridAutoScrollerClassAutoScrollingTopic.html) property.

{% tabs %}
{% highlight c# %}

this.dataGrid.AutoScroller.AutoScrolling = AutoScrollOrientation.Both;

{% endhighlight %}
{% endtabs %}

### Scroll to particular RowColumnIndex

You can scroll programmatically to particular cell using [ScrollInView](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfDataGridClassScrollInViewTopic.html) method by passing row and column index. 

{% tabs %}
{% highlight c# %}

int rowIndex = this.dataGrid.GetLastDataRowIndex();
int columnIndex = this.dataGrid.GetLastColumnIndex();
this.dataGrid.ScrollInView(new RowColumnIndex(rowIndex, columnIndex));

{% endhighlight %}
{% endtabs %}

### Scroll to SelectedItem

You can scroll programmatically to the `SelectedItem` using the `ScrollInView` method.

{% tabs %}
{% highlight c# %}

using Syncfusion.UI.Xaml.Grid.Helpers;
var rowindex = this.datagrid.ResolveToRowIndex(this.datagrid.SelectedItem);
var columnindex = this.datagrid.ResolveToStartColumnIndex();
this.datagrid.ScrollInView(new RowColumnIndex(rowindex, columnindex));

{% endhighlight %}
{% endtabs %}

## Mouse and Keyboard Behaviors

### Keyboard Behavior

<table>
<tr>
<th>
Key or KeyCombinations 
</th>
<th>
Description
</th>
</tr>
<tr>
<td>
<kbd>DownArrow</kbd>
</td>
<td>
Moves CurrentCell directly below the active current cell. If the CurrentCell is in last row, pressing Down arrow does nothing.
</td>
</tr>
<tr>
<td>
<kbd>UpArrow</kbd>
</td>
<td>
Moves the CurrentCell directly above the active current cell. If the CurrentCell is in first row, pressing Up arrow does nothing.
</td>
</tr>
<tr>
<td>
<kbd>LeftArrow</kbd>
</td>
<td>
Moves the current cell to previous to the active current cell. If the CurrentCell is in first cell, pressing Left arrow does nothing. If the focused row is group header, the group will be collapsed when it is in expanded state.
</td>
</tr>
<tr>
<td>
<kbd>RightArrow</kbd>
</td>
<td>
Moves the current cell to next to the active current cell. If the CurrentCell is in last cell, pressing Right arrow does nothing. If the focused row is group header, the group will expanded when it is in collapsed state.
</td>
</tr>
<tr>
<td>
<kbd>Home</kbd> / <kbd>Ctrl</kbd> + <kbd>LeftArrow</kbd>
</td>
<td>
Moves the current cell to the first cell of the current row.
</td>
</tr>
<tr>
<td>
<kbd>End</kbd> / <kbd>Ctrl </kbd> + <kbd> RightArrow</kbd>
</td>
<td>
Moves the current cell to the last cell of the current row.
</td>
</tr>
<tr>
<td>
<kbd>PageDown</kbd>
</td>
<td>
The SfDataGrid will be scrolled to next set of rows that are not displayed in view, including the row that are partially displayed and the current cell is set to last row.
</td>
</tr>
<tr>
<td>
<kbd>PageUp</kbd>
</td>
<td>
The SfDataGrid will be scrolled to previous set of rows that are not displayed in view, including the row that are partially displayed and the current cell is set to the first row.
</td>
</tr>
<tr>
<td>
<kbd>Tab</kbd>
</td>
<td>
Moves the current cell to next to the active current cell. If the active current cell is the last cell of the current row, the focus will moved to first cell of the row next to the current row.If the active current cell is the last cell of the last row, the focus will be moved to next control in the tab order of the parent container.
</td>
</tr>
<tr>
<td>
<kbd>Shift</kbd> + <kbd>Tab</kbd>
</td>
<td>
Moves the current cell to previous to the active current cell. If the active current cell is the first cell of the current row, the current cell will moved to last cell of the row previous to the current row.If the active current cell is the first cell of the first row, the focus will be moved to previous control in the tab order of the parent container.
</td>
</tr>
<tr>
<td>
<kbd>Ctrl</kbd> + <kbd>DownArrow</kbd>
</td>
<td>
Moves the current cell to the current column of the last row.
</td>
</tr>
<tr>
<td>
<kbd>Ctrl</kbd> + <kbd>UpArrow</kbd>
</td>
<td>
Moves the current cell to the current column of the first row.
</td>
</tr>
<tr>
<td>
<kbd>Ctrl</kbd> + <kbd>Home</kbd>
</td>
<td>
Moves the current cell to the first cell of the first row.
</td>
</tr>
<tr>
<td>
<kbd>Ctrl</kbd> + <kbd>End</kbd>
</td>
<td>
Moves the current cell to the last cell of the last row.
</td>
</tr>
<tr>
<td>
<kbd>Enter</kbd>
</td>
<td>
If the active current cell is in edit mode, the changes will committed and moves the current cell to below the active current cell. If the active current cell is in last row, commits changes only and retains in the same cell.
</td>
</tr>
<tr>
<td>
<kbd>Ctrl</kbd> + <kbd>Enter</kbd>
</td>
<td>
Commits only the changes when the current cell in edit mode and retains the focus in same cell.
</td>
</tr>
<tr>
<td>
<kbd>F2</kbd>
</td>
<td>
If the [DataGrid.AllowEditing](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfGridBaseClassAllowEditingTopic.html) property is true and the [GridColumn.AllowEditing](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridColumnBaseClassAllowEditingTopic.html) property is true for the current column, the current cell enters into edit mode.
</td>
</tr>
<tr>
<td>
<kbd>Esc</kbd>
</td>
<td>
If the current cell is in edit mode, reverts the changes that had been done in the current cell. If the underlying source implements the {{'[IEditableObject](https://msdn.microsoft.com/en-us/library/system.componentmodel.ieditableobject)'| markdownify }}, on pressing of Esc key for the second time will cancel the edit mode for entire row.
</td>
</tr>
<tr>
<td>
<kbd>Delete</kbd>
</td>
<td>
If the current cell is not in edit mode, the current row will be deleted.
</td>
</tr>
<tr>
<td>
<kbd>Ctrl</kbd> + <kbd>A</kbd>
</td>
<td>
All rows or cells will be selected.
</td>
</tr>
</table>
N> When the `NavigationMode` is in `Row`, the Right Arrow and Left Arrow only work for grouping headers and the following keys <kbd>Tab</kbd>, <kbd>Shift</kbd> + <kbd>Tab</kbd>, <kbd>Delete</kbd>, <kbd>Home</kbd>, <kbd>End</kbd> will not work. 

### Shift Key Combinations

When the [SelectionMode](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfGridBaseClassSelectionModeTopic.html) is set to `Extended`, you can select multiple rows or cells using the navigation keys along with the <kbd>Shift</kbd> key. Before navigation starts, the current cell will be marked as a pressed cell and the selection will be done in all rows or cells between the pressed cell and current cell. 

<table>
<tr>
<th>
KeyCombinations
</th>
</tr>
<tr>
<td>
<kbd>Shift</kbd> + <kbd>DownArrow</kbd>
</td>
</tr>
<tr>
<td>
<kbd>Shift</kbd> + <kbd>UpArrow</kbd>
</td>
</tr>
<tr>
<td>
<kbd>Shift</kbd> + <kbd>RightArrow</kbd>
</td>
</tr>
<tr>
<td>
<kbd>Shift</kbd> + <kbd>LeftArrow</kbd>
</td>
</tr>
<tr>
<td>
<kbd>Shift</kbd> + <kbd>Home</kbd>
</td>
</tr>
<tr>
<td>
<kbd>Shift</kbd> + <kbd> End</kbd>
</td>
</tr>
<tr>
<td>
<kbd>Shift</kbd> + <kbd>PageDown</kbd>
</td>
</tr>
<tr>
<td>
<kbd>Shift</kbd> + <kbd>PageUp</kbd>
</td>
</tr>
<tr>
<td>
<kbd>Shift</kbd> + <kbd>Ctrl</kbd> + <kbd>DownArrow</kbd>
</td>
</tr>
<tr>
<td>
<kbd>Shift</kbd> +<kbd> Ctrl</kbd> + <kbd>UpArrow</kbd>
</td>
</tr>
<tr>
<td>
<kbd>Shift</kbd> + <kbd>Ctrl</kbd> + <kbd>RightArrow</kbd>
</td>
</tr>
<tr>
<td>
<kbd>Shift</kbd> + <kbd>Ctrl</kbd> + <kbd>LeftArrow</kbd>
</td>
</tr>
<tr>
<td>
<kbd>Shift</kbd> + <kbd>Ctrl</kbd> + <kbd>Home</kbd>
</td>
</tr>
<tr>
<td>
<kbd>Shift</kbd> +<kbd> Ctrl</kbd> + <kbd>End</kbd>
</td>
</tr>
<tr>
<td>
<kbd>Shift</kbd> + <kbd>Ctrl</kbd> + <kbd>PageDown</kbd>
</td>
</tr>
<tr>
<td>
<kbd>Shift</kbd> + <kbd>Ctrl</kbd> + <kbd>PageUp</kbd>
</td>
</tr>
</table>
### Mouse Behavior

You can enable/disable the selection when the mouse button is in pressed state by setting the AllowSelectionOnPointerPressed property.

When the `SelectionMode` is set to `Extended`, you can select multiple rows or cells by clicking on any cell along with <kbd>ctrl</kbd> and <kbd>Shift</kbd> key. When you click a cell along with <kbd>Ctrl</kbd> key, you can select or deselect the particular row or cell. When you click a cell along with <kbd>Shift</kbd> key, you can select the range rows or cells from the pressed cell to the current cell.

### Customizing mouse and keyboard behaviors

You can customize mouse and keyboard behaviors by overriding the selection controller. You can refer the section `Customizing Selection Behaviors` to override the selection controller.

## Events Processed on Selection

### CurrentCellActivating Event

The [CurrentCellActivating](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfDataGridClassCurrentCellActivatingTopic.html) event will occurs before moving the current cell to particular cell. [CurrentCellActivatingEventArgs](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridCurrentCellActivatingEventArgsClassTopic.html) has following members which provides information for `CurrentCellActivatingEvent`.

[ActivationTrigger](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridCurrentCellActivatingEventArgsClassActivationTriggerTopic.html) – Returns the reason for moving the current cell.

[CurrentRowColumnIndex](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridCurrentCellActivatingEventArgsClassCurrentRowColumnIndexTopic.html) – `RowColumnIndex` of the cell where the current cell need to move.

[PreviousRowColumnIndex](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridCurrentCellActivatingEventArgsClassPreviousRowColumnIndexTopic.html) – `RowColumnIndex` of the cell from where the current cell was move.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfDataGrid x:Name="dataGrid"
                       CurrentCellActivating="dataGrid_CurrentCellActivating"
                       ItemsSource="{Binding Orders}">

{% endhighlight %}

{% highlight c# %}

this.dataGrid.CurrentCellActivating += dataGrid_CurrentCellActivating;

void dataGrid_CurrentCellActivating(object sender, CurrentCellActivatingEventArgs args)
{
}

{% endhighlight %}
{% endtabs %}

You can cancel the current cell moving process within this event by setting [GridCurrentCellActivatingEventArgs.Cancel](http://msdn2.microsoft.com/en-us/library/system.componentmodel.canceleventargs.cancel.aspx) as true.

{% tabs %}
{% highlight c# %}

void dataGrid_CurrentCellActivating(object sender, CurrentCellActivatingEventArgs args)
{
    var provider = this.dataGrid.View.GetPropertyAccessProvider();
    var record = this.dataGrid.GetRecordAtRowIndex(args.CurrentRowColumnIndex.RowIndex);
    if (record == null)
        return;
        
    var column = this.dataGrid.Columns[this.dataGrid.ResolveToGridVisibleColumnIndex(args.CurrentRowColumnIndex.ColumnIndex)];
    var cellValue = provider.GetValue(record, column.MappingName);
    if (cellValue.ToString() == "1001")
        args.Cancel = true;
}

{% endhighlight %}
{% endtabs %}

### CurrentCellActivated Event

The [CurrentCellActivated](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfDataGridClassCurrentCellActivatedTopic.html) event will occur once the current cell is moved to corresponding cell. [CurrentCellActivatedEventArgs](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridCurrentCellActivatedEventArgsClassTopic.html) has following members which provides information for `CurrentCellActivated` event.

[ActivationTrigger](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridCurrentCellActivatedEventArgsClassActivationTriggerTopic.html) – Returns the reason of the current cell movement.

[CurrentRowColumnIndex](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridCurrentCellActivatedEventArgsClassCurrentRowColumnIndexTopic.html) – `RowColumnIndex` of the cell where the current cell was moved.

[PreviousRowColumnIndex](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridCurrentCellActivatedEventArgsClassPreviousRowColumnIndexTopic.html) – `RowColumnIndex` of the cell from where the current cell has been moved.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfDataGrid x:Name="dataGrid"
                       CurrentCellActivated="dataGrid_CurrentCellActivated"
                       ItemsSource="{Binding Orders}">

{% endhighlight %}

{% highlight c# %}

this.dataGrid.CurrentCellActivated += dataGrid_CurrentCellActivated;

void dataGrid_CurrentCellActivated(object sender, CurrentCellActivatedEventArgs args)
{
}

{% endhighlight %}
{% endtabs %}

### SelectionChanging Event

[SelectionChanging](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfDataGridClassSelectionChangingTopic.html) event occurs before processing the selection to particular row or cell. This event will be triggered only to the keyboard and mouse interactions. [GridSelectionChangingEventArgs](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridSelectionChangingEventArgsClassTopic.html) has the following members which provides the information for `SelectionChanging` event.  

[AddedItems](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridSortColumnsChangingEventArgsClassAddedItemsTopic.html) – Collection of `GridRowInfo` or `GridCellInfo` where the selection going to process.

[RemovedItems](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridSortColumnsChangingEventArgsClassRemovedItemsTopic.html) – Collection of `GridRowInfo` or `GridCellInfo` where the selection going to remove.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfDataGrid x:Name="dataGrid"
                       SelectionChanging="dataGrid_SelectionChanging"
                       ItemsSource="{Binding Orders}">

{% endhighlight %}

{% highlight c# %}

this.dataGrid.SelectionChanging += dataGrid_SelectionChanging;

void dataGrid_SelectionChanging(object sender, GridSelectionChangingEventArgs e)
{
}

{% endhighlight %}
{% endtabs %}

You can cancel the selection process within this event by setting [GridSelectionChangingEventArgs.Cancel](http://msdn2.microsoft.com/en-us/library/system.componentmodel.canceleventargs.cancel.aspx) property as true.

{% tabs %}
{% highlight c# %}

void dataGrid_SelectionChanging(object sender, GridSelectionChangingEventArgs e)
{
    var unBounRow = e.AddedItems.Where(rowInfo => (rowInfo as GridRowInfo).IsUnBoundRow).ToList();
    if(unBounRow.Count() > 0)
        unBounRow.All(row => e.AddedItems.Remove(row));
}

{% endhighlight %}
{% endtabs %}

### SelectionChanged Event

The [SelectionChanged](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfDataGridClassSelectionChangedTopic.html) event will occurs once the selection process has been completed for particular row or cell in SfDataGrid. [GridSelectionChangedEventArgs](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridSelectionChangedEventArgsClassTopic.html) has following members which provides information for `SelectionChanged` event.

[AddedItems](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridSelectionChangedEventArgsClassAddedItemsTopic.html) – Collection of `GridRowInfo` or `GridCellInfo` where the selection has been processed.

[RemovedItems](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridSelectionChangedEventArgsClassRemovedItemsTopic.html) – Collection of `GridRowInfo` or `GridCellInfo` from where the selection has been removed.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfDataGrid x:Name="dataGrid"
                       SelectionChanged="dataGrid_SelectionChanged"
                       ItemsSource="{Binding Orders}">

{% endhighlight %}

{% highlight c# %}

this.dataGrid.SelectionChanged += dataGrid_SelectionChanged;

void dataGrid_SelectionChanged(object sender, GridSelectionChangedEventArgs e)
{
}

{% endhighlight %}
{% endtabs %}

## Appearance

### Changing Selection Background and Foreground

You can change the selection background and foreground using [RowSelectionBrush](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfDataGridClassRowSelectionBrushTopic.html), [GroupRowSelectionBrush](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfDataGridClassGroupRowSelectionBrushTopic.html) and [SelectionForeGroundBrush](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfDataGridClassSelectionForegroundBrushTopic.html) properties. The `RowSelectionBrush` is only applied to the rows other than summary rows and the `GroupRowSelectionRows` is applied for caption summary and group summary rows.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfDataGrid x:Name="dataGrid"
                       AllowGrouping="True"
                       ShowGroupDropArea="True"
                       RowSelectionBrush="#FFDFF3F4"
                       GroupRowSelectionBrush="#FFC8E3E3"
                       SelectionForegroundBrush="DarkBlue"
                       SelectionMode="Extended"
                       ItemsSource="{Binding Orders}">

{% endhighlight %}
{% endtabs %}

![](Selection_images/Selection_img11.png)


### Changing Current Cell Border Style

You can change the current cell border thickness and border color using [CurrentCellBorderThickness](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfGridBaseClassCurrentCellBorderThicknessTopic.html) and [CurrentCellBorderBrush](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfGridBaseClassCurrentCellBorderBrushTopic.html) property.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfDataGrid x:Name="dataGrid"
                       CurrentCellBorderBrush="Red"
                       CurrentCellBorderThickness="1.6"
                       ItemsSource="{Binding Orders}">

{% endhighlight %}
{% endtabs %}

![](Selection_images/Selection_img12.png)


### Customizing Row Selection Border

You can customize the row selection by editing the control template of corresponding row controls.

Data Row / Add New Row – [VirtualizingCellsControl](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridVirtualizingCellsControlClassTopic.html)

CaptionSummary Row – [CaptionSummaryRowControl](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridCaptionSummaryRowControlClassTopic.html)

GroupSummary Row – [GroupSummaryRowControl](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGroupSummaryRowControlClassTopic.html)

UnBound Row – [UnBoundRowControl](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridUnBoundRowControlClassTopic.html)

Filter Row - `FilterRowControl`

{% tabs %}
{% highlight xaml %}

<Style TargetType=" syncfusion:VirtualizingCellsControl ">
    <Setter Property="Background" Value="Transparent" />
    <Setter Property="BorderBrush" Value="Gray" />
    <Setter Property="BorderThickness" Value="0" />
    <Setter Property="IsTabStop" Value="False" />
    <Setter Property="Template">
        <Setter.Value>
            <ControlTemplate TargetType="syncfusion:VirtualizingCellsControl">
                <Grid>
                    <Border x:Name="PART_RowBorder"
                            BorderBrush="{TemplateBinding BorderBrush}"
                            BorderThickness="{TemplateBinding BorderThickness}"/>
                    <Rectangle x:Name="PART_CurrentFocusRow"
                               Margin="{TemplateBinding CurrentFocusBorderMargin}"
                               Stroke="DarkGray"
                               StrokeDashArray="2,2"
                               StrokeThickness="1"
                               Visibility="{TemplateBinding CurrentFocusRowVisibility}" />
                    <Border Background="{TemplateBinding RowHoverBackgroundBrush}"
                            BorderBrush="{TemplateBinding RowHoverBackgroundBrush}"
                            BorderThickness="{TemplateBinding RowHighlightBorderThickness}"
                            Clip="{TemplateBinding HighlightBorderClipRect}"
                            Visibility="{TemplateBinding HighlightSelectionBorderVisiblity}" />
                    <Rectangle Clip="{TemplateBinding RowBackgroundClip}" 
                               Fill="{TemplateBinding Background}" />
                    <!-- Adding new border to show border for whole selected row -->
                    <Border x:Name="PART_SelectionBorder"
                            BorderBrush="Red"
                            BorderThickness="1.5,1.5,1.5,2.5"
                            Opacity="0.75"
                            Background="{TemplateBinding RowSelectionBrush}"
                            Clip="{TemplateBinding SelectionBorderClipRect}"
                            Visibility="{TemplateBinding SelectionBorderVisiblity}" />
                    <Border BorderBrush="{TemplateBinding BorderBrush}"
                            BorderThickness="{TemplateBinding BorderThickness}">
                        <ContentPresenter />
                    </Border>
                </Grid>
            </ControlTemplate>
        </Setter.Value>
    </Setter>
</Style>

{% endhighlight %}
{% endtabs %}

![](Selection_images/Selection_img13.png)


### Customizing Cell Selection

You can customize the cell selection by editing the control template of the corresponding cell control.

DataRow / AddNewRow – [GridCell](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridCellClassTopic.html)

UnBound Row – [GridUnBoundRowCell](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridUnBoundRowCellClassTopic.html)

Filter Row - `GridFilterRowCell`

{% tabs %}
{% highlight xaml %}

<Style TargetType=" syncfusion:GridCell ">
    <Setter Property="Background" Value="Transparent" />
    <Setter Property="BorderBrush" Value="Gray" />
    <Setter Property="BorderThickness" Value="0,0,1,1" />
    <Setter Property="Padding" Value="0,0,0,0" />
    <Setter Property="IsTabStop" Value="False" />
    <Setter Property="VerticalContentAlignment" Value="Center"/>
    <Setter Property="Template">
        <Setter.Value>
            <ControlTemplate TargetType="{x:Type syncfusion:GridCell}">
                <Grid >
                    <Border Background="{TemplateBinding CellSelectionBrush}"
                            Visibility="{TemplateBinding SelectionBorderVisibility}" />
                    <Border x:Name="PART_GridCellBorder"
                            Background="{TemplateBinding Background}"
                            BorderBrush="{TemplateBinding BorderBrush}"
                            BorderThickness="{TemplateBinding BorderThickness}">
                        <Grid>
                            <ContentPresenter Margin="{TemplateBinding Padding}" />
                        </Grid>
                    </Border>
                    <Border Background="Transparent"
                            BorderBrush="Red"
                            BorderThickness="0.5"
                            IsHitTestVisible="False"
                            Margin="0,0,1,1"
                            Visibility="{TemplateBinding CurrentCellBorderVisibility}" />
                    <!—Adding new border to show inner border to the CurrentCellBorder -->
                    <Border Background="Transparent"
                            BorderBrush="Red"
                            BorderThickness="0.5"
                            IsHitTestVisible="False"
                            Margin="2,2,3,3"
                            Visibility="{TemplateBinding CurrentCellBorderVisibility}" />
                    <Border x:Name="PART_InValidCellBorder"
                            Width="10"
                            Height="10"
                            HorizontalAlignment="Right"
                            Visibility="Collapsed"
                            VerticalAlignment="Top">
                        <Path Data="M0.5,0.5 L12.652698,0.5 12.652698,12.068006 z"
                              Fill="Red"
                              Stretch="Fill" />
                    </Border>
                </Grid>
            </ControlTemplate>
        </Setter.Value>
    </Setter>
</Style>

{% endhighlight %}
{% endtabs %}

![](Selection_images/Selection_img14.png)


## Binding Selection Properties

You can bind the selection properties like `SelectedItem`, `SelectedIndex` and `CurrentItem` to the properties in ViewModel directly. 

{% tabs %}
{% highlight xaml %}

<syncfusion:SfDataGrid x:Name="dataGrid"
                       SelectedItem="{Binding DataGridSelectedItem, Mode=TwoWay}"
                       CurrentItem="{Binding DataGridCurrentItem,Mode=TwoWay}"
                       SelectedIndex="{Binding DataGridSelectedIndex,Mode=TwoWay}"
                       ItemsSource="{Binding Orders}">
                       

{% endhighlight %}
{% endtabs %}

## Customizing Selection Behaviors

The SfDataGrid process the selection operations in selection controller. Below are the built-in selection controllers,

[GridSelectionController](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridSelectionControllerClassTopic.html) – Process selection operations when selection unit as row.

[GridCellSelectionController](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridCellSelectionControllerClassTopic.html) – process selection operations when selection unit as cell or Any.

You can customize the default row selection behaviors by overriding `GridSelectionController` class and set it to `SfDataGrid.SelectionController`.

{% tabs %}
{% highlight c# %}

this.dataGrid.SelectionController = new GridSelectionControllerExt(this.dataGrid);

public class GridSelectionControllerExt:GridSelectionController
{
    public GridSelectionControllerExt(SfDataGrid dataGrid):base(dataGrid)
    {     
    }
}

{% endhighlight %}
{% endtabs %}

### Changing Enter Key Behavior

By default, while pressing <kbd>Enter</kbd> key the current cell will be moved to next focused cell in the same column. You can change the behavior by overriding the corresponding selection controllers based on `SelectionUnit`.

You can change the <kbd>Enter</kbd> key behavior by overriding [ProcessKeyDown](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridSelectionControllerClassProcessKeyDownTopic.html) method in selection controller. In this method you have to create new [KeyEventArgs](https://msdn.microsoft.com/en-us/library/system.windows.input.keyeventargs) which refers the <kbd>Tab</kbd> key and processes the <kbd>Tab</kbd> key action.

{% tabs %}
{% highlight c# %}

public class GridSelectionControllerExt:GridSelectionController
{
    public GridSelectionControllerExt(SfDataGrid dataGrid):base(dataGrid)
    {    
    }
    
    protected override void ProcessKeyDown(KeyEventArgs args)
    {
        if (args.Key == Key.Enter)
        {
            //Creates new KeyEventArgs to refer the Tab key.
            KeyEventArgs arguments = new KeyEventArgs(args.KeyboardDevice, args.InputSource, args.Timestamp, Key.Tab) { RoutedEvent = args.RoutedEvent };
            //Base ProcessKeyDown is invoked to process Tab key operations.
            base.ProcessKeyDown(arguments);
            args.Handled = arguments.Handled;
            return;
        }
        base.ProcessKeyDown(args);
    }
}

{% endhighlight %}
{% endtabs %}

### Selecting all rows in a group when expanding

You can select all the rows in the group which is expanding through mouse click. To achieve this, you have to set `SelectionMode` as `Extended` or `Multiple` and also need to override [HandlePointerOperations](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridBaseSelectionControllerClassHandlePointerOperationsTopic.html) method in selection controller.

{% tabs %}
{% highlight c# %}

public class GridSelectionControllerExt:GridSelectionController
{
    public GridSelectionControllerExt(SfDataGrid dataGrid):base(dataGrid)
    {     
    }
    
    public override void HandlePointerOperations(GridPointerEventArgs args, Syncfusion.UI.Xaml.ScrollAxis.RowColumnIndex rowColumnIndex)
    {
        base.HandlePointerOperations(args, rowColumnIndex);
        if (args.Operation == PointerOperation.Released)
        {
            if (this.DataGrid.View.TopLevelGroup != null)
            {
                //Get the group from the DisplayElements by resolving record index of corresponding row index
                var group = this.DataGrid.View.TopLevelGroup.DisplayElements[this.DataGrid.ResolveToRecordIndex(rowColumnIndex.RowIndex)];
                if (group != null && group is Group)
                SelectGroupRows(group as Group);
            }
        }
    }
    
    private void SelectGroupRows(Group group)
    {
        if (group == null || !group.IsExpanded)
            return;
        //Check whether the group contains inner level groups.
        if (group.Groups == null)
        {
            //Get the corresponding start index of record by getting it from DisplayElements .
            var startindex = this.DataGrid.View.TopLevelGroup.DisplayElements.IndexOf(group as Group);
            //Resolve the recordIndex to RowIndex.
            var startRowIndex = this.DataGrid.ResolveToRowIndex(startindex);
            //Gets the count of rows in the group.
            var count = group.ItemsCount + this.DataGrid.GroupSummaryRows.Count;
            //Select the rows from corresponding start and end row index
            this.DataGrid.SelectionController.SelectRows(startRowIndex, startRowIndex + count);
        }
        else
        {
            foreach (var gr in group.Groups)
            {
                //Called recursively, to traverse it inner level of group.
                SelectGroupRows(gr);
                var startindex = this.DataGrid.View.TopLevelGroup.DisplayElements.IndexOf(group as Group);
                var startRowIndex = this.DataGrid.ResolveToRowIndex(startindex);
                //Get the corresponding end index of the group by getting it from DisplayElements using the innter level group.
                var endindex = this.DataGrid.View.TopLevelGroup.DisplayElements.IndexOf(gr as Group);
                var endRowIndex = this.DataGrid.ResolveToRowIndex(endindex);                    
                this.DataGrid.SelectionController.SelectRows(startRowIndex, endRowIndex);
            }
        }
    }
}

{% endhighlight %}
{% endtabs %}

### Selecting the column when clicking header

You can select entire column on clicking column header by handling [MouseLeftButtonUp](https://msdn.microsoft.com/en-us/library/system.windows.uielement.mouseleftbuttonup) event of SfDataGrid. You have to set `SelectionUnit` as `Cell` or `Any` and `SelectionMode` as `Extended` or `Multiple` to achieve this behavior. 

By default the sorting operation will be performed while clicking on column header where you can disable this action by setting `AllowSorting` as false or [SortClickAction](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfGridBaseClassSortClickActionTopic.html) as `DoubleClick`.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfDataGrid x:Name="dataGrid"
                       SelectionUnit="Cell"
                       SortClickAction="DoubleClick"
                       SelectionMode="Extended"
                       ItemsSource="{Binding Orders}">

{% endhighlight %}

{% highlight c# %}

this.sfdatagrid.PointerPressed += Sfdatagrid_PointerPressed;

private void Sfdatagrid_PointerPressed(object sender, PointerRoutedEventArgs e)
{
    //GetVisualContainer 
    var visualContainer = this.sfdatagrid.GetVisualContainer();
    var rowcolumnindex = visualContainer.PointToCellRowColumnIndex(e.GetCurrentPoint(visualContainer).Position);
    var columnindex = this.sfdatagrid.ResolveToGridVisibleColumnIndex(rowcolumnindex.ColumnIndex);
    if (columnindex < 0)
        return;
    //Return if it is not HeaderRow
    if (this.sfdatagrid.GetHeaderIndex() != rowcolumnindex.RowIndex)
        return;
    var firstrowdata = this.sfdatagrid.GetRecordAtRowIndex(sfdatagrid.GetFirstRowIndex());
    //Get the record of LastRowIndex 
    var lastrowdata = this.sfdatagrid.GetRecordAtRowIndex(sfdatagrid.GetLastRowIndex());
    //Get the column of particular index
    var column = this.sfdatagrid.Columns[columnindex];
    if (firstrowdata == null || lastrowdata == null)
        return;
    //Select the column
    this.sfdatagrid.SelectCells(firstrowdata, column, lastrowdata, column);
}

{% endhighlight %}
{% endtabs %}

You can get the sample from [here](http://www.syncfusion.com/downloads/support/directtrac/general/COLUMN~1-134284707.ZIP).

![](Selection_images/Selection_img15.png)


### Avoid CaptionSummaryRow selection on Grouping

While grouping any column, by default the first `CaptionSummaryRow` will be selected when the `CurrentItem` is null. You can change this action by overriding the `ProcessOnGroupChanged` method in selection controller. 

{% tabs %}
{% highlight c# %}

public class GridSelectionControllerExt:GridSelectionController
{
    public GridSelectionControllerExt(SfDataGrid dataGrid):base(dataGrid)
    {     
    }

    protected override void ProcessOnGroupChanged(System.Collections.Specialized.NotifyCollectionChangedEventArgs args)
    {
        base.ProcessOnGroupChanged(args);
        var removedItems = new List<object>();
        //Refresh the selection only in record rows.
        this.RefreshSelectedItems(ref removedItems);
        //Updates the current cell and current row.
        this.UpdateCurrentRowIndex();
    }
}

{% endhighlight %}
{% endtabs %}

