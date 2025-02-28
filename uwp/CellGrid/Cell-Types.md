---
layout: post
title: Cell Types in UWP CellGrid control | Syncfusion®
description: Learn here all about Cell Types support in Syncfusion® UWP CellGrid (SfCellGrid) control and more.
platform: uwp
control: SfCellGrid
documentation: ug
---

# Cell Types in UWP CellGrid (SfCellGrid)

SfCellGrid allows the inclusion of some special controls in the cells. This attribute of a grid cell is referred to as its Cell Type.

## Setting cell type for a cell

To add the desired cell type in a cell, the `CellType` property can be used. 

{% tabs %}
{% highlight c# %}

cellGrid.Model[2, 2].CellType = "CheckBox";
cellGrid.Model[2, 2].CellValue = true;

{% endhighlight %}
{% endtabs %}

## TextBox Cell Type

TextBox cells are the default cell type of SfCellGrid. TextBox cells displays text which can be edited when clicked.

{% tabs %}
{% highlight c# %}

cellGrid.Model[2, 3].CellType = "TextBox";
cellGrid.Model[2, 3].CellValue = "text";

{% endhighlight %}
{% endtabs %}

## Static Cell Type

Static cell type will display text that cannot be edited. It is possible to make the static cells as current cell but static cells cannot be activated for editing.

{% tabs %}
{% highlight c# %}

cellGrid.Model[2, 3].CellType = "Static";
cellGrid.Model[2, 3].CellValue = "text";
 
{% endhighlight %}
{% endtabs %}

## Header Cell Type

Header cells are as same as that of static cells. Header cell type is mainly used as header for rows and columns. 
If a cell/row/column needs to be of type header, then make use of this cell type.

{% tabs %}
{% highlight c# %}

cellGrid.Model.ColStyles[1].CellType = "Header";
cellGrid.Model.ColStyles[1].Background = new SolidColorBrush(Colors.LightPink);

{% endhighlight %}
{% endtabs %}

## CheckBox Cell Type

`CheckBox` cell type displays a check box in the mentioned cell of SfCellGrid. The check box has three states: **Checked, Unchecked and Indeterminate**. It is possible to decide whether the check box should behave as a two-state check box or a three-state check box 
by using the `IsThreeState` property.

{% tabs %}
{% highlight c# %}

cellGrid.Model[2, 2].CellType = "CheckBox";
cellGrid.Model[2, 2].IsThreeState = true;
cellGrid.Model[2, 2].CellValue = true;

{% endhighlight %}
{% endtabs %}

## ComboBox Cell Type

`ComboBox` cell type displays a combo box in the mentioned cell of SfCellGrid. A combo box is a component with a drop-down arrow that users click to display an associated list of choices.
This cell type allows you to choose the cell value from a drop-down list.
  
{% tabs %}
{% highlight c# %}

cellGrid.Model[2, 2].CellType = "ComboBox";
cellGrid.Model[2, 2].ComboBoxEdit.ItemSource = new List<int> {1,2,3,4,5,6 };

{% endhighlight %}
{% endtabs %}

## DateTime Cell Type

This cell type can be used to display the DateTime in the mentioned cell of SfCellGrid. Users can customize this date time cell by using `DateTimeEdit` property of `GridStyleInfo` class.

{% tabs %}
{% highlight c# %}

cellGrid.Model[2, 2].CellType = "DateTimeEdit";
cellGrid.Model[2, 2].CellValue = new DateTime(2016, 10, 9);
cellGrid.Model[2, 2].DateTimeEdit.AccentBrush = new SolidColorBrush(Colors.Blue);

{% endhighlight %}
{% endtabs %}

Below table describes the properties associated with `DateTimeEdit`,

<table>
<tr>
<th>
Property</th><th>
Description</th></tr>
<tr>
<td>
<code>AccentBrush</code></td><td>
Gets or sets the color of the DateTime control in the cell. </td></tr>
<tr>
<td>
<code>MaxDate</code></td><td>
Gets or sets the Maximum date. </td></tr>
<tr>
<td>
<code>MinDate</code></td><td>
Gets or sets the Minimum date. </td></tr>
<tr>
<td>
<code>AllowInlineEditing</code></td><td>
Gets or sets the bool value. If true, editing will be enabled in the cell. </td></tr>
<tr>
<td>
<code>ShowDropDownButton</code></td><td>
Gets or sets the bool value. If true, dropdown button will be shown. </td></tr>
<tr>
<td>
<code>Format</code></td><td>
Gets or sets the DateTime format. </td></tr>
<tr>
<td>
<code>DropDownHeight</code></td><td>
Gets or sets the height of the DateTime dropdown window. </td></tr>
<tr>
<td>
<code>IsDropDownOpen</code></td><td>
Gets or sets the bool value. If true, the dropdown will be opened. </td></tr>
<tr>
<td>
<code>SelectorItemCount</code></td><td>
Gets or sets the number of items to be used in dropdown popup. </td></tr>
<tr>
<td>
<code>SelectorFormatString</code></td><td>
Gets or sets the format of DateTime selector. </td></tr>
<tr>
<td>
<code>InputScope</code></td><td>
Gets or sets the input scope of the on-screen keyboard. </td></tr>
<tr>
<td>
<code>SelectorItemSpacing</code></td><td>
Gets or sets the space between the items in dropdown popup. </td></tr>
</table>

## Numeric Cell Type

This cell type can be used for restricting the numeric values entered in the cell. User can display different formats like currency format, scientific format, etc.,

{% tabs %}
{% highlight c# %}

cellGrid.Model[4, 5].CellType = "NumericEdit";
cellGrid.Model[4, 5].CellValue = 5;
cellGrid.Model[4, 5].NumericEdit.FormatString = "C";

{% endhighlight %}
{% endtabs %}

Below table describes the properties associated with `NumericEdit`,

<table>
<tr>
<th>
Property</th><th>
Description</th></tr>
<tr>
<td>
<code>MaxNumberOfDecimalDigits</code></td><td>
Gets or sets the number of decimal digits. </td></tr>
<tr>
<td>
<code>FormatString</code></td><td>
Gets or sets the number format. </td></tr>
<tr>
<td>
<code>Parsers</code></td><td>
Gets or sets the parsing mode. </td></tr>
<tr>
<td>
<code>PercentDisplayMode</code></td><td>
Gets or sets the percentage format type. </td></tr>
</table>

## UpDown Cell Type

This cell type displays up and down repeat buttons to increment and decrement the values in the cell of SfCellGrid. User can display different formats like currency format, scientific format, etc.,

{% tabs %}
{% highlight c# %}

cellGrid.Model[5, 5].CellType = "UpDownEdit";
cellGrid.Model[5, 5].UpDownEdit.Minimum = 1;
cellGrid.Model[5, 5].UpDownEdit.Maximum = 5;
cellGrid.Model[5, 5].CellValue = 10;

{% endhighlight %}
{% endtabs %}

Below table describes the properties associated with `UpDownEdit`,

<table>
<tr>
<th>
Property</th><th>
Description</th></tr>
<tr>
<td>
<code>AccentBrush</code></td><td>
Gets or sets the color of the Up-Down control in the cell. </td></tr>
<tr>
<td>
<code>NumberOfDecimalDigits</code></td><td>
Gets or sets the number of decimal digits. </td></tr>
<tr>
<td>
<code>Maximum</code></td><td>
Gets or sets the Maximum value. </td></tr>
<tr>
<td>
<code>Minimum</code></td><td>
Gets or sets the Minimum value. </td></tr>
<tr>
<td>
<code>FormatString</code></td><td>
Gets or sets the number format. </td></tr>
<tr>
<td>
<code>Parsers</code></td><td>
Gets or sets the parsing mode. </td></tr>
<tr>
<td>
<code>PercentDisplayMode</code></td><td>
Gets or sets the percentage format type. </td></tr>
<tr>
<td>
<code>LargeChange</code></td><td>
Gets or sets the value which gets incremented when PageUp key is pressed and validation is done based on Maximum value. </td></tr>
<tr>
<td>
<code>AutoReverse</code></td><td>
Gets or sets the bool value. If true, while incrementing, the control will start from Minimum once it reaches the Maximum and vice-versa. </td></tr>
<tr>
<td>
<code>SmallChange</code></td><td>
Gets or sets the value which gets incremented or decremented on mouse wheel. </td></tr>
<tr>
<td>
<code>SpinButtonAlignment</code></td><td>
Gets or sets the spin button position in the UpDown control and can be changed relative to the `TextBox` based on SpinButtonsAlignment. </td></tr>
<tr>
<td>
<code>TextAlignment</code></td><td>
Gets or sets the alignment of the contents in the cell. </td></tr>
</table>

## Hyperlink Cell Type

This cell type displays the hyperlink in the cell of SfCellGrid. This hyperlink cell type will be useful in navigating to browsers, other cells, mail. etc.,
The Url or the reference for the hyperlink cell will be given in the `Hyperlink` property.

{% tabs %}
{% highlight c# %}

cellGrid.Model[4, 5].CellType = "Hyperlink";
cellGrid.Model[4, 5].CellValue = "Google";
cellGrid.Model[4, 5].Hyperlink = "www.google.com";

{% endhighlight %}
{% endtabs %}

## DataTemplate Cell Type

This cell type is used to display the template-specified cell content. Users can load any WPF control in the display mode for all cells by setting `CellItemTemplate` and `CellEditTemplate` properties.

{% tabs %}
{% highlight xaml %}

<Page.Resources>
<DataTemplate x:Key="ButtonTemplate">
    <Button x:Name="Button"
                    Width="138.5"
                    Height="38"
                    BorderBrush="#0078D7"
                    Content="Click"
                    />
</DataTemplate>
</Page.Resources>
 
{% endhighlight %}
{% highlight c# %}

cellGrid.Model[4, 5].CellType = "DataTemplate";
cellGrid.Model[4, 5].CellItemTemplate = this.Resources["ButtonTemplate"] as DataTemplate;

{% endhighlight %}
{% endtabs %}

## Formula Cell Type

This cell type is used to enter the formula in the cell of SfCellGrid. The formulas in the `CellValue` property must be preceded with "=" sign.

{% tabs %}
{% highlight c# %}

cellGrid.Model[4, 4].CellType = "FormulaCell";
cellGrid.Model[4, 4].CellValue = "=Sum(A1:A2)";

{% endhighlight %}
{% endtabs %}

For more information regarding supported formulas in SfCellGrid, please refer [here](https://help.syncfusion.com/uwp/sfcellgrid/formulas#supported-functions).
