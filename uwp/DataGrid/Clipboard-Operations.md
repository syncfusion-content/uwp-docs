---
layout: post
title: Clipboard Operations in UWP DataGrid control | Syncfusion
description: Learn here all about Clipboard Operations support in Syncfusion UWP DataGrid (SfDataGrid) control and more.
platform: uwp
control: SfDataGrid
documentation: ug
--- 


# Clipboard Operations in UWP DataGrid (SfDataGrid)

SfDataGrid provide support for the clipboard operations such as cut, copy and paste the data within control and between other applications such as Notepad, Excel. Clipboard operations copy and paste is enabled by default. You can copy selected records/cells from SfDataGrid by pressing <kbd>Ctrl</kbd>+<kbd>C</kbd> and also can paste the content from [Clipboard](https://learn.microsoft.com/en-us/uwp/api/windows.applicationmodel.datatransfer.clipboard?view=winrt-22621&redirectedfrom=MSDN) to SfDataGrid by pressing <kbd>Ctrl</kbd>+<kbd>V</kbd>.

N> Clipboard operations is not supported for the summary rows, add new row and unbound rows.

## Copy

Copy operation works based on [GridCopyOption](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_GridCopyOption) property.`GridCopyOption` provides the following options,

[None](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCopyOption.html#Syncfusion_UI_Xaml_Grid_GridCopyOption_None) – Disables copy in SfDataGrid.

[CopyData](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCopyOption.html#Syncfusion_UI_Xaml_Grid_GridCopyOption_CopyData) – Enabled copy in SfDataGrid.

[IncludeHeaders](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCopyOption.html#Syncfusion_UI_Xaml_Grid_GridCopyOption_IncludeHeaders) – Column header also copied along with data.

[IncludeFormat](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCopyOption.html#Syncfusion_UI_Xaml_Grid_GridCopyOption_IncludeFormat) – Copies the display text with format instead of actual value.

[IncludeHiddenColumn](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCopyOption.html#Syncfusion_UI_Xaml_Grid_GridCopyOption_IncludeHiddenColumn) – Hidden column also copied to clipboard.

You have to use `IncludeHeaders`, `IncludeFormat`, `IncludeHiddenColumn` options along with `CopyData` option.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       SelectionUnit="Row"
                       SelectionMode="Single"
                       GridCopyOption="CopyData,IncludeHeaders" 
                       ItemsSource="{Binding Orders}"/>
{% endhighlight %}
{% highlight c# %}
this.dataGrid.GridCopyOption = GridCopyOption.CopyData | GridCopyOption.IncludeHeaders;
{% endhighlight %}
{% endtabs %}

![Clipboard-Operations_img1](Clipboard-Operations_images/Clipboard-Operations_img1.png)


N> `IncludeHiddenColumn` is not supported when `SelectionUnit` is `Cell`.

## Paste

Paste operation works based on [GridPasteOption](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_GridPasteOption) property. `GridPasteOption` provides the following options,

[None](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridPasteOption.html#Syncfusion_UI_Xaml_Grid_GridPasteOption_None) – Disable paste in SfDataGrid.

[PasteData](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridPasteOption.html#Syncfusion_UI_Xaml_Grid_GridPasteOption_PasteData) – Enabled paste in SfDataGrid and when an incompatible value is pasted into a record/cell, the pasting operation is skipped for that particular record/cell.

[ExcludeFirstLine](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridPasteOption.html#Syncfusion_UI_Xaml_Grid_GridPasteOption_ExcludeFirstLine) – This can be used when pasting data copied with `IncludeHeaders` copy option.

[IncludeHiddenColumn](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridPasteOption.html#Syncfusion_UI_Xaml_Grid_GridPasteOption_IncludeHiddenColumn) – Paste the values in hidden columns also.

You have to use `ExcludeFirstLine`, `IncludeHiddenColumn` options along with `PasteData` option.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       SelectionUnit="Row"
                       SelectionMode="Single"
                       GridPasteOption="PasteData,ExcludeFirstLine" 
                       ItemsSource="{Binding Orders}"/>
{% endhighlight %}
{% highlight c# %}
this.dataGrid.GridPasteOption = GridPasteOption.PasteData | GridPasteOption.ExcludeFirstLine;
{% endhighlight %}
{% endtabs %}

![Clipboard-Operations_img2](Clipboard-Operations_images/Clipboard-Operations_img2.png)

## Cut

Cut operation works based on [GridCopyOption](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_GridCopyOption) property. `GridCopyOption` provides the following options,

[None](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCopyOption.html#Syncfusion_UI_Xaml_Grid_GridCopyOption_None) – Disables cut in SfDataGrid.

[CutData](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCopyOption.html#Syncfusion_UI_Xaml_Grid_GridCopyOption_CutData) – Enabled cut in SfDataGrid.

[IncludeHeaders](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCopyOption.html#Syncfusion_UI_Xaml_Grid_GridCopyOption_IncludeHeaders) – Column header also copied along with data.

[IncludeFormat](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCopyOption.html#Syncfusion_UI_Xaml_Grid_GridCopyOption_IncludeFormat) – Cut the display text with format instead of actual value.

[IncludeHiddenColumn](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCopyOption.html#Syncfusion_UI_Xaml_Grid_GridCopyOption_IncludeHiddenColumn) – Hidden column also cut to clipboard.

You have to use `IncludeHeaders`, `IncludeFormat`, `IncludeHiddenColumn` options along with `CutData` option.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       SelectionUnit="Row"
                       SelectionMode="Single"
                       GridCopyOption="CutData,IncludeHeaders" 
                       ItemsSource="{Binding Orders}"/>
{% endhighlight %}
{% highlight c# %}
this.dataGrid.GridCopyOption = GridCopyOption.CutData | GridCopyOption.IncludeHeaders;
{% endhighlight %}
{% endtabs %}

![Clipboard-Operations_img3](Clipboard-Operations_images/Clipboard-Operations_img3.png)

N> `IncludeHiddenColumn` is not supported when `SelectionUnit` is `Cell`.

## Events

### GridCopyContent

[GridCopyContent](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_GridCopyContent) event occurs when copy/cut the cells in SfDataGrid. [GridCopyPasteEventArgs](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCopyPasteEventArgs.html) provides information for `GridCopyContent` event. You can cancel copy operation by handling this event.

{% tabs %}
{% highlight c# %}
this.dataGrid.GridCopyContent += DataGrid_GridCopyContent;

private void DataGrid_GridCopyContent(object sender, GridCopyPasteEventArgs e)
{
}
{% endhighlight %}
{% endtabs %}

### GridPasteContent

[GridPasteContent](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_GridPasteContent) event occurs when paste the clipboard value into SfDataGrid. [GridCopyPasteEventArgs](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCopyPasteEventArgs.html) provides information for `GridPasteContent` event. You can cancel paste operation by handling this event.

{% tabs %}
{% highlight c# %}
this.dataGrid.GridPasteContent += DataGrid_GridPasteContent;

private void DataGrid_GridPasteContent(object sender, GridCopyPasteEventArgs e)
{

    if (((e.OriginalSender as SfDataGrid).SelectedItem as OrderInfo).OrderID == 1004)
        e.Handled = true;
}

{% endhighlight %}
{% endtabs %}

### CopyGridCellContent

[CopyGridCellContent](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_CopyGridCellContent) event occurs when cell being copy/cut. [GridCopyPasteCellEventArgs](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCopyPasteCellEventArgs.html) provides information for `CopyGridCellContent` event, which has following members,

[ClipBoardValue](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCopyPasteCellEventArgs.html#Syncfusion_UI_Xaml_Grid_GridCopyPasteCellEventArgs_ClipBoardValue) – Returns cell value.

[Column](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCopyPasteCellEventArgs.html#Syncfusion_UI_Xaml_Grid_GridCopyPasteCellEventArgs_Column) – Returns corresponding GridColumn of a cell.

[RowData](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCopyPasteCellEventArgs.html#Syncfusion_UI_Xaml_Grid_GridCopyPasteCellEventArgs_RowData) – Returns corresponding RowData of a cell.

[OriginalSender](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCancelEventArgs.html#Syncfusion_UI_Xaml_Grid_GridCancelEventArgs_OriginalSender) – Returns the SfDataGrid.

You can change the text copied to clipboard by changing the `ClipBoardValue`.
 
{% tabs %}
{% highlight c# %}
this.dataGrid.CopyGridCellContent += DataGrid_CopyGridCellContent;

private void DataGrid_CopyGridCellContent(object sender, GridCopyPasteCellEventArgs e)
{            
}
{% endhighlight %}
{% endtabs %}

The below code example change the clipboard value as 100 instead of cell value 1003 in SfDataGrid.

{% tabs %}
{% highlight c# %}
this.dataGrid.CopyGridCellContent += DataGrid_CopyGridCellContent;

private void DataGrid_CopyGridCellContent(object sender, GridCopyPasteCellEventArgs e)
{

    if (e.Column.MappingName == "OrderID" && (e.RowData as OrderInfo).OrderID == 1003)
        e.ClipBoardValue = 100;
}
{% endhighlight %}
{% endtabs %}

![Clipboard-Operations_img4](Clipboard-Operations_images/Clipboard-Operations_img4.png)

The below code example handled the copy operation when `MappingName` of a Column is Country.

{% tabs %}
{% highlight c# %}
this.dataGrid.CopyGridCellContent += DataGrid_CopyGridCellContent;

private void DataGrid_CopyGridCellContent(object sender, GridCopyPasteCellEventArgs e)
{          

    if (e.Column.MappingName == "Country")
        e.Handled = true;
}
{% endhighlight %}
{% endtabs %}

![Clipboard-Operations_img5](Clipboard-Operations_images/Clipboard-Operations_img5.png)

### PasteGridCellContent

[PasteGridCellContent](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_PasteGridCellContent) event occurs when cell being paste. [GridCopyPasteCellEventArgs](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCopyPasteCellEventArgs.html) provides information for `PasteGridCellContent` event, which has following members

[ClipBoardValue](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCopyPasteCellEventArgs.html#Syncfusion_UI_Xaml_Grid_GridCopyPasteCellEventArgs_ClipBoardValue) - Returns clipboard value of a particular cell.

[Column](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCopyPasteCellEventArgs.html#Syncfusion_UI_Xaml_Grid_GridCopyPasteCellEventArgs_Column) – Returns corresponding GridColumn of a cell.

[RowData](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCopyPasteCellEventArgs.html#Syncfusion_UI_Xaml_Grid_GridCopyPasteCellEventArgs_RowData) – Returns corresponding RowData of a cell.

[OriginalSender](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCancelEventArgs.html#Syncfusion_UI_Xaml_Grid_GridCancelEventArgs_OriginalSender) – Returns the SfDataGrid.

You can change the text paste to SfDataGrid by changing the `ClipBoardValue`.

{% tabs %}
{% highlight c# %}
this.dataGrid.PasteGridCellContent += DataGrid_PasteGridCellContent;

private void DataGrid_PasteGridCellContent(object sender, GridCopyPasteCellEventArgs e)
{            
}
{% endhighlight %}
{% endtabs %}

The below code example change the clipboard value as Test instead of clipboard value BOLID.

{% tabs %}
{% highlight c# %}
this.dataGrid.PasteGridCellContent += DataGrid_PasteGridCellContent;

private void DataGrid_PasteGridCellContent(object sender, GridCopyPasteCellEventArgs e)
{

    if (e.Column.MappingName == "CustomerID" && (e.RowData as OrderInfo).CustomerID == "BERGS")
        e.ClipBoardValue = "Test";
}
{% endhighlight %}
{% endtabs %}

![Clipboard-Operations_img6](Clipboard-Operations_images/Clipboard-Operations_img6.png)

The below code example handled the paste operation when MappingName of Column is OrderID

{% tabs %}
{% highlight c# %}
this.dataGrid.PasteGridCellContent += DataGrid_PasteGridCellContent;
private void DataGrid_PasteGridCellContent(object sender, GridCopyPasteCellEventArgs e)
{

    if (e.Column.MappingName == "OrderID")
        e.Handled = true;
}
{% endhighlight %}
{% endtabs %}

![Clipboard-Operations_img7](Clipboard-Operations_images/Clipboard-Operations_img7.png)

## Handling Programmatically

### Copy programmatically

Copy the selected records/cells in SfDataGrid by using [Copy](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCutCopyPaste.html#Syncfusion_UI_Xaml_Grid_GridCutCopyPaste_Copy) method in [GridCopyPaste](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_GridCopyPaste) of SfDataGrid.

{% tabs %}
{% highlight c# %}
this.dataGrid.GridCopyPaste.Copy();
{% endhighlight %}
{% endtabs %}

Copy a record by selecting the record using [MoveCurrentCell](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridBaseSelectionController.html#Syncfusion_UI_Xaml_Grid_GridBaseSelectionController_MoveCurrentCell_Syncfusion_UI_Xaml_ScrollAxis_RowColumnIndex_System_Boolean_) method and [Copy](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCutCopyPaste.html#Syncfusion_UI_Xaml_Grid_GridCutCopyPaste_Copy) method in [GridCopyPaste](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_GridCopyPaste) of SfDataGrid.

{% tabs %}
{% highlight c# %}
RowColumnIndex rowColumnIndex = new RowColumnIndex();
rowColumnIndex.RowIndex = 2;
rowColumnIndex.ColumnIndex = 2;
this.dataGrid.SelectionController.MoveCurrentCell(rowColumnIndex);
this.dataGrid.GridCopyPaste.Copy();
{% endhighlight %}
{% endtabs %}

Copy the multiple records by selecting group of records using `SelectRows` method and [Copy](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCutCopyPaste.html#Syncfusion_UI_Xaml_Grid_GridCutCopyPaste_Copy) method in [GridCopyPaste](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_GridCopyPaste) of SfDataGrid.

{% tabs %}
{% highlight c# %}
this.dataGrid.SelectionController.SelectRows(1, 7);
this.dataGrid.GridCopyPaste.Copy();
{% endhighlight %}
{% endtabs %}

Copy the multiple cells by selecting group of cells using `SelectCells` method and `Copy` method in `GridCopyPaste` of SfDataGrid.

{% tabs %}
{% highlight c# %}
using Syncfusion.UI.Xaml.Grid.Helpers;

this.dataGrid.SelectCells(this.dataGrid.GetRowGenerator().Items[2].RowData, this.dataGrid.Columns[1], this.dataGrid.GetRowGenerator().Items[5].RowData, this.dataGrid.Columns[3]);
this.dataGrid.GridCopyPaste.Copy();
{% endhighlight %}
{% endtabs %}

### Copy rows without selecting

You can copy the records without selection by using [CopyRowsToClipboard](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCutCopyPaste.html#Syncfusion_UI_Xaml_Grid_GridCutCopyPaste_CopyRowsToClipboard_System_Int32_System_Int32_) method in `GridCopyPaste` of SfDataGrid.
 
{% tabs %}
{% highlight c# %}
this.dataGrid.GridCopyPaste.CopyRowsToClipboard(2, 4);
{% endhighlight %}
{% endtabs %}

### Cut Programmatically

Cut the selected records/cells in SfDataGrid by using [Cut](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCutCopyPaste.html#Syncfusion_UI_Xaml_Grid_GridCutCopyPaste_Cut) method in `GridCopyPaste` of SfDataGrid.

{% tabs %}
{% highlight c# %}
this.dataGrid.GridCopyPaste.Cut();
{% endhighlight %}
{% endtabs %}

Cut the entire record in SfDataGrid by selecting whole SfDataGrid using [SelectAll](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_SelectAll_System_Boolean_) method and `Cut` method in `GridCopyPaste` of SfDataGrid.

{% tabs %}
{% highlight c# %}
this.dataGrid.SelectionController.SelectAll();
this.dataGrid.GridCopyPaste.Cut();
{% endhighlight %}
{% endtabs %}

Cut the entire column in SfDataGrid by using [SelectCells](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_SelectCells_System_Object_Syncfusion_UI_Xaml_Grid_GridColumn_System_Object_Syncfusion_UI_Xaml_Grid_GridColumn_System_Boolean_) method and `Cut` method in `GridCopyPaste` of SfDataGrid.

{% tabs %}
{% highlight c# %}
using Syncfusion.UI.Xaml.Grid.Helpers;

var firstRowdata = this.dataGrid.GetRecordAtRowIndex(dataGrid.GetFirstRowIndex());
var lastRowdata = this.dataGrid.GetRecordAtRowIndex(dataGrid.GetLastRowIndex());

this.dataGrid.SelectCells(firstRowdata, this.dataGrid.Columns[2], lastRowdata, this.dataGrid.Columns[2]);
this.dataGrid.GridCopyPaste.Cut();
{% endhighlight %}
{% endtabs %}

### Paste programmatically

Paste the clipboard value into SfDataGrid by using [Paste](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCutCopyPaste.html#Syncfusion_UI_Xaml_Grid_GridCutCopyPaste_Paste) method in `GridCopyPaste` of SfDataGrid.

{% tabs %}
{% highlight c# %}
this.dataGrid.GridCopyPaste.Paste();
{% endhighlight %}
{% endtabs %}

Paste the clipboard value into selected record by selecting the record using MoveCurrentCell method and `Paste` method in `GridCopyPaste` of SfDataGrid.

{% tabs %}
{% highlight c# %}
RowColumnIndex rowColumnIndex = new RowColumnIndex();
rowColumnIndex.RowIndex = 1;
rowColumnIndex.ColumnIndex = 1;

this.dataGrid.SelectionController.MoveCurrentCell(rowColumnIndex);
this.dataGrid.GridCopyPaste.Paste();
{% endhighlight %}
{% endtabs %}

## Customizing Copy Paste behavior

SfDataGrid process the clipboard operations in [GridCutCopyPaste](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCutCopyPaste.html) class. You can customize the default copy paste behaviors by overriding `GridCutCopyPaste` class and set it to `SfDataGrid.GridCopyPaste`.

{% tabs %}
{% highlight c# %}
public class CustomCopyPaste : GridCutCopyPaste
{

    public CustomCopyPaste(SfDataGrid sfGrid) : base(sfGrid)
    {         
    }
}

public MainWindow()
{
    InitializeComponent();
    this.dataGrid.GridCopyPaste = new CustomCopyPaste(this.dataGrid);
}
{% endhighlight %}
{% endtabs %}

### Paste a cell into many cells

By default, you can copy one cell and paste it into another cell when Cell Selection is enabled in SfDataGrid. The below code shows how to copy one cell and paste it into all the selected cells by overriding [PasteToCell](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCutCopyPaste.html#Syncfusion_UI_Xaml_Grid_GridCutCopyPaste_PasteToCell_System_Object_Syncfusion_UI_Xaml_Grid_GridColumn_System_Object_) method in [GridCutCopyPaste](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCutCopyPaste.html) class.
 
{% tabs %}
{% highlight c# %}
using Syncfusion.UI.Xaml.Grid;

public class CustomCopyPaste: GridCutCopyPaste
{

    public CustomCopyPaste(SfDataGrid dataGrid) : base(dataGrid)
    {
    }

    async protected override void PasteToCell(object record, GridColumn column, object rowData)
    {
        DataPackageView dataPackageView = Clipboard.GetContent();
        String text = null;

        if (dataPackageView.Contains(StandardDataFormats.Text))
            text = await dataPackageView.GetTextAsync();

        string[] clipBoardText = Regex.Split(text, @"\r\n");
        clipBoardText = Regex.Split(clipBoardText[0], @"\t");

        //Gets the clipBoardText and checks whether the clipBoardText is more than one cell or not

        //Calls the base.

        if (clipBoardText.Count() > 1)
        {
            base.PasteToCell(record, column, rowData);
            return;
        }

        //Gets the selectedCells for paste the copied cell 
        var selectedCells = this.dataGrid.GetSelectedCells();
        int selectedCellsCount = selectedCells.Count;

        for (int i = 0; i < selectedCellsCount; i++)
        {
            record = selectedCells[i].RowData;
            column = selectedCells[i].Column;

            //Calls the PasteToCell method with particular record of selectedCells,
            
            // Column of selected records and rowData
            base.PasteToCell(record, column, rowData);
        }
    }
}
{% endhighlight %}
{% endtabs %}

### Paste a record into many rows

By default, you can able to copy one row and paste it into another row when Row Selection is enabled in SfDataGrid. The below code shows how to copy one row and paste it into all selected rows by overriding the [PasteToRow](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCutCopyPaste.html#Syncfusion_UI_Xaml_Grid_GridCutCopyPaste_PasteToRow_System_Object_System_Object_) method in the `GridCutCopyPaste` class.
 
{% tabs %}
{% highlight c# %}
public class CustomCopyPaste : GridCutCopyPaste
{

    public CustomCopyPaste(SfDataGrid dataGrid) : base(dataGrid)
    {
    }

    async protected override void PasteToRow(object copiedRecord, object selectedRecords)
    {
        DataPackageView dataPackageView = Clipboard.GetContent();
        String text = null;

        if (dataPackageView.Contains(StandardDataFormats.Text))
            text = await dataPackageView.GetTextAsync();

        string[] clipBoardText = Regex.Split(text, @"\r\n");

        //Gets the clipBoardText and checks whether the clipBoardText is more than one row or not

        //Calls the base.

        if (clipBoardText.Count() > 1)
        {
            base.PasteToRow(copiedRecord, selectedRecords);
            return;
        }

        var selectedRecord = this.dataGrid.SelectedItems;

        for (int i = 0; i < selectedRecord.Count; i++)
        {
            //Gets the Selected records for paste the copied row.
            selectedRecords = selectedRecord[i];

            // Calls the PasteToRow method with copiedRecord and selectedRecord
            base.PasteToRow(copiedRecord, selectedRecords);
        }
    }
}
{% endhighlight %}
{% endtabs %}

### Select pasted records

By default, after pasting the clipboard value to SfDataGrid selection is maintains in previously selected records as it is. The below code shows select the pasted records after the Paste operation, by overriding the [PasteToRows](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCutCopyPaste.html#Syncfusion_UI_Xaml_Grid_GridCutCopyPaste_PasteToRows_System_Object_) and [PasteToRow](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCutCopyPaste.html#Syncfusion_UI_Xaml_Grid_GridCutCopyPaste_PasteToRow_System_Object_System_Object_) methods in [GridCutCopyPaste](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCutCopyPaste.html) class. This code is applicable when [SelectionUnit](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_SelectionUnit) is `Row`.

{% tabs %}
{% highlight c# %}
public class CustomCopyPaste : GridCutCopyPaste
{

    public CustomCopyPaste(SfDataGrid dataGrid) : base(dataGrid)
    {
    }

    //Creates the new list for add the selected records
    public List<object> selectedItem = new List<object>();

    protected override void PasteToRows(object clipBoardRows)
    {
        base.PasteToRows(clipBoardRows);

        //Uses the SelectionController to apply the selection for Pasted records
        this.dataGrid.SelectionController.HandleGridOperations(new GridOperationsHandlerArgs(GridOperation.Paste, selectedItem));
    }

    protected override void PasteToRow(object clipBoardContent, object selectedRecords)
    {

        //Adds the selected record to list
        selectedItem.Add(selectedRecords);

        base.PasteToRow(clipBoardContent, selectedRecords);
    }
}
{% endhighlight %}
{% endtabs %}

### Create new records while pasting

By default, while paste the clipboard value to SfDataGrid, it changes the values of the already existing records. The below code example shows how to add the copied records as new rows in SfDataGrid by overriding the `PasteToRows` method in `GridCutCopyPaste` class.
 
{% tabs %}
{% highlight c# %}
public class CustomCopyPaste : GridCutCopyPaste
{
    public CustomCopyPaste(SfDataGrid dataGrid) : base(dataGrid)
    {
    }

    //Creates the new list for add the selected records
    public List<object> selectedItem = new List<object>();

    protected override void PasteToRows(object clipBoardRows)
    {
        var copiedRecord = (string[])clipBoardRows;
        int copiedRecordsCount = copiedRecord.Count();

        //Based on the clipboard count, the new record for paste is added

        if (copiedRecordsCount > 0)
        {
            //Gets the viewModel for adding the record
            var rec = this.dataGrid.DataContext as ViewModel;

            for (int i = 0; i < copiedRecordsCount; i++)
            {
                //Creates the new instance for Model, for adding the new record
                OrderInfo entity = new OrderInfo();

                for (int j = 0; j < this.dataGrid.Columns.Count; j++)
                {
                    var record = copiedRecord[i];
                    string[] recd = Regex.Split(record, @"\t");

                    //Adds the new record by using PasteToCell method by passing the created data, particular column, and clipboard value
                    this.PasteToCell(entity, this.dataGrid.Columns[j], recd[j]);
                }

                //Adds the pasted record in collection
                rec.Orders.Add(entity);
            }
        }
    }
}
{% endhighlight %}
{% endtabs %}
