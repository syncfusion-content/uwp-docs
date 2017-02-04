---
layout: post
title: Interactive Features
description: Interactive operations in SfCellGrid
platform: uwp
control: SfCellGrid
documentation: ug
---


# Interactive Features

This section explains about the interactive operations with SfCellGrid.

## Clipboard Operations

SfCellGrid provides support to clipboard operations such as Cut, Copy and Paste which are managed in `GridCopyPaste` class. This class can be accessed by
`CopyPaste` property of SfCellGrid which provides methods to perform clipboard operations.

### Cut

The selected range of cells or data can be cut by using `Cut` method. The keyboard keys <kbd>Ctrl</kbd> +<kbd> X</kbd> combination is also used to perform the Cut operation.

{% tabs %}
{% highlight c# %}

//To cut the selected ranges,
cellGrid.CopyPaste.Cut();

//To cut the ranges passed at runtime,
var range = GridRangeInfo.Cells(2, 3, 4, 5);
cellGrid.CopyPaste.Copy(range, true);

{% endhighlight %}
{% endtabs %}

#### Event related with Cut Operation

The `ClipboardCut` event occurs when the cut operation is performed in SfCellGrid. It receives an argument of type `GridCutPasteEventArgs` which provides an option to get the copied range and handle the event.

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

The selected range of cells or data can be copied using `Copy` method. The keyboard keys <kbd>Ctrl</kbd> + <kbd>C</kbd> combination is also used to perform Copy operation.

{% tabs %}
{% highlight c# %}

//To copy the selected ranges,
cellGrid.CopyPaste.Copy();

//To copy the ranges passed at runtime,
var range = GridRangeInfo.Cells(2, 3, 4, 5);
cellGrid.CopyPaste.Copy(range, false);

{% endhighlight %}
{% endtabs %}

#### Event related with Copy Operation

The `ClipboardCopy` event occurs when the copy operation is performed in SfCellGrid. It receives an argument of type `GridCutPasteEventArgs` which provides an option to get the copied range and handle the event.

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

The copied ranges from the SfCellGrid can be pasted using `Paste` method. The keyboard keys <kbd>Ctrl<kbd> + <kbd>V</kbd> combination is also used to perform Paste operation.

{% tabs %}
{% highlight c# %}

//To paste the copied ranges including formatting,

cellGrid.Model.CopyPasteOptions = CopyPasteOptions.All;
cellGrid.CopyPaste.Paste();

{% endhighlight %}
{% endtabs %}

#### Copy Paste Options

The following are the list of paste options enum that can be used to perform paste operation based on user's requirement.

<table>
<tr>
<th>
Options</th><th>
Description</th></tr>
<tr>
<td>
All</td><td>
To paste with all the format options. </td></tr>
<tr>
<td>
Formulas</td><td>
To paste the formulas alone. </td></tr>
<tr>
<td>
Formats</td><td>
To maintain the copied range’s formatting</td></tr>
<tr>
<td>
Values</td><td>
To paste the values alone</td></tr>
<tr>
<td>
Comments</td><td>
To paste comments only without pasting formats and values. </td></tr>
<tr>
<td>
Transpose</td><td>
Copies the vertical range of cells and paste in horizontal range or vice versa. </td></tr>
<tr>
<td>
ClipboardOnly</td><td>
To copy and paste from clipboard without pasting any styles. </td></tr>
</table>

#### Event related with Paste Operation

The `ClipboardPaste` event occurs when the paste operation is performed in SfCellGrid. It receives an argument of type `GridCutPasteEventArgs` which provides an option to get or set the pasting range and handle the event.

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

## Tool Tip

SfCellGrid provides support for adding tooltip for individual cells. Tooltip will be displayed as small popup window, when the mouse hover the cells in SfCellGrid. 

To display the Tooltip, user need to set `ShowTooltip` property to true.

{% tabs %}
{% highlight c# %}

cellGrid.ShowTooltip  = true;

{% endhighlight %}
{% endtabs %}

### Adding Tooltip

The Tooltip can be added to the cell by setting the `Tooltip` property. The text assigned will be displayed in the tooltip window.

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

### Customization of Tooltip

The tooltip can be customized by defining a custom data template and assign to `TooltipTemplate` property of SfCellGrid.

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

### Reset Tooltip

`ResetTooltip` method is used to reset or remove the tooltip in SfCellGrid.

{% tabs %}
{% highlight c# %}

cellGrid.Model[3, 3].ResetTooltip();

{% endhighlight %}
{% endtabs %}

### Reset Tooltip template

`ResetTooltipTemplate` method is used to reset or remove the custom tooltip template defined in SfCellGrid.

{% tabs %}
{% highlight c# %}

cellGrid.Model[3, 3].ResetTooltipTemplate();

{% endhighlight %}
{% endtabs %}

### CellTooltipOpening Event

`CellTooltipOpening` event occurs when the tooltip is opened in SfCellGrid. It receives an argument of type `CellTooltipOpeningEventArgs` containing the following information about the event.

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
Gets or sets whether the event should be cancel or not. </td></tr>
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
    var cellindex = e.Cell;
    var text = e.Tooltip;
    e.Cancel = true;
}

{% endhighlight %}
{% endtabs %}

## Comment Tip

SfCellGrid provides support for adding the Excel-like comment tip to the individual cells. This acts as note that provides more information about data in an individual cell on mouse hover.
When a cell has a comment, a red indicator appears in the corner of the cell. When you rest the pointer on the cell, the comment appears.

To display the Comment, user need to set `ShowComment` property to true.

{% tabs %}
{% highlight c# %}

cellGrid.ShowComment  = true;

{% endhighlight %}
{% endtabs %}

### Adding Comment

The Comment tip can be added to the cell by setting the `Comment` property. The text assigned will be displayed in the comment window.

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

### Comment Brush

This `CommentBrush` property is used to determine the color of the rectangle at the top corner of the comment cell.

{% tabs %}
{% highlight c# %}

cellGrid.Model[5, 5].CommentBrush = new SolidColorBrush(Colors.GreenYellow);

{% endhighlight %}
{% endtabs %}

### Customization of Comment

The comment can be customized by defining a custom data template and assign to `CommentTemplate` property of SfCellGrid.

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

N> Customized data template should be defined in SfCellGrid.Resources in XAML file.

### Reset Comment

`ResetComment` method is used to reset or remove the comment in SfCellGrid.

{% tabs %}
{% highlight c# %}

cellGrid.Model[3, 3].ResetComment();

{% endhighlight %}
{% endtabs %}

### Reset Comment template

`ResetCommentTemplate` method is used to reset or remove the custom comment template defined in SfCellGrid.

{% tabs %}
{% highlight c# %}

cellGrid.Model[3, 3].ResetCommentTemplate();

{% endhighlight %}
{% endtabs %}

### CellCommentOpening Event

`CellCommentOpening` event occurs when the comment is opened in SfCellGrid. It receives an argument of type `CellCommentOpeningEventArgs` containing the following information about the event.

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
    var cellindex = e.Cell;
    var text = e.Comment;
    var color = e.CommentBrush;
    e.Cancel = true;
}

{% endhighlight %}
{% endtabs %}

## Context menu

Context menu is customizable menu which can be used for various functionalities. The Context menu opens when the user right-click on cell or selection of cells in SfCellGrid.

Users can add their own menu items and assign to the `CellContextMenu` property.

{% tabs %}
{% highlight c# %}

cellGrid.CellContextMenu = menu();

public ContextMenu menu()
{
    var menu = new ContextMenu();
           
    var Insertrow = new MenuFlyoutItem() { Text = "InsertRow", Height = 50 };
    Insertrow.BorderThickness = new Thickness(0);
    Insertrow.Click += Insertrow_Click;
    menu.Items.Add(Insertrow);

    var Deleterow = new MenuFlyoutItem() { Text = "DeleteRow", Height = 50 };
    Deleterow.BorderThickness = new Thickness(0);
    Deleterow.Click += Deleterow_Click;
    menu.Items.Add(Deleterow);
    return menu;         
}
{% endhighlight %}
{% endtabs %}

### CellContextMenuOpening Event

This event occurs when the context menu opens in SfCellGrid. It receives an argument of type `CellContextMenuOpeningEventArgs` containing the following information about the event.

<table>
<tr>
<th>
Property</th><th>
Description</th></tr>
<tr>
<td>
<code>Cell</code></td><td>
Gets or sets the row/column index of the cell. </td></tr>
<tr>
<td>
<code>Handled</code></td><td>
Gets or sets whether the event should be handled or not. </td></tr>
<tr>
<td>
<code>CellContextMenu</code></td><td>
Gets or sets the context menu for the cell. </td></tr>
</table>

Users can add or delete the context menu items at runtime using `CellContextMenuOpening` Event.

{% tabs %}
{% highlight c# %}

cellGrid.CellContextMenuOpening += CellGrid_CellContextMenuOpening;

private void CellGrid_CellContextMenuOpening(object sender, CellContextMenuOpeningEventArgs e)
{
    var cellindex = e.Cell;
    
    //To remove the context menu 
    e.CellContextMenu.Items.RemoveAt(0);
    
    e.Handled = true;
}

{% endhighlight %}
{% endtabs %}
