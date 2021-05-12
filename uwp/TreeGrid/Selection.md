---
layout: post
title: Selection in UWP TreeGrid control | Syncfusion
description: Learn here all about Selection support in Syncfusion UWP TreeGrid (SfTreeGrid) control and more.
platform: uwp
control: SfTreeGrid
documentation: ug
---

# Selection in UWP TreeGrid (SfTreeGrid)

SfTreeGrid allows you select one or more rows.

## Current cell navigation

Keyboard navigation through the rows is determined based on the [NavigationMode](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_NavigationMode) property. [NavigationMode.Cell](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.NavigationMode.html) allows you navigate between the cells in a row and between rows. [NavigationMode.Row](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.NavigationMode.html) allows you navigate only between rows.

## Selection modes

The [SelectionMode](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_SelectionMode) property define the behavior of selection in tree grid. If `SelectionMode` is `Single`, you can select a single row, and if the `SelectionMode` is `Extended` or `Multiple`, you can select multiple rows. If you want to disable the selection, set `SelectionMode` to `None`.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeGrid Name="treeGrid"
                                       AutoExpandMode="RootNodesExpanded"
                                       AutoGenerateColumns="False" 
                                       NavigationMode="Row"
                                       ChildPropertyName="Children"
                                       SelectionMode="Single"
                                       ColumnSizer="Star" 
                                       ExpanderColumn="FirstName"
                                       ItemsSource="{Binding PersonDetails}"
                                       >
{% endhighlight %}
{% endtabs %}

![Row selected in UWP treegrid](Selection_images/Selection_img1.jpeg)

## Disable selection for rows and columns

