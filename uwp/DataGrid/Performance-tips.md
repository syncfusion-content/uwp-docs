---
layout: post
title: Performance tips in UWP DataGrid control | Syncfusion®
description: Learn here all about Performance tips support in Syncfusion® UWP DataGrid (SfDataGrid) control and more.
platform: uwp
control: SfDataGrid
documentation: ug
---

# Performance tips in UWP DataGrid (SfDataGrid)

SfDataGrid provides various built-in options to optimize the performance when handling large amount of data or high frequency updates. 

## Improving loading performance

### Data virtualization for loading

You can load the large amount of data in less time using built-in [Data Virtualization](https://help.syncfusion.com/uwp/sfdatagrid/data-virtualization).

## Improving performance when doing batch updates

SfDataGrid allows you to add, remove and update more number of records efficiently when you are having sorting, grouping and more summaries in place. By default, SfDataGrid responds to the collection changes and updates the UI instantly. If you are doing bulk or more updates to grid then you can follow below steps for better performance, 

1. Invoke [SfDataGrid.View.BeginInit](https://help.syncfusion.com/cr/uwp/Syncfusion.Data.CollectionViewAdv.html#Syncfusion_Data_CollectionViewAdv_BeginInit_System_Boolean_) before update the data.
2. After that update underlying collection.
3. Then call [SfDataGrid.View.EndInit](https://help.syncfusion.com/cr/uwp/Syncfusion.Data.CollectionViewAdv.html#Syncfusion_Data_CollectionViewAdv_EndInit) method, to refresh the View and UI.  Now summaries, sort order and groups will be updated as expected. 

{% tabs %}
{% highlight c# %}
//Batch Updates

//Suspends data manipulation operations in View
this.dataGrid.View.BeginInit();

// Add, remove and update the underlying collection. 

//Resumes data manipulation operations and refresh the View.
this.dataGrid.View.EndInit();
{% endhighlight %}
{% endtabs %}

## Adding columns efficiently

SfDataGrid allows you to add more number of columns to [SfDataGrid.Columns](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_Columns) collection efficiently. Adding or removing more no of columns to collection, updates the UI for each time which negatively impact the performance.

You can improve the performance while adding, removing columns by suspending all the UI updates using [Suspend](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.Columns.html#Syncfusion_UI_Xaml_Grid_Columns_Suspend) and resume the updates after adding columns using [Resume](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.Columns.html#Syncfusion_UI_Xaml_Grid_Columns_Resume) methods. You have to refresh the UI using [RefreshColumns](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.Helpers.GridHelper.html#Syncfusion_UI_Xaml_Grid_Helpers_GridHelper_RefreshColumns_Syncfusion_UI_Xaml_Grid_SfDataGrid_) method.

{% tabs %}
{% highlight c# %}
using Syncfusion.UI.Xaml.Grid.Helpers;
this.dataGrid.Columns.Suspend();

// Add or Remove More columns
this.dataGrid.Columns.Resume();
this.dataGrid.RefreshColumns();
{% endhighlight %}
{% endtabs %}

## Optimizing summary calculation performance

SfDataGrid optimizes the summary calculation when updating the underlying collection. It calculates the summaries optimistically by listening the data updates and using old calculated summary values without doing complete recalculation. 

Below sections explains how SfDataGrid handles the updates efficiently for different data operations and what you have to do in application for the same.

### Adding Record

SfDataGrid considers only the `added` item value and the current summary value instead of recalculating the summary based on all records. Based on these two values recalculates the summary efficiently. 

### Removing a Record

SfDataGrid considers only the `removed` item value and the current summary value instead of recalculating the summary based on all records. Based on these two values recalculates the summary efficiently.

### Property Change in a record

SfDataGrid considers only the changed item value and the current aggregated value instead of recalculating the summary based on all records.  For this you have to implement [INotifyPropertyChanging](https://learn.microsoft.com/en-us/dotnet/api/system.componentmodel.inotifypropertychanging?view=net-7.0&redirectedfrom=MSDN) and [INotifyPropertyChanged](https://learn.microsoft.com/en-us/dotnet/api/system.componentmodel.inotifypropertychanged?view=net-7.0&redirectedfrom=MSDN "") interface to your Data Model.

Below code to enable summary calculation optimization by inheriting [INotifyPropertyChanging](https://learn.microsoft.com/en-us/dotnet/api/system.componentmodel.inotifypropertychanging?view=net-7.0&redirectedfrom=MSDN) and [INotifyPropertyChanged](https://learn.microsoft.com/en-us/dotnet/api/system.componentmodel.inotifypropertychanged?view=net-7.0&redirectedfrom=MSDN) interface to Data Model.

{% tabs %}
{% highlight c# %}
public class OrderInfo : INotifyPropertyChanged, INotifyPropertyChanging
{
    private int orderID;

    public int OrderID
    {
        get { return orderID; }
        set 
        {
            this.RaisePropertyChanging("OrderID");
            orderID = value;
            this.RaisePropertyChanged("OrderID");
        }
    }

    public void RaisePropertyChanged(string propName)
    {

        if (this.PropertyChanged != null)
            this.PropertyChanged(this, new PropertyChangedEventArgs(propName));
    }
    public event PropertyChangedEventHandler PropertyChanged;

    public void RaisePropertyChanging(string propName)
    {

        if (this.PropertyChanging != null)
            this.PropertyChanging(this, new PropertyChangingEventArgs(propName));
    }
    public event PropertyChangingEventHandler PropertyChanging;
}
{% endhighlight %}
{% endtabs %}

### Loading performance - On demand summary calculation for group and caption summary 

You can calculate the Caption and Group summary on-demand by setting [SfDataGrid.SummaryCalculationMode](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_SummaryCalculationMode) as ‘CalculationMode.OndemandCaptionSummary’ or ‘CalculationMode.OndemandGroupSummary’. You can set this property when you are loading more number of summary columns on summary row or more number of group summaries to improve loading performance. On-demand summary calculation will calculate summaries for the summary rows which are visible and summaries for other rows will be calculated only when it comes into view. 

{% tabs %}
{% highlight xaml %}
<Syncfusion:SfDataGrid x:Name="datagrid"                               
                       SummaryCalculationMode="OnDemandCaptionSummary"                            
                       ItemsSource="{Binding OrderInfoCollection }">
{% endhighlight %}
{% highlight c# %}
this.datagrid.SummaryCalculationMode = CalculationMode.OnDemandCaptionSummary | CalculationMode.OnDemandGroupSummary;
{% endhighlight %}
{% endtabs %}

## Improving UI Filter loading time

SfDataGrid allows you to open filter popup in less time by setting [CanGenerateUniqueItems](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.AdvancedFilterControl.html#Syncfusion_UI_Xaml_Grid_AdvancedFilterControl_CanGenerateUniqueItems) property to false. By default `GridFilterControl` loads unique items in popup which takes more time to load.
`CanGenerateUniqueItems` property loading `TextBox` to filter instead of `ComboBox` in advanced filter UI View.

{% tabs %}
{% highlight xaml %}
<Window.Resources>    
    <Style TargetType="syncfusion:GridFilterControl">
        <Setter Property="FilterMode" Value="AdvancedFilter" />
    </Style>

    <Style TargetType="syncfusion:AdvancedFilterControl">
        <Setter Property="CanGenerateUniqueItems" Value="False" />
    </Style>
</Window.Resources>
{% endhighlight %}
{% endtabs %}

## Improving performance while adding multiple FilterPredicates to the column in loop

For more details, refer the [Filtering](https://help.syncfusion.com/uwp/datagrid/filtering#improving-performance-while-adding-multiple-filterpredicates-to-the-column-in-loop) section.
