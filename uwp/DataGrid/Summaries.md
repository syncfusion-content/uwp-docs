---
layout: post
title: Summaries in UWP DataGrid control | Syncfusion
description: Learn here all about Summaries support in Syncfusion UWP DataGrid (SfDataGrid) control and more.
platform: uwp
control: SfDataGrid
documentation: ug
---


# Summaries in UWP DataGrid (SfDataGrid)

SfDataGrid provides support to display the concise information about the data objects using summaries. SfDataGrid provides below three different types of summary rows.

* **Table Summary** – Used to display summary information of table either at top or bottom of SfDataGrid.
 
* **Group Summary** – used to display summary information of data objects in each group.

* **Caption Summary** – used to display summary information in the caption of the group.
 
![Shows the different summaries in UWP DataGrid](Summaries_images/Summaries_img1.png)


![Shows the different summaries in tablet mode of UWP DataGrid](Summaries_images/Summaries_img2.png)

Summary rows are represented by using [GridSummaryRow](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryRow.html) and each `GridSummaryRow` hold summary information of columns in [SummaryColumns](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryRow.html#Syncfusion_UI_Xaml_Grid_GridSummaryRow_SummaryColumns) property. The `SummaryColumns` contains the collection of [GridSummaryColumn](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryColumn.html) which carries the name of column, format and its summary aggregate type.

## Table Summary

The table summary calculates the summary value over all the records. SfDataGrid allows you to add any number of table summary rows in top and bottom of SfDataGrid.

You can add table summary row in SfDataGrid by adding [GridTableSummaryRow](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridTableSummaryRow.html) to [SfDataGrid.TableSummaryRows](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_TableSummaryRows) collection.

### Defining summary for column

You can display summary information in the column by setting [GridSummaryRow.ShowSummaryInRow](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryRow.html#Syncfusion_UI_Xaml_Grid_GridSummaryRow_ShowSummaryInRow) to `false` and defining summary columns. To calculate summary based on column you have to specify the below properties,

1. [GridSummaryColumn.MappingName](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryColumn.html#Syncfusion_UI_Xaml_Grid_GridSummaryColumn_MappingName) – MappingName of the column (Property name of data object) that you want calculate summary.

2. [GridSummaryColumn.SummaryType](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryColumn.html#Syncfusion_UI_Xaml_Grid_GridSummaryColumn_SummaryType) – SfDataGrid provides different built-in summary calculation functions for various types.

3. [GridSummaryColumn.Format](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryColumn.html#Syncfusion_UI_Xaml_Grid_GridSummaryColumn_Format) – Used to define format string for summary based on support function name’s in specified SummaryType.

Refer [Formatting Summary](#formatting-summary) section to know more about how to format summary and [Aggregate Types](#aggregate-types) section to know about different Summary Types.

In the below code snippet, summary is defined for `UnitPrice` and `ProductName` columns.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"                               
                       AutoGenerateColumns="True"
                       ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.TableSummaryRows>
        <syncfusion:GridTableSummaryRow ShowSummaryInRow="False">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="PriceAmount"
                                              Format="'Total UnitPrice : {Sum:c}'"
                                              MappingName="UnitPrice"
                                              SummaryType="DoubleAggregate" />
                <syncfusion:GridSummaryColumn Name="ProductCount"
                                              Format="'Total Product Count : {Count:d}'"
                                              MappingName="ProductName"
                                              SummaryType="CountAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridTableSummaryRow>
    </syncfusion:SfDataGrid.TableSummaryRows>

</syncfusion:SfDataGrid>

{% endhighlight %}
{% endtabs %}


![SummaryColumns in TableSummaryRow for UWP DataGrid](Summaries_images/Summaries_img3.png)

### Displaying summary for Row

You can display summary information in row by setting [GridSummaryRow.ShowSummaryInRow](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryRow.html#Syncfusion_UI_Xaml_Grid_GridSummaryRow_ShowSummaryInRow) to `true` and defining summary columns. You have to set [GridSummaryRow.Title](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryRow.html#Syncfusion_UI_Xaml_Grid_GridSummaryRow_Title) based on [GridSummaryColumn.Name](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryColumn.html#Syncfusion_UI_Xaml_Grid_GridSummaryColumn_Name) property to format summary columns values in row.
 
Refer [Formatting Summary](##formatting-summary) section to know more about how to format summary.
 
{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       AutoGenerateColumns="True"
                       ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.TableSummaryRows>
        <syncfusion:GridTableSummaryRow Title=" Total Price : {PriceAmount} " 
                                        ShowSummaryInRow="True">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="PriceAmount"
                                              Format="'{Sum:c}'"
                                              MappingName="UnitPrice"
                                              SummaryType="DoubleAggregate" />

  <syncfusion:GridSummaryColumn Name="ProductCount"
                                                    Format="'{Count:d}'"
                                                    MappingName="ProductName"
                                                    SummaryType="CountAggregate" />

            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridTableSummaryRow>
    </syncfusion:SfDataGrid.TableSummaryRows>
</syncfusion:SfDataGrid>

{% endhighlight %}
{% highlight c# %}
this.dataGrid.TableSummaryRows.Add(new GridTableSummaryRow()
{
    ShowSummaryInRow = true,
    Title = "Total Price: {PriceAmount} for {ProductCount} Products",
    SummaryColumns = new ObservableCollection<ISummaryColumn>()
    {
        new GridSummaryColumn()
        { 
            Name = "PriceAmount", 
            MappingName="UnitPrice", 
            SummaryType= SummaryType.Int32Aggregate, 
            Format="{Sum:c}"
        }, 

        new GridSummaryColumn()
        {
            Name="ProductCount",
            MappingName="ProductName",
            SummaryType=SummaryType.CountAggregate,
            Format="{Count:d}"
        },
    }
});
{% endhighlight %}
{% endtabs %}


![Table summary row in UWP DataGrid](Summaries_images/Summaries_img4.png)

### Displaying column summary with title

SfDataGrid supports to show column summary and title summary at the same time. You can show column summary along with title by defining the [GridSummaryRow.Title](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryRow.html#Syncfusion_UI_Xaml_Grid_GridSummaryRow_Title)  and [GridSummaryRow.TitleColumnCount](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryRow.html#Syncfusion_UI_Xaml_Grid_GridSummaryRow_TitleColumnCount) property along with defining summary columns. Showing column summary along with title can be only supported if [GridSummaryRow.ShowSummaryInRow](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryRow.html#Syncfusion_UI_Xaml_Grid_GridSummaryRow_ShowSummaryInRow) is disabled.

Refer [Defining summary for column](#defining-summary-for-column) section to know more about how to define summary columns.

In the below code snippet, `GridSummaryRow.TitleColumnCount` is set as 2 and [GridSummaryRow.Title](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryRow.html#Syncfusion_UI_Xaml_Grid_GridSummaryRow_Title) is defined along with summary columns.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       AutoGenerateColumns="True"
                       ItemsSource="{Binding Orders}"
                       ShowGroupDropArea="True">
    <syncfusion:SfDataGrid.TableSummaryRows>
       <syncfusion:GridTableSummaryRow ShowSummaryInRow="False" TitleColumnCount="2" Position="Top"
                                       Title="Total Price : {PriceAmount} for {ProductCount} products">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="CustomerName" 
                                              Format=" {Count:d}"
                                              MappingName="CustomerName" 
                                              SummaryType="CountAggregate" />
                <syncfusion:GridSummaryColumn Name="PriceAmount"
                                              Format=" {Sum:c}"
                                              MappingName="UnitPrice"
                                              SummaryType="DoubleAggregate" />
                <syncfusion:GridSummaryColumn Name="ProductCount"
                                              Format=" {Count:d}"
                                              MappingName="ProductName"
                                              SummaryType="CountAggregate" />                        
            </syncfusion:GridSummaryRow.SummaryColumns>
       </syncfusion:GridTableSummaryRow>
    </syncfusion:SfDataGrid.TableSummaryRows>    
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
this.dataGrid.TableSummaryRows.Add(new GridTableSummaryRow()
{
    ShowSummaryInRow = false,
    Position = TableSummaryRowPosition.Top,
    Title = "Total Price : {PriceAmount} for {ProductCount} products",
    TitleColumnCount = 2,
    SummaryColumns = new ObservableCollection<ISummaryColumn>()
    {
        new GridSummaryColumn()
        {
            Name="CustomerName",
            Format="{Count:d}",
            MappingName="CustomerName",
            SummaryType=SummaryType.CountAggregate
        },
		
        new GridSummaryColumn()
        {
            Name = "PriceAmount",
            MappingName="UnitPrice",
            SummaryType= SummaryType.DoubleAggregate,
            Format="{Sum:c}"
        },
		
        new GridSummaryColumn()
        {
            Name="ProductCount",
            MappingName="ProductName",
            SummaryType=SummaryType.CountAggregate,
            Format="{Count:d}"
        }        
    }
});

{% endhighlight %}
{% endtabs %}

The following screenshot illustrates displaying summary columns with title at same time for `TableSummaryRow`.

![SummaryColumns with title in TableSummaryRow for UWP DataGrid](Summaries_images/Summaries_img21.png)

#### Limitations

The following are the limitations of displaying column summary along with title at same time for `TableSummaryRow`:

* If [FrozenColumnCount](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_FrozenColumnCount) is defined lesser than `GridSummaryRow.TitleColumnCount`, the title summary will be spanned to [FrozenColumnCount](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_FrozenColumnCount) range, since spanned range and frozen range cannot be vary.
* Summary columns defined in the `GridSummaryRow.TitleColumnCount` range will not be shown.

### Positioning TableSummaryRow

You can position the table summary either at top or bottom of SfDataGrid by setting [GridTableSummaryRow.Position](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridTableSummaryRow.html#Syncfusion_UI_Xaml_Grid_GridTableSummaryRow_Position) property.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                        AutoGenerateColumns="True"
                        ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.TableSummaryRows>
        <syncfusion:GridTableSummaryRow Position="Top" ShowSummaryInRow="False">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="PriceAmount"
                                              Format="'{Sum:c}'"
                                              MappingName="UnitPrice"
                                              SummaryType="DoubleAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridTableSummaryRow>
        <syncfusion:GridTableSummaryRow Title=" Total Product count: {ProductCount}"
                                        Position="Bottom"
                                        ShowSummaryInRow="True">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="ProductCount"
                                                Format="'{Count:d}'"
                                                MappingName="ProductName"
                                                SummaryType="CountAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridTableSummaryRow>
    </syncfusion:SfDataGrid.TableSummaryRows>

</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
GridTableSummaryRow tablesummaryrow1 = new GridTableSummaryRow() 
{ 
    ShowSummaryInRow = false, 
    Position = TableSummaryRowPosition.Top,
    SummaryColumns = new ObservableCollection<ISummaryColumn>()
    {
    
        new GridSummaryColumn()
        {
            Name="PriceAmount",
            Format="{Sum:c}",
            MappingName="UnitPrice",
            SummaryType=SummaryType.DoubleAggregate 

        }
    }
};

GridTableSummaryRow tablesummaryrow2 = new GridTableSummaryRow()
{
    ShowSummaryInRow = true,
    Position = TableSummaryRowPosition.Bottom,
    Title="Total Product count: {ProductCount}",
    SummaryColumns = new ObservableCollection<ISummaryColumn>()
    {
   
        new GridSummaryColumn()
        {
            Name="ProductCount",
            Format="{Count:d}",
            MappingName="ProductName",
            SummaryType=SummaryType.CountAggregate 
        }
    }
};

this.dataGrid.TableSummaryRows.Add(tablesummaryrow1);
this.dataGrid.TableSummaryRows.Add(tablesummaryrow2);
{% endhighlight %}
{% endtabs %}


![Different positions of table summary row in UWP DataGrid](Summaries_images/Summaries_img5.png)

## Group Summary

Group summary values calculated based on the records in the group and the summary information will be displayed at the bottom of each group. You can view the group summary row by expanding the corresponding group header. SfDataGrid allows you to add any number of group summary rows.

You can add the group summary rows in SfDataGrid by adding the `GridSummaryRow` to [SfDataGrid.GroupSummaryRows](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_GroupSummaryRows) collection.

### Defining summary for column

You can display summary information in the column by setting [GridSummaryRow.ShowSummaryInRow](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryRow.html#Syncfusion_UI_Xaml_Grid_GridSummaryRow_ShowSummaryInRow) to `false` and defining summary columns. To calculate summary based on column you have to specify the below properties,

1. [GridSummaryColumn.MappingName](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryColumn.html#Syncfusion_UI_Xaml_Grid_GridSummaryColumn_MappingName) – MappingName of the column (Property name of data object) that you want calculate summary.

2. [GridSummaryColumn.SummaryType](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryColumn.html#Syncfusion_UI_Xaml_Grid_GridSummaryColumn_SummaryType) –  SfDataGrid provides different built-in summary calculation functions for various types.

3. [GridSummaryColumn.Format](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryColumn.html#Syncfusion_UI_Xaml_Grid_GridSummaryColumn_Format) –  Used to define format string for summary based on support function name’s in specified SummaryType.

Refer [Formatting Summary](##formatting-summary) section to know more about how to format summary and [Aggregate Types](#aggregate-types) section to know about different Summary Type’s.

In the below code snippet, summary is defined for `UnitPrice` and `ProductName` columns.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"                             
                       AutoGenerateColumns="True"
                       ItemsSource="{Binding Orders}"
                       ShowGroupDropArea="True">
    <syncfusion:SfDataGrid.GroupSummaryRows>
        <syncfusion:GridSummaryRow ShowSummaryInRow="False">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="PriceAmount"
                                              Format="'Amount - {Sum:c}'"
                                              MappingName="UnitPrice"
                                              SummaryType="DoubleAggregate" />
                <syncfusion:GridSummaryColumn Name="ProductCount"
                                              Format="'Count - {Count:d}'"
                                              MappingName="ProductName"
                                              SummaryType="CountAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridSummaryRow>
    </syncfusion:SfDataGrid.GroupSummaryRows>
    
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
this.dataGrid.GroupSummaryRows.Add(new GridSummaryRow()
{
    ShowSummaryInRow = false,    
    SummaryColumns = new ObservableCollection<ISummaryColumn>()
    {
 
        new GridSummaryColumn()
        { 
            Name = "PriceAmount", 
            MappingName="UnitPrice", 
            SummaryType= SummaryType.Int32Aggregate, 
            Format="Amount - {Sum:c}"
        }, 
 
        new GridSummaryColumn()
        {
            Name="ProductCount",
            MappingName="ProductName",
            SummaryType=SummaryType.CountAggregate,
            Format="Count - {Count:d}"
        },
    }
});
{% endhighlight %}
{% endtabs %}

![SummaryColumns in group summary row for UWP DataGrid](Summaries_images/Summaries_img6.png)

### Displaying summary for Row

You can display summary information in row by setting [GridSummaryRow.ShowSummaryInRow](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryRow.html#Syncfusion_UI_Xaml_Grid_GridSummaryRow_ShowSummaryInRow) to `true` and defining summary columns. You have to define [GridSummaryRow.Title](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryRow.html#Syncfusion_UI_Xaml_Grid_GridSummaryRow_Title) based on [GridSummaryColumn.Name](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryColumn.html#Syncfusion_UI_Xaml_Grid_GridSummaryColumn_Name) property to format summary columns values in row.
 
Refer [Formatting Summary](#formatting-summary) section to know more about how to format summary.
 
{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       AutoGenerateColumns="True"
                       ItemsSource="{Binding Orders}"
                       ShowGroupDropArea="True">
    <syncfusion:SfDataGrid.GroupSummaryRows>
        <syncfusion:GridSummaryRow Title="Total Price : {PriceAmount} for {ProductCount} products" ShowSummaryInRow="True">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="PriceAmount"
                                              Format="'{Sum:c}'"
                                              MappingName="UnitPrice"
                                              SummaryType="DoubleAggregate" />
                <syncfusion:GridSummaryColumn Name="ProductCount"
                                              Format="'{Count:d}'"
                                              MappingName="ProductName"
                                              SummaryType="CountAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridSummaryRow>
    </syncfusion:SfDataGrid.GroupSummaryRows>

</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
this.dataGrid.GroupSummaryRows.Add(new GridSummaryRow()
{
    Title = "Total Price : {PriceAmount} for {ProductCount} products",
    ShowSummaryInRow = true,
    SummaryColumns = new ObservableCollection<ISummaryColumn>()
    {
        new GridSummaryColumn()
        { 
            Name = "PriceAmount", 
            MappingName="UnitPrice", 
            SummaryType= SummaryType.Int32Aggregate, 
            Format="{Sum:c}"
        }, 

        new GridSummaryColumn()
        {
            Name="ProductCount",
            MappingName="ProductName",
            SummaryType=SummaryType.CountAggregate,
            Format="{Count:d}"
        },
    }
});

{% endhighlight %}
{% endtabs %}


![Group summaries in a row for UWP DataGrid](Summaries_images/Summaries_img7.png)

### Displaying column summary with title

SfDataGrid supports to show column summary and title summary at the same time. You can show column summary along with title by defining the [GridSummaryRow.Title](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryRow.html#Syncfusion_UI_Xaml_Grid_GridSummaryRow_Title)  and [GridSummaryRow.TitleColumnCount](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryRow.html#Syncfusion_UI_Xaml_Grid_GridSummaryRow_TitleColumnCount) property along with defining summary columns. Showing column summary along with title can be only supported if [GridSummaryRow.ShowSummaryInRow](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryRow.html#Syncfusion_UI_Xaml_Grid_GridSummaryRow_ShowSummaryInRow) is disabled.

Refer [Defining summary for column](#defining-summary-for-column-1) section to know more about how to define summary columns.

In the below code snippet, `GridSummaryRow.TitleColumnCount` is set as 2 and [GridSummaryRow.Title](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryRow.html#Syncfusion_UI_Xaml_Grid_GridSummaryRow_Title) is defined along with summary columns.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"                             
                       AutoGenerateColumns="True"
                       ItemsSource="{Binding Orders}"
                       ShowGroupDropArea="True">
    <syncfusion:SfDataGrid.GroupSummaryRows>
        <syncfusion:GridSummaryRow ShowSummaryInRow="False" TitleColumnCount="2" 
                                   Title="Total Price: {PriceAmount} for {ProductCount} Products" >
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="CustomerName" 
                                              Format=" {Count:d}"
                                              MappingName="CustomerName" 
                                              SummaryType="CountAggregate" />
                <syncfusion:GridSummaryColumn Name="PriceAmount"
                                              Format=" {Sum:c}"
                                              MappingName="UnitPrice"
                                              SummaryType="DoubleAggregate" />
                <syncfusion:GridSummaryColumn Name="ProductCount"
                                              Format=" {Count:d}"
                                              MappingName="ProductName"
                                              SummaryType="CountAggregate" />                        
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridSummaryRow>
    </syncfusion:SfDataGrid.GroupSummaryRows>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
this.dataGrid.GroupSummaryRows.Add(new GridSummaryRow()
{
    ShowSummaryInRow = false,
    Title = "Total Price: {PriceAmount} for {ProductCount} Products",
    TitleColumnCount = 2,
    SummaryColumns = new ObservableCollection<ISummaryColumn>()
    {
        new GridSummaryColumn()
        {
            Name="CustomerName",
            Format="{Count:d}",
            MappingName="CustomerName",
            SummaryType=SummaryType.CountAggregate
        },
		
        new GridSummaryColumn()
        {
            Name = "PriceAmount",
            MappingName="UnitPrice",
            SummaryType= SummaryType.DoubleAggregate,
            Format="{Sum:c}"
        },
		
        new GridSummaryColumn()
        {
            Name="ProductCount",
            MappingName="ProductName",
            SummaryType=SummaryType.CountAggregate,
            Format="{Count:d}"
        }        
    }
});

{% endhighlight %}
{% endtabs %}

The following screenshot illustrates displaying summary columns with title at same time for `GroupSummaryRow`.

![SummaryColumns with title in group summary row for UWP DataGrid](Summaries_images/Summaries_img20.png)

#### Limitations

The following are the limitations of displaying column summary along with title at same time for `GroupSummaryRow`:

* If [FrozenColumnCount](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_FrozenColumnCount) is defined lesser than `GridSummaryRow.TitleColumnCount`, the title summary will be spanned to [FrozenColumnCount](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_FrozenColumnCount) range, since spanned range and frozen range cannot be vary.
* Summary columns defined in the `GridSummaryRow.TitleColumnCount` range will not be shown.

## Caption Summaries

SfDataGrid provides built-in support for caption summaries. The caption summary value calculated based on the records in a group and the summary information will be displayed in the caption of group.

Below screen shot shows the built-in caption summary of Group.

![Built-in caption summary in UWP DataGrid](Summaries_images/Summaries_img8.png)

### Formatting built-in caption summary

By default, the summary value displayed in CaptionSummaryRow based on [SfDataGrid.GroupCaptionTextFormat](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_GroupCaptionTextFormat) property. The default group caption format is `{ColumnName}: {Key} - {ItemsCount} Items`.
 
* **ColumnName** -   Displays the name of the column currently grouped.

* **Key**   -   Displays the key value of group.

* **ItemsCount** -   Displays the number of items in group.

You can change group caption format to display column name and count alone by setting `GroupCaptionTextFormat` as below,

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid  x:Name="dataGrid"
                        AllowGrouping="True"
                        AutoGenerateColumns="True"
                        GroupCaptionTextFormat=" ColumnName: {Key} "
                        ItemsSource="{Binding Orders}"
                        ShowGroupDropArea="True"/>
{% endhighlight %}
{% endtabs %}


![Caption summary formatting using GroupCaptionTextFormat in UWP DataGrid](Summaries_images/Summaries_img9.png)


### Defining summary for column

You can display summary information in the column by setting [GridSummaryRow.ShowSummaryInRow](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryRow.html#Syncfusion_UI_Xaml_Grid_GridSummaryRow_ShowSummaryInRow) to `false` and defining summary columns. To calculate summary based on column you have to specify the below properties,

1. [GridSummaryColumn.MappingName](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryColumn.html#Syncfusion_UI_Xaml_Grid_GridSummaryColumn_MappingName) –  MappingName of the column (Property name of data object) that you want calculate summary.

2. [GridSummaryColumn.SummaryType](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryColumn.html#Syncfusion_UI_Xaml_Grid_GridSummaryColumn_SummaryType) –  SfDataGrid provides different built-in summary calculation functions for various types.

3. [GridSummaryColumn.Format](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryColumn.html#Syncfusion_UI_Xaml_Grid_GridSummaryColumn_Format) –  Used to define format string for summary based on support function name’s in specified SummaryType.

Refer [Formatting Summary](#formatting-summary) section to know more about how to format summary and [Aggregate Types](#aggregate-types) section to know about different Summary Type’s.

In the below code snippet, summary is defined for `UnitPrice` and `ProductName` columns.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       AutoGenerateColumns="True"
                       ItemsSource="{Binding Orders}"
                       ShowGroupDropArea="True">
            
    <syncfusion:SfDataGrid.CaptionSummaryRow>
        <syncfusion:GridSummaryRow ShowSummaryInRow="False">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="PriceAmount"
                                                Format="'{Sum:c}'"
                                                MappingName="UnitPrice"
                                                SummaryType="DoubleAggregate" />
                <syncfusion:GridSummaryColumn Name="ProductCount"
                                                Format="'{Count:d}'"
                                                MappingName="ProductName"
                                                SummaryType="CountAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridSummaryRow>
    </syncfusion:SfDataGrid.CaptionSummaryRow>
    
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
this.dataGrid.CaptionSummaryRow = new GridSummaryRow()
{
    ShowSummaryInRow = false,                
    SummaryColumns = new ObservableCollection<ISummaryColumn>()
    {
        new GridSummaryColumn()
        { 
            Name = "PriceAmount", 
            MappingName="UnitPrice", 
            SummaryType= SummaryType.Int32Aggregate, 
            Format="{Sum:c}"
        }, 
        new GridSummaryColumn()
        {
            Name="ProductCount",
            MappingName="ProductName",
            SummaryType=SummaryType.CountAggregate,
            Format="{Count:d}"
        },
    }
};
{% endhighlight %}
{% endtabs %}


![Caption summary in columns for UWP DataGrid](Summaries_images/Summaries_img10.png)

### Displaying summary for Row

You can display summary information in row by setting [GridSummaryRow.ShowSummaryInRow](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryRow.html#Syncfusion_UI_Xaml_Grid_GridSummaryRow_ShowSummaryInRow) to `true` and defining summary columns. You have to define [GridSummaryRow.Title](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryRow.html#Syncfusion_UI_Xaml_Grid_GridSummaryRow_Title) based on [GridSummaryColumn.Name](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryColumn.html#Syncfusion_UI_Xaml_Grid_GridSummaryColumn_Name) property to format summary columns values in row.
 
Refer [Formatting Summary](#formatting-summary) section to know more about how to format summary.
 
{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       AutoGenerateColumns="True"
                       ItemsSource="{Binding Orders}"
                       ShowGroupDropArea="True">
    <syncfusion:SfDataGrid.CaptionSummaryRow>
        <syncfusion:GridSummaryRow Title="Total Price : {PriceAmount} for {ProductCount} Products" ShowSummaryInRow="True">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="PriceAmount"
                                              Format="'{Sum:c}'"
                                              MappingName="UnitPrice"
                                              SummaryType="DoubleAggregate" />
                <syncfusion:GridSummaryColumn Name="ProductCount"
                                              Format="'{Count:d}'"
                                              MappingName="ProductName"
                                              SummaryType="CountAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridSummaryRow>
    </syncfusion:SfDataGrid.CaptionSummaryRow>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
this.dataGrid.CaptionSummaryRow = new GridSummaryRow()
{
    ShowSummaryInRow = true,
    Title = "Total Price: {PriceAmount} for {ProductCount} Products",
    SummaryColumns = new ObservableCollection<ISummaryColumn>()
    {
  
        new GridSummaryColumn()
        { 
            Name = "PriceAmount", 
            MappingName="UnitPrice", 
            SummaryType= SummaryType.Int32Aggregate, 
            Format="{Sum:c}"
        }, 
  
        new GridSummaryColumn()
        {
            Name="ProductCount",
            MappingName="ProductName",
            SummaryType=SummaryType.CountAggregate,
            Format="{Count:d}"
        },
    }
};

{% endhighlight %}
{% endtabs %}


![Caption summaries in rows for UWP DataGrid](Summaries_images/Summaries_img11.png)

### Displaying column summary with title

SfDataGrid supports to show column summary and title summary at the same time. You can show column summary along with title by defining the [GridSummaryRow.Title](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryRow.html#Syncfusion_UI_Xaml_Grid_GridSummaryRow_Title)  and [GridSummaryRow.TitleColumnCount](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryRow.html#Syncfusion_UI_Xaml_Grid_GridSummaryRow_TitleColumnCount) property along with defining summary columns. Showing column summary along with title can be only supported if [GridSummaryRow.ShowSummaryInRow](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryRow.html#Syncfusion_UI_Xaml_Grid_GridSummaryRow_ShowSummaryInRow) is disabled.

Refer [Defining summary for column](#defining-summary-for-column-2) section to know more about how to define summary columns.

In the below code snippet, `GridSummaryRow.TitleColumnCount` is set as 2 and [GridSummaryRow.Title](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryRow.html#Syncfusion_UI_Xaml_Grid_GridSummaryRow_Title) is defined along with summary columns.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       AutoGenerateColumns="True"
                       ItemsSource="{Binding Orders}"
                       ShowGroupDropArea="True">
    <syncfusion:SfDataGrid.CaptionSummaryRow>
        <syncfusion:GridSummaryRow  ShowSummaryInRow="False" TitleColumnCount="2" 
		                            Title=" {ColumnName} : {Key} - {ItemsCount} Items ">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="CustomerName" 
                                              Format=" {Count:d}"
                                              MappingName="CustomerName" 
                                              SummaryType="CountAggregate" />
                <syncfusion:GridSummaryColumn Name="PriceAmount"
                                              Format=" {Sum:c}"
                                              MappingName="UnitPrice"
                                              SummaryType="DoubleAggregate" />
                <syncfusion:GridSummaryColumn Name="ProductCount"
                                              Format=" {Count:d}"
                                              MappingName="ProductName"
                                              SummaryType="CountAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridSummaryRow>
    </syncfusion:SfDataGrid.CaptionSummaryRow>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
this.dataGrid.CaptionSummaryRow = new GridSummaryRow()
{
    ShowSummaryInRow = false,
    Title = "{ColumnName} : {Key} - {ItemsCount} Items",
    TitleColumnCount = 2,
    SummaryColumns = new ObservableCollection<ISummaryColumn>()
    {
        new GridSummaryColumn()
        {
            Name="CustomerName",
            Format="{Count:d}",
            MappingName="CustomerName",
            SummaryType=SummaryType.CountAggregate
        },

        new GridSummaryColumn()
        {
            Name = "PriceAmount",
            MappingName="UnitPrice",
            SummaryType= SummaryType.DoubleAggregate,
            Format="{Sum:c}"
        },

        new GridSummaryColumn()
        {
            Name="ProductCount",
            MappingName="ProductName",
            SummaryType=SummaryType.CountAggregate,
            Format="{Count:d}"
        }
    }
};

{% endhighlight %}
{% endtabs %}

The following screenshot illustrates displaying summary columns with title at same time for `CaptionSummaryRow`.

![Caption summary columns with title in UWP DataGrid](Summaries_images/Summaries_img22.png)

#### Limitations

The following are the limitations of displaying column summary along with title at same time for `CaptionSummaryRow`:

* If [FrozenColumnCount](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_FrozenColumnCount) is defined lesser than `GridSummaryRow.TitleColumnCount`, the title summary will be spanned to [FrozenColumnCount](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_FrozenColumnCount) range, since spanned range and frozen range cannot be vary.
* Summary columns defined in the `GridSummaryRow.TitleColumnCount` range will not be shown.

## Formatting summary

In the below sections formatting is explained using TableSummary. In the same way, you can format group and caption summaries also.

### Defining Summary Function

In the below code snippet `Format` property is defined to display sum of `UnitPrice` by specifying the function name inside curly braces.
  
N> `DoubleAggregate` is used as SummaryType which has Count, Max, Min, Average and Sum functions.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       AutoGenerateColumns="True"
                       ItemsSource="{Binding Orders}"
                       ShowGroupDropArea="True">
    <syncfusion:SfDataGrid.TableSummaryRows>
        <syncfusion:GridTableSummaryRow ShowSummaryInRow="False">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="PriceAmount"
                                              Format="'{Sum}'"
                                              MappingName="UnitPrice"
                                              SummaryType="DoubleAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridTableSummaryRow>
    </syncfusion:SfDataGrid.TableSummaryRows>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% endtabs %}


![Shows the sum function in UWP DataGrid](Summaries_images/Summaries_img12.png)

### Formatting Summary Value

You can format the summary value by setting the appropriate format after the aggregate function followed by colon (:) in [GridSummaryColumn.Format](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryColumn.html#Syncfusion_UI_Xaml_Grid_GridSummaryColumn_Format) property.
 
In the below code snippet `UnitPrice` column summary is formatted using `c` format specifier. Refer [here](https://msdn.microsoft.com/en-us/library/dwhawy9k.aspx?f=255&MSPPError=-2147217396) to know about how to set different format.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       AutoGenerateColumns="True"
                       ItemsSource="{Binding Orders}"
                       ShowGroupDropArea="True">
                       
    <syncfusion:SfDataGrid.TableSummaryRows>
        <syncfusion:GridTableSummaryRow ShowSummaryInRow="False">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="PriceAmount"
                                              Format="'{Sum:c}'"
                                              MappingName="UnitPrice"
                                              SummaryType="DoubleAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridTableSummaryRow>
    </syncfusion:SfDataGrid.TableSummaryRows>
    
</syncfusion:SfDataGrid>
{% endhighlight %}
{% endtabs %}


![Summary value formatting in UWP DataGrid](Summaries_images/Summaries_img13.png)

### Displaying additional Content in Summary

You can append additional content with summary value using [GridSummaryColumn.Format](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryColumn.html#Syncfusion_UI_Xaml_Grid_GridSummaryColumn_Format) property.

In the below code snippet `Total UnitPrice: ` text is appended before summary value.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"                               
                       AutoGenerateColumns="True"
                       ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.TableSummaryRows>
        <syncfusion:GridTableSummaryRow ShowSummaryInRow="False">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="PriceAmount"
                                              Format="'Total UnitPrice : {Sum:c}'"
                                              MappingName="UnitPrice"
                                              SummaryType="DoubleAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridTableSummaryRow>
    </syncfusion:SfDataGrid.TableSummaryRows>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% endtabs %}


![Additional content in summary for UWP DataGrid](Summaries_images/Summaries_img14.png)

### Formatting Summary for Row using Title Property

You can format the summary value for row using [GridSummaryRow.Title](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryRow.html#Syncfusion_UI_Xaml_Grid_GridSummaryRow_Title) when ShowSummaryInRow set to `true`.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       AutoGenerateColumns="True"
                       ItemsSource="{Binding Orders}">
                       
    <syncfusion:SfDataGrid.TableSummaryRows>
        <syncfusion:GridTableSummaryRow Title=" Total Price : {PriceAmount} "  
                                        ShowSummaryInRow="True">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="PriceAmount"
                                              Format="'{Sum:c}'"
                                              MappingName="UnitPrice"
                                              SummaryType="DoubleAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridTableSummaryRow>
    </syncfusion:SfDataGrid.TableSummaryRows>
    
</syncfusion:SfDataGrid>
{% endhighlight %}
{% endtabs %}

![Summary value formatting using Title property in UWP DataGrid](Summaries_images/Summaries_img15.png)

## Aggregate Types

You can specify the different summary aggregate types by using [GridSummaryColumn.SummaryType](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryColumn.html#Syncfusion_UI_Xaml_Grid_GridSummaryColumn_SummaryType) property and use the built-in function in [GridSummaryColumn.Format](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryColumn.html#Syncfusion_UI_Xaml_Grid_GridSummaryColumn_Format).

The following are the list of predefined aggregate types and its built-in functions.

<table>
<tr>
<th>
Aggregate Type
</th>
<th>
Built-in function
</th>
</tr>
<tr>
<td>
CountAggregate
</td>
<td>
Count
</td>
</tr>
<tr>
<td>
Int32Aggregate
</td>
<td>
Count, Max, Min, Average and Sum
</td>
</tr>
<tr>
<td>
DoubleAggregate
</td>
<td>
Count, Max, Min, Average and Sum
</td>
</tr>
<tr>
<td>
Custom
</td>
<td>
Used for custom summaries
</td>
</tr>
</table>

## Calculate summary for selected rows

SfDataGrid calculates the summaries for all records by default. You can calculate the summaries for selected records by using the `SfDataGrid.SummaryCalculationUnit` or `GridSummaryRow.CalculationUnit` property.
This is applicable for all type of summary rows such as table, caption and group summary.

In the below code snippet, the summaries for selected records are calculated for the top positioned `TableSummaryRow` and the summaries for all records are calculated for the bottom positioned `TableSummaryRow`.

{% tabs %}
{% highlight xaml %}
  <syncfusion:SfDataGrid x:Name="sfDataGrid"
                       AutoGenerateColumns="True"
                       SelectionMode="Multiple"
                       ItemsSource="{Binding Orders}" >
    <syncfusion:SfDataGrid.TableSummaryRows>
        <syncfusion:GridTableSummaryRow ShowSummaryInRow="True" Title="Total Price for all records:{UnitPrice}">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="UnitPrice"
                                      Format="'{Sum:c}'"
                                      MappingName="UnitPrice"
                                      SummaryType="DoubleAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridTableSummaryRow>
        <syncfusion:GridTableSummaryRow ShowSummaryInRow="True" Title="Total price for selected records: {UnitPrice}" CalculationUnit="SelectedRows" Position="Top">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="UnitPrice"
                                      Format="'{Sum:c}'"
                                      MappingName="UnitPrice"
                                      SummaryType="DoubleAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridTableSummaryRow>
    </syncfusion:SfDataGrid.TableSummaryRows>
</syncfusion:SfDataGrid>


{% endhighlight %}
{% highlight c# %}

GridTableSummaryRow tableSummaryRow1 = new GridTableSummaryRow()
{
    ShowSummaryInRow = true,
    Position = TableSummaryRowPosition.Top,
    CalculationUnit = SummaryCalculationUnit.SelectedRows,
    Title = "Total price for selected records: {PriceAmount}",
    SummaryColumns = new ObservableCollection<ISummaryColumn>()
    {
        new GridSummaryColumn()
        {
           Name="PriceAmount",
           Format="{Sum:c}",
           MappingName="UnitPrice",
           SummaryType=SummaryType.DoubleAggregate
        }
    }
};

GridTableSummaryRow tableSummaryRow2 = new GridTableSummaryRow()
{
    ShowSummaryInRow = true,
    Position = TableSummaryRowPosition.Bottom,
    Title = "Total price for all records: {UnitPrice}",
    SummaryColumns = new ObservableCollection<ISummaryColumn>()
    {
        new GridSummaryColumn()
        {
            Name="UnitPrice",
            Format="{Sum:c}",
            MappingName="UnitPrice",
            SummaryType=SummaryType.DoubleAggregate
        }
    }
};

this.sfDataGrid.TableSummaryRows.Add(tableSummaryRow1);
this.sfDataGrid.TableSummaryRows.Add(tableSummaryRow2);

{% endhighlight %}
{% endtabs %}

![Calculate summaries for selected records in WPF SfDataGrid](Summaries_images/Summaries_img19.png)

N> The `GridSummaryRow.CalculationUnit` takes higher priority than the `SfDataGrid.SummaryCalculationUnit`.

### Limitation

`SummaryCalculationUnit.SelectedRows` or `SummaryCalculationUnit.Mixed` will not be considered for cell selection.


## Custom summaries

SfDataGrid allows you to implement your own aggregate functions, when the built-in aggregate functions don’t meet your requirement.

You can calculate the summary values based on custom logic using [GridSummaryColumn.CustomAggregate](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryColumn.html#Syncfusion_UI_Xaml_Grid_GridSummaryColumn_CustomAggregate) property.

### Implementing custom aggregate

1.Create custom aggregate class by deriving from [ISummaryAggregate](https://help.syncfusion.com/cr/uwp/Syncfusion.Data.ISummaryAggregate.html) interface.

2.In the `CalculateAggregateFunc` method, you have to calculate the summary and assign it to the property.
 
In the below code snippet, the Standard Deviation is calculated for quantity of products.

{% tabs %}
{% highlight c# %}
public class CustomAggregate : ISummaryAggregate
{
   
    public CustomAggregate()
    {
    }
   
    public double StdDev { get; set; }
   
    public Action<System.Collections.IEnumerable, string, PropertyInfo> CalculateAggregateFunc()
    {
        return (items, property, pd) =>
        {
            var enumerableItems = items as IEnumerable<OrderInfo>;
   
            if (pd.Name == "StdDev")
            {
                this.StdDev = enumerableItems.StdDev<OrderInfo>(q => q.Quantity);
            }
        };
    }
}


public static class LinqExtensions
{
   
    public static double StdDev<T>(this IEnumerable<T> values, Func<T, double?> selector)
    {
        double rect = 0;
        var count = values.Count();
   
        if (count > 0)
        {
            double? avg = values.Average(selector);
            double sum = values.Select(selector).Sum(d =>
            {
   
                if (d.HasValue)
                {
                    return Math.Pow(d.Value - avg.Value, 2);
                }
                return 0.0;
            });
            rect = Math.Sqrt((sum) / (count - 1));
        }
        return rect;
    }
}
{% endhighlight %}
{% endtabs %}


3.Assign the custom aggregate to `GridSummaryColumn.CustomAggregate` property and set the [SummaryType](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryColumn.html#Syncfusion_UI_Xaml_Grid_GridSummaryColumn_SummaryType) as `Custom`. [GridSummaryColumn.Format](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridSummaryColumn.html#Syncfusion_UI_Xaml_Grid_GridSummaryColumn_Format) property is defined based on property name in custom aggregate `StdDev`.

{% tabs %}
{% highlight xaml %}

<Page.Resources>
     <local:CustomAggregate x:Key="customAggregate" />
</Page.Resources>

<syncfusion:SfDataGrid.TableSummaryRows>
    <syncfusion:GridTableSummaryRow Name="Total Products"
                                    Title="Standard Deviation: {Discount}"
                                    Position="Top"
                                    ShowSummaryInRow="True">
        <syncfusion:GridSummaryRow.SummaryColumns>
            <syncfusion:GridSummaryColumn   Name="Discount"
                                            CustomAggregate="{StaticResource customAggregate}"
                                            Format="'{StdDev:##.##}'"
                                            MappingName="Discount"
                                            SummaryType="Custom" />
        </syncfusion:GridSummaryRow.SummaryColumns>
    </syncfusion:GridTableSummaryRow>
</syncfusion:SfDataGrid.TableSummaryRows>


{% endhighlight %}
{% highlight c# %}
this.dataGrid.TableSummaryRows.Add(new GridTableSummaryRow()
{
    ShowSummaryInRow = true,
    Position=TableSummaryRowPosition.Top,
    Title = "Standard Deviation: {Discount}",
    SummaryColumns = new ObservableCollection<ISummaryColumn>()
    {
   
        new GridSummaryColumn()
        { 
            Name = "Discount", 
            MappingName="Discount", 
            CustomAggregate=new CustomAggregate(),
            SummaryType=SummaryType.Custom, 
            Format="{StdDev}"
        },      
    }
});
{% endhighlight %}
{% endtabs %}


![Custom aggregate summaries in UWP SfDataGrid](Summaries_images/Summaries_img16.png)

You can download the sample demo [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/CustomSummaries958318941.zip) .

## Overriding Summary Renderer

Each summary cell is associated with its own renderer and you can customize it by overriding the available virtual methods in the renderer.
 
There will be specific key for each summary row. You can remove and add the key from [SfDataGrid.CellRenderers](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_CellRenderers) collection, when the renderer is need to be customized.

<table>
<tr>
<th>
Types of summary
</th>
<th>
Renderer
</th>
<th>
Key
</th>
</tr>
<tr>
<td>
Table summary
</td>
<td>
[GridTableSummaryCellRenderer](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.Cells.GridTableSummaryCellRenderer.html)
</td>
<td>
TableSummary
</td>
</tr>
<tr>
<td>
Caption summary
</td>
<td>
[GridCaptionSummaryCellRenderer](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.Cells.GridCaptionSummaryCellRenderer.html)
</td>
<td>
CaptionSummary
</td>
</tr>
<tr>
<td>
Group summary
</td>
<td>
[GridSummaryCellRenderer](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.Cells.GridSummaryCellRenderer.html)
</td>
<td>
GroupSummary
</td>
</tr>
</table>


### Formatting Table Summary

You can apply number format for numeric values displayed on `GridTableSummaryRow` by overriding the `OnUpdateEditBinding` method in [GridTableSummaryCellRenderer](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.Cells.GridTableSummaryCellRenderer.html) class.

{% tabs %}
{% highlight c# %}
this.dataGrid.CellRenderers.Remove("TableSummary");
this.dataGrid.CellRenderers.Add("TableSummary", new GridTableSummaryCellRendererExt());

public class GridTableSummaryCellRendererExt : GridTableSummaryCellRenderer
{
    
    public override void OnUpdateEditBinding(Syncfusion.UI.Xaml.Grid.DataColumnBase dataColumn, Syncfusion.UI.Xaml.Grid.GridTableSummaryCell element, object dataContext)
    {
    
        //Check whether the dataContext is SummaryRecordEntry
        var record = dataContext as SummaryRecordEntry;
    
        if (!(dataContext is SummaryRecordEntry))
            return;
    
        //Process each SummaryColumn and get the display text of corresponding summary
    
        foreach (ISummaryColumn summaryColumn in record.SummaryRow.SummaryColumns)
        {
    
            if (!summaryColumn.MappingName.Contains(dataColumn.GridColumn.MappingName))
                continue;
            string summaryText = string.Empty;
    
            if (record.SummaryRow.ShowSummaryInRow)
                summaryText = SummaryCreator.GetSummaryDisplayTextForRow(record, this.DataGrid.View);
    
            else
                summaryText = SummaryCreator.GetSummaryDisplayText(record, dataColumn.GridColumn.MappingName, this.DataGrid.View);
    
            if (!string.IsNullOrEmpty(summaryText))
            {
    
                //Create new number format and apply it to summary columns 
                NumberFormatInfo format = new NumberFormatInfo();
                format.NumberDecimalDigits = 3;
                format.NumberDecimalSeparator = "*";
                format.NumberGroupSeparator = ",";
    
                //Number format is applied to summary columns                    
                element.Content = Convert.ToDouble(double.Parse(summaryText, NumberStyles.Currency)).ToString("N", format);
            }
        }
    }
}
{% endhighlight %}
{% endtabs %}


![Table summary formatting using renderer in UWP DataGrid](Summaries_images/Summaries_img17.png)

You can download the sample demo [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/SfDataGridDemo-1847415283.zip).

### Customizing GroupCaptionText

You can apply different group caption text format for available groups based on certain conditions by deriving the [GridCaptionSummaryCellRenderer](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.Cells.GridCaptionSummaryCellRenderer.html) class.

For example, the group caption text is customized based on the group name and items count of the column.

{% tabs %}
{% highlight c# %}
this.dataGrid.CellRenderers.Remove("CaptionSummary");
this.dataGrid.CellRenderers.Add("CaptionSummary", new GridCaptionSummaryCellRendererExt());

public class GridCaptionSummaryCellRendererExt : GridCaptionSummaryCellRenderer
{    
  
    public override void OnUpdateEditBinding(Syncfusion.UI.Xaml.Grid.DataColumnBase dataColumn, Syncfusion.UI.Xaml.Grid.GridCaptionSummaryCell element, object dataContext)
    {
  
        if (element.DataContext is Group && this.DataGrid.View.GroupDescriptions.Count > 0)
        {
            var groupRecord = element.DataContext as Group;                
            var groupedColumn = this.GetGroupedColumn(groupRecord);
  
            if (this.DataGrid.CaptionSummaryRow == null)
            {
  
                if (this.DataGrid.View.GroupDescriptions.Count < groupRecord.Level)
                    return;
  
                //Set the CaptionSummaryCell text as customized.
                element.Content = GetCustomizedCaptionText(groupedColumn.HeaderText, groupRecord.Key, groupRecord.ItemsCount);
            }
  
            else if (this.DataGrid.CaptionSummaryRow.ShowSummaryInRow)
            {
                element.Content = SummaryCreator.GetSummaryDisplayTextForRow(groupRecord.SummaryDetails, this.DataGrid.View, groupedColumn.HeaderText);
            }
  
            else
                element.Content = SummaryCreator.GetSummaryDisplayText(groupRecord.SummaryDetails, dataColumn.GridColumn.MappingName, this.DataGrid.View);
        }
    }
    private GridColumn GetGroupedColumn(Group group)
    {
        var groupDesc = this.DataGrid.View.GroupDescriptions[group.Level - 1] as PropertyGroupDescription;
     
        foreach (var column in this.DataGrid.Columns)
        {
     
            if (column.MappingName == groupDesc.PropertyName)
            {
                return column;
            }
        }
        return null;
    }
    
    private string GetCustomizedCaptionText(string columnName, object groupName, int itemsCount)
    {
        string entryText = string.Empty;
    
        if (itemsCount < 20)
            entryText = "entries in the Group";
    
        else if (itemsCount < 40)
            entryText = "elements in the Group";
    
        else if (itemsCount < 60)
            entryText = "list in the Group";
    
        else
            entryText = "items in the Group";
    
        if (groupName.ToString().Equals("1001"))
            groupName = "Thousand and One";
    
        else if (groupName.ToString().Equals("1002"))
            groupName = "Thousand and Two";
    
        else if (groupName.ToString().Equals("1004"))
            groupName = "Thousand and Four";
        return string.Format("{0}: {1} - {2} {3}", columnName, groupName, itemsCount, entryText);
    }
}
{% endhighlight %}
{% endtabs %}

![Customize the group caption text format in UWP DataGrid](Summaries_images/Summaries_img18.png)

You can download the sample demo [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/SfDataGridDemo-827769441.zip). 