You can disable selection and navigation on a particular column by setting the [GridColumn.AllowFocus](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridColumnBase.html#Syncfusion_UI_Xaml_Grid_GridColumnBase_AllowFocus) property. You can disable selection on a particular row or column by handling the [CurrentCellActivating](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html) event.

## Multiple row selection

The tree grid allows you select multiple rows by setting the [SelectionMode](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_SelectionMode) property to [Extended](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSelectionMode.html) or [Multiple](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSelectionMode.html), where you can select multiple rows by dragging the mouse on tree grid and using the key modifiers.

When using Extended, you can select multiple rows by pressing the key modifiers Ctrl and Shift.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeGrid Name="treeGrid"
                                       AutoExpandMode="RootNodesExpanded"
                                       AutoGenerateColumns="False" 
                                       NavigationMode="Row"
                                       ChildPropertyName="Children"
                                       SelectionMode="Extended"
                                       ColumnSizer="Star" 
                                       ExpanderColumn="FirstName"
                                       ItemsSource="{Binding PersonDetails}"
                                       >
{% endhighlight %}
{% endtabs %}

![Multiple rows selected in UWP treegrid](Selection_images/Selection_img2.jpeg)

N> When [SelectionMode](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_SelectionMode) is [Multiple](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSelectionMode.html), you can select or deselect multiple rows by clicking the respective rows. In multiple selection, pressing navigation keys moves only the current cell, and you can select or deselect by pressing the <kbd>space</kbd> key.

## Get selected rows

The [SelectedItem](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_SelectedItem) property returns the data object of the selected row, and the [SelectedIndex](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_SelectedIndex) property returns the index of the SelectedItem in SfTreeGrid. SelectedItem denotes the first selected row in multiple selection.

The [CurrentItem](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_CurrentItemProperty) returns the data object that currently has focus, and the [CurrentColumn](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_CurrentColumn) denotes the [GridColumn](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.TreeGridColumn.html) that currently has focus. 

The [CurrentCellInfo](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_CurrentCellInfo) returns an instance [GridCellInfo](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCellInfo.html), which contains the information about the cell that currently has focus.

### Row selection

You can get all the selected records using the [SelectedItems](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_SelectedItems) property, and you can also get all the selected rows' information through [SfTreeGrid.SelectionController.SelectedRows](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.TreeGridBaseSelectionController.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridBaseSelectionController_SelectedRows), which is a collection of [TreeGridRowInfo](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.TreeGridRowInfo.html).

### CurrentItem Vs SelectedItem

Both [SelectedItem](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_SelectedItem) and [CurrentItem ](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_CurrentItem) return the same data object when a single row is selected in tree grid. When you select more than one rows or cells, the record that had been selected initially is maintained in SelectedItem, and the record that currently has focus is maintained in CurrentItem.

## Programmatic selection

### Process selection using properties

You can select a single row by setting the [SelectedItem](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_SelectedItem) property or [SelectedIndex](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_SelectedIndex) property.

{% tabs %}
{% highlight c# %}

var recordIndex = this.treeGrid.ResolveToNodeIndex(6);
this.treeGrid.SelectedIndex = recordIndex;

{% endhighlight %}
{% highlight c# %}

var node = this.treeGrid.GetNodeAtRowIndex(6);
this.treeGrid.SelectedItem = node.Item;

{% endhighlight %}
{% endtabs %}
In row selection, you can select multiple rows by adding data objects to the [SelectedItems](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_SelectedItems) property.
{% tabs %}
{% highlight c# %}
var viewModel = this.treeGrid.DataContext as ViewModel;

foreach (var order in viewModel.PersonDetails)
{
        if (order.LastName == "Buchanan")
        this.treeGrid.SelectedItems.Add(order);
}
{% endhighlight %}
{% endtabs %}

![UWP treegrid shows row with LastName as Buchanan added to SelectedItems collection](Selection_images/Selection_img3.jpeg)

### Process selection using methods

You can select a range of rows using the [SelectRows](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.TreeGridBaseSelectionController.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridBaseSelectionController_SelectedRows) method in row selection.

{% tabs %}
{% highlight c# %}

this.treeGrid.SelectRows(3, 7);

{% endhighlight %}
{% endtabs %}

![UWP treegrid shows with rows from 3 to 7 are selected](Selection_images/Selection_img4.jpeg)

### Process current cell

When you set [CurrentItem](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_CurrentItemProperty) to a particular record, the [CurrentCell](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCurrentCellManager.html#Syncfusion_UI_Xaml_Grid_GridCurrentCellManager_CurrentCell) will be moved to the corresponding record. When [SelectionMode](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_SelectionMode) is [Multiple](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSelectionMode.html) or [Extended](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSelectionMode.html), the selection will added to the particular record item. When the SelectionMode is [Single](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSelectionMode.html), only one cell will be selected.

You can move the [CurrentCell](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCurrentCellManager.html#Syncfusion_UI_Xaml_Grid_GridCurrentCellManager_CurrentCell) to a particular row or column index using the [MoveCurrentCell](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.TreeGridRowSelectionController.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridRowSelectionController_MoveCurrentCell_Syncfusion_UI_Xaml_ScrollAxis_RowColumnIndex_System_Boolean_) method.

{% tabs %}
{% highlight c# %}

this.treeGrid.SelectionController.MoveCurrentCell(new RowColumnIndex(3, 2), false);

{% endhighlight %}
{% endtabs %}

### Clear selection

You can clear the selections using the [ClearSelections](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.TreeGridRowSelectionController.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridRowSelectionController_ClearSelections_System_Boolean_) method. In row selection, you can remove the selection by setting null to the [SelectedItem](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_SelectedItem) or clearing the [SelectedItems](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_SelectedItems) property.

{% tabs %}
{% highlight c# %}

this.treeGrid.SelectionController.ClearSelections(true);

{% endhighlight %}
{% endtabs %}

## Scrolling rows and columns

### Automatic scrolling on drag selection

SfTreeGrid allows scrolling rows and columns automatically when you try to perform the drag selection like in Excel. You can enable or disable auto scrolling by setting the [AutoScroller.AutoScrolling](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_AutoScroller) property.

{% tabs %}
{% highlight c# %}

this.treeGrid.AutoScroller.AutoScrolling = AutoScrollOrientation.Both;

{% endhighlight %}
{% endtabs %}

### Scroll to a particular row and column index

You can scroll programmatically to a particular cell using the [ScrollInView](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_ScrollInView_Syncfusion_UI_Xaml_ScrollAxis_RowColumnIndex_) method by passing row and column indexes.

{% tabs %}
{% highlight c# %}

int rowIndex = this.treeGrid.GetLastDataRowIndex();
int columnIndex = this.treeGrid.GetLastColumnIndex();
this.treeGrid.ScrollInView(new RowColumnIndex(rowIndex, columnIndex));

{% endhighlight %}
{% endtabs %}

### Scroll to selected item

You can scroll programmatically to the `SelectedItem` sing the `ScrollInView` method by resolving the index of the item selected.

{% tabs %}
{% highlight c# %}

var rowIndex = this.treeGrid.ResolveToRowIndex(this.treeGrid.SelectedItem);
var columnIndex = this.treeGrid.ResolveToStartColumnIndex();
this.treeGrid.ScrollInView(new RowColumnIndex(rowIndex, columnIndex));

{% endhighlight %}
{% endtabs %}

## Mouse and keyboard behaviors

### Keyboard behavior

<table>
<tr>
<td>
{{'**Key or Key combinations**'| markdownify }}
</td>
<td>
{{'**Description**'| markdownify }}
</td>
</tr>
<tr>
<td>
<kbd>
DownArrow
</kbd>

</td>
<td>
Moves CurrentCell directly below the active current cell. If the CurrentCell is in the last row, pressing the Down arrow does nothing.
</td>
</tr>
<tr>
<td>
<kbd>
UpArrow
</kbd>

</td>
<td>
Moves the CurrentCell directly above the active current cell. If the CurrentCell is in the first row, pressing the Up arrow does nothing.
</td>
</tr>
<tr>
<td>
<kbd>
LeftArrow
</kbd>

</td>
<td>
Moves the current cell previous to the active current cell. If the CurrentCell is in the first cell, pressing the Left arrow does nothing. If the focused row is group header, the group will be collapsed when it is in expanded state.
</td>
</tr>
<tr>
<td>
<kbd>
RightArrow
</kbd>

</td>
<td>
Moves the current cell to next to the active current cell. If the CurrentCell is in the last cell, pressing the Right arrow does nothing. If the focused row is group header, the group will be expanded when it is in collapsed state.
</td>
</tr>
<tr>
<td>
<kbd>Home</kbd> / <kbd>Ctrl</kbd> + <kbd>LeftArrow</kbd>

</td>
<td>
Moves the current cell to the first cell of the current row.
</td>
</tr>
<tr>
<td>
<kbd>End</kbd> / <kbd>Ctrl</kbd> + <kbd>RightArrow</kbd>

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
The tree grid will be scrolled to the next set of rows that is not displayed in view, including the row that is partially displayed, and the current cell is set to the last row.
</td>
</tr>
<tr>
<td>
<kbd>PageUp</kbd>

</td>
<td>
The tree grid will be scrolled to the previous set of rows that is not displayed in view, including the row that is partially displayed, and the current cell is set to the the first row.
</td>
</tr>
<tr>
<td>
<kbd>Tab</kbd>

</td>
<td>
Moves the current cell next to the active current cell. If the active current cell is the last cell of the current row, the focus will be moved to the first cell of the row next to the current row. If the active current cell is the last cell of the last row, the focus will be moved to next control in the tab order of the parent container.
</td>
</tr>
<tr>
<td>
<kbd>Shift</kbd> + <kbd>Tab</kbd>

</td>
<td>
Moves the current cell previous to the active current cell. If the active current cell is the first cell of the current row, the current cell will be moved to the last cell of the row previous to the current row. If the active current cell is the first cell of the first row, the focus will be moved to previous control in the tab order of the parent container.
</td>
</tr>
<tr>
<td>
<kbd>Ctrl</kbd> + <kbd>DownArrow</kbd>

</td>
<td>
Moves the current cell to the current column of the last row.
</td>
</tr>
<tr>
<td>
<kbd>Ctrl</kbd> + <kbd>UpArrow</kbd>

</td>
<td>
Moves the current cell to the current column of the first row.
</td>
</tr>
<tr>
<td>
<kbd>Ctrl</kbd> + <kbd>Home</kbd>

</td>
<td>
Moves the current cell to the first cell of the first row.
</td>
</tr>
<tr>
<td>
<kbd>Ctrl</kbd> + <kbd>End</kbd>

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
If the active current cell is in edit mode, the changes will be committed, and moves the current cell below the active current cell. If the active current cell is in the last row, commits changes only and retains in the same cell.
</td>
</tr>
<tr>
<td>
<kbd>Ctrl</kbd> + <kbd>Enter</kbd>

</td>
<td>
Commits only the changes when the current cell is in edit mode and retains the focus in same cell.
</td>
</tr>
<tr>
<td>
<kbd>F2</kbd>

</td>
<td>
If the tree grid property is true and the 
{{'[GridColumn.AllowEditing](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridColumnBase.html#Syncfusion_UI_Xaml_Grid_GridColumnBase_AllowEditing)'| markdownify }} property is true for the current column, the current cell enters into the edit mode.
</td>
</tr>
<tr>
<td>
<kbd>Esc</kbd>
</td>
<td>
If the current cell is in edit mode, reverts the changes that had been done in the current cell. If the underlying source implements the {{'[IEditableObject](https://msdn.microsoft.com/en-us/library/system.componentmodel.ieditableobject#%22%22"")'| markdownify }}, pressing the Esc key for the second time cancels the edit mode for entire row.
</td>
</tr>
<tr>
<td>
<kbd>Ctrl</kbd> + <kbd>A</kbd>
</td>
<td>
All rows or cells will be selected.
</td>
</tr>
</table>

### Shift key combinations

When [SelectionMode](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_SelectionMode) is set to [Extended](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSelectionMode.html), you can select multiple rows using the navigation keys along with the Shift key. Before starting navigation, the current cell will be marked as a pressed cell, and the selection will be done in all rows between the pressed cell and current cell.

<table>
<tr>
<td>
{{'**Key combinations**'| markdownify }}
</td>
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
<kbd>Shift</kbd> + <kbd>End</kbd>
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
<kbd>Shift</kbd> + <kbd>Ctrl</kbd> + <kbd>UpArrow</kbd>
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
<kbd>Shift</kbd> + <kbd>Ctrl</kbd> + <kbd>End</kbd>
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

### Mouse behavior

You can enable/disable the selection when the mouse button is in pressed state by setting the [AllowSelectionOnPointerPressed](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_AllowSelectionOnPointerPressed) property.

When [SelectionMode](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_SelectionMode) is set to [Extended](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSelectionMode.html), you can select multiple rows by clicking any cell along with `Ctrl` and `Shift` keys. When you click a cell along with `Ctrl` key, you can select or deselect a particular row. When you click a cell along with `Shift` key, you can select a range row from the pressed cell to the current cell.

### Customize mouse and keyboard behaviors

You can customize the mouse and keyboard behaviors by overriding the selection controller. Refer to the "Customizing Selection Behaviors" section to override the selection controller.

## Events

### CurrentCellActivating

[ActivationTrigger](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.CurrentCellActivatingEventArgs.html#Syncfusion_UI_Xaml_Grid_CurrentCellActivatingEventArgs_ActivationTrigger): Returns the reason for moving the current cell.

[CurrentRowColumnIndex](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.CurrentCellActivatingEventArgs.html#Syncfusion_UI_Xaml_Grid_CurrentCellActivatingEventArgs_CurrentRowColumnIndex): RowColumnIndex of the cell where the current cell needs to move.

[PreviousRowColumnIndex](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.CurrentCellActivatingEventArgs.html#Syncfusion_UI_Xaml_Grid_CurrentCellActivatingEventArgs_PreviousRowColumnIndex): RowColumnIndex of the cell from where the current cell moved.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeGrid Name="treeGrid"
                       Grid.Row="0"
                       AutoExpandMode="RootNodesExpanded"
                       AutoGenerateColumns="False"
                       ChildPropertyName="ReportsTo"
                       CurrentCellActivating="TreeGrid_CurrentCellActivating"                        
                       ItemsSource="{Binding EmployeeInfo}"
                       LiveNodeUpdateMode="AllowDataShaping"
                       Converter="{StaticResource SelectionModeConverter}">
                                                                                                          
{% endhighlight %}
{% highlight c# %}
this.treeGrid.CurrentCellActivating += TreeGrid_CurrentCellActivating;

private void TreeGrid_CurrentCellActivating(object sender, Syncfusion.UI.Xaml.Grid.CurrentCellActivatingEventArgs e)
{
           
}
{% endhighlight %}
{% endtabs %}

You can cancel the current cell moving process within this event by setting [GridCurrentCellActivatingEventArgs.Cancel](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html) to true.

{% tabs %}
{% highlight c# %}
private void TreeGrid_CurrentCellActivating(object sender, Syncfusion.UI.Xaml.Grid.CurrentCellActivatingEventArgs e)
{
    var provider = this.treeGrid.View.GetPropertyAccessProvider();
    var record = this.treeGrid.GetNodeAtRowIndex(e.CurrentRowColumnIndex.RowIndex).Item;

    if (record == null)
        return;

    var column = this.treeGrid.Columns[this.treeGrid.ResolveToGridVisibleColumnIndex(e.CurrentRowColumnIndex.ColumnIndex)];
    var cellValue = provider.GetValue(record, column.MappingName);

    if (cellValue.ToString() == "1001")
        e.Cancel = true;
}
{% endhighlight %}
{% endtabs %}

### CurrentCellActivated

The [CurrentCellActivated](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html) event occurs after the current cell has been moved to the corresponding cell. [CurrentCellActivatedEventArgs](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.CurrentCellActivatedEventArgs.html) has the following members, which provide information to the CurrentCellActivated event.

[ActivationTrigger](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.CurrentCellActivatedEventArgs.html#Syncfusion_UI_Xaml_Grid_CurrentCellActivatedEventArgs_ActivationTrigger): Returns the reason of the current cell movement.

[CurrentRowColumnIndex](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.CurrentCellActivatedEventArgs.html#Syncfusion_UI_Xaml_Grid_CurrentCellActivatedEventArgs_CurrentRowColumnIndex): RowColumnIndex of the cell where the current cell moves.

[PreviousRowColumnIndex](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.CurrentCellActivatedEventArgs.html#Syncfusion_UI_Xaml_Grid_CurrentCellActivatedEventArgs_PreviousRowColumnIndex): RowColumnIndex of the cell where the current cell moved.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeGrid Name="treeGrid"
                       Grid.Row="0"
                       AutoExpandMode="RootNodesExpanded"
                       AutoGenerateColumns="False"
                       ChildPropertyName="ReportsTo"
                       CurrentCellActivated="TreeGrid_CurrentCellActivated"                        
                       ItemsSource="{Binding EmployeeInfo}"
                       LiveNodeUpdateMode="AllowDataShaping"
                       Converter="{StaticResource SelectionModeConverter}">

{% endhighlight %}
{% highlight c# %}
this.treeGrid.CurrentCellActivated += TreeGrid_CurrentCellActivated;

private void TreeGrid_CurrentCellActivated(object sender, Syncfusion.UI.Xaml.Grid.CurrentCellActivatedEventArgs e)
{

}
{% endhighlight %}
{% endtabs %}

### SelectionChanging

The [SelectionChanging](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html) event occurs before processing the selection to a particular row or cell. This event is triggered only to the keyboard and mouse interactions. [GridSelectionChangingEventArgs](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSelectionChangingEventArgs.html) has the following members, which provide information to the `SelectionChanging` event.

[AddedItems](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSelectionChangingEventArgs.html#Syncfusion_UI_Xaml_Grid_GridSelectionChangingEventArgs_AddedItems): Collection of GridCellInfo where selection is going to be processed.

[RemovedItems](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSelectionChangingEventArgs.html#Syncfusion_UI_Xaml_Grid_GridSelectionChangingEventArgs_RemovedItems): Collection of GridRowInfo where the selection is going  to be removed.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeGrid Name="treeGrid"
                       Grid.Row="0"
                       AutoExpandMode="RootNodesExpanded"
                       AutoGenerateColumns="False"
                       ChildPropertyName="ReportsTo"
                       SelectionChanging="TreeGrid_SelectionChanging"
                       ItemsSource="{Binding EmployeeInfo}"
                       LiveNodeUpdateMode="AllowDataShaping"
                       Converter="{StaticResource SelectionModeConverter}">

{% endhighlight %}
{% highlight c# %}
this.treeGrid.SelectionChanging += TreeGrid_SelectionChanging;

private void TreeGrid_SelectionChanging(object sender, Syncfusion.UI.Xaml.Grid.GridSelectionChangingEventArgs e)
{
            
}
{% endhighlight %}
{% endtabs %}

### SelectionChanged

The [SelectionChanged](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html) event occurs after the selection process has been completed for a particular row or cell in tree grid. [GridSelectionChangedEventArgs](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSelectionChangedEventArgs.html) has the following members, which provide information to the `SelectionChanged` event:

[AddedItems](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSelectionChangedEventArgs.html#Syncfusion_UI_Xaml_Grid_GridSelectionChangedEventArgs_AddedItems): Collection of GridRowInfo where selection has been processed.

[RemovedItems](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSelectionChangedEventArgs.html#Syncfusion_UI_Xaml_Grid_GridSelectionChangedEventArgs_RemovedItems): Collection of `GridRowInfo` where selection has been removed.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeGrid Name="treeGrid"
                       Grid.Row="0"
                       AutoExpandMode="RootNodesExpanded"
                       AutoGenerateColumns="False"
                       ChildPropertyName="ReportsTo"
                       SelectionChanged="TreeGrid_SelectionChanged"
                       ItemsSource="{Binding EmployeeInfo}"
                       LiveNodeUpdateMode="AllowDataShaping"
                       Converter="{StaticResource SelectionModeConverter}">

{% endhighlight %}
{% highlight c# %}
this.treeGrid.SelectionChanged += TreeGrid_SelectionChanged;

private void TreeGrid_SelectionChanged(object sender, Syncfusion.UI.Xaml.Grid.GridSelectionChangedEventArgs e)
{
           
}
{% endhighlight %}
{% endtabs %}

## Appearance

### Change selection background and foreground

You can change the selection background and foreground using the [SelectionBackGround](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_SelectionBackgroundProperty) and [SelectionForeGround](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_SelectionForegroundProperty) properties.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeGrid Name="treeGrid"
                                           Grid.Row="0"
                                           AutoExpandMode="RootNodesExpanded"
                                           AutoGenerateColumns="False"
                                           SelectionMode="Multiple"
                                           ChildPropertyName="ReportsTo"
                                           SelectionChanged="TreeGrid_SelectionChanged"
                                           ItemsSource="{Binding EmployeeInfo}"
                                           SelectionBackground="SkyBlue"                                                    
                                           SelectionForeground="DarkBlue"
                                         >
{% endhighlight %}
{% endtabs %}

![Background and foreground of the selected rows are changed in UWP treegrid](Selection_images/Selection_img5.jpeg)

### Change current cell border style

You can change the current cell's border thickness and border color using the [CurrentCellBorderThickness](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_CurrentCellBorderThickness) and [CurrentCellBorderBrush](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_CurrentCellBorderBrush) properties.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeGrid Name="treeGrid"
                                           Grid.Row="0"
                                           AutoExpandMode="RootNodesExpanded"
                                           AutoGenerateColumns="False"
                                           SelectionMode="Multiple"
                                           ChildPropertyName="ReportsTo"
                                           SelectionChanged="TreeGrid_SelectionChanged"
                                           ItemsSource="{Binding EmployeeInfo}"
                                           LiveNodeUpdateMode="AllowDataShaping"
                                           ParentPropertyName="ID"
                                           SelectedIndex="0"
                                           CurrentCellBorderBrush="Red"
                                           CurrentCellBorderThickness="1.6"
                                         >
{% endhighlight %}
{% endtabs %}

![Style of current cell border is customized in UWP treegrid](Selection_images/Selection_img6.jpeg)

### Customize row selection border

You can customize the row selection by editing the control template of TreeGridRowControl.

{% tabs %}
{% highlight xaml %}
<Style TargetType="syncfusion:TreeGridRowControl">
            <Setter Property="BorderBrush" Value="{StaticResource ContentBorderBrush}" />
            <Setter Property="Template">
                <Setter.Value>
                    <ControlTemplate TargetType="syncfusion:TreeGridRowControl">
                        <Grid>
                            <Border x:Name="PART_BackgroundBorder"
                                Margin="{TemplateBinding IndentMargin}"
                                Background="{TemplateBinding Background}"
                                Visibility="Visible">
                                <Rectangle x:Name="PART_FocusRect"
                                       Margin="1,2,2,2"
                                       Fill="Transparent"
                                       Stroke="DarkGray"
                                       StrokeDashArray="2,2"
                                       StrokeThickness="1"
                                       Visibility="Collapsed" />
                            </Border>
             <!-- Adding new border to show border for whole selected row -->
                            <Border x:Name="PART_SelectionBorder"
                                Margin="{TemplateBinding IndentMargin}"
                                Background="{TemplateBinding SelectionBackground}"
                                Visibility="Collapsed"
                                BorderBrush="Red"
                                BorderThickness="1.5,1.5,1.5,2.5"
                                Opacity="0.75"/>
                           
                            <ContentPresenter />
                           
                            <VisualStateManager.VisualStateGroups>
                                <VisualStateGroup x:Name="SelectionStates">
                                    <VisualState x:Name="Unselected" />
                                    <VisualState x:Name="Selected">
                                        <Storyboard>
                                            <ObjectAnimationUsingKeyFrames BeginTime="00:00:00"
                                                                       Storyboard.TargetName="PART_SelectionBorder"
                                                                       Storyboard.TargetProperty="(UIElement.Visibility)">
                                                <DiscreteObjectKeyFrame KeyTime="00:00:00" Value="{x:Static Visibility.Visible}" />
                                            </ObjectAnimationUsingKeyFrames>
                                        </Storyboard>
                                    </VisualState>
                                    <VisualState x:Name="SelectedPointerOver">
                                        <Storyboard>
                                            <ObjectAnimationUsingKeyFrames BeginTime="00:00:00"
                                                                       Storyboard.TargetName="PART_SelectionBorder"
                                                                       Storyboard.TargetProperty="(UIElement.Visibility)">
                                                <DiscreteObjectKeyFrame KeyTime="00:00:00" Value="{x:Static Visibility.Visible}" />
                                            </ObjectAnimationUsingKeyFrames>
                                        </Storyboard>
                                    </VisualState>
                                    <VisualState x:Name="SelectedPressed">
                                        <Storyboard>
                                            <ObjectAnimationUsingKeyFrames BeginTime="00:00:00"
                                                                       Storyboard.TargetName="PART_SelectionBorder"
                                                                       Storyboard.TargetProperty="(UIElement.Visibility)">
                                                <DiscreteObjectKeyFrame KeyTime="00:00:00" Value="{x:Static Visibility.Visible}" />
                                            </ObjectAnimationUsingKeyFrames>
                                        </Storyboard>
                                    </VisualState>

                                    <VisualState x:Name="UnselectedPointerOver" />
                                    <VisualState x:Name="UnselectedPressed" />
                                    <VisualState x:Name="Focused">
                                        <Storyboard>
                                            <ObjectAnimationUsingKeyFrames BeginTime="00:00:00"
                                                                       Storyboard.TargetName="PART_FocusRect"
                                                                       Storyboard.TargetProperty="(UIElement.Visibility)">
                                                <DiscreteObjectKeyFrame KeyTime="00:00:00" Value="{x:Static Visibility.Visible}" />
                                            </ObjectAnimationUsingKeyFrames>
                                        </Storyboard>

                                    </VisualState>
                                </VisualStateGroup>
                            </VisualStateManager.VisualStateGroups>
                        </Grid>
                    </ControlTemplate>
                </Setter.Value>
            </Setter>
        </Style>
{% endhighlight %}
{% endtabs %}

## Customize selection behaviors

The tree grid processes the selection operations in selection controller. [GridSelectionController](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.TreeGridRowSelectionController.html) processes selection operations when `SelectionUnit` is `Row`.

You can customize the default row selection behaviors by overriding the [GridSelectionController](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSelectionController.html) class and set it to [SfTreeGrid.SelectionController](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_SelectionController).

{% tabs %}
{% highlight c# %}
this.treeGrid.SelectionController = new GridSelectionControllerExt(this.treeGrid);
public class GridSelectionControllerExt : TreeGridRowSelectionController
{

    public GridSelectionControllerExt(SfTreeGrid treeGrid) : base(treeGrid)
    {
    }
}
{% endhighlight %}
{% endtabs %}

### Scroll and select the record programmatically

You can scroll to a record programmatically using the [ScrollInView](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_ScrollInView_Syncfusion_UI_Xaml_ScrollAxis_RowColumnIndex_) method by passing the row index of the record. You can get the row index of the record by using the [ResolveToRowIndex](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.TreeGridIndexResolver.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridIndexResolver_ResolveToRowIndex_Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_Syncfusion_UI_Xaml_TreeGrid_TreeNode_) extension method present in `Syncfusion.UI.Xaml.TreeGrid.Helpers`.

You can select a record programmatically by setting the [SelectedItem](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_SelectedItem) property in tree grid.

{% tabs %}
{% highlight c# %}
private void Treegrid_Loaded(object sender, System.Windows.RoutedEventArgs e)
{
    var selectedItem = (this.treegrid.DataContext as ViewModel).SelectedItem;
    var rowIndex = this.treegrid.ResolveToRowIndex(selectedItem);
    var columnIndex = this.treegrid.ResolveToStartColumnIndex();
    //Make the row in to available on the view. 
    this.treegrid.ScrollInView(new RowColumnIndex(rowIndex, columnIndex));
    //Set the SelectedItem in SfTreeGrid.
    this.treegrid.SelectedItem = selectedItem;
}
{% endhighlight %}
{% endtabs %}

You can download the [sample](https://github.com/SyncfusionExamples/how-to-scroll-and-select-the-record-programmatically-in-wpf-and-uwp-treegrid/tree/master/UWP).

### Prevent the selection when right-click

You can prevent the selection when right-clicking in tree grid by customizing the [SelectionController](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.TreeGridRowSelectionController.html) and overriding the [ProcessPointerPressed](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.TreeGridRowSelectionController.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridRowSelectionController_ProcessPointerPressed_Windows_UI_Xaml_Input_PointerRoutedEventArgs_Syncfusion_UI_Xaml_ScrollAxis_RowColumnIndex_).

{% tabs %}
{% highlight c# %}
protected override void ProcessPointerPressed(PointerRoutedEventArgs args, RowColumnIndex rowColumnIndex)
{
    var properties = args.GetCurrentPoint(TreeGrid).Properties;
    if (properties.IsRightButtonPressed)
    {
        args.Handled = true;
    }
    else
        base.ProcessPointerPressed(args, rowColumnIndex);
}
{% endhighlight %}
{% endtabs %}

You can download the [sample](https://github.com/SyncfusionExamples/how-to-prevent-the-selection-while-pressing-right-click-in-wpf-and-uwp-treegrid/tree/master/UWP).

### Select rows based on cell value

In tree grid, you can select the rows based on cell value by adding the corresponding records to [SelectedItems](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_SelectedItems). You can get the cell value of a particular cell using the `View.GetPropertyAccessProvider` method.

{% tabs %}
{% highlight c# %}
private void Button_Click(object sender, RoutedEventArgs e)
{
    if (treeGrid.View != null)
        reflector = treeGrid.View.GetPropertyAccessProvider();
    else
        reflector = null;

    var totalRowIndex = treeGrid.View.Nodes.Count;
    var totalColumnIndex = treeGrid.Columns.Count;

    for (int recordIndex = 0; recordIndex < totalRowIndex; recordIndex++)
    {
        for (int colIndex = 0; colIndex < totalColumnIndex; colIndex++)
        {
            var record = this.treeGrid.View.Nodes[recordIndex];
            var mappingName = treeGrid.Columns[colIndex].MappingName;
            //Get the cell value based on mappingName.
            var currentCellValue = reflector.GetValue(record.Item, mappingName);
            if (currentCellValue == "Steven")
            {
                object node = treeGrid.View.Nodes[recordIndex];
                //selected rows should be added here.
                treeGrid.SelectedItems.Add((node as TreeNode).Item);
            }
        }
    }
}
{% endhighlight %}
{% endtabs %}

### Search and select the record

You can search and select a record in tree grid based on the searched text using the `TextChanged` event of `TextBox`.

{% tabs %}
{% highlight c# %}
private void Textbox_TextChanged(object sender, TextChangedEventArgs e)
{
    var textBox = sender as TextBox;
            
    if (textBox.Text == "")
        treeGrid.SelectedItems.Clear();

    for (int i = 0; i < treeGrid.View.Nodes.Count; i++)
    {
        if (Provider == null)
            Provider = treeGrid.View.GetPropertyAccessProvider();

        if (treeGrid.View.Nodes[i].HasChildNodes && treeGrid.View.Nodes[i].ChildNodes.Count == 0)
        {
            treeGrid.ExpandNode(treeGrid.View.Nodes[i]);
            treeGrid.CollapseNode(treeGrid.View.Nodes[i]);
        }
        else if (treeGrid.View.Nodes[i].HasChildNodes)
        {
            dataRow = (treeGrid.View.Nodes[i].Item as PersonInfo);
            FindMatchText(dataRow);
            GetChildNodes(treeGrid.View.Nodes[i]);
        }
        else
        {
            dataRow = (treeGrid.View.Nodes[i].Item as PersonInfo);
            FindMatchText(dataRow);
        }
    }
}
{% endhighlight %}
{% endtabs %}

You can download the [sample](https://github.com/SyncfusionExamples/how-to-search-and-select-the-record-in-wpf-and-uwp-treegrid/tree/master/UWP).

### Read cell values from selected items

You can get the cell values of [SelectedItems](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_SelectedItems) using [SfTreeGrid.SelectedItems](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_SelectedItems) and internal reflector, which reflects the field value from data object based on field name.

{% tabs %}
{% highlight c# %}
private void Button_Click(object sender, RoutedEventArgs e)
{
    listBox.Items.Clear();
    // Get the selected items of SfTreeGrid
    var reflector = this.treeGrid.View.GetPropertyAccessProvider();
    foreach (var row in this.treeGrid.SelectedItems)
    {
        foreach (var column in treeGrid.Columns)
        {
            //Get the value from data object based on MappingName 
            var cellValue = reflector.GetValue(row, column.MappingName);
            //Returns the display value of the cell from data object based on MappingName 
            //var displayValue = reflector.GetFormattedValue(row, column.MappingName);
            listBox.Items.Add(cellValue.ToString());
        }
    }
}
{% endhighlight %}
{% endtabs %}

### Show the selection of row/cell when setting the background to SfTreeGrid

The `Row`/`Cell` selection border is behind the grid cell content. So, when you apply the background for row, the selection is not displayed in `UI`. You can overcome this by setting opacity in `TreeGridCell`.

{% tabs %}
{% highlight xaml %}
<Style TargetType="syncfusion:TreeGridCell">
            <Setter Property="Background">
                <Setter.Value>
                    <SolidColorBrush Color="Blue" Opacity="0.5"/>
                </Setter.Value>
            </Setter>
</Style>
{% endhighlight %}
{% endtabs %}

### Set the current cell on a particular row when tree grid is loaded 

You can set the current cell in tree grid using the [treeGrid.SelectionController.MoveCurrentCell](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.TreeGridRowSelectionController.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridRowSelectionController_MoveCurrentCell_Syncfusion_UI_Xaml_ScrollAxis_RowColumnIndex_System_Boolean_) method.

{% tabs %}
{% highlight c# %}
private void TreeGrid_Loaded(object sender, RoutedEventArgs e)
{
    var viewModel = this.treeGrid.DataContext as ViewModel;
    // Find the RowIndex for a particular record.
    var RowIndex = this.treeGrid.ResolveToRowIndex(viewModel.EmployeeInfo[5]);
    // Find the ColumnIndex for that row.
    var ColumnIndex = this.treeGrid.ResolveToScrollColumnIndex(2);
    // CurrentCell is set if MappingName is EmployeeID
    if (this.treeGrid.Columns[ColumnIndex].MappingName == "FirstName")
        this.treeGrid.SelectionController.MoveCurrentCell(new RowColumnIndex(RowIndex, ColumnIndex));
}
{% endhighlight %}
{% endtabs %}
