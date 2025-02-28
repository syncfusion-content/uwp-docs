---
layout: post
title: ToolTip in UWP DataGrid control | Syncfusion®
description: Learn here all about ToolTip support in Syncfusion® UWP DataGrid (SfDataGrid) control and more.
platform: UWP
control: SfDataGrid
documentation: ug
---

# ToolTip in UWP DataGrid (SfDataGrid)

ToolTip provides the support to show the pop-up window that displays the information when the mouse hovers in cells of SfDataGrid.

## Record cell tooltip

You can enable the ToolTip for the GridCell by setting the [SfDataGrid.ShowToolTip](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_ShowToolTip) as true.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfDataGrid x:Name="dataGrid" 
                       AutoGenerateColumns="True"
                       ShowToolTip="True"
                       ItemsSource="{Binding Orders}" >
</syncfusion:SfDataGrid>

{% endhighlight %}

{% highlight c# %}

this.dataGrid.ShowToolTip = true;

{% endhighlight %}
{% endtabs %}

You can enable the ToolTip for the particular column by setting the [GridColumn.ShowToolTip](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridColumnBase.html#Syncfusion_UI_Xaml_Grid_GridColumnBase_ShowToolTip) as true.
{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid.Columns>
    <syncfusion:GridTextColumn HeaderText="Order ID" ShowToolTip="True" MappingName="OrderID" />
    <syncfusion:GridTextColumn HeaderText="CustomerID" ShowToolTip="True" MappingName="CustomerID" />
</syncfusion:SfDataGrid.Columns>

{% endhighlight %}

{% highlight c# %}

this.dataGrid.Columns["OrderID"].ShowToolTip = true;
this.dataGrid.Columns["CustomerID"].ShowToolTip = true;


{% endhighlight %}
{% endtabs %}

N> `GridColumn.ShowToolTip` takes higher priority than [SfDataGrid.ShowToolTip](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridColumnBase.html#Syncfusion_UI_Xaml_Grid_GridColumnBase_ShowToolTip).

![InteractiveFeatures_img4](Interactive-Features_images/InteractiveFeatures_img4.png)

## Header tooltip

You can enable the ToolTip for the header cell by setting the [GridColumn.ShowHeaderToolTip](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridColumnBase.html#Syncfusion_UI_Xaml_Grid_GridColumnBase_ShowHeaderToolTip) as true.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfDataGrid.Columns>
    <syncfusion:GridTextColumn HeaderText="Order ID" ShowHeaderToolTip="True" MappingName="OrderID" />
</syncfusion:SfDataGrid.Columns>

{% endhighlight %}

{% highlight c# %}

this.dataGrid.Columns["OrderID"].ShowHeaderToolTip = true;

{% endhighlight %}
{% endtabs %}

![InteractiveFeatures_img5](Interactive-Features_images/InteractiveFeatures_img5.png)


## ToolTip Customization

You can customize the template of ToolTip by using the [GridColumn.ToolTipTemplate](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridColumnBase.html#Syncfusion_UI_Xaml_Grid_GridColumnBase_ToolTipTemplate) and [GridColumn.ToolTipTemplateSelector](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridColumnBase.html#Syncfusion_UI_Xaml_Grid_GridColumnBase_ToolTipTemplateSelector) properties. 

### Customize the ToolTip using ToolTipTemplate

You can customize the appearance of the ToolTip for particular column by setting `GridColumn.ToolTipTemplate`. And you can also customize the appearance of header ToolTip for particular column by [GridColumn.HeaderToolTipTemplate](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridColumnBase.html#Syncfusion_UI_Xaml_Grid_GridColumnBase_HeaderToolTipTemplate) property.

{% tabs %}
{% highlight xaml %}
<Page.Resources>
    <local:StringToImageConverter x:Key="ImageConverter" />        
    <DataTemplate x:Key="TemplateToolTip">
        <Image Height="100" Width="100" Source="{Binding CustomerID,Converter={StaticResource ImageConverter}}" />
    </DataTemplate>
</Page.Resources>

<syncfusion:SfDataGrid.Columns>
    <syncfusion:GridTextColumn HeaderText="Order ID"  ShowToolTip="True" MappingName="OrderID" />
    <syncfusion:GridTextColumn HeaderText="CustomerID" ToolTipTemplate="{StaticResource TemplateToolTip}" ShowToolTip="True" MappingName="CustomerID" />
</syncfusion:SfDataGrid.Columns>

{% endhighlight %}
{% endtabs %}

![InteractiveFeatures_img6](Interactive-Features_images/InteractiveFeatures_img6.png)


You can get the sample from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/TemplateSample-844671609.zip). 

### Customize the ToolTip with ToolTipTemplateSelector

The different ToolTip template can be loaded in a same column conditionally based on data by setting `GridColumn.ToolTipTemplateSelector`

{% tabs %}
{% highlight xaml %}

<Page.Resources>        
    <DataTemplate x:Key="ToolTip1">
        <Grid>
            <Rectangle Fill="Transparent"/>
            <TextBlock Text="{Binding OrderID}" FontWeight="Bold" Background="LightPink"/>
        </Grid>
    </DataTemplate>
    <DataTemplate x:Key="ToolTip2">
        <Grid>
            <Rectangle Fill="Transparent"/>
            <TextBlock Text="{Binding OrderID}" FontStyle="Italic" Background="LightGreen"/>
        </Grid>
    </DataTemplate>
</Page.Resources>

<syncfusion:SfDataGrid.Columns>
    <syncfusion:GridTextColumn HeaderText="Order ID" ShowToolTip="True" MappingName="OrderID" >
        <syncfusion:GridTextColumn.ToolTipTemplateSelector>
            <local:ToolTipTemplateSelector  
                   AlternateTemplate="{StaticResource ToolTip2}"  
                   DefaultTemplate="{StaticResource ToolTip1}" />
        </syncfusion:GridTextColumn.ToolTipTemplateSelector>
    </syncfusion:GridTextColumn>
</syncfusion:SfDataGrid.Columns>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}
public class ToolTipTemplateSelector : DataTemplateSelector
{
    private DataTemplate _defaultTemplate;
    /// <summary>
    /// Gets or sets DefaultTemplate.
    /// </summary>

    public DataTemplate DefaultTemplate
    {
        get { return _defaultTemplate; }
        set { _defaultTemplate = value; }
    }
    private DataTemplate _alternateTemplate;
    /// <summary>
    /// Gets or Sets AlternateTemplate.
    /// </summary>

    public DataTemplate AlternateTemplate
    {
        get { return _alternateTemplate; }
        set { _alternateTemplate = value; }
    }

    public override System.Windows.DataTemplate SelectTemplate(object item, System.Windows.DependencyObject container)
    {

        //The item that comes from ToolTipTemplate is DataContextHelper. When set SetCellBoundValue to true, it sets DataContextHelper as DataContext to DataTemplate. Refer property section of CellTemplate.
        OrderInfo dataUnit = item as OrderInfo;

        if (dataUnit == null) return this.DefaultTemplate;

        //use reflection to retrieve property
        Type type = dataUnit.GetType();
        PropertyInfo property = type.GetProperty("OrderID");

        //To see what template needs to be select according to the specified property value.

        if (property.GetValue(dataUnit, null).ToString().Contains('9') || property.GetValue(dataUnit, null).ToString().Contains('4'))
            return this.AlternateTemplate;

        else
            return this.DefaultTemplate;
    }
}

{% endhighlight %}
{% endtabs %}

The below image refers the DefaultTemplate which is applied through ToolTipTemplateSelector.

![InteractiveFeatures_img7](Interactive-Features_images/InteractiveFeatures_img7.png)


The below image refers the AlternateTemplate which is applied through ToolTipTemplateSelector.

![InteractiveFeatures_img8](Interactive-Features_images/InteractiveFeatures_img8.png)


You can get the sample from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/ToolTipSample-394161722.zip).

## Events

### CellToolTipOpening event

The [CellToolTipOpening](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event occurs when any tooltip of the cell is opened. The `CellToolTipOpening` event receives the [GridCellToolTipOpeningEventArgs](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.CellToolTipOpeningEventArgs.html) as argument which has the following properties:

<ul>
<li> <a href="https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.CellToolTipOpeningEventArgs.html#Syncfusion_UI_Xaml_Grid_CellToolTipOpeningEventArgs_Column">Column:</a> Gets the hovered cell column in the SfTreeGrid.</li>
<li> <a href="https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.CellToolTipOpeningEventArgs.html#Syncfusion_UI_Xaml_Grid_CellToolTipOpeningEventArgs_Record">Record:</a> Gets the data context of hovered cell.</li>
<li> <a href="https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.CellToolTipOpeningEventArgs.html#Syncfusion_UI_Xaml_Grid_CellToolTipOpeningEventArgs_RowColumnIndex">RowColumnIndex:</a> Gets the row and column index of the hovered cell.</li>
<li> <a href="https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.CellToolTipOpeningEventArgs.html#Syncfusion_UI_Xaml_Grid_CellToolTipOpeningEventArgs_ToolTip">ToolTip:</a> Gets the tooltip of the hovered cells.</li>
</ul>

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid Name="DataGrid"  
                        CellToolTipOpening="DataGrid_CellToolTipOpening"
                        AutoGenerateColumns="True"
                        ItemsSource="{Binding Orders}">
{% endhighlight %}
{% highlight c# %}
this.DataGrid.CellToolTipOpening += DataGrid_CellToolTipOpening;

private void DataGrid_CellToolTipOpening(object sender, Syncfusion.UI.Xaml.Grid.GridCellToolTipOpeningEventArgs e)
{
           
}
{% endhighlight %}
{% endtabs %}
