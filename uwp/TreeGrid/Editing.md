---
layout: post
title: Editing in UWP TreeGrid control | Syncfusion®
description: Learn here all about Editing support in Syncfusion® UWP TreeGrid (SfTreeGrid) control and more.
platform: uwp
control: SfTreeGrid
documentation: ug
---



# Editing in UWP TreeGrid (SfTreeGrid)

SfTreeGrid provides support for editing and it can be enabled or disabled by setting [SfTreeGrid.AllowEditing](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_AllowEditing) property.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeGrid x:Name="treeGrid"
                        AllowEditing="True"
                        AutoGenerateColumns="True"
                        ItemsSource="{Binding EmployeeDetails}" />
{% endhighlight %}
{% highlight c# %}
treeGrid.AllowEditing = true;
{% endhighlight %}
{% endtabs %}

You can enable or disable editing for particular column by setting [TreeGridColumn.AllowEditing](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridColumnBase.html#Syncfusion_UI_Xaml_Grid_GridColumnBase_AllowEditing) property.

{% tabs %}
{% highlight xaml %}
<syncfusion:TreeGridTextColumn AllowEditing="True"
                                HeaderText="First Name"
                                MappingName="FirstName" />
{% endhighlight %}
{% highlight c# %}
treeGrid.Columns["FirstName"].AllowEditing = true;
{% endhighlight %}
{% endtabs %}

N> `TreeGridColumn.AllowEditing` takes higher priority than `SfTreeGrid.AllowEditing`

![Editing in UWP treegrid](Editing_images/Editing_img1.png)

N> It is mandatory to set the NavigationMode to Cell to enable CurrentCell navigation and editing.

### Entering into edit mode

You can enter into edit mode by pressing &lt;kbd&gt;F2&lt;/kbd&gt; key or clicking (touch also supported) the cell. You can allow users to edit the cell in single click (OnTap) or double click (OnDoubleTab) by setting [SfTreeGrid.EditTrigger](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_EditTrigger) property.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeGrid Name="treeGrid"
                        EditTrigger="OnTap"
                        AllowEditing="True"
                        AutoExpandMode="RootNodesExpanded"                             
                        ChildPropertyName="ReportsTo"
                        ItemsSource="{Binding EmployeeInfo}"
                        ParentPropertyName="ID"/>
{% endhighlight %}
{% highlight c# %}
treeGrid.EditTrigger = EditTrigger.OnTap;
{% endhighlight %}
{% endtabs %}

### Cursor placement

When the cell enters into edit mode, cursor is placed based on [SfTreeGrid.EditorSelectionBehavior](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_EditorSelectionBehavior) property.

SelectAll – selects the text of edit element loaded inside cell.

MoveLast – places the cursor at the last of edit element loaded inside cell.  

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeGrid Name="treeGrid"
                        AllowEditing="True"
                        EditorSelectionBehavior="SelectAll"
                        AutoExpandMode="RootNodesExpanded"
                        ChildPropertyName="ReportsTo"
                        EditTrigger="OnTap"
                        ParentPropertyName="ID"
                        ItemsSource="{Binding EmployeeInfo}" />
{% endhighlight %}
{% highlight c# %}
treeGrid.EditorSelectionBehavior = EditorSelectionBehavior.SelectAll;
{% endhighlight %}
{% endtabs %}

## Support for IEditableObject

SfTreeGrid supports to commit and roll back the changes in row level when underlying data object implements [IEditableObject](https://msdn.microsoft.com/en-us/library/system.componentmodel.ieditableobject.aspx) interface.

The editing changes in a row will be committed only when user move to next row or pressing enter key in [EndEdit](https://msdn.microsoft.com/en-us/library/system.componentmodel.ieditableobject.endedit.aspx). Also when user press &lt;kbd&gt; Esc &lt;/kbd&gt; key, then the changes made in a row will be reverted in [CancelEdit](https://msdn.microsoft.com/en-us/library/system.componentmodel.ieditableobject.canceledit.aspx). 

`IEditableObject` has the following methods to capture editing,

[BeginEdit](https://msdn.microsoft.com/en-us/library/system.componentmodel.ieditableobject.beginedit.aspx) - Gets called to begin edit on underlying data object when cell in a row get into edit mode. 

[CancelEdit](https://msdn.microsoft.com/en-us/library/system.componentmodel.ieditableobject.canceledit.aspx) - Gets called when user press the &lt;kbd&gt;Esc&lt;/kbd&gt; key to discard the changes in a row since last `BeginEdit` call. 

[EndEdit](https://msdn.microsoft.com/en-us/library/system.componentmodel.ieditableobject.endedit.aspx) - Gets called when user move to the next row or press Enter key  to commit changes in underlying data object since last `BeginEdit` call. 

In the below code snippet explains the simple implementation of IEditableObject.

{% tabs %}
{% highlight c# %}
public class EmployeeInfo : IEditableObject, INotifyPropertyChanged
{      
    int _id;
    /// <summary>
    /// Gets or sets the ID.
    /// </summary>
    /// <value>The ID.</value>

    public int ID
    {
        get
        {
            return _id;
        }
        set
        {
            _id = value;
            RaisePropertyChanged("ID");
        }
    }

    string _firstName;
    /// <summary>
    /// Gets or sets the first name.
    /// </summary>
    /// <value>The first name.</value>   
 
    public string FirstName
    {
        get { return _firstName; }
        set
        {
            _firstName = value;
            RaisePropertyChanged("FirstName");
        }
    }

    string _lastName;
    /// <summary>
    /// Gets or sets the last name.
    /// </summary>
    /// <value>The last name.</value>

    public string LastName
    {
        get { return _lastName; }
        set
        {
            _lastName = value;
            RaisePropertyChanged("LastName");
        }
    }
    private string _title;
    /// <summary>
    /// Gets or sets the title.
    /// </summary>
    /// <value>The title.</value>

    public string Title
    {
        get
        {
            return _title;
        }
        set
        {
            _title = value;
            RaisePropertyChanged("Title");
        }
    }

    double? _salary;
    /// <summary>
    /// Gets or sets the salary.
    /// </summary>
    /// <value>The salary.</value>

    public double? Salary
    {
        get
        {
            return _salary;
        }
        set
        {
            _salary = value;
            RaisePropertyChanged("Salary");
        }
    }

    int _reportsTo;
    /// <summary>
    /// Gets or sets the reports to.
    /// </summary>
    /// <value>The reports to.</value>

    public int ReportsTo
    {
        get
        {
            return _reportsTo;
        }
        set
        {
            _reportsTo = value;
            RaisePropertyChanged("ReportsTo");
        }
    }
      
    protected Dictionary<string, object> BackUp()
    {
        var dictionary = new Dictionary<string, object>();
        var itemProperties = this.GetType().GetTypeInfo().DeclaredProperties;

        foreach (var pDescriptor in itemProperties)
        {

            if (pDescriptor.CanWrite)
                dictionary.Add(pDescriptor.Name, pDescriptor.GetValue(this));
        }
        return dictionary;
    }

    private Dictionary<string, object> storedValues;

    public void BeginEdit()
    {
        this.storedValues = this.BackUp();
    }

    public void CancelEdit()
    {

        if (this.storedValues == null)
            return;

        foreach (var item in this.storedValues)
        {
            var itemProperties = this.GetType().GetTypeInfo().DeclaredProperties;
            var pDesc = itemProperties.FirstOrDefault(p => p.Name == item.Key);

            if (pDesc != null)
                pDesc.SetValue(this, item.Value);
        }
    }

    public void EndEdit()
    {           

        if (this.storedValues != null)
        {
            this.storedValues.Clear();
            this.storedValues = null;
        }
    }
    public event PropertyChangedEventHandler PropertyChanged;

    public void RaisePropertyChanged(string propertyName)
    {

        if (PropertyChanged != null)
            PropertyChanged(this, new PropertyChangedEventArgs(propertyName));
    }
}
{% endhighlight %}
{% endtabs %}

## Events

SfTreeGrid triggers the following events during editing. 

### CurrentCellBeginEdit Event

[CurrentCellBeginEdit](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html) event occurs when the `CurrentCell` enter into edit mode. [TreeCurrentCellBeginEditEventArgs](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.TreeGridCurrentCellBeginEditEventArgs.html) has following members which provides information for `CurrentCellBeginEdit` event.

*  [Cancel](https://msdn.microsoft.com/en-us/library/system.componentmodel.canceleventargs.cancel.aspx) : When set to `true`, the event is canceled and the `CurrentCell` does not enter into the edit mode.

* [RowColumnIndex](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.TreeGridCurrentCellBeginEditEventArgs.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridCurrentCellBeginEditEventArgs_RowColumnIndex) : Gets the current row column index of the TreeGrid.

* [Column](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.TreeGridCurrentCellBeginEditEventArgs.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridCurrentCellBeginEditEventArgs_Column) : Gets the Tree Grid Column of the SfTreeGrid.

{% tabs %}
{% highlight c# %}
treeGrid.CurrentCellBeginEdit += TreeGrid_CurrentCellBeginEdit;

void TreeGrid_CurrentCellBeginEdit(object sender, TreeGridCurrentCellBeginEditEventArgs args)
{
}
{% endhighlight %}
{% endtabs %}

### CurrentCellEndEdit Event

[CurrentCellEndEdit](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html) event occurs when the `CurrentCell` exits the edit mode. 
[CurrentCellEndEditEventArgs](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.CurrentCellEndEditEventArgs.html) has following members which provides information for [CurrentCellEndEdit](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html) event.

* RowColumnIndex : Gets the value for the current row column index.

{% tabs %}
{% highlight c# %}
treeGrid.CurrentCellEndEdit += TreeGrid_CurrentCellEndEdit;

void TreeGrid_CurrentCellEndEdit(object sender, CurrentCellEndEditEventArgs args)
{
}
{% endhighlight %}
{% endtabs %}

### CurrentCellValueChanged Event

[CurrentCellValueChanged](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html) event occurs whenever a value changes in TreeGridColumn that supports editing. 
[TreeGridCurrentCellValueChangedEventArgs](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.TreeGridCurrentCellValueChangedEventArgs.html) has following members which provides information for `CurrentCellValueChanged` event.

* [Column](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.TreeGridCurrentCellValueChangedEventArgs.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridCurrentCellValueChangedEventArgs_Column) : Gets the Grid Column of the SfTreeGrid.
* [RowColumnIndex](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.TreeGridCurrentCellValueChangedEventArgs.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridCurrentCellValueChangedEventArgs_RowColumnIndex) : Gets the value of the current RowColumnIndex.

{% tabs %}
{% highlight c# %}
treeGrid.CurrentCellValueChanged += TreeGrid_CurrentCellValueChanged;

void TreeGrid_CurrentCellValueChanged(object sender, TreeGridCurrentCellValueChangedEventArgs args)
{
}
{% endhighlight %}
{% endtabs %}
N> For TreeGridComboBoxColumn, you have to use the CurrentCellDropDownSelectionChanged event.

### CurrentCellDropDownSelectionChanged Event

[CurrentCellDropDownSelectionChanged](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html) event occurs whenever the `SelectedItem` of `TreeGridComboBoxColumn` column changed.
[CurrentCellDropDownSelectionChangedEventArgs](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.CurrentCellDropDownSelectionChangedEventArgs.html) has following members which provides information for `CurrentCellDropDownSelectionChanged` event.

* [RowColumnIndex](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.CurrentCellDropDownSelectionChangedEventArgs.html#Syncfusion_UI_Xaml_Grid_CurrentCellDropDownSelectionChangedEventArgs_RowColumnIndex)  - Gets the RowColumnIndex of the corresponding item that were selected from the drop-down control.
* [SelectedIndex](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.CurrentCellDropDownSelectionChangedEventArgs.html#Syncfusion_UI_Xaml_Grid_CurrentCellDropDownSelectionChangedEventArgs_SelectedIndex) - Gets the index of the corresponding item that were selected from the drop-down control.
* [SelectedItem](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.CurrentCellDropDownSelectionChangedEventArgs.html#Syncfusion_UI_Xaml_Grid_CurrentCellDropDownSelectionChangedEventArgs_SelectedItem) - Gets the data item that were selected from the drop-down control.

{% tabs %}
{% highlight c# %}
treeGrid.CurrentCellDropDownSelectionChanged += TreeGrid_CurrentCellDropDownSelectionChanged;

void TreeGrid_CurrentCellDropDownSelectionChanged(object sender, CurrentCellDropDownSelectionChangedEventArgs args)
{
}
{% endhighlight %}
{% endtabs %}

## Programmatically edit the cell

### BeginEdit

SfTreeGrid allows you to edit the cell programmatically by calling the [BeginEdit](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.TreeGridCurrentCellManager.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridCurrentCellManager_BeginEdit) method. Initially the[CurrentCell](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.TreeGridCurrentCellManager.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridCurrentCellManager_CurrentCell) need to set before calling the `BeginEdit` method when the CurrentCell value is null.

{% tabs %}
{% highlight c# %}
treeGrid.Loaded += TreeGrid_Loaded;

void TreeGrid_Loaded(object sender, RoutedEventArgs e)
{            
    RowColumnIndex rowColumnIndex = new RowColumnIndex(2, 3);
    treeGrid.SelectionController.MoveCurrentCell(rowColumnIndex);
    treeGrid.SelectionController.CurrentCellManager.BeginEdit();
}
{% endhighlight %}
{% endtabs %}

### EndEdit

You can call the [EndEdit](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.TreeGridCurrentCellManager.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridCurrentCellManager_EndEdit_System_Boolean_) method to programmatically end edit. 

{% tabs %}
{% highlight c# %}
treeGrid.Loaded += TreeGrid_Loaded;
 
void TreeGrid_Loaded(object sender, RoutedEventArgs e)
{            
    RowColumnIndex rowColumnIndex = new RowColumnIndex(2, 3);
    treeGrid.SelectionController.MoveCurrentCell(rowColumnIndex);
    treeGrid.SelectionController.CurrentCellManager.EndEdit();
}
{% endhighlight %}
{% endtabs %}

### CancelEdit

You can use the [CurrentCellBeginEdit](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html) event to cancel the editing operation for the corresponding cell.

{% tabs %}
{% highlight c# %}
treeGrid.CurrentCellBeginEdit += TreeGrid_CurrentCellBeginEdit;void TreeGrid_CurrentCellBeginEdit(object sender, TreeGridCurrentCellBeginEditEventArgs args)
{
    var mappingName = treeGrid.Columns[args.RowColumnIndex.ColumnIndex].MappingName;
    var node = treeGrid.View.GetNodeAt(args.RowColumnIndex.RowIndex);

    if (args.RowColumnIndex == new RowColumnIndex(2, 2))
        args.Cancel = true;
}
{% endhighlight %}
{% endtabs %}

## ReadOnly

You can prevent users from modifying the contents of a treegrid cell by setting the [SfTreeGrid.IsReadOnly ](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_IsReadOnly) property, but the user can able to perform copy and selection operation.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeGrid Name="treeGrid"
            AllowEditing="True"
            IsReadOnly="True"
            AutoGenerateColumns="True"
            ItemsSource="{Binding EmployeeDetails}"/>

{% endhighlight %}
{% highlight c# %}

this.treeGrid.IsReadOnly = true;

{% endhighlight %}
{% endtabs %}

You can enable or disable editing for particular column by setting [TreeGridColumn.IsReadOnly](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridColumnBase.html#Syncfusion_UI_Xaml_Grid_GridColumnBase_IsReadOnly) property.

{% tabs %}
{% highlight xaml %}
<syncfusion:TreeGridTextColumn  HeaderText="Order ID" 
                                MappingName="OrderID"
                                IsReadOnly="True"/>
{% endhighlight %}
{% highlight c# %}

this.treeGrid.Columns["OrderID"].IsReadOnly = true;

{% endhighlight %}
{% endtabs %}

N> We should set the AllowEditing property to achieve the IsReadOnly behavior.
[TreeGridColumn.IsReadOnly ](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridColumnBase.html#Syncfusion_UI_Xaml_Grid_GridColumnBase_IsReadOnly)takes higher priority than [SfTreeGrid.IsReadOnly](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_IsReadOnly).

## Keyboard operations for UIElement inside Template

You can directly load edit element using [TreeGridTemplateColumn.CellTemplate](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Grid.GridColumnBase.html#Syncfusion_UI_Xaml_Grid_GridColumnBase_CellTemplate) property. In this case, you can provide focus and control to the UIElement inside
 CellTemplate in the below ways,

You can allow focus to the particular UIElement loaded inside template when cell gets activated by setting [FocusedManager.FocusedElement](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.FocusManagerHelper.html#Syncfusion_UI_Xaml_Grid_FocusManagerHelper_FocusedElementProperty) attached property to the `UIElement` inside DataTemplate and let the UIElement to handle keyboard operations which is loaded inside the template by setting [FocusManagerHelper.WantsKeyInput](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.FocusManagerHelper.html#Syncfusion_UI_Xaml_Grid_FocusManagerHelper_WantsKeyInputProperty) attached property to `TreeGridColumn`.

{% tabs %}
{% highlight xaml %}

xmlns:syncfusion="using:Syncfusion.UI.Xaml.TreeGrid"
xmlns:sync="using:Syncfusion.UI.Xaml.Grid"

<syncfusion:TreeGridTemplateColumn sync:FocusManagerHelper.WantsKeyInput="True"
                                    HeaderText="First Name"
                                    MappingName="FirstName">

    <syncfusion:TreeGridTemplateColumn.CellTemplate>
        <DataTemplate>
            <TextBlock FontStyle="Italic"
                        FontWeight="SemiBold"
                        Padding="2,0"
                        Text="{Binding FirstName}" />
        </DataTemplate>
    </syncfusion:TreeGridTemplateColumn.CellTemplate>

    <syncfusion:TreeGridTemplateColumn.EditTemplate>
        <DataTemplate>
            <TextBox sync:FocusManagerHelper.FocusedElement="True"
                        FontStyle="Italic"
                        FontWeight="SemiBold"
                        Padding="2,0"
                        Text="{Binding FirstName}" />
        </DataTemplate>
    </syncfusion:TreeGridTemplateColumn.EditTemplate>

</syncfusion:TreeGridTemplateColumn>

{% endhighlight %}
{% endtabs %}

N> Enter and Tab keys are always handled by SfTreeGrid only.
