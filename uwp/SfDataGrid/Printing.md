---
layout: post
title: Printing in SfDataGrid
description: How to print the SfDataGrid data
platform: uwp
control: SfDataGrid
documentation: ug
---

# Printing

SfDataGrid provides support to print the data displayed in the DataGrid using [SfDataGrid.Print](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfDataGridClassPrintTopic.html) method.
 
{% tabs %}
{% highlight c# %}
dataGrid.Print();
{% endhighlight %}
{% endtabs %}

## Print Settings

SfDataGrid provides various options to customize print preview settings using [SfDataGrid.PrintSettings](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfDataGridClassPrintSettingsTopic.html) property of type [PrintSettings](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintSettingsClassTopic.html).

{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings = new PrintSettings();
dataGrid.PrintSettings.AllowRepeatHeaders = false;            
dataGrid.Print();
{% endhighlight %}
{% endtabs %}

### Print

Print method opens the System print dialog where user can select the printer and set the number of copies to be printed.

![](Printing_images/Printing_img1.png)

### Scaling

SfDataGrid provides support to scale rows or columns or both while printing to fit on one page. Scaling options can be changed by setting [PrintSettings.PrintScaleOption](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintSettingsClassPrintScaleOptionTopic.html) property.

{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings = new PrintSettings();
dataGrid.PrintSettings.AllowColumnWidthFitToPrintPage = false;
dataGrid.PrintSettings.PrintScaleOption = PrintScaleOptions.FitAllColumnsonOnePage;
dataGrid.ShowPrintPreview();
{% endhighlight %}
{% endtabs %}

### Column Header on each page

Column headers can be printed on each page by enabling [PrintSettings.AllowRepeatHeaders](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintSettingsClassAllowRepeatHeadersTopic.html) property while printing.

{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings = new PrintSettings();
dataGrid.PrintSettings.AllowRepeatHeaders = true;
dataGrid.Print();
{% endhighlight %}
{% endtabs %}

### Changing Flow Direction while printing

You can change the text direction in print page by using [PrintSettings.PrintFlowDirection](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintSettingsClassPrintFlowDirectionTopic.html) property.

{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings = new PrintSettings();
dataGrid.PrintSettings.PrintFlowDirection = FlowDirection.RightToLeft;
dataGrid.Print();
{% endhighlight %}
{% endtabs %}

### Print with StackedHeaders

SfDataGrid provides support to print the StackedHeaders by setting the [PrintSettings.CanPrintStackedHeaders](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/index.html#frlrfSyncfusionUIXamlGridPrintSettingsClassCanPrintStackedHeadersTopic.html) as ‘true’.
{% tabs %}
{% highlight c# %}
this.sfDataGrid.PrintSettings.CanPrintStackedHeaders = true;
{% endhighlight %}
{% endtabs %}

![](Printing_images/Printing_img13.png)

## Page Settings

SfDataGrid provides various options to customize page settings using [SfDataGrid.PrintSettings](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridSfDataGridClassPrintSettingsTopic.html) property of type [PrintSettings](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintSettingsClassTopic.html).

### Orientation

SfDataGrid provides support to switch between Portrait (more rows but fewer columns) and Landscape (more columns but fewer rows) orientation while printing. Orientation can be changed by setting [PrintSettings.PrintPageOrientation](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintSettingsClassPrintPageOrientationTopic.html) Property.

{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings = new PrintSettings();
dataGrid.PrintSettings.PrintPageOrientation = PrintOrientation.Landscape;
dataGrid.ShowPrintPreview();
{% endhighlight %}
{% endtabs %}

### Page size

SfDataGrid provides support to change the page size. Page size can be changed by setting [PrintSettings.PrintPageWidth](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintSettingsClassPrintPageWidthTopic.html) and [PrintSettings.PrintPageHeight](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintSettingsClassPrintPageHeightTopic.html) properties.

{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings = new PrintSettings();
dataGrid.PrintSettings.PrintPageHeight = 800;            
dataGrid.PrintSettings.PrintPageWidth = 800;
dataGrid.Print();
{% endhighlight %}
{% endtabs %}

### Page margin

SfDataGrid provides support to change the page margins to adjust content in printed page. Page margin can be changed by setting [PrintSettings.PrintPageMargin](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintSettingsClassPrintPageMarginTopic.html) property. 

{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings = new PrintSettings();
dataGrid.PrintSettings.PrintPageMargin = new Thickness(5);
dataGrid.Print();
{% endhighlight %}
{% endtabs %}

## Setting Header and Footer

SfDataGrid provides a way to display additional content at the top (Header) or bottom (Footer) of the page while printing. This can be achieved by setting [PrintPageHeaderHeight](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintSettingsClassPrintPageHeaderHeightTopic.html), [PrintPageHeaderTemplate](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintSettingsClassPrintPageHeaderTemplateTopic.html), [PrintPageFooterHeight](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintSettingsClassPrintPageFooterHeightTopic.html), [PrintPageFooterTemplate](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintSettingsClassPrintPageFooterTemplateTopic.html) properties in [PrintSettings](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintSettingsClassTopic.html).
Steps to add page header while printing,

1. Create DataTemplate in Application.Resources.
{% tabs %}
{% highlight xaml %}
<Application.Resources>
    <DataTemplate x:Key="PageHeaderTempalte">
        <Grid Background="Gray">
            <TextBlock Text="Syncfusion" FontSize="18" FontWeight="Bold" 
                       Foreground="White" HorizontalAlignment="Center"/>
        </Grid>
    </DataTemplate>
</Application.Resources>
{% endhighlight %}
{% endtabs %}

2. Set the above defined DataTemplate to [PrintSettings.PrintPageHeaderTemplate](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintSettingsClassPrintPageHeaderTemplateTopic.html) and assign value for [PrintSettings.PrintPageHeaderHeight](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintSettingsClassPrintPageHeaderHeightTopic.html) property also.

{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings = new PrintSettings();
dataGrid.PrintSettings.PrintPageHeaderHeight = 30;
dataGrid.PrintSettings.PrintPageHeaderTemplate = Application.Current.Resources["PageHeaderTempalte"] as DataTemplate;
dataGrid.Print();
{% endhighlight %}
{% endtabs %}

3.Now run the application and you can see page header in all the pages. In the same way, you can set [PrintSettings.PrintPageFooterTemplate](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintSettingsClassPrintPageFooterTemplateTopic.html) also.

![](Printing_images/Printing_img2.png)

N> [PrintManagerBase](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintManagerBaseClassTopic.html) is the DataContext for [PrintPageControl](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintPageControlClassTopic.html), where the header and footer templates are loaded.

### Printing Current Date time

You can print current Date and Time at each page by setting the  [PrintPageFooterHeight](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintSettingsClassPrintPageFooterHeightTopic.html),  [PrintPageFooterTemplate](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintSettingsClassPrintPageFooterTemplateTopic.html) properties in [PrintSettings](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintSettingsClassTopic.html). 

{% tabs %}
{% highlight xaml %}
<Page.Resources>        
    <local:ViewModel x:Key="viewModel"/>        
    <DataTemplate x:Key="PageFooterTempalte">
        <Grid>
            <TextBlock HorizontalAlignment="Center" FontSize="20" VerticalAlignment="Center"  
                    Text="{Binding Path=Date, Source={StaticResource viewModel}}"/>
        </Grid>
    </DataTemplate>
</Page.Resources>
{% endhighlight %}
{% highlight c# %}
dataGrid.PrintSettings = new PrintSettings();
dataGrid.PrintSettings.PrintPageFooterHeight = 30;
dataGrid.PrintSettings.PrintPageFooterTemplate = Resources["PageFooterTempalte"] as DataTemplate;
dataGrid.Print();
{% endhighlight %}
{% endtabs %}

![](Printing_images/Printing_img3.png)

## Printing using UIElement Rendering

When you want to print the SfDataGrid with same appearance settings as in the display (Background and Foreground) or with custom appearance by writing styles.
You can print SfDataGrid as it displayed in View by setting [PrintSettings.AllowPrintStyles](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintSettingsClassAllowPrintStylesTopic.html) to true.

{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings = new PrintSettings();
dataGrid.PrintSettings.AllowPrintStyles = true;
dataGrid.Print();
{% endhighlight %}
{% endtabs %}

[GridHeaderCellControl](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridHeaderCellControlClassTopic.html) style customized and the same style will be exported while printing by setting [PrintSettings.AllowPrintStyles](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintSettingsClassAllowPrintStylesTopic.html) to true.

{% tabs %}
{% highlight xaml %}
<Application.Resources>
     <Style TargetType="syncfusion:GridHeaderCellControl">
         <Setter Property="Background" Value="LightPink"/>            
     </Style>
</Application.Resources>
{% endhighlight %}
{% endtabs %}

![](Printing_images/Printing_img4.png)

### Applying custom style

Custom styles can be applied while printing by setting [PrintSettings.AllowPrintStyles](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintSettingsClassAllowPrintStylesTopic.html) to false and writing style for below controls based on your requirement.

<table>
<tr>
<th>
**Appearance to be customized**
</th>
<th>
**TargetType of Style**
</th>
</tr>
<tr>
<td>
Header Cell
</td>
<td>
[PrintHeaderCell](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintHeaderCellClassTopic.html)
</td>
</tr>
<tr>
<td>
Normal Cells
</td>
<td>
[PrintGridCell](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintGridCellClassTopic.html)
</td>
</tr>
<tr>
<td>
Caption summary cells
</td>
<td>
[PrintCaptionSummaryCell](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintCaptionSummaryCellClassTopic.html)
</td>
</tr>
<tr>
<td>
Group summary cells
</td>
<td>
[PrintGroupSummaryCell](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintGroupSummaryCellClassTopic.html)
</td>
</tr>
<tr>
<td>
Table summary cells
</td>
<td>
[PrintTableSummaryCell](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintTableSummaryCellClassTopic.html)
</td>
</tr>
<tr>
<td>
Unbound row cells
</td>
<td>
[PrintUnboundRowCell](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintUnboundRowCellClassTopic.html)
</td>
</tr>
</table>

To provide custom appearance for Header cells while printing, [PrintHeaderCell](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintHeaderCellClassTopic.html) style is customized.

{% tabs %}
{% highlight xaml %}
<Application.Resources>
    <Style TargetType="syncfusion:PrintHeaderCell">
         <Setter Property="Background" Value="LightSkyBlue"/>            
    </Style>
</Application.Resources>
{% endhighlight %}
{% endtabs %}

To print SfDataGrid with custom styles, [PrintSettings.AllowPrintStyles](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintSettingsClassAllowPrintStylesTopic.html) property to false.

{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings = new PrintSettings();
dataGrid.PrintSettings.AllowPrintStyles = false;
dataGrid.Print();
{% endhighlight %}
{% endtabs %}

![](Printing_images/Printing_img5.png)

## Printing Customization 

Printing operations can be customized by overriding [GridPrintManager](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridPrintManagerClassTopic.html) and its available methods.

### Setting different Row Height 

SfDataGrid allows you to set different Row height for specific rows while printing. You can achieve this by overriding the [GetRowHeight](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintManagerBaseClassGetRowHeightTopic.html) method in [PrintManagerBase](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintManagerBaseClassTopic.html) class.

{% tabs %}
{% highlight c# %}
private class CustomPrintManager : GridPrintManager
{
    public CustomPrintManager(SfDataGrid grid)
        : base(grid)
    {
    }
    protected override double GetRowHeight(object record, int rowIndex, RowType rowtype)
    {
        if (rowIndex != -1 && !(record is Group))
            if (rowIndex % 2 != 0)
                return 80.0;
        return base.GetRowHeight(record, rowIndex, rowtype);
    }       
}
{% endhighlight %}
{% endtabs %}


{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings.PrintManagerBase = new CustomPrintManager(this.dataGrid);
dataGrid.PrintSettings.PrintManagerBase.Print();
{% endhighlight %}
{% endtabs %}

![](Printing_images/Printing_img6.png)

### Hiding rows while printing
     
You can hide specific row by using [GetRowHeight](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintManagerBaseClassGetRowHeightTopic.html) method in [PrintManagerBase](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintManagerBaseClassTopic.html) class and setting height as 0.
Here, unbound row is excluded while printing. Likewise, you can hide any row based on record and row index.

{% tabs %}
{% highlight c# %}
public class CustomPrintManager : GridPrintManager
{
    public CustomPrintManager(SfDataGrid grid)
        : base(grid)
    {
    }
    protected override double GetRowHeight(object record, int rowIndex, RowType rowtype)
    {
            if (record is GridUnBoundRow)
                return 0;
            return base.GetRowHeight(record, rowIndex, rowtype);
    }       
}
{% endhighlight %}
{% endtabs %}


{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings.PrintManagerBase = new CustomPrintManager(this.dataGrid);
dataGrid.PrintSettings.PrintManagerBase.Print();
{% endhighlight %}
{% endtabs %}

### Setup columns to be printed

SfDataGrid allows you to the exclude the columns while printing the grid. You can change the column list by overriding the [GetColumnNames](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridPrintManagerClassGetColumnNamesTopic.html) method in [PrintManagerBase](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintManagerBaseClassTopic.html) class.

{% tabs %}
{% highlight c# %}
public class CustomPrintManager : GridPrintManager
{
    public CustomPrintManager(SfDataGrid grid)
        : base(grid)
    {
    }

    protected override List<string> GetColumnNames()
    {
        List<string> columnList = this.dataGrid.Columns.
                                Select(x => x.MappingName).ToList();
        columnList.Remove("CustomerName");
        return columnList;
    }
}
{% endhighlight %}
{% endtabs %}


{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings.PrintManagerBase = new CustomPrintManager(this.dataGrid);
dataGrid.PrintSettings.PrintManagerBase.Print();
{% endhighlight %}
{% endtabs %}

![](Printing_images/Printing_img7.png)

### Customize the header text while printing

SfDataGrid allows you to change column header text while printing the grid. You can change the Column header text by overriding the [GetColumnHeaderText](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridPrintManagerClassGetColumnHeaderTextTopic.html) method in [GridPrintManager](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridPrintManagerClassTopic.html).

{% tabs %}
{% highlight c# %}
public class CustomPrintManager : GridPrintManager
{
    public CustomPrintManager(SfDataGrid grid)
        : base(grid)
    {
    }    

    protected override string GetColumnHeaderText(string mappingName)
    {
        if (mappingName == "OrderID")
            return "Order ID";
        return base.GetColumnHeaderText(mappingName);
    }
}
{% endhighlight %}
{% endtabs %}


{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings.PrintManagerBase = new CustomPrintManager(this.dataGrid);
dataGrid.PrintSettings.PrintManagerBase.Print();
{% endhighlight %}
{% endtabs %}

![](Printing_images/Printing_img8.png)

### Styling Rows

You can apply row styles based on custom logic by overriding [GetPrintGridCell](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridPrintManagerClassGetPrintGridCellTopic.html) method in [GridPrintManager](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridPrintManagerClassTopic.html).

{% tabs %}
{% highlight c# %}
public class CustomPrintManager : GridPrintManager
{
    public CustomPrintManager(SfDataGrid grid)
        : base(grid)
    {
    }

    public override ContentControl GetPrintGridCell(object record, string mappingName)
    {
        if (!(record is OrderInfo))
            return base.GetPrintGridCell(record, mappingName);

        if ((record as OrderInfo).Country == "Germany")
            return new PrintGridCell() { Background = new SolidColorBrush(Colors.Bisque) };
        else if ((record as OrderInfo).Country == "Mexico")
            return new PrintGridCell() { Background = new SolidColorBrush(Colors.LightSkyBlue) };
        return base.GetPrintGridCell(record, mappingName);
    }
}
{% endhighlight %}
{% endtabs %}


{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings.PrintManagerBase = new CustomPrintManager(this.dataGrid);
dataGrid.PrintSettings.PrintManagerBase.Print();
{% endhighlight %}
{% endtabs %}

N> 
<table>
<tr>
<th>
**Appearance to be customized**
</th>
<th>
**Method**
</th>
</tr>
<tr>
<td>
Header Cell
</td>
<td>
[GetPrintHeaderCell](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridPrintManagerClassGetPrintHeaderCellTopic.html)
</td>
</tr>
<tr>
<td>
Normal Cells
</td>
<td>
[GetPrintGridCell](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridPrintManagerClassGetPrintGridCellTopic.html)
</td>
</tr>
<tr>
<td>
Caption summary cells
</td>
<td>
[GetPrintCaptionSummaryCell](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridPrintManagerClassGetPrintCaptionSummaryCellTopic.html)
</td>
</tr>
<tr>
<td>
Group summary cells
</td>
<td>
[GetPrintGroupSummaryCell](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridPrintManagerClassGetPrintGroupSummaryCellTopic.html)
</td>
</tr>
<tr>
<td>
Table summary cells
</td>
<td>
[GetPrintTableSummaryCell](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridPrintManagerClassGetPrintTableSummaryCellTopic.html)
</td>
</tr>
<tr>
<td>
Unbound row cells
</td>
<td>
[GetPrintUnboundRowCell](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridPrintManagerClassGetPrintUnboundRowCellTopic.html)
</td>
</tr>
</table>

![](Printing_images/Printing_img9.png)

### Setup alternate row style

SfDataGrid allows you to apply alternative row style by overriding [GetPrintGridCell](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridPrintManagerClassGetPrintGridCellTopic.html) method in `GridPrintManager`.

{% tabs %}
{% highlight c# %}
public class CustomPrintManager : GridPrintManager
{
    public CustomPrintManager(SfDataGrid grid)
        : base(grid)
    {
    }

    public override ContentControl GetPrintGridCell(object record, string mappingName)
    {
       var index = dataGrid.View.Records.IndexOfRecord(record);
       if (index % 2 == 0)
          return new PrintGridCell() { Background = new SolidColorBrush(Colors.Bisque) };
       return base.GetPrintGridCell(record, mappingName);
    }
}
{% endhighlight %}
{% endtabs %}


{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings.PrintManagerBase = new CustomPrintManager(this.dataGrid);
dataGrid.PrintSettings.PrintManagerBase.Print();
{% endhighlight %}
{% endtabs %}

![](Printing_images/Printing_img10.png)

### Styling Columns

You can apply column styles based on custom logic by overriding [GetPrintGridCell](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridGridPrintManagerClassGetPrintGridCellTopic.html) method in `GridPrintManager`.

{% tabs %}
{% highlight c# %}
public class CustomPrintManager : GridPrintManager
{
    public CustomPrintManager(SfDataGrid grid)
        : base(grid)
    {
    }

    public override ContentControl GetPrintGridCell(object record, string mappingName)
    {
    if (mappingName == "OrderID")
        return new PrintGridCell() { Background = new SolidColorBrush(Colors.LightGreen), FontStyle = Windows.UI.Text.FontStyle.Italic };
    return base.GetPrintGridCell(record, mappingName);
    }
}
{% endhighlight %}
{% endtabs %}


{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings.PrintManagerBase = new CustomPrintManager(this.dataGrid);
dataGrid.PrintSettings.PrintManagerBase.Print();
{% endhighlight %}
{% endtabs %}

![](Printing_images/Printing_img11.png)

N> [GetColumnWidth](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintManagerBaseClassGetColumnWidthTopic.html), [GetColumnTextWrapping](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintManagerBaseClassGetColumnTextWrappingTopic.html), [GetColumnTextAlignment](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintManagerBaseClassGetColumnTextAlignmentTopic.html) and [GetColumnPadding](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintManagerBaseClassGetColumnPaddingTopic.html) methods are also used for column customization while printing.

### Printing Selected rows

Selected rows can be printed by overriding [GetSourceListForPrinting](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlGridPrintManagerBaseClassGetSourceListForPrintingTopic.html) method in `PrintManagerClass` class.

{% tabs %}
{% highlight c# %}
public class CustomPrintManager : GridPrintManager
{
    public CustomPrintManager(SfDataGrid grid)
        : base(grid)
    {
    }
    
    protected override IList GetSourceListForPrinting()
    {
        List<object> selectedRecords = new List<object>();
        var selectedRows = dataGrid.SelectionController.SelectedRows.ToList();
        foreach (var row in selectedRows)
        {
            if (row.IsAddNewRow || (row.NodeEntry != null && (!row.NodeEntry.IsRecords)))
                continue;
            if (row.IsUnBoundRow)
            {
                var _row = dataGrid.UnBoundRows.FirstOrDefault(r => r.Position == row.GridUnboundRowInfo.Position && r.ShowBelowSummary == row.GridUnboundRowInfo.ShowBelowSummary && r.RowIndex == row.GridUnboundRowInfo.RowIndex);
                selectedRecords.Add(_row);
            }
            else
                selectedRecords.Add(row.NodeEntry);
        }
        return selectedRecords;
    }
}
{% endhighlight %}
{% endtabs %}


{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings.PrintManagerBase = new CustomPrintManager(this.dataGrid);
dataGrid.PrintSettings.PrintManagerBase.Print();
{% endhighlight %}
{% endtabs %}

![](Printing_images/Printing_img12.png)

