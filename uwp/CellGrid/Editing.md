---
layout: post
title: Editing in UWP CellGrid control | Syncfusion®
description: Learn here all about Editing support in Syncfusion® UWP CellGrid (SfCellGrid) control, its elements and more details.
platform: uwp
control: SfCellGrid
documentation: ug
---

# Editing in UWP CellGrid (SfCellGrid)

This section explains about the properties, methods associated with editing in SfCellGrid.

## Editing

The SfCellGrid control provides editing support for cells. For changing the edit behavior of cells, `EditTrigger` property is used. This property determines whether to edit the cells
with single click/tap or double click/tap.

{% tabs %}
{% highlight c# %}

// Begin editing after user clicks on a cell,
cellGrid.EditTrigger = EditTrigger.OnTap;

// Begin editing after user double clicks on a cell,   
cellGrid.EditTrigger = EditTrigger.OnDoubleTap;

{% endhighlight %}
{% endtabs %}

By default, editing will be enabled in SfCellGrid. But if you want to disable the editing, then set the `AllowEditing` property to be false.

{% tabs %}
{% highlight c# %}

    cellGrid.AllowEditing = false;

{% endhighlight %}
{% endtabs %}

### Editing a cell programmatically

#### Start Editing
    
User can edit a cell programmatically by using `BeginEdit` method.

{% tabs %}
{% highlight c# %}

    cellGrid.CurrentCell.BeginEdit(true);

{% endhighlight %}
{% endtabs %}

T>To check whether the current cell is in editing mode, make use of the `CurrentCell.IsEditing` property.

#### End Editing

User can end the editing of a cell programmatically in any of the following way,

* `ValidateAndEndEdit` - Validates and ends the edit operation for the current cell. if the cancel is "true", then the current cell remains in edit mode else if the validation is true, commits the new value and moved to next cell or else if the validation is false, it reverts the old value and moved to next cell.

* `EndEdit`   - Commits and ends the edit operation for the current cell, if it is passed with parameter _"true"_, commits the new changes for the cell, else reverts the old value.

{% tabs %}
{% highlight c# %}

//Validates and end the edit operation,

cellGrid.CurrentCell.ValidateAndEndEdit();

//Commits the value and end the edit operation,

cellGrid.CurrentCell.EndEdit(true);

{% endhighlight %}
{% endtabs %}

## Read Only

SfCellGrid allows the user to disable editing and formatting of the cells by using `ReadOnly` Property.

{% tabs %}
{% highlight c# %}

//To disable editing for entire grid,
cellGrid.Model.TableStyle.ReadOnly = true;

//To disable editing for row,
cellGrid.Model.RowStyles[3].ReadOnly = true;

//To disable editing for column,
cellGrid.Model.ColStyles[4].ReadOnly = true;

//To disable editing for cell,
cellGrid.Model[5, 6].ReadOnly = true;

{% endhighlight %}
{% endtabs %}

## Events related with Editing

### CurrentCellBeginEdit

This event occurs when the current cell enters edit mode. It receives an argument of type `CurrentCellBeginEditEventArgs` that provides an option of canceling the edit mode of current cell.

{% tabs %}
{% highlight c# %}

cellGrid.CurrentCellBeginEdit += CellGrid_CurrentCellBeginEdit;

private void CellGrid_CurrentCellBeginEdit(object sender, CurrentCellBeginEditEventArgs e)
{
    //To get the current cell index,
    var row = e.RowcolumnIndex.RowIndex;
    var col = e.RowcolumnIndex.ColumnIndex;

    //To cancel the edit operation,
    e.Cancel = true;
}

{% endhighlight %}
{% endtabs %}

### CurrentCellEndEdit

This event occurs when the grid completes the editing mode for active current cell. 

{% tabs %}
{% highlight c# %}

cellGrid.CurrentCellEndEdit += CellGrid_CurrentCellEndEdit;

private void CellGrid_CurrentCellEndEdit(object sender, CurrentCellEndEditEventArgs e)
{
    //To get the current cell index,
    var row = e.RowcolumnIndex.RowIndex;
    var col = e.RowcolumnIndex.ColumnIndex;
}

{% endhighlight %}
{% endtabs %}

### CurrentCellValueChanged

This event occurs when the user changes the contents of active current cell. It receives an argument of type `CurrentCellValueChangedEventArgs` which provides an 
option to get the cell value.

{% tabs %}
{% highlight c# %}

cellGrid.CurrentCellValueChanged += CellGrid_CurrentCellValueChanged;

private void CellGrid_CurrentCellValueChanged(object sender, CurrentCellValueChangedEventArgs e)
{
    //To get the current cell index,
    var row = e.RowcolumnIndex.RowIndex;
    var col = e.RowcolumnIndex.ColumnIndex;
    
    //To get the text in current cell,
    var text = e.ControlText;
}

{% endhighlight %}
{% endtabs %}

### CurrentCellValidating

This event occurs when the current cell value is going to be validated. It receives an argument of type `CurrentCellValidatingEventArgs` which provides an option to validate and cancel the editing.

{% tabs %}
{% highlight c# %}

cellGrid.CurrentCellValidating += CellGrid_CurrentCellValidating;

private void CellGrid_CurrentCellValidating(object sender, CurrentCellValidatingEventArgs e)
{
    //To get the current cell index,
    var row = e.RowcolumnIndex.RowIndex;
    var col = e.RowcolumnIndex.ColumnIndex;
    
    //To get the value in current cell,
    var old_val = e.OldValue;
    var new_val = e.NewValue;
    
    //Validating the cell value,
    int value = int.Parse(e.NewValue.ToString());
    if (value < 10)
    {
      e.IsValid = false;
      e.Cancel = true;
     }  
}

{% endhighlight %}
{% endtabs %}

T> Data validation can be done with `CurrentCellValidating` event. For more information, refer the topic [here](http://help.syncfusion.com/uwp/sfcellgrid/editing#programmatic-validation).

### CurrentCellValidated

This event occurs when the grid has successfully validated the contents of active current cell.

{% tabs %}
{% highlight c# %}

cellGrid.CurrentCellValidated += CellGrid_CurrentCellValidated;

private void CellGrid_CurrentCellValidated(object sender, CurrentCellValidatedEventArgs e)
{
    //To get the current cell index,
    var row = e.RowcolumnIndex.RowIndex;
    var col = e.RowcolumnIndex.ColumnIndex;
    
    //To get the value in current cell,
    var old_val = e.OldValue;
    var new_val = e.NewValue;   
}

{% endhighlight %}
{% endtabs %}

## Programmatic Validation

SfCellGrid allows the user to limit the type of data or the values that can be entered in the cell or range using `CurrentCellValidating` event.

{% tabs %}
{% highlight c# %}

cellGrid.CurrentCellValidating += cellGrid_CurrentCellValidating;

private async void CellGrid_CurrentCellValidating(object sender, CurrentCellValidatingEventArgs args)
{
    if (args.RowcolumnIndex.RowIndex == 4 && args.RowcolumnIndex.ColumnIndex == 5)
    {
        int value = 0;
        
        //Number Validation
        if (int.TryParse(args.NewValue.ToString(), out value))
        {
            if (value < 10)
            {
                args.IsValid = false;
                args.Cancel = true;
                var message = new MessageDialog("Enter a value greater than 10...", "Validation Error");
                await message.ShowAsync();
            }
        }
        else
        {
            args.IsValid = false;
            args.Cancel = true;
            var message = new MessageDialog("Enter valid integer value...", "Validation Error");
            await message.ShowAsync();
        }
    }
    if (args.RowcolumnIndex.RowIndex == 6 && args.RowcolumnIndex.ColumnIndex == 5)
    {
        int value = 0;
        if (int.TryParse(args.NewValue.ToString(), out value))
        {
            if (value < 10 || value > 20)
            {
                args.IsValid = false;
                args.Cancel = true;
                var message = new MessageDialog("Enter a value between 10 and 20...", "Validation Error");
                await message.ShowAsync();
            }
        }
        else
        {
            args.IsValid = false;
            args.Cancel = true;
            var message = new MessageDialog("Enter valid integer value...", "Validation Error");
            await message.ShowAsync();
        }
    }
    
    //TextLength Validation
    if (args.RowcolumnIndex.RowIndex == 8 && args.RowcolumnIndex.ColumnIndex == 5)
    {
        if (args.NewValue.ToString().Length < 5)
        {
            args.IsValid = false;
            args.Cancel = true;
            var message = new MessageDialog("Enter string length greater than 5...", "Validation Error");
            await message.ShowAsync();
        }
    }
    
    //Date Validation
    if (args.RowcolumnIndex.RowIndex == 12 && args.RowcolumnIndex.ColumnIndex == 5)
    {
        DateTime date;
        if (DateTime.TryParse(args.NewValue.ToString(), out date))
        {
            if (date.Month != DateTime.Now.Month)
            {
                args.IsValid = false;
                args.Cancel = true;
                var message = new MessageDialog("Enter a date from this month...", "Validation Error");
                await message.ShowAsync();
            }
        }
        else
        {
            args.IsValid = false;
            args.Cancel = true;
            var message = new MessageDialog("Enter valid Date...", "Validation Error");
            await message.ShowAsync();
        }
    }
}

{% endhighlight %}
{% endtabs %}


## Properties

Below table list the properties associated with Editing.

<table>
<tr>
<th>
Properties</th><th>
Description</th></tr>
<tr>
<td>
<code>AllowEditing</code></td><td>
Gets or sets the value indicating whether to allow the editing operation or not. </td></tr>
<tr>
<td>
<code>EditorSelectionBehavior</code></td><td>
Gets or sets a value indicating whether editor select all the value or move last position. </td></tr>
<tr>
<td>
<code>EditTrigger</code></td><td>
Gets or sets a value indicating any of the trigger options will cause cells to enter Edit Mode. </td></tr>
<tr>
<td>
<code>IsEditing</code></td><td>
Gets whether the current cell is in edit mode or not. </td></tr>
</table>

## Methods

Below table list the methods associated with Editing.

<table>
<tr>
<th>
Methods</th><th>
Description</th></tr>
<tr>
<td>
<code>BeginEdit</code></td><td>
Begins the editing operation of the current cell and returns true if the current cell enters edit mode. </td></tr>
<tr>
<td>
<code>EndEdit</code></td><td>
Commits and ends the edit operation of the current cell. </td></tr>
<tr>
<td>
<code>ValidateAndEndEdit</code></td><td>
Validates and ends the edit operation of the current cell. </td></tr>
<tr>
<td>
<code>Validate</code></td><td>
Validates the current cell in the SfCellGrid. </td></tr>
</table>
