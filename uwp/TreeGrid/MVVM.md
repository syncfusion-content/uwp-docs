---
layout: post
title: MVVM in UWP TreeGrid control | Syncfusion®
description: Learn here all about MVVM support in Syncfusion® UWP TreeGrid (SfTreeGrid) control and more.
platform: uwp
control: SfTreeGrid
documentation: ug
---

# MVVM in UWP TreeGrid (SfTreeGrid)

This section explains various MVVM requirements using SfTreeGrid.

## Bind the SelectedItem property of treegrid

You can bind the [SelectedItem](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_SelectedItem) property directly to treegrid by setting the `SfTreeGrid.SelectedItem` property.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeGrid Name="treeGrid" 
                               Grid.Row="1" 
                               ChildPropertyName="ReportsTo"  
                               AutoExpandMode="AllNodesExpanded"
                               ShowRowHeader="True" 
                               SelectedItem="{Binding SelectedItem, Mode=TwoWay, UpdateSourceTrigger=PropertyChanged}"
                               AutoGenerateColumns="False"
                               ItemsSource="{Binding Employees}"
                               ParentPropertyName="ID"
                               SelfRelationRootValue="-1"/>
{% endhighlight %}
{% endtabs %}

Whenever the `SelectedItem` is changed, the `ViewModel` property will get notified.

{% tabs %}
{% highlight c# %}
public class ViewModel: NotificationObject
{
    private object selectedItem;
    public object SelectedItem
    {
        get
        {
           return selectedItem;
        }
        set
        {
           selectedItem = value;
           RaisePropertyChanged("SelectedItem");
        }
    }
}
{% endhighlight %}
{% endtabs %}

You can download the sample [here](https://github.com/SyncfusionExamples/how-to-bind-the-SelectedItem-property-of-wpf-and-uwp-tree-grid-in-mvvm/tree/master/UWP).

## Bind button command to view model

You can load a button for the columns in treegrid using [TreeGridTemplateColumn](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.TreeGridTemplateColumn.html). When loading the buttons, you can bind a command in ViewModel using `ElementName` binding.

In the following example, ViewModel command receives the underlying data object as command parameter, since the DataContext is bound as command parameter.

{% tabs %}
{% highlight xaml %}
<syncfusion:TreeGridTemplateColumn HeaderText="Click Action" MappingName="Cake" >
        <syncfusion:TreeGridTemplateColumn.CellTemplate>
               <DataTemplate>
                   <Button  Content="Click"  
                                     Command="{Binding Path=DataContext.RowDataCommand,ElementName=treeGrid}" CommandParameter="{Binding}"/>
               </DataTemplate>
       </syncfusion:TreeGridTemplateColumn.CellTemplate>
 </syncfusion:TreeGridTemplateColumn>
{% endhighlight %}
{% endtabs %}

![Button command image](MVVM_images/MVVM_img1.jpeg)

You can download the sample [here](https://github.com/SyncfusionExamples/how-to-bind-button-command-to-view-model-in-wpf-and-uwp-treegrid-in-mvvm/tree/master/UWP).

## Bind combobox column ItemsSource from view model

You can bind the ItemsSource from ViewModel to [TreeGridComboBoxColumn](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.TreeGridComboBoxColumn.html) or using `ElementName` binding.

{% tabs %}
{% highlight xaml %}
<syncfusion:TreeGridComboBoxColumn AllowEditing="True" 
                                   MappingName="MyEyeColor"
                                   HeaderText="MyEyeColor"
                                   ItemsSource="{Binding DataContext.EyeColorList,
                                   ElementName=treeGrid}"/>
{% endhighlight %}
{% highlight c# %}
private ObservableCollection<string> eyeList;
public ObservableCollection<string> EyeColorList
{
    get { return eyeList; }
    set { eyeList = value; }
}
{% endhighlight %}
{% endtabs %}

![ComboBox column image](MVVM_images/MVVM_img2.jpeg)

You can download the sample [here](https://github.com/SyncfusionExamples/how-to-bind-combobox-column-ItemsSource-from-view-model-in-wpf-and-uwp-treegrid-in-mvvm/tree/master/UWP).

## Bind view model ItemsSource to ComboBox inside template

You can load a ComboBox inside [TreeGridTemplateColumn ](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.TreeGridTemplateColumn.html#) and bind the ItemsSource from ViewModel to ComboBox using `ElementName` binding.

{% tabs %}
{% highlight xaml %}
  <syncfusion:TreeGridTemplateColumn MappingName="MyEyeColor">
       <syncfusion:TreeGridTemplateColumn.CellTemplate>
               <DataTemplate>
                     <TextBlock Text="{Binding MyEyeColor}"/>
                </DataTemplate>
       </syncfusion:TreeGridTemplateColumn.CellTemplate>
       <syncfusion:TreeGridTemplateColumn.EditTemplate>
                <DataTemplate>
                    <ComboBox Width="170" Height="40" ItemsSource="{Binding Path=DataContext.EyeColorList, ElementName=treeGrid}" />
                </DataTemplate>
       </syncfusion:TreeGridTemplateColumn.EditTemplate>
 </syncfusion:TreeGridTemplateColumn>
{% endhighlight %}
{% endtabs %}

You can download the sample [here](https://github.com/SyncfusionExamples/how-to-bind-view-model-ItemsSource-to-combo-box-inside-template-in-wpf-and-uwp-treegrid-in-mvvm/tree/master/UWP).

## Bind columns from view model

You can bind the [SfTreeGrid.Columns ](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_ColumnsProperty) property in ViewModel by having the binding property of `Syncfusion.SfGrid.UI.Xaml.TreeGrid.Columns` type. Thus, you can set binding to the SfTreeGrid.Columns property that provides DataContext of treegrid in ViewModel.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeGrid Name="treeGrid"
                                       AutoExpandMode="RootNodesExpanded"
                                       AutoGenerateColumns="False" 
                                       AllowEditing="True"
                                       SelectionMode="Extended"
                                       ShowRowHeader="True"
                                       Columns="{Binding TreeGridColumns, Mode=TwoWay}"
                                       ChildPropertyName="Children"
                                       ColumnSizer="Star" 
                                       ExpanderColumn="FirstName"
                                       ItemsSource="{Binding PersonDetails}"
                                       >
{% endhighlight %}
{% endtabs %}

Refer to the following code example in which the treegrid column is populated with some [TreeGridTextColumn](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.TreeGridTextColumn.html) when creating the ViewModel instance.

{% tabs %}
{% highlight c# %}
   public class ViewModel: NotificationObject
    {
        #region Private Variables
        private ObservableCollection<EmployeeInfo> _employees;
      
        #endregion

        #region ctr

        public ViewModel()
        {
            this.Employees = GetEmployeesDetails();
            rowDataCommand = new RelayCommand(ChangeCanExecute);
this.sfGridColumns = new TreeGridColumns();
            sfGridColumns.Add(new TreeGridTextColumn() { MappingName = "FirstName" });
            sfGridColumns.Add(new TreeGridTextColumn() { MappingName = "LastName" });
            sfGridColumns.Add(new TreeGridTextColumn() { MappingName = "Id" });
            sfGridColumns.Add(new TreeGridTextColumn() { MappingName = "DOB" });        }

        
        }
        #endregion
    }
{% endhighlight %}
{% endtabs %}

You can download the sample [here](https://github.com/SyncfusionExamples/how-to-bind-columns-from-view-model-in-wpf-and-uwp-treegrid-in-mvvm/tree/master/UWP).
