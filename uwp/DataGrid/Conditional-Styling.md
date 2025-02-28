---
layout: post
title: Conditional Styling in UWP DataGrid control | Syncfusion®
description: Learn here all about Conditional Styling support in Syncfusion® UWP DataGrid (SfDataGrid) control and more.
platform: uwp
control: SfDataGrid
documentation: ug
---

# Conditional Styling in UWP DataGrid (SfDataGrid)

You can style the SfDataGrid and its inner elements conditionally based on data in two ways,

1. Using Converter
2. Using StyleSelector

<table>
<tr>
<td>
{{'**Styling Ways**'| markdownify }}
</td>
<td>
{{'**Performance Details**'| markdownify }}
</td>
</tr>
<tr>
<td>
Using Converter
</td>
<td>
Provide good performance when compared other two ways.
</td>
</tr>
<tr>
<td>
Using StyleSelector
</td>
<td>
It affects scrolling performance while styling more number of columns based on number of columns visible.
</td>
</tr>
</table>

## Cells

### Styling cells using Converter

The record cells ([GridCell](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCell.html#Syncfusion_SfGrid_UWP__ctor)) can be customized conditionally by changing its property value based on `cell value` or `data object` using `converter`.
Here, `GridCell` background is changed using `converter`, where converter returns the value based on `OrderID` property of underlying record.

{% tabs %}
{% highlight xaml %}
xmlns:utils="using:Syncfusion.UI.Xaml.Utils"

<Page.Resources>
    <local:ColorConverter x:Key="converter"/>
</Page.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid"
                       ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.Columns>
        <syncfusion:GridTextColumn MappingName="OrderID">
            <syncfusion:GridTextColumn.CellStyle>
                <Style TargetType="syncfusion:GridCell">
                    <Setter Property="utils:SetterValueBindingHelper.PropertyBinding">
                        <Setter.Value>
                            <utils:SetterValueBindingHelper Property="Background" Binding="{Binding OrderID,Converter={StaticResource converter}}"/>
                        </Setter.Value>
                    </Setter>
                </Style>
            </syncfusion:GridTextColumn.CellStyle>
        </syncfusion:GridTextColumn>
    </syncfusion:SfDataGrid.Columns>
</syncfusion:SfDataGrid>
{% endhighlight %}

{% highlight c# %}
public class ColorConverter : IValueConverter
{

    public object Convert(object value, Type targetType, object parameter, string language)
    {
        int input = (int)value;

        if (input < 1003)
            return new SolidColorBrush(Colors.LightBlue);

        else if (input < 1007)
            return new SolidColorBrush(Colors.Bisque);

        else
            return DependencyProperty.UnsetValue;
    }
    
    public object ConvertBack(object value, Type targetType, object parameter, string language)
    {
        throw new NotImplementedException();
    }     
}
{% endhighlight %}
{% endtabs %}

![Conditional-Styling_img1](Conditional-Styling_images/Conditional-Styling_img1.png)

### Styling cells based on record using Converter

You can also style the cells based on record instead of passing single property to converter, where `converter` returns the value based on underlying record. This can be assigned to [GridColumn.CellStyle](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridColumnBase.html#Syncfusion_UI_Xaml_Grid_GridColumnBase_CellStyle) to style the column based on other column properties.

{% tabs %}
{% highlight xaml %}
xmlns:utils="using:Syncfusion.UI.Xaml.Utils"

<Page.Resources>
    <local:ColorConverter x:Key="converter"/>
    <Style TargetType="syncfusion:GridCell">
        <Setter Property="utils:SetterValueBindingHelper.PropertyBinding">
            <Setter.Value>
                <utils:SetterValueBindingHelper Property="Background" Binding="{Binding Converter={StaticResource converter}}"/>
            </Setter.Value>
        </Setter>
    </Style>
</Page.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid"
                       ItemsSource="{Binding Orders}">
</syncfusion:SfDataGrid>
{% endhighlight %}

{% highlight c# %}
public class ColorConverter : IValueConverter
{

    public object Convert(object value, Type targetType, object parameter, string language)
    {
        var data = value as OrderInfo;

        //custom condition is checked based on data.

        if (data.OrderID < 1003)
            return new SolidColorBrush(Colors.LightBlue);

        else if (data.OrderID < 1007)
            return new SolidColorBrush(Colors.Bisque);

        else
            return DependencyProperty.UnsetValue;
    }

    public object ConvertBack(object value, Type targetType, object parameter, string language)
    {
        throw new NotImplementedException();
    }
}  
{% endhighlight %}
{% endtabs %}

![Conditional-Styling_img2](Conditional-Styling_images/Conditional-Styling_img2.png)

### Styling cells using StyleSelector

The record cells [GridCell](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCell.html#Syncfusion_SfGrid_UWP__ctor)) can be customized conditionally based on data by setting [SfDataGrid.CellStyleSelector](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_CellStyleSelector) property and the particular column record cells can be customized by setting [GridColumn.CellStyleSelector](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridColumnBase.html#Syncfusion_UI_Xaml_Grid_GridColumnBase_CellStyleSelector) property and you can get the container as `GridCell` in the StyleSelector.

N> `GridColumn.CellStyleSelector` takes higher priority than `SfDataGrid.CellStyleSelector` property.

{% tabs %}
{% highlight xaml %}
<Application.Resources>
    <local:SelectorClass x:Key="styleSelector"/>
    <Style x:Key="redCellStyle" TargetType="syncfusion:GridCell">
        <Setter Property="Foreground" Value="Red" />
    </Style>
    <Style x:Key="blueCellStyle" TargetType="syncfusion:GridCell">
        <Setter Property="Foreground" Value="DarkBlue" />
    </Style>
</Application.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid" 
                       CellStyleSelector="{StaticResource styleSelector}"
                       ItemsSource="{Binding Orders}">
</syncfusion:SfDataGrid>
{% endhighlight %}

{% highlight c# %}
public class SelectorClass : StyleSelector
{

    protected override Style SelectStyleCore(object item, DependencyObject container)
    {
        var data = item as OrderInfo;

        if (data != null && ((container as GridCell).ColumnBase.GridColumn.MappingName == "OrderID"))
        {

            //custom condition is checked based on data.

            if (data.OrderID < 1005)
                return App.Current.Resources["redCellStyle"] as Style;
            return App.Current.Resources["blueCellStyle"] as Style;
        }
        return base.SelectStyleCore(item, container);
    }        
}
{% endhighlight %}
{% endtabs %}

Here, GridCell’s are customized based on `OrderID` property of underlying record.

![Conditional-Styling_img3](Conditional-Styling_images/Conditional-Styling_img3.png)

## Rows

### Styling rows using Converter

The record rows ([VirtualizingCellsControl](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.VirtualizingCellsControl.html)) can be customized conditionally by changing its property value based on `cell value` or `data object` by using `converter`, where converter returns the value based on Underlying record.

{% tabs %}
{% highlight xaml %}
xmlns:utils="using:Syncfusion.UI.Xaml.Utils"

<Page.Resources>
    <local:ColorConverter x:Key="converter"/>
    <Style TargetType="syncfusion:VirtualizingCellsControl">
        <Setter Property="utils:SetterValueBindingHelper.PropertyBinding">
            <Setter.Value>
                <utils:SetterValueBindingHelper Property="Background" Binding="{Binding Converter={StaticResource converter}}"/>
            </Setter.Value>
        </Setter>
    </Style>
</Page.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid"                                                 
            ItemsSource="{Binding Orders}">
</syncfusion:SfDataGrid>
{% endhighlight %}

{% highlight c# %}
public class ColorConverter : IValueConverter
{

    public object Convert(object value, Type targetType, object parameter, string language)
    {
        var input = (value as OrderInfo).OrderID;

        //custom condition is checked based on data.

        if (input < 1003)
            return new SolidColorBrush(Colors.Bisque);

        else if (input < 1007)
            return new SolidColorBrush(Colors.LightBlue);

        else
            return DependencyProperty.UnsetValue;
    }
    public object ConvertBack(object value, Type targetType, object parameter, string language)
    {
        throw new NotImplementedException();
    }
}
{% endhighlight %}
{% endtabs %}

Here, rows are customized based on `OrderID`property of underlying record.

![Conditional-Styling_img4](Conditional-Styling_images/Conditional-Styling_img4.png)

### Styling rows using StyleSelector

The record rows ([VirtualizingCellsControl](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.VirtualizingCellsControl.html)) can be customized conditionally based on data by setting [SfDataGrid.RowStyleSelector](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_RowStyleSelector) property and you can get the container as `VirtualizingCellsControl` in StyleSelector.

{% tabs %}
{% highlight xaml %}
<Application.Resources>
    <local:SelectorClass x:Key="styleSelector"/>
    <Style x:Key="rowStyle1" TargetType="syncfusion:VirtualizingCellsControl">
        <Setter Property="Background" Value="Bisque" />
    </Style>
    <Style x:Key="rowStyle2" TargetType="syncfusion:VirtualizingCellsControl">
        <Setter Property="Background" Value="Aqua" />
    </Style>
</Application.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid"                     
                        RowStyleSelector="{StaticResource styleSelector}"
                        ItemsSource="{Binding Orders}">
{% endhighlight %}

{% highlight c# %}
public class SelectorClass : StyleSelector
{
 
    protected override Style SelectStyleCore(object item, DependencyObject container)
    {
        var row = (item as DataRowBase).RowData;
        var data = row as OrderInfo;
 
        if (data.OrderID < 1004)
            return App.Current.Resources["rowStyle1"] as Style;
        return App.Current.Resources["rowStyle2"] as Style;
    }
}
{% endhighlight %}
{% endtabs %}

Here, rows are customized based on `OrderID`property of underlying record.

![Conditional-Styling_img5](Conditional-Styling_images/Conditional-Styling_img5.png)

### Styling Alternate Rows

The appearance of alternating rows can be customized conditionally based on data by setting [SfDataGrid.AlternatingRowStyleSelector](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_AlternatingRowStyleSelector) property.

{% tabs %}
{% highlight xaml %}
<Application.Resources>
    <local:SelectorClass x:Key="styleSelector"/>
    <Style x:Key="rowStyle1" TargetType="syncfusion:VirtualizingCellsControl">
        <Setter Property="Background" Value="Bisque" />
    </Style>
    <Style x:Key="rowStyle2" TargetType="syncfusion:VirtualizingCellsControl">
        <Setter Property="Background" Value="Aqua" />
    </Style>
</Application.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid"                        
                       AlternatingRowStyleSelector="{StaticResource styleSelector}"
                       ItemsSource="{Binding Orders}">
{% endhighlight %}
{% highlight c# %}
public class SelectorClass : StyleSelector
{

    protected override Style SelectStyleCore(object item, DependencyObject container)
    {
        var row = (item as DataRowBase).RowData;
        var data = row as OrderInfo;

        if (data.OrderID < 1006)
            return App.Current.Resources["rowStyle1"] as Style;
        return App.Current.Resources["rowStyle2"] as Style;
    }
}
{% endhighlight %}
{% endtabs %}

Here, alternating rows are customized based on`OrderID` property of underlying record.

![Conditional-Styling_img6](Conditional-Styling_images/Conditional-Styling_img6.png)

## CaptionSummaryCell

### Styling caption summary cell using Converter

The appearance of caption summary cell can be customized conditionally based on summary value by using `converter`, where converter returns the value based on summary value.

{% tabs %}
{% highlight xaml %}
xmlns:utils="using:Syncfusion.UI.Xaml.Utils"

<Page.Resources>
    <local:ColorConverter x:Key="converter"/>
    <Style TargetType="syncfusion:GridCaptionSummaryCell">
        <Setter Property="utils:SetterValueBindingHelper.PropertyBinding">
            <Setter.Value>
                <utils:SetterValueBindingHelper Property="Foreground" Binding="{Binding Converter={StaticResource converter}}"/>
            </Setter.Value>
        </Setter>

    </Style>
</Page.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid" 
                        ColumnSizer="Star"
                        ShowGroupDropArea="True"
                        ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.CaptionSummaryRow>
        <syncfusion:GridSummaryRow ShowSummaryInRow="False">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="price"
                                            Format="'{Sum:c}'"
                                            MappingName="TotalPrice"
                                            SummaryType="DoubleAggregate" />
                <syncfusion:GridSummaryColumn Name="customerID"
                                            Format="'{Count:c}'"
                                            MappingName="UnitPrice"
                                            SummaryType="CountAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridSummaryRow>
    </syncfusion:SfDataGrid.CaptionSummaryRow>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public class ColorConverter : IValueConverter
{

    public object Convert(object value, Type targetType, object parameter, string language)
    {
        var summaryValue = (value as Group).SummaryDetails.SummaryValues[0];
        var aggregateValue = summaryValue.AggregateValues.ElementAt(0);
        var calculatedValue = aggregateValue.Value;

        //custom condition is checked.

        if ((double)calculatedValue < 1005)
            return new SolidColorBrush(Colors.Red);
        return new SolidColorBrush(Colors.DarkBlue);
    }

    public object ConvertBack(object value, Type targetType, object parameter, string language)
    {
        throw new NotImplementedException();
    }
}
{% endhighlight %}
{% endtabs %}

Here, caption summary cells are customized based on `TotalPrice`summary value.

![Conditional-Styling_img7](Conditional-Styling_images/Conditional-Styling_img7.png)

### Styling caption summary using StyleSelector

The appearance of caption summary cell can be customized conditionally based on summary value by setting [SfDataGrid.CaptionSummaryCellStyleSelector](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_CaptionSummaryCellStyleSelector) and you can get the container as [GridCaptionSummaryCell](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridCaptionSummaryCell.html) using `StyleSelector`.

{% tabs %}
{% highlight xaml %}
<Application.Resources>
    <local:SelectorClass x:Key="selector"/>
    <Style TargetType="syncfusion:GridCaptionSummaryCell" x:Key="captionSummaryStyle">
        <Setter Property="Foreground" Value="Red"/>
    </Style>
</Application.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid" 
                                           ShowGroupDropArea="True"
                                           CaptionSummaryCellStyleSelector="{StaticResource  selector}"
                                           ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.CaptionSummaryRow>
        <syncfusion:GridSummaryRow ShowSummaryInRow="False">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="price"
                                            Format="'{Sum:c}'"
                                            MappingName="TotalPrice"
                                            SummaryType="DoubleAggregate" />
                <syncfusion:GridSummaryColumn Name="customerID"
                                            Format="'{Count:c}'"
                                            MappingName="UnitPrice"
                                            SummaryType="CountAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridSummaryRow>
    </syncfusion:SfDataGrid.CaptionSummaryRow>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public class SelectorClass : StyleSelector
{

    protected override Style SelectStyleCore(object item, DependencyObject container)
    {
        var summaryValue = (item as Group).SummaryDetails.SummaryValues[0];
        var aggregateValue = summaryValue.AggregateValues.ElementAt(0);
        var calculatedValue = aggregateValue.Value;

        //custom condition is checked.

        if ((double)calculatedValue > 1005)
            return App.Current.Resources["captionSummaryStyle"] as Style;
        return base.SelectStyleCore(item, container);
    }        
}
{% endhighlight %}
{% endtabs %}

Here, caption summary cells are customized based on `TotalPrice`summary value.
![Conditional-Styling_img8](Conditional-Styling_images/Conditional-Styling_img8.png)

### Styling caption summary cell based on column

The caption summary cells can be conditionally customized summary column. Here, caption summary cells are customized based on `TotalPrice`summary column.

{% tabs %}
{% highlight xaml %}
<Application.Resources>
    <local:SelectorClass x:Key="selector"/>
    <Style TargetType="syncfusion:GridCaptionSummaryCell" x:Key="captionSummaryStyle">
        <Setter Property="Foreground" Value="Red"/>
    </Style>
</Application.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid" 
                       ShowGroupDropArea="True"
                       CaptionSummaryCellStyleSelector="{StaticResource selector}"
                       ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.CaptionSummaryRow>
        <syncfusion:GridSummaryRow ShowSummaryInRow="False">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="price"
                                            Format="'{Sum:c}'"
                                            MappingName="TotalPrice"
                                            SummaryType="DoubleAggregate" />
                <syncfusion:GridSummaryColumn Name="customerID"
                                            Format="'{Count:c}'"
                                            MappingName="UnitPrice"
                                            SummaryType="CountAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridSummaryRow>
    </syncfusion:SfDataGrid.CaptionSummaryRow>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public class SelectorClass : StyleSelector
{

    protected override Style SelectStyleCore(object item, DependencyObject container)
    {
        var cell = container as GridCaptionSummaryCell;

        if (cell.ColumnBase.GridColumn.MappingName == "TotalPrice")
        {
            var groupKey = (int)(item as Group).Key;

            //custom condition is checked.

            if (groupKey < 1005)
                return App.Current.Resources["captionSummaryStyle"] as Style;
        }
        return null;
    }
}
{% endhighlight %}
{% endtabs %}

![Conditional-Styling_img9](Conditional-Styling_images/Conditional-Styling_img9.png)

## CaptionSummaryRow

### Styling caption summary row using Converter

The appearance of caption summary row can be customized conditionally based on summary value by using `converter`, where converter returns the value based on summary value.

{% tabs %}
{% highlight xaml %}
xmlns:utils="using:Syncfusion.UI.Xaml.Utils"

<Page.Resources>
    <local:ColorConverter x:Key="converter"/>
    <Style TargetType="syncfusion:CaptionSummaryRowControl">
        <Setter Property="utils:SetterValueBindingHelper.PropertyBinding">
            <Setter.Value>
                <utils:SetterValueBindingHelper Property="Background" Binding="{Binding Converter={StaticResource converter}}"/>
            </Setter.Value>
        </Setter>
    </Style>
</Page.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid"                     
                       ShowGroupDropArea="True"                
                       ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.CaptionSummaryRow>
        <syncfusion:GridSummaryRow Title="Total Price : {price}" ShowSummaryInRow="True">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="price"
                                        Format="'{Sum:c}'"
                                        MappingName="TotalPrice"
                                        SummaryType="DoubleAggregate" />
                <syncfusion:GridSummaryColumn Name="customerID"
                                        Format="'{Count:c}'"
                                        MappingName="UnitPrice"
                                        SummaryType="CountAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridSummaryRow>
    </syncfusion:SfDataGrid.CaptionSummaryRow>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public class ColorConverter : IValueConverter
{

    public object Convert(object value, Type targetType, object parameter, string language)
    {
            var summaryValue = (value as Group).SummaryDetails.SummaryValues[0];
            var aggregateValue = summaryValue.AggregateValues.ElementAt(0);
            var calculatedValue = aggregateValue.Value;

            //custom condition is checked.

            if ((double)calculatedValue < 1005)
                return new SolidColorBrush(Colors.LightBlue);
            return new SolidColorBrush(Colors.Bisque);
    }

    public object ConvertBack(object value, Type targetType, object parameter, string language)
    {
        throw new NotImplementedException();
    }
}
{% endhighlight %}
{% endtabs %}

Here, caption summary rows are customized based on `TotalPrice` summary value.

![Conditional-Styling_img10](Conditional-Styling_images/Conditional-Styling_img10.png)

### Styling caption summary row using StyleSelector

In another way, appearance of caption summary row can be customized conditionally based on summary value by setting [SfDataGrid.CaptionSummaryRowStyleSelector](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_CaptionSummaryRowStyleSelector) and you can get the container as [CaptionSummaryRowControl](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.CaptionSummaryRowControl.html) in `StyleSelector`.

{% tabs %}
{% highlight xaml %}
<Application.Resources>
    <local:SelectorClass x:Key="styleSelector"/>
    <Style TargetType="syncfusion:CaptionSummaryRowControl" x:Key="captionSummaryStyle">
        <Setter Property="Background" Value="Bisque"/>
    </Style>
</Application.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid"                         
                       ShowGroupDropArea="True"                
                       CaptionSummaryRowStyleSelector="{StaticResource styleSelector}"
                       ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.CaptionSummaryRow>
        <syncfusion:GridSummaryRow Title="Total Price : {price}" ShowSummaryInRow="True">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="price"
                                        Format="'{Sum:c}'"
                                        MappingName="TotalPrice"
                                        SummaryType="DoubleAggregate" />
                <syncfusion:GridSummaryColumn Name="customerID"
                                        Format="'{Count:c}'"
                                        MappingName="UnitPrice"
                                        SummaryType="CountAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridSummaryRow>
    </syncfusion:SfDataGrid.CaptionSummaryRow>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public class SelectorClass : StyleSelector
{

    protected override Style SelectStyleCore(object item, DependencyObject container)
    {
        var row = (item as SpannedDataRow).RowData;
        var groupKey = (int)(row as Group).Key;

        //custom condition is checked.

        if (groupKey < 1005)
            return App.Current.Resources["captionSummaryStyle"] as Style;
        return null;
    }      
}
{% endhighlight %}
{% endtabs %}

Here, caption summary rows are customized where [group key](https://help.syncfusion.com/cr/uwp/Syncfusion.Data.Group.html#Syncfusion_Data_Group_Key) value is less than 1005.

![Conditional-Styling_img11](Conditional-Styling_images/Conditional-Styling_img11.png)

### Styling caption summary row based on grouping level

The appearance of caption summary row can be conditionally customized based on [grouping level](https://help.syncfusion.com/cr/uwp/Syncfusion.Data.NodeEntry.html#Syncfusion_Data_NodeEntry_Level) using `StyleSelector`.

{% tabs %}
{% highlight xaml %}
<Application.Resources>
    <local:SelectorClass x:Key="styleSelector"/>
    <Style x:Key="rowStyle1" TargetType="syncfusion:CaptionSummaryRowControl">
        <Setter Property="Background" Value="LightPink" />
        <Setter Property="FontSize" Value="16" />
    </Style>
    <Style x:Key="rowStyle2" TargetType="syncfusion:CaptionSummaryRowControl">
        <Setter Property="Background" Value="LightSteelBlue" />
        <Setter Property="FontStyle" Value="Italic" />
    </Style>
    <Style x:Key="rowStyle3" TargetType="syncfusion:CaptionSummaryRowControl">
        <Setter Property="Background" Value="LightGreen" />
    </Style>
</Application.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid"                 
                       ShowGroupDropArea="True"                
                       CaptionSummaryRowStyleSelector="{StaticResource styleSelector}"
                       ItemsSource="{Binding Orders}">
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public class SelectorClass : StyleSelector
{
 
    protected override Style SelectStyleCore(object item, DependencyObject container)
    {
        var dataRow = item as DataRowBase;
        var level = dataRow.Level;
 
        //based on group levels, style applied to CaptionSummaryRow
 
        if (level == 1)
            return App.Current.Resources["rowStyle1"] as Style;
 
        else if (level == 2)
            return App.Current.Resources["rowStyle2"] as Style;
 
        else if (level == 3)
            return App.Current.Resources["rowStyle3"] as Style;
        return base.SelectStyle(item, container);
    }
}
{% endhighlight %}
{% endtabs %}

Here, caption summary rows are customized based on `grouping level` (example: level1, level2, level3, etc.).

![Conditional-Styling_img12](Conditional-Styling_images/Conditional-Styling_img12.png)

## GroupSummaryCell

Group summary cells can be customized conditionally by getting particular summary value from [SummaryValues](https://help.syncfusion.com/cr/uwp/Syncfusion.Data.SummaryRecordEntry.html#Syncfusion_Data_SummaryRecordEntry_SummaryValues) through converter or style selector. Likewise, you can also customize the group summary cell based on various properties exposed in [GridSummaryRow](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryRow.html) (example: [ShowSummaryInRow](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryRow.html#Syncfusion_UI_Xaml_Grid_GridSummaryRow_ShowSummaryInRow) property).

### Styling group summary cell using Converter

The appearance of group summary cell can be customized conditionally based on summary value by using `converter`, where converter returns the value based on summary value.

{% tabs %}
{% highlight xaml %}
xmlns:utils="using:Syncfusion.UI.Xaml.Utils"

<Page.Resources>
    <local:ColorConverter x:Key="converter"/>
    <Style TargetType="syncfusion:GridGroupSummaryCell">
        <Setter Property="utils:SetterValueBindingHelper.PropertyBinding">
            <Setter.Value>
                <utils:SetterValueBindingHelper Property="Foreground" Binding="{Binding Converter={StaticResource converter}}"/>
            </Setter.Value>
        </Setter>
    </Style>
</Page.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid" 
                       ShowGroupDropArea="True"
                       ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.GroupSummaryRows>
        <syncfusion:GridSummaryRow ShowSummaryInRow="False">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="price"
                                                Format="'{Sum:c}'"
                                                MappingName="TotalPrice"
                                                SummaryType="DoubleAggregate" />
                <syncfusion:GridSummaryColumn Name="customerID"
                                                Format="'{Count:n}'"
                                                MappingName="CustomerID"
                                                SummaryType="CountAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridSummaryRow>
        <syncfusion:GridSummaryRow Title="TotalPrice:  {totalPrice}" ShowSummaryInRow="True">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="totalPrice"
                                                Format="'{Sum:c}'"
                                                MappingName="TotalPrice"
                                                SummaryType="DoubleAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridSummaryRow>
    </syncfusion:SfDataGrid.GroupSummaryRows>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public class ColorConverter : IValueConverter
{

    public object Convert(object value, Type targetType, object parameter, string language)
    {
        var summaryValue = (value as SummaryRecordEntry).SummaryValues[0];
        var aggregateValue = summaryValue.AggregateValues.ElementAt(0);
        var calculatedValue = aggregateValue.Value;

        //custom condition is checked.

        if ((double)calculatedValue % 2 == 0 )
            return new SolidColorBrush(Colors.Red);
        return new SolidColorBrush(Colors.DarkBlue);
    }

    public object ConvertBack(object value, Type targetType, object parameter, string language)
    {
        throw new NotImplementedException();
    }
}
{% endhighlight %}
{% endtabs %}

Here, group summary cells are customized based on `TotalPrice` summary value.

![Conditional-Styling_img13](Conditional-Styling_images/Conditional-Styling_img13.png)

### Styling group summary cell using StyleSelector

The appearance of group summary cell can be customized conditionally based on summary value by setting [SfDataGrid.GroupSummaryCellStyleSelector](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_GroupSummaryCellStyleSelector) and you can get the container as [GridGroupSummaryCell](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridGroupSummaryCell.html) in `StyleSelector`.

{% tabs %}
{% highlight xaml %}
<Application.Resources>
    <local:SelectorClass x:Key="styleSelector"/>
    <Style TargetType="syncfusion:GridGroupSummaryCell" x:Key="customGroupSummary">
        <Setter Property="Foreground" Value="DarkBlue"/>
    </Style>
    <Style TargetType="syncfusion:GridGroupSummaryCell" x:Key="customGroupSummary1">
        <Setter Property="Foreground" Value="Red"/>
    </Style>
</Application.Resources>
<syncfusion:SfDataGrid x:Name="dataGrid" 
                       ShowGroupDropArea="True"
                       GroupSummaryCellStyleSelector="{StaticResource styleSelector}"
                       ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.GroupSummaryRows>
        <syncfusion:GridSummaryRow ShowSummaryInRow="False">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="price"
                                                Format="'{Sum:c}'"
                                                MappingName="TotalPrice"
                                                SummaryType="DoubleAggregate" />
                <syncfusion:GridSummaryColumn Name="customerID"                                              
                                                Format="'{Count:n0}'"
                                                MappingName="CustomerID"
                                                SummaryType="CountAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridSummaryRow>
        <syncfusion:GridSummaryRow Title="TotalPrice:  {totalPrice}" ShowSummaryInRow="True">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="totalPrice"
                                                Format="'{Sum:c}'"
                                                MappingName="TotalPrice"
                                                SummaryType="DoubleAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridSummaryRow>
    </syncfusion:SfDataGrid.GroupSummaryRows>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public class SelectorClass : StyleSelector
{
 
    protected override Style SelectStyleCore(object item, DependencyObject container)
    {
        var summaryValue = (item as SummaryRecordEntry).SummaryValues[0];
        var aggregateValue = summaryValue.AggregateValues.ElementAt(0);
        var calculatedValue = aggregateValue.Value;
 
        //custom condition is checked.
 
        if ((double)calculatedValue < 0)
            return App.Current.Resources["customGroupSummary1"] as Style;
       return App.Current.Resources["customGroupSummary"] as Style;
    }        
}
{% endhighlight %}
{% endtabs %}

Here, group summary cells are customized based on summary values whether it’s positive or negative.

![Conditional-Styling_img14](Conditional-Styling_images/Conditional-Styling_img14.png)

### Styling group summary cell based on column

The group summary cells can be conditionally customized based on summary column.

{% tabs %}
{% highlight xaml %}
<Application.Resources>
    <local:SelectorClass x:Key="styleSelector"/>
    <Style TargetType="syncfusion:GridGroupSummaryCell" x:Key="customGroupSummary">
        <Setter Property="Foreground" Value="DarkBlue"/>
    </Style>
    <Style TargetType="syncfusion:GridGroupSummaryCell" x:Key="customGroupSummary1">
        <Setter Property="Foreground" Value="Red"/>
    </Style>
</Application.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid" 
                       ShowGroupDropArea="True"
                       GroupSummaryCellStyleSelector="{StaticResource styleSelector}"
                       ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.GroupSummaryRows>
        <syncfusion:GridSummaryRow ShowSummaryInRow="False">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="price"
                                                Format="'{Sum:c}'"
                                                MappingName="TotalPrice"
                                                SummaryType="DoubleAggregate" />
                <syncfusion:GridSummaryColumn Name="customerID"                                              
                                                Format="'{Count:n0}'"
                                                MappingName="CustomerID"
                                                SummaryType="CountAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridSummaryRow>
        <syncfusion:GridSummaryRow Title="TotalPrice:  {totalPrice}" ShowSummaryInRow="True">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="totalPrice"
                                                Format="'{Sum:c}'"
                                                MappingName="TotalPrice"
                                                SummaryType="DoubleAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridSummaryRow>
    </syncfusion:SfDataGrid.GroupSummaryRows>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public class SelectorClass : StyleSelector
{

    protected override Style SelectStyleCore(object item, DependencyObject container)
    {
        var cell = container as GridGroupSummaryCell;

        if (cell.ColumnBase.GridColumn.MappingName == "TotalPrice")
        {
            var summaryValue = (item as SummaryRecordEntry).SummaryValues[0];
            var aggregateValue = summaryValue.AggregateValues.ElementAt(0);
            var calculatedValue = aggregateValue.Value;

            //custom condition is checked.

            if (aggregateValue.Key != "Count" && (double)calculatedValue < 0)
                return App.Current.Resources["customGroupSummary1"] as Style;
        }
        return App.Current.Resources["customGroupSummary"] as Style;
    }
}
{% endhighlight %}
{% endtabs %}

Here, group summary cells are customized based on `TotalPrice` summary column.

![Conditional-Styling_img15](Conditional-Styling_images/Conditional-Styling_img15.png)

## GroupSummaryRow

Group summary row can be customized conditionally by getting particular summary value from [SummaryValues](https://help.syncfusion.com/cr/uwp/Syncfusion.Data.SummaryRecordEntry.html#Syncfusion_Data_SummaryRecordEntry_SummaryValues) through `converter` or `style selector`. Likewise, you can also customize the group summary row based on various properties exposed in [GridSummaryRow](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryRow.html) (example: [ShowSummaryInRow](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryRow.html#Syncfusion_UI_Xaml_Grid_GridSummaryRow_ShowSummaryInRow) property).

### Styling group summary row using Converter

The appearance of group summary row can be customized conditionally based on summary value by using `converter`, where converter returns the value based on summary value.

{% tabs %}
{% highlight xaml %}
xmlns:utils="using:Syncfusion.UI.Xaml.Utils"

<Page.Resources>
    <local:ColorConverter x:Key="converter"/>
    <Style TargetType="syncfusion:GroupSummaryRowControl">
        <Setter Property="utils:SetterValueBindingHelper.PropertyBinding">
            <Setter.Value>
                <utils:SetterValueBindingHelper Property="Background" Binding="{Binding Converter={StaticResource converter}}"/>
            </Setter.Value>
        </Setter>
    </Style>
</Page.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid"        
                       ShowGroupDropArea="True"
                       ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.GroupSummaryRows>
        <syncfusion:GridSummaryRow ShowSummaryInRow="False">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="price"
                                                Format="'{Sum:c}'"
                                                MappingName="TotalPrice"
                                                SummaryType="DoubleAggregate" />
                <syncfusion:GridSummaryColumn Name="customerID"
                                                Format="'{Count:n}'"
                                                MappingName="CustomerID"
                                                SummaryType="CountAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridSummaryRow>
        <syncfusion:GridSummaryRow Title="TotalPrice:  {totalPrice}" ShowSummaryInRow="True">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="totalPrice"
                                                Format="'{Sum:c}'"
                                                MappingName="TotalPrice"
                                                SummaryType="DoubleAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridSummaryRow>
    </syncfusion:SfDataGrid.GroupSummaryRows>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public class ColorConverter : IValueConverter
{
 
    public object Convert(object value, Type targetType, object parameter, string language)
    {
        var summaryValue = (value as SummaryRecordEntry).SummaryValues[0];
        var aggregateValue = summaryValue.AggregateValues.ElementAt(0);
        var calculatedValue = aggregateValue.Value;
 
        //custom condition is checked.
 
        if (aggregateValue.Key != "Count" && (double)calculatedValue % 2 == 0)
            return new SolidColorBrush(Colors.LightBlue);
        return new SolidColorBrush(Colors.Bisque);
    }
 
    public object ConvertBack(object value, Type targetType, object parameter, string language)
    {
        throw new NotImplementedException();
    }
}
{% endhighlight %}
{% endtabs %}

Here, group summary rows are customized based on `TotalPrice` summary value.

![Conditional-Styling_img16](Conditional-Styling_images/Conditional-Styling_img16.png)

### Styling group summary row using StyleSelector

The appearance of group summary row can be customized conditionally based on summary value by setting [SfDataGrid.GroupSummaryRowStyleSelector](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_GroupSummaryRowStyleSelector) and you can get the container as [GridGroupSummaryRowControl](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GroupSummaryRowControl.html) in `StyleSelector`.

{% tabs %}
{% highlight xaml %}
<Application.Resources>
    <local:SelectorClass x:Key="styleSelector"/>
    <Style TargetType="syncfusion:GroupSummaryRowControl" x:Key="customGroupSummary">
        <Setter Property="Background" Value="LightBlue"/>
    </Style>
    <Style TargetType="syncfusion:GroupSummaryRowControl" x:Key="customGroupSummary1">
        <Setter Property="Background" Value="Yellow"/>
    </Style>
</Application.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid"                                           
                       ShowGroupDropArea="True"     
                       GroupSummaryRowStyleSelector="{StaticResource styleSelector}"
                       ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.GroupSummaryRows>
        <syncfusion:GridSummaryRow ShowSummaryInRow="False">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="price"
                                                Format="'{Sum:c}'"
                                                MappingName="TotalPrice"
                                                SummaryType="DoubleAggregate" />
                <syncfusion:GridSummaryColumn Name="customerID"
                                                Format="'{Count:n}'"
                                                MappingName="CustomerID"
                                                SummaryType="CountAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridSummaryRow>
        <syncfusion:GridSummaryRow Title="TotalPrice:  {totalPrice}" ShowSummaryInRow="True">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="totalPrice"
                                                Format="'{Sum:c}'"
                                                MappingName="TotalPrice"
                                                SummaryType="DoubleAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridSummaryRow>
    </syncfusion:SfDataGrid.GroupSummaryRows>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public class SelectorClass : StyleSelector
{

    protected override Style SelectStyleCore(object item, DependencyObject container)
    {
        var summaryRecordEntry = (item as SpannedDataRow).RowData;
        var summaryValue = (summaryRecordEntry as SummaryRecordEntry).SummaryValues[0];
        var aggregateValue = summaryValue.AggregateValues.ElementAt(0);
        var calculatedValue = aggregateValue.Value;

        //custom condition is checked.

        if ((double)calculatedValue % 2 == 0)
            return App.Current.Resources["customGroupSummary1"] as Style;
        return App.Current.Resources["customGroupSummary"] as Style;
    }    
}
{% endhighlight %}
{% endtabs %}

Here, group summary rows are customized based on `TotalPrice` summary value.

![Conditional-Styling_img17](Conditional-Styling_images/Conditional-Styling_img17.png)

## TableSummaryCell

Table summary cells can be customized conditionally by getting particular summary value from [SummaryValues](https://help.syncfusion.com/cr/uwp/Syncfusion.Data.SummaryRecordEntry.html#Syncfusion_Data_SummaryRecordEntry_SummaryValues) through `converter` or `style selector`. Likewise, you can also customize the table summary cell based on various properties exposed in [GridSummaryRow](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryRow.html) (example: [ShowSummaryInRow](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryRow.html#Syncfusion_UI_Xaml_Grid_GridSummaryRow_ShowSummaryInRow) property).

### Styling table summary cell using Converter

The appearance of table summary cell can be customized conditionally based on summary value using `converter`, where converter returns the value based on summary value.

{% tabs %}
{% highlight xaml %}
xmlns:utils="using:Syncfusion.UI.Xaml.Utils"

<Page.Resources>
    <local:ColorConverter x:Key="converter"/>
    <Style TargetType="syncfusion:GridTableSummaryCell">
        <Setter Property="utils:SetterValueBindingHelper.PropertyBinding">
            <Setter.Value>
                <utils:SetterValueBindingHelper Property="Foreground" Binding="{Binding Converter={StaticResource converter}}"/>
            </Setter.Value>
        </Setter>
    </Style>
</Page.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid" 
                       ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.TableSummaryRows>
        <syncfusion:GridTableSummaryRow Position="Top" ShowSummaryInRow="False">
            <syncfusion:GridTableSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="price"
                                              Format="'{Sum:c}'"
                                              MappingName="TotalPrice"
                                              SummaryType="DoubleAggregate" />
                <syncfusion:GridSummaryColumn Name="customerID"
                                              Format="'{Count:n0}'"
                                              MappingName="CustomerID"
                                              SummaryType="CountAggregate" />
            </syncfusion:GridTableSummaryRow.SummaryColumns>
        </syncfusion:GridTableSummaryRow>
        <syncfusion:GridSummaryRow Title="Count : {count}, Total Price :  {totalPrice}" ShowSummaryInRow="True">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="count"
                                              Format="'{Count:n0}'"
                                              MappingName="CustomerID"
                                              SummaryType="DoubleAggregate" />
                <syncfusion:GridSummaryColumn Name="totalPrice"
                                              Format="'{Sum:c}'"
                                              MappingName="TotalPrice"
                                              SummaryType="DoubleAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridSummaryRow>
    </syncfusion:SfDataGrid.TableSummaryRows>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public class ColorConverter : IValueConverter
{

    public object Convert(object value, Type targetType, object parameter, string language)
    {
        var summaryValue = (value as SummaryRecordEntry).SummaryValues[0];
        var aggregateValue = summaryValue.AggregateValues.ElementAt(0);
        var calculatedValue = aggregateValue.Value;

        //custom condition is checked.

        if (aggregateValue.Key != "Count" && (double)calculatedValue < 1500)
            return new SolidColorBrush(Colors.Red);
        return new SolidColorBrush(Colors.LightBlue);
    }

    public object ConvertBack(object value, Type targetType, object parameter, string language)
    {
        throw new NotImplementedException();
    }
}
{% endhighlight %}
{% endtabs %}

Here, table summary cells are customized based on `TotalPrice` summary value.

![Conditional-Styling_img18](Conditional-Styling_images/Conditional-Styling_img18.png)

### Styling table summary cell using StyleSelector

The appearance of table summary cell can be customized conditionally based on summary value by setting [SfDataGrid.TableSummaryCellStyleSelector](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_TableSummaryCellStyleSelector) and you can get the container as [GridTableSummaryCell](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridTableSummaryCell.html) in `StyleSelector`.

{% tabs %}
{% highlight xaml %}
<Application.Resources>
    <local:SelectorClass x:Key="styleSelector"/>
    <Style TargetType="syncfusion:GridTableSummaryCell" x:Key="customTableSummary">
        <Setter Property="Foreground" Value="Red"/>
    </Style>
    <Style TargetType="syncfusion:GridTableSummaryCell" x:Key="customTableSummary1">
        <Setter Property="Foreground" Value="DarkBlue"/>
    </Style>
</Application.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid"   
                       TableSummaryCellStyleSelector="{StaticResource styleSelector}"
                       ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.TableSummaryRows>
        <syncfusion:GridTableSummaryRow Position="Top" ShowSummaryInRow="False">
            <syncfusion:GridTableSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="price"
                                              Format="'{Sum:c}'"
                                              MappingName="TotalPrice"
                                              SummaryType="DoubleAggregate" />
                <syncfusion:GridSummaryColumn Name="customerID"
                                              Format="'{Count:n0}'"
                                              MappingName="CustomerID"
                                              SummaryType="CountAggregate" />
            </syncfusion:GridTableSummaryRow.SummaryColumns>
        </syncfusion:GridTableSummaryRow>
        <syncfusion:GridSummaryRow Title="Total Price :  {totalPrice}" ShowSummaryInRow="True">
                    <syncfusion:GridSummaryRow.SummaryColumns>
                        <syncfusion:GridSummaryColumn Name="totalPrice"
                                                      Format="'{Sum:c}'"
                                                      MappingName="TotalPrice"
                                                      SummaryType="DoubleAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridSummaryRow>
    </syncfusion:SfDataGrid.TableSummaryRows>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public class SelectorClass : StyleSelector
{

    protected override Style SelectStyleCore(object item, DependencyObject container)
    {
        var summaryValue = (item as SummaryRecordEntry).SummaryValues[0];
        var aggregateValue = summaryValue.AggregateValues.ElementAt(0);
        var calculatedValue = aggregateValue.Value;
        var cell = container as GridTableSummaryCell;

        //custom condition is checked.

        if ((double)calculatedValue > 8500 && cell.ColumnBase.GridColumn.MappingName == "TotalPrice")
            return App.Current.Resources["customTableSummary"] as Style;
        return App.Current.Resources["customTableSummary1"] as Style;
    }
}
{% endhighlight %}
{% endtabs %}

Here, table summary cells are customized based on `TotalPrice` summary value.

![Conditional-Styling_img19](Conditional-Styling_images/Conditional-Styling_img19.png)

### Styling table summary cell based on column

The table summary cells can be conditionally customized based on summary column.

{% tabs %}
{% highlight xaml %}
<Application.Resources>
    <local:SelectorClass x:Key="styleSelector"/>
    <Style TargetType="syncfusion:GridTableSummaryCell" x:Key="customTableSummary">
        <Setter Property="Foreground" Value="Red"/>
    </Style>
    <Style TargetType="syncfusion:GridTableSummaryCell" x:Key="customTableSummary1">
        <Setter Property="Foreground" Value="DarkBlue"/>
    </Style>
</Application.Resources>
<syncfusion:SfDataGrid x:Name="dataGrid" 
                       TableSummaryCellStyleSelector="{StaticResource styleSelector}"
                       ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.TableSummaryRows>
        <syncfusion:GridTableSummaryRow Position="Top" ShowSummaryInRow="False">
            <syncfusion:GridTableSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="price"
                                                Format="'{Sum:c}'"
                                                MappingName="TotalPrice"
                                                SummaryType="DoubleAggregate" />
                <syncfusion:GridSummaryColumn Name="customerID"
                                                Format="'{Count:n0}'"
                                                MappingName="CustomerID"
                                                SummaryType="CountAggregate" />
            </syncfusion:GridTableSummaryRow.SummaryColumns>
        </syncfusion:GridTableSummaryRow>
        <syncfusion:GridSummaryRow Title="Total Price :  {totalPrice}" ShowSummaryInRow="True">
                    <syncfusion:GridSummaryRow.SummaryColumns>
                        <syncfusion:GridSummaryColumn Name="totalPrice"
                                                Format="'{Sum:c}'"
                                                MappingName="TotalPrice"
                                                SummaryType="DoubleAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridSummaryRow>
    </syncfusion:SfDataGrid.TableSummaryRows>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public class SelectorClass : StyleSelector
{

    protected override Style SelectStyleCore(object item, DependencyObject container)
    {
        var cell = container as GridTableSummaryCell;

        // column name is checked.

        if (cell.ColumnBase.GridColumn.MappingName == "TotalPrice")
            return App.Current.Resources["customTableSummary"] as Style;
        return App.Current.Resources["customTableSummary1"] as Style;
    }
}
{% endhighlight %}
{% endtabs %}

Here, table summary cells are customized based on `TotalPrice` summary column.

![Conditional-Styling_img20](Conditional-Styling_images/Conditional-Styling_img20.png)

## TableSummaryRow

Table summary rows can be customized conditionally by getting particular summary value from [SummaryValues](https://help.syncfusion.com/cr/uwp/Syncfusion.Data.SummaryRecordEntry.html#Syncfusion_Data_SummaryRecordEntry_SummaryValues) through converter or style selector. Likewise, you can also customize the table summary row based on various properties exposed in [GridSummaryRow](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryRow.html) (example: [ShowSummaryInRow](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryRow.html#Syncfusion_UI_Xaml_Grid_GridSummaryRow_ShowSummaryInRow) property).

### Styling table summary row using Converter

The appearance of table summary row can be customized conditionally based on summary value using `converter`, where converter returns the value based on summary value.

{% tabs %}
{% highlight xaml %}
<Page.Resources>
    <local:ColorConverter x:Key="converter"/>
    <Style TargetType="syncfusion:TableSummaryRowControl">
        <Setter Property="utils:SetterValueBindingHelper.PropertyBinding">
            <Setter.Value>
                <utils:SetterValueBindingHelper Property="Background" Binding="{Binding Converter={StaticResource converter}}"/>
            </Setter.Value>
        </Setter>
    </Style>
</Page.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid" 
                       ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.TableSummaryRows>
        <syncfusion:GridTableSummaryRow Position="Top" ShowSummaryInRow="False">
            <syncfusion:GridTableSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="price"
                                                Format="'{Sum:c}'"
                                                MappingName="TotalPrice"
                                                SummaryType="DoubleAggregate" />
                <syncfusion:GridSummaryColumn Name="customerID"
                                                Format="'{Count:n0}'"
                                                MappingName="CustomerID"
                                                SummaryType="CountAggregate" />
            </syncfusion:GridTableSummaryRow.SummaryColumns>
        </syncfusion:GridTableSummaryRow>
        <syncfusion:GridSummaryRow Title="Count : {count}, Total Price :  {totalPrice}" ShowSummaryInRow="True">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="count"
                                                Format="'{Count:n0}'"
                                                MappingName="CustomerID"
                                                SummaryType="DoubleAggregate" />
                <syncfusion:GridSummaryColumn Name="totalPrice"
                                                Format="'{Sum:c}'"
                                                MappingName="TotalPrice"
                                                SummaryType="DoubleAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridSummaryRow>
    </syncfusion:SfDataGrid.TableSummaryRows>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public class ColorConverter : IValueConverter
{

    public object Convert(object value, Type targetType, object parameter, string language)
    {
        var summaryValue = (value as SummaryRecordEntry).SummaryValues[0];
        var aggregateValue = summaryValue.AggregateValues.ElementAt(0);
        var calculatedValue = aggregateValue.Value;

        //custom condition is checked.

        if (aggregateValue.Key != "Count" && (double)calculatedValue < 1500)
            return new SolidColorBrush(Colors.Bisque);
        return new SolidColorBrush(Colors.LightBlue);
    }

    public object ConvertBack(object value, Type targetType, object parameter, string language)
    {
        throw new NotImplementedException();
    }
}
{% endhighlight %}
{% endtabs %}

Here, table summary rows are customized based on `TotalPrice` summary value.

![Conditional-Styling_img21](Conditional-Styling_images/Conditional-Styling_img21.png)

### Styling table summary row using StyleSelector

The appearance of table summary row can be customized conditionally based on summary value by setting [SfDataGrid.TableSummaryRowStyleSelector](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_TableSummaryRowStyleSelector) and you can get the container as [GridTableSummaryRowControl](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.TableSummaryRowControl.html#) in `StyleSelector`.

{% tabs %}
{% highlight xaml %}
<Application.Resources>
    <local:SelectorClass x:Key="styleSelector"/>
        <Style TargetType="syncfusion:TableSummaryRowControl" x:Key="tableSummaryRowStyle">
            <Setter Property="Background" Value="Bisque"/>
        </Style>
        <Style TargetType="syncfusion:TableSummaryRowControl" x:Key="tableSummaryRowStyle1">
            <Setter Property="Background" Value="LightBlue"/>
        </Style>
    </Application.Resources>
</Application>

<syncfusion:SfDataGrid x:Name="dataGrid" 
                       TableSummaryRowStyleSelector="{StaticResource styleSelector}"
                       ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.TableSummaryRows>
        <syncfusion:GridTableSummaryRow Position="Top" ShowSummaryInRow="False">
            <syncfusion:GridTableSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="price"
                                                Format="'{Sum:c}'"
                                                MappingName="TotalPrice"
                                                SummaryType="DoubleAggregate" />
                <syncfusion:GridSummaryColumn Name="customerID"
                                                Format="'{Count:n0}'"
                                                MappingName="CustomerID"
                                                SummaryType="CountAggregate" />
            </syncfusion:GridTableSummaryRow.SummaryColumns>
        </syncfusion:GridTableSummaryRow>
                <syncfusion:GridSummaryRow Title="Count : {count}, Total Price :  {totalPrice}" ShowSummaryInRow="True">
                    <syncfusion:GridSummaryRow.SummaryColumns>
                        <syncfusion:GridSummaryColumn Name="count"
                                                      Format="'{Count:n0}'"
                                                      MappingName="CustomerID"
                                                      SummaryType="DoubleAggregate" />
                        <syncfusion:GridSummaryColumn Name="totalPrice"
                                                Format="'{Sum:c}'"
                                                MappingName="TotalPrice"
                                                SummaryType="DoubleAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridSummaryRow>
    </syncfusion:SfDataGrid.TableSummaryRows>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public class SelectorClass : StyleSelector
{
 
    protected override Style SelectStyleCore(object item, DependencyObject container)
    {
        var summaryRecordEntry = (item as SpannedDataRow).RowData;
        var summaryValue = (summaryRecordEntry as SummaryRecordEntry).SummaryValues[0];
        var aggregateValue = summaryValue.AggregateValues.ElementAt(0);
        var calculatedValue = aggregateValue.Value;
 
        //custom condition is checked.
 
        if (aggregateValue.Key != "Count" && (double)calculatedValue < 0)
            return App.Current.Resources["tableSummaryRowStyle"] as Style;
       return App.Current.Resources["tableSummaryRowStyle1"] as Style;
    }
}
{% endhighlight %}
{% endtabs %}

Here, table summary rows are customized based on `TotalPrice` summary value.

![Conditional-Styling_img22](Conditional-Styling_images/Conditional-Styling_img22.png)

## Summary Cell alignment based on column

The alignment of summary cells can be customized conditionally based on summary column. Here, horizontal alignment of table summary cells is changed based on column name. Likewise, you can change the horizontal alignment of group, caption summary cells.

{% tabs %}
{% highlight xaml %}
<Application.Resources>
    <local:SelectorClass x:Key="styleSelector"/>
    <Style TargetType="syncfusion:GridTableSummaryCell" x:Key="customTableSummary">
        <Setter Property="HorizontalContentAlignment" Value="Center"/>
    </Style>
    <Style TargetType="syncfusion:GridTableSummaryCell" x:Key="customTableSummary1">
        <Setter Property="HorizontalContentAlignment" Value="Right"/>
    </Style>
</Application.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid" 
                       TableSummaryCellStyleSelector="{StaticResource styleSelector}"
                       ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.TableSummaryRows>
    <syncfusion:GridTableSummaryRow Position="Top" ShowSummaryInRow="False">
        <syncfusion:GridTableSummaryRow.SummaryColumns>
           <syncfusion:GridSummaryColumn Name="price"
                                                Format="'{Sum:c}'"
                                                MappingName="TotalPrice"
                                                SummaryType="DoubleAggregate" />
            <syncfusion:GridSummaryColumn Name="customerID"
                                                Format="'{Count:n0}'"
                                                MappingName="CustomerID"
                                                SummaryType="CountAggregate" />
        </syncfusion:GridTableSummaryRow.SummaryColumns>
    </syncfusion:GridTableSummaryRow>
    <syncfusion:GridSummaryRow Title="Count : {count}, Total Price :  {totalPrice}" ShowSummaryInRow="True">
        <syncfusion:GridSummaryRow.SummaryColumns>
            <syncfusion:GridSummaryColumn Name="count"
                                                Format="'{Count:n0}'"
                                                MappingName="CustomerID"
                                                SummaryType="DoubleAggregate" />
            <syncfusion:GridSummaryColumn Name="totalPrice"
                                                Format="'{Sum:c}'"
                                                MappingName="TotalPrice"
                                                SummaryType="DoubleAggregate" />
        </syncfusion:GridSummaryRow.SummaryColumns>
    </syncfusion:GridSummaryRow>
    </syncfusion:SfDataGrid.TableSummaryRows>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public class SelectorClass : StyleSelector
{
 
    protected override Style SelectStyleCore(object item, DependencyObject container)
    {
        var cell = container as GridTableSummaryCell;
 
        // column name is checked.
 
        if (cell.ColumnBase.GridColumn.MappingName == "TotalPrice")
            return App.Current.Resources["customTableSummary"] as Style;
        return App.Current.Resources["customTableSummary1"] as Style;
    }
}
{% endhighlight %}
{% endtabs %}

Here, horizontal alignment of `TotalPrice` column alone center, other column horizontal alignment are changed into right

![Conditional-Styling_img23](Conditional-Styling_images/Conditional-Styling_img23.png)

## Row Header

The appearance of row header ([GridRowHeaderCell](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridRowHeaderCell.html)) can be customized conditionally by changing its property value based on `cell value` or `data object` by using `converter`, where converter returns the value based on Underlying record.

{% tabs %}
{% highlight xaml %}
xmlns:utils="using:Syncfusion.UI.Xaml.Utils"

<Page.Resources>
    <local:ColorConverter x:Key="converter"/>
        <Style TargetType="syncfusion:GridRowHeaderCell">
            <Setter Property="utils:SetterValueBindingHelper.PropertyBinding">
            <Setter.Value>
                <utils:SetterValueBindingHelper Property="Background" Binding="{Binding Converter={StaticResource converter}}"/>
            </Setter.Value>
        </Setter>
    </Style>
</Page.Resources>
<syncfusion:SfDataGrid x:Name="dataGrid" 
                       ShowRowHeader="True"
                       ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.Columns>
        <syncfusion:GridCheckBoxColumn MappingName="AmountPaid" />
    </syncfusion:SfDataGrid.Columns>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public class ColorConverter : IValueConverter
{

    public object Convert(object value, Type targetType, object parameter, string language)
    {
        var data = value as OrderInfo;

        //custom condition is checked.

        if (data.AmountPaid)
            return new SolidColorBrush(Colors.Green);

        else
            return new SolidColorBrush(Colors.Red);
    }

    public object ConvertBack(object value, Type targetType, object parameter, string language)
    {
        throw new NotImplementedException();
    }
}
{% endhighlight %}
{% endtabs %}

Here, row headers are customized based on `AmountPaid` property of underlying record.

![Conditional-Styling_img24](Conditional-Styling_images/Conditional-Styling_img24.png)

