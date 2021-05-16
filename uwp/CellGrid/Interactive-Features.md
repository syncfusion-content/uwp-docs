---
layout: post
title: Interactive Features in UWP CellGrid control | Syncfusion
description: Learn here all about Interactive Features support in Syncfusion UWP CellGrid (SfCellGrid) control and more.
platform: uwp
control: SfCellGrid
documentation: ug
---

# Interactive Features in UWP CellGrid (SfCellGrid)

This section explains interactive operations in the SfCellGrid.

## Clipboard operations

The supported clipboard operations, cut, copy, and paste are managed in `GridCopyPaste` class. This class can be accessed by using the `CopyPaste` property of the SfCellGrid that provides methods to perform clipboard operations.

### Cut

The selected range of cells or data can be cut by using the `Cut` method or keyboard keys <kbd>Ctrl</kbd> +<kbd> X</kbd> combination.

{% tabs %}
{% highlight c# %}

//To cut the selected ranges,
cellGrid.CopyPaste.Cut();

//To cut the ranges passed at runtime,
var range = GridRangeInfo.Cells(2, 3, 4, 5);
cellGrid.CopyPaste.Copy(range, true);

{% endhighlight %}
{% endtabs %}

#### Event related with cut operation

The `ClipboardCut` event occurs when performing cut operation in the SfCellGrid. It receives an argument of type `GridCutPasteEventArgs` that provides an option to get the copied range and handles this event.

{% tabs %}
{% highlight c# %}

cellGrid.Model.ClipboardCut += Model_ClipboardCut;

private void Model_ClipboardCut(object sender, GridCutPasteEventArgs e)
{
    var range = e.Range;
    e.Handled = true;        
}

{% endhighlight %}
{% endtabs %}

### Copy

The selected range of cells or data can be copied by using the `Copy` method or keyboard keys <kbd>Ctrl</kbd> + <kbd>C</kbd> combination.

{% tabs %}
{% highlight c# %}

//To copy the selected ranges,
cellGrid.CopyPaste.Copy();

//To copy the ranges passed at runtime,
var range = GridRangeInfo.Cells(2, 3, 4, 5);
cellGrid.CopyPaste.Copy(range, false);

{% endhighlight %}
{% endtabs %}

#### Event related with copy operation

The `ClipboardCopy` event occurs when performing copy operation in the SfCellGrid. It receives an argument of type `GridCutPasteEventArgs` that provides an option to get the copied range and handles this event.

{% tabs %}
{% highlight c# %}

cellGrid.Model.ClipboardCopy += Model_ClipboardCopy;
private void Model_ClipboardCopy(object sender, GridCutPasteEventArgs e)
{
    var range = e.Range;
    e.Handled = true;        
}

{% endhighlight %}
{% endtabs %}

### Paste

The copied ranges from the SfCellGrid can be pasted by using the `Paste` method or keyboard keys <kbd>Ctrl<kbd> + <kbd>V</kbd> combination.

{% tabs %}
{% highlight c# %}

//To paste the copied ranges including formatting,

cellGrid.Model.CopyPasteOptions = CopyPasteOptions.All;
cellGrid.CopyPaste.Paste();

{% endhighlight %}
{% endtabs %}

#### Copy paste options

The following list of paste enum options can be used to perform paste operation.

<table>
<tr>
<th>
Options</th><th>
Description</th></tr>
<tr>
<td>
All</td><td>
Pastes with all the format options. </td></tr>
<tr>
<td>
Formulas</td><td>
Pastes the formulas alone. </td></tr>
<tr>
<td>
Formats</td><td>
Maintains the formatting of copied range.</td></tr>
<tr>
<td>
Values</td><td>
Pastes the values alone.</td></tr>
<tr>
<td>
Comments</td><td>
Pastes the comments without formats and values. </td></tr>
<tr>
<td>
Transpose</td><td>
Copies the vertical range of cells and pastes in horizontal range and vice-versa. </td></tr>
<tr>
<td>
ClipboardOnly</td><td>
Copies and pastes from the clipboard without pasting any styles. </td></tr>
</table>

#### Event related with paste operation

The `ClipboardPaste` event occurs when performing paste operation in the SfCellGrid. It receives an argument of type `GridCutPasteEventArgs` that provides an option to get or set the pasting range and handles this event.

{% tabs %}
{% highlight c# %}

cellGrid.Model.ClipboardPaste += Model_ClipboardPaste;
private void Model_ClipboardPaste(object sender, GridCutPasteEventArgs e)
{
    var range = e.Range;
    e.Handled = true;        
}

{% endhighlight %}
{% endtabs %}

## Tooltip

The SfCellGrid provides support for adding tooltip for individual cells. Tooltip will be displayed as small pop-up window when the mouse hover the cells. 

To display the tooltip, set the `ShowTooltip` property to true.

{% tabs %}
{% highlight c# %}

cellGrid.ShowTooltip  = true;

{% endhighlight %}
{% endtabs %}

### Adding tooltip

Tooltip can be added to the cell by setting the `Tooltip` property. The assigned text will be displayed in the tooltip window.

{% tabs %}
{% highlight c# %}

//To add the tooltip for cell,
cellGrid.Model[3, 3].Tooltip = "Syncfusion";

//To add the tooltip for header cells alone,
cellGrid.Model.HeaderStyle.Tooltip = "Syncfusion";

//To add the tooltip for the footer cells alone,
cellGrid.Model.FooterStyle.Tooltip = "Syncfusion";

//To add the tooltip for the column,
cellGrid.Model.ColStyles[4].Tooltip = "Syncfusion");

//To add the tooltip for the row,
cellGrid.Model.RowStyles[3].Tooltip = "Syncfusion";

{% endhighlight %}
{% endtabs %}

### Customization of tooltip

The tooltip can be customized by defining a custom data template and assign to the `TooltipTemplate` property of the SfCellGrid.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfCellGrid.Resources>
    <DataTemplate x:Key="Customtool">
       <Border BorderThickness="2"
            Background="Orange"
             BorderBrush="Green">
            <TextBlock Text="{Binding Path=Tooltip}" 
                 FontSize="12"
                 Foreground="Black"
                 Padding="2"/>
        </Border>
    </DataTemplate>
</syncfusion:SfCellGrid.Resources>

{% endhighlight %}
{% highlight c# %}

cellGrid.Model[3, 3].TooltipTemplate = cellGrid.Resources["Customtool"] as DataTemplate;
cellGrid.Model[3, 3].Tooltip = "Custom Tooltip";

{% endhighlight %}
{% endtabs %}

N> Customized data template should be defined in SfCellGrid.Resources in XAML file.

### Reset tooltip

The `ResetTooltip` method is used to reset or remove the tooltip from the SfCellGrid.

{% tabs %}
{% highlight c# %}

cellGrid.Model[3, 3].ResetTooltip();

{% endhighlight %}
{% endtabs %}

### Reset tooltip template

The `ResetTooltipTemplate` method is used to reset or remove the defined custom tooltip template from the SfCellGrid.

{% tabs %}
{% highlight c# %}

cellGrid.Model[3, 3].ResetTooltipTemplate();

{% endhighlight %}
{% endtabs %}

### CellTooltipOpening event

The `CellTooltipOpening` event occurs when opening the tooltip in the SfCellGrid. It receives an argument of type `CellTooltipOpeningEventArgs` containing the following information about the event.

<table>
<tr>
<th>
Property</th><th>
Description</th></tr>
<tr>
<td>
<code>Cell</code></td><td>
Gets or sets the value that indicates cell tooltip index. </td></tr>
<tr>
<td>
<code>Cancel</code></td><td>
Gets or sets whether the event should be canceled or not. </td></tr>
<tr>
<td>
<code>Tooltip</code></td><td>
Gets or sets the tooltip text. </td></tr>
</table>

{% tabs %}
{% highlight c# %}

cellGrid.CellTooltipOpening += CellGrid_CellTooltipOpening;

private void CellGrid_CellTooltipOpening(object sender, CellTooltipOpeningEventArgs e)
{
    var cellIndex = e.Cell;
    var text = e.Tooltip;
    e.Cancel = true;
}

{% endhighlight %}
{% endtabs %}

## Comment tip

The SfCellGrid provides support for adding the Excel-like comment tip to the individual cells. This acts as note that provides more information about the data in an individual cell on mouse hover.

When a cell has a comment, a red indicator appears in the corner of the cell. When resetting the pointer on the cell, the comment appears.

To display the comment, set the `ShowComment` property to true.

{% tabs %}
{% highlight c# %}

cellGrid.ShowComment  = true;

{% endhighlight %}
{% endtabs %}

### Adding comment

The comment tip can be added to the cell by setting the `Comment` property. The assigned text will be displayed in the comment window.

{% tabs %}
{% highlight c# %}

//To add the Comment for cell,
cellGrid.Model[3, 3].Comment = "Syncfusion";

//To add the Comment for header cells alone,
cellGrid.Model.HeaderStyle.Comment = "Syncfusion";

//To add the Comment for the footer cells alone,
cellGrid.Model.FooterStyle.Comment= "Syncfusion";

//To add the Comment for the column,
cellGrid.Model.ColStyles[4].Comment = "Syncfusion");

//To add the Comment for the row,
cellGrid.Model.RowStyles[3].Comment = "Syncfusion";

{% endhighlight %}
{% endtabs %}

### Comment brush

The `CommentBrush` property is used to determine the color of the rectangle at the top corner of the comment cell.

{% tabs %}
{% highlight c# %}

cellGrid.Model[5, 5].CommentBrush = new SolidColorBrush(Colors.GreenYellow);

{% endhighlight %}
{% endtabs %}

### Customization of comment

The comment can be customized by defining a custom data template and assign to the `CommentTemplate` property of the SfCellGrid.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfCellGrid.Resources>
    <DataTemplate x:Key="custom">
       <Border BorderThickness="2"
            Background="Orange"
             BorderBrush="Green">
            <TextBlock Text="{Binding Path=Comment}" 
                 FontSize="12"
                 Foreground="Green"
                 Padding="2"/>
        </Border>
    </DataTemplate>
</syncfusion:SfCellGrid.Resources>

{% endhighlight %}
{% highlight c# %}

cellGrid.Model[3, 3].CommentTemplate = cellGrid.Resources["custom"] as DataTemplate;
cellGrid.Model[3, 3].Comment = "CustomComment";

{% endhighlight %}
{% endtabs %}

N> Customized data template should be defined in the SfCellGrid.Resources in XAML file.

### Reset comment

The `ResetComment` method is used to reset or remove the comment from the SfCellGrid.

{% tabs %}
{% highlight c# %}

cellGrid.Model[3, 3].ResetComment();

{% endhighlight %}
{% endtabs %}

### Reset comment template

The `ResetCommentTemplate` method is used to reset or remove the custom comment template defined in the SfCellGrid.

{% tabs %}
{% highlight c# %}

cellGrid.Model[3, 3].ResetCommentTemplate();

{% endhighlight %}
{% endtabs %}

### CellCommentOpening event

The `CellCommentOpening` event occurs when opening the comment in the SfCellGrid. It receives an argument of type `CellCommentOpeningEventArgs` containing the following information about the event.

<table>
<tr>
<th>
Property</th><th>
Description</th></tr>
<tr>
<td>
<code>Cell</code></td><td>
Gets or sets the value that indicates cell comment index. </td></tr>
<tr>
<td>
<code>Cancel</code></td><td>
Gets or sets whether the event should be cancel or not. </td></tr>
<tr>
<td>
<code>Comment</code></td><td>
Gets or sets the comment text. </td></tr>
<tr>
<td>
<code>CommentBrush</code></td><td>
Gets or sets the comment brush color. </td></tr>
</table>

{% tabs %}
{% highlight c# %}

cellGrid.CellCommentOpening += CellGrid_CellCommentOpening;

private void CellGrid_CellCommentOpening(object sender, CellCommentOpeningEventArgs e)
{
    var cellIndex = e.Cell;
    var text = e.Comment;
    var color = e.CommentBrush;
    e.Cancel = true;
}

{% endhighlight %}
{% endtabs %}

## Context menu

Context menu is a customizable menu used for various functionalities. The context menu opens when the user right-click the cell or selection of cells in the SfCellGrid.

User can add their own menu items and assign to the `CellContextMenu` property.

{% tabs %}
{% highlight c# %}

cellGrid.CellContextMenu = menu();

public ContextMenu menu()
{
    var menu = new ContextMenu();
           
    var insertRow = new MenuFlyoutItem() { Text = "InsertRow", Height = 50 };
    insertRow.BorderThickness = new Thickness(0);
    insertRow.Click += insertRow_Click;
    menu.Items.Add(insertRow);

    var deleteRow = new MenuFlyoutItem() { Text = "DeleteRow", Height = 50 };
    deleteRow.BorderThickness = new Thickness(0);
    deleteRow.Click += deleteRow_Click;
    menu.Items.Add(deleteRow);
    return menu;         
}
{% endhighlight %}
{% endtabs %}

### CellContextMenuOpening event

This event occurs when the context menu opens in the SfCellGrid. It receives an argument of type `CellContextMenuOpeningEventArgs` containing the following information about the event.

<table>
<tr>
<th>
Property</th><th>
Description</th></tr>
<tr>
<td>
<code>Cell</code></td><td>
Gets or sets the row or column index of the cell. </td></tr>
<tr>
<td>
<code>Handled</code></td><td>
Gets or sets whether the event should be handled or not. </td></tr>
<tr>
<td>
<code>CellContextMenu</code></td><td>
Gets or sets the context menu for the cell. </td></tr>
</table>

User can add or delete the context menu items at runtime by using the `CellContextMenuOpening` event.

{% tabs %}
{% highlight c# %}

cellGrid.CellContextMenuOpening += CellGrid_CellContextMenuOpening;

private void CellGrid_CellContextMenuOpening(object sender, CellContextMenuOpeningEventArgs e)
{
    var cellIndex = e.Cell;
    
    //To remove the context menu 
    e.CellContextMenu.Items.RemoveAt(0);
    
    e.Handled = true;
}

{% endhighlight %}
{% endtabs %}
