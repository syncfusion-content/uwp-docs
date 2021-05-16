---
layout: post
title: Getting Started with UWP Gantt control | Syncfusion
description: Learn here all about getting started with Syncfusion UWP Gantt (SfGantt) control and more.
platform: uwp
control: SfGantt
documentation: ug
---

# Getting Started with UWP Gantt (SfGantt)

This section explains how to create and configure a simple Gantt application.

## Referencing Essential Studio components in your solution

### Adding SDK reference

1. Open Reference Manager window in your project.
2. Go to Universal Windows > Extensions.
3. Select Syncfusion Controls for UWP XAML.

![Adding SDK references in project](SfGantt_images/SDK_Reference.jpeg)

### Adding assembly reference

Individual references can be added to the project instead of SDK “Syncfusion Controls for UWP XAML”, which refers to all the controls in the Syncfusion control library.

In the Add Reference window, browse and choose the reference assembly from the following location.

**[Installed location]**\Syncfusion\Essential Studio\\**[Installed version]**\Assemblies for Universal Windows\10.0\

![Adding UWP Gantt assembly reference in project](SfGantt_images/Gantt_dll_reference.jpeg)

The following list of assemblies should be added as references to use the Gantt control in applications.

<table>
<tr>
<th>
Required assemblies
</th>
<th>
Description
</th>
</tr>
<tr>
<td>
Syncfusion.SfGantt.UWP
</td>
<td>
Contains classes that handles all the operations in Gantt.
</td>
</tr>
<tr>
<td>
Syncfusion.Data.UWP
</td>
<td>
Dependent assembly for Syncfusion.SfGrid.UWP.
</td>
</tr>
<tr>
<td>
Syncfusion.SfGrid.UWP
</td>
<td>
Contains classes that handles all UI operations of tree grid view in the Gantt.
</td>
</tr>
<tr>
<td>
Syncfusion.SfInput.UWP
</td>
<td>
Contains various editor controls (SfNumericTextBox, SfDateTimeEdit, etc.), which are used in the tree grid view.
</td>
</tr>
<tr>
<td>
Syncfusion.SfShared.UWP
</td>
<td>
Dependent assembly for Syncfusion.SfInput.UWP.
</td>
</tr>
<tr>
<td>
Syncfusion.SfTabControl.UWP
</td>
<td>
Contains classes that handles tab control.
</td>
</tr>
</table>

## Adding SfGantt manually

1. After adding the required assembly references to the project as discussed in the previous section, add the “Syncfusion.UI.Xaml.Gantt” namespace to the application as shown in the following code sample.

{% tabs %}

{% highlight xaml %}

xmlns:gantt="using:Syncfusion.UI.Xaml.Gantt"

{% endhighlight %}

{% highlight C# %}

using Syncfusion.UI.Xaml.Gantt;

{% endhighlight %}

{% endtabs %}

2. Instance the Gantt as shown in the following code sample.

{% tabs %}

{% highlight xaml %}

<gantt:SfGantt></gantt:SfGantt>

{% endhighlight %}

{% highlight C# %}

SfGantt sfGantt = new SfGantt();

{% endhighlight %}

{% endtabs %}

## Adding SfGantt from toolbox

Drag the SfGantt control from the toolbox to your application.

![Loading UWP Gantt control to toolbox page](SfGantt_images/Tool_Box.jpeg)

Now, the “Syncfusion Controls for UWP XAML” reference will be added to the application references, and the xmlns namespace will be generated in MainWindow.xaml as shown in the following screenshot.

![Adding SDK reference automatically](SfGantt_images/Added_SDK.jpeg)

![Initializes the UWP Gantt control instance automatically](SfGantt_images/XAML_Reference.jpeg)

## Creating data model

Create a collection of TaskDetails objects to populate a task in SfGantt as shown in the following code sample.

{% highlight C# %}

public class ProjectTrackerViewModel
{
    public ProjectTrackerViewModel()
    {
        _taskCollection = this.GetData();
    }

    private ObservableCollection<TaskDetail> _taskCollection;

    /// <summary>
    /// Gets or sets the appointment item source.
    /// </summary>
    /// <value>The appointment item source.</value>
    public ObservableCollection<TaskDetail> TaskCollection
    {

        get { return _taskCollection; }

        set { _taskCollection = value; }

    }

    /// <summary>
    /// Gets the data.
    /// </summary>
    /// <returns></returns>
    public ObservableCollection<TaskDetail> GetData()
    {
        ObservableCollection<TaskDetail> Schedule = new ObservableCollection<TaskDetail>();

        Schedule.Add(new TaskDetail
        {
            Name = "Project Schedule",
            ID = "1"
        });

        ObservableCollection<TaskDetail> ScheduleProcess = new ObservableCollection<TaskDetail>();

        ScheduleProcess.Add(new TaskDetail
        {
            Name = "Planning",
            ID = "2"
        });

        ScheduleProcess.Add(new TaskDetail
        {
            StartDate = new DateTime(2014, 3, 30),
            FinishDate = new DateTime(2014, 4, 2),
            Name = "Design",
            ID = "7"
        });

        ScheduleProcess.Add(new TaskDetail
        {
            StartDate = new DateTime(2014, 4, 2),
            FinishDate = new DateTime(2014, 4, 7),
            Name = "Implementation Phase",
            ID = "12"
        });

        ScheduleProcess.Add(new TaskDetail
        {
            StartDate = new DateTime(2014, 4, 7),
            FinishDate = new DateTime(2014, 4, 12),
            Name = "Integration",
            ID = "37"
        });

        ScheduleProcess.Add(new TaskDetail
        {
            StartDate = new DateTime(2014, 4, 12),
            FinishDate = new DateTime(2014, 4, 17),
            Name = "Final Testing",
            ID = "38"
        });

        ScheduleProcess.Add(new TaskDetail
        {
            StartDate = new DateTime(2014, 4, 18),
            FinishDate = new DateTime(2014, 4, 18),
            Name = "Final Delivery",
            ID = "39"
        });

        Schedule[0].Children = ScheduleProcess;

        ObservableCollection<TaskDetail> Planning = new ObservableCollection<TaskDetail>();

        Planning.Add(new TaskDetail
        {
            StartDate = new DateTime(2014, 3, 25),
            FinishDate = new DateTime(2014, 3, 30),
            Name = "Plan timeline",
            ID = "3",
            Progress = 100
        });

        Planning.Add(new TaskDetail
        {
            StartDate = new DateTime(2014, 3, 25),
            FinishDate = new DateTime(2014, 3, 30),
            Name = "Plan budget",
            ID = "4",
            Progress = 100
        });

        Planning.Add(new TaskDetail
        {
            StartDate = new DateTime(2014, 3, 25),
            FinishDate = new DateTime(2014, 3, 30),
            Name = "Allocate resources",
            ID = "5",
            Progress = 100
       });

       Planning.Add(new TaskDetail
       {
            StartDate = new DateTime(2014, 3, 30),
            FinishDate = new DateTime(2014, 3, 30),
            Name = "Planning complete",
            ID = "6",
            Progress = 100
        });
		
        ScheduleProcess[0].Children = Planning;

        return Schedule;
    }
}

{% endhighlight %}

## Binding data

To bind the data source of the SfGantt, set the [`ItemsSource`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.SfGantt.html#Syncfusion_UI_Xaml_Gantt_SfGantt_ItemsSource) property as shown in the following code sample.

{% tabs %}

{% highlight xaml %}

<gantt:SfGantt ItemsSource="{Binding TaskCollection}" />

{% endhighlight %}

{% highlight C# %}

SfGantt sfGantt = new SfGantt();
sfGantt.ItemsSource = (this.DataContext as ProjectTrackerViewModel).TaskCollection;

{% endhighlight %}

{% endtabs %}

## Defining visible columns

By default, the grid view is manipulated with name, start date, finish date, duration, progress, predecessor, and resources columns.

The visible columns of grid view can be customized using the [`VisibleGridColumns`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.SfGantt.html#Syncfusion_UI_Xaml_Gantt_SfGantt_VisibleGridColumns) property.

The following code sample demonstrates how to customize the visible columns.

{% tabs %}

{% highlight xaml %}

<gantt:SfGantt VisibleGridColumns="Id,Name,StartDate,FinishDate,Progress" 
               ItemsSource="{Binding TaskCollection}" >
</gantt:SfGantt>

{% endhighlight %}

{% highlight C# %}

SfGantt sfGantt = new SfGantt();

sfGantt.ItemsSource = (this.DataContext as ProjectTrackerViewModel).TaskCollection;

sfGantt.VisibleGridColumns = TaskAttributes.ID | TaskAttributes.Name | TaskAttributes.StartDate |
                             TaskAttributes.FinishDate | TaskAttributes.Progress;
						   
{% endhighlight %}

{% endtabs %}

![UWP Gantt with visible columns](SfGantt_images/Getting_Started.jpeg)

## Sorting

Sorting can be enabled using the [`AllowSorting`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.SfGantt.html#Syncfusion_UI_Xaml_Gantt_SfGantt_AllowSorting) property. The sorting functionality is used to arrange the tasks in ascending or descending order based on a column.

The following code sample demonstrates how to enable sorting in the Gantt control.

{% tabs %}

{% highlight xaml %}

<gantt:SfGantt ItemsSource="{Binding TaskCollection}" AllowSorting="True" >

</gantt:SfGantt>

{% endhighlight %}

{% highlight C# %}

SfGantt sfGantt = new SfGantt();

sfGantt.ItemsSource = (this.DataContext as ProjectTrackerViewModel).TaskCollection;

sfGantt.AllowSorting = true;

{% endhighlight %}

{% endtabs %}

![UWP Gantt with sorting feature](SfGantt_images/Sorting.jpeg)

## Editing

Editing can be enabled using the [`AllowEditing`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.SfGantt.html#Syncfusion_UI_Xaml_Gantt_SfGantt_AllowEditing) property. You can edit cells and drag or resize the task bar or progress bar in chart view. The drag-and-drop functionality establishes the relationship between two tasks.

The following code sample demonstrates how to enable editing in the Gantt control.

{% tabs %}

{% highlight xaml %}

<gantt:SfGantt ItemsSource="{Binding TaskCollection}" AllowEditing="True" >

</gantt:SfGantt>

{% endhighlight %}

{% highlight C# %}

SfGantt sfGantt = new SfGantt();

sfGantt.ItemsSource = (this.DataContext as ProjectTrackerViewModel).TaskCollection;

sfGantt.AllowEditing = true;

{% endhighlight %}

{% endtabs %}

N> Now, editing cannot be done in Windows Phones.

## Task relationships

You can visualize the relationship between two tasks in the Gantt. These relationships are categorized into four types based on the start and finish dates of the tasks.

* Start to Start(SS): You cannot start a task until the other task also starts.
* Start to Finish(SF): You cannot finish a task until the other task finishes.
* Finish to Start(FS): You cannot start a task until the other task finishes.
* Finish to Finish(FF): You cannot finish a task until the other task finishes.

The relationship can be created between two tasks by adding the task relationship in predecessor collection for the task in the TaskDetails.

The following code sample demonstrates how to add predecessor in the tasks.

{% highlight C# %}

ScheduleProcess[4].Predecessors.Add(new TaskRelationship()
{
    ID = "37",
    Relationship = Relationship.FinishToStart
});

ScheduleProcess[5].Predecessors.Add(new TaskRelationship()
{
    ID = "38",
    Relationship = Relationship.FinishToStart
});

Planning[3].Predecessors.Add(new TaskRelationship()
{
    ID = "3",
    Relationship = Relationship.FinishToStart
});

Planning[3].Predecessors.Add(new TaskRelationship()
{
    ID = "4",
    Relationship = Relationship.FinishToStart
});

Planning[3].Predecessors.Add(new TaskRelationship()
{
    ID = "5",
    Relationship = Relationship.FinishToStart
});

{% endhighlight %}

![UWP Gantt with task relationship](SfGantt_images/Task_Relationships.jpeg)

### Predecessor offset 

In Gantt, the predecessor [`Offset`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.TaskRelationship.html#Syncfusion_UI_Xaml_Gantt_TaskRelationship_Offset) can be defined with the day duration unit.

The following code sample demonstrates how to define offset time to the predecessor.

{% highlight C# %}

ImplementiationModule1Child[1].Predecessors.Add(new TaskRelationship
{
    ID = "15",
	Offset = 4,
    Relationship = Relationship.FinishToStart
});
ImplementiationModule1Child[2].Predecessors.Add(new TaskRelationship
{
    ID = "16",
	Offset = 2,
    Relationship = Relationship.FinishToStart
});
ImplementiationModule1Child[3].Predecessors.Add(new TaskRelationship
{
    ID = "17",
	Offset = -4,
    Relationship = Relationship.FinishToStart
});
ImplementiationModule1Child[4].Predecessors.Add(new TaskRelationship
{
    ID = "18",
	Offset = -2,
    Relationship = Relationship.FinishToStart
});

{% endhighlight %}
![UWP Gantt with predecessor offset](SfGantt_images/predecessor.jpeg)

## Resources

In the Gantt control, you can display and assign the resource for every task.

1. Create a resource collection to be displayed in Gantt.

{% highlight C# %}

private GanttResourceCollection _resourceCollection;

/// <summary>
/// Gets or sets the SfGantt resources.
/// </summary>
/// <value>The SfGantt resources.</value>
public GanttResourceCollection ResourceCollection
{
    get { return _resourceCollection; }
    set { _resourceCollection = value; }
}

/// <summary>
/// Gets the resources for the project.
/// </summary>
/// <returns></returns>
private GanttResourceCollection GetResources()
{
    GanttResourceCollection Resources = new GanttResourceCollection();
    Resources.Add(new GanttResource { ID = "1", Name = "Project Manager" });
    Resources.Add(new GanttResource { ID = "2", Name = "Developer" });
    Resources.Add(new GanttResource { ID = "3", Name = "Testing Engineer" });
    return Resources;
}

{% endhighlight %}

2. Bind the resource collection to the [`ProjectResources`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.SfGantt.html#Syncfusion_UI_Xaml_Gantt_SfGantt_ProjectResources) property.

{% tabs %}

{% highlight xaml %}

<gantt:SfGantt ItemsSource="{Binding TaskCollection}" ProjectResources="{Binding ResourceCollection}" >

</gantt:SfGantt>

{% endhighlight %}

{% highlight C# %}

SfGantt sfGantt = new SfGantt();

sfGantt.ItemsSource = (this.DataContext as ProjectTrackerViewModel).TaskCollection;

sfGantt.ProjectResources = (this.DataContext as ProjectTrackerViewModel)..ResourceCollection;

{% endhighlight %}

{% endtabs %}

3. Assign the resource to tasks.

{% highlight C# %}

public ObservableCollection<TaskDetail> GetData()
{
    this._resourceCollection = this.GetResources();

    //To define resource for a task.
    Planning[0].Resources.Add("1");
    Planning[1].Resources.Add("1");
    Planning[2].Resources.Add("1");
    ScheduleProcess[3].Resources.Add("2");
    ScheduleProcess[4].Resources.Add("3");
}

{% endhighlight %}

![UWP Gantt can assign the resource for task](SfGantt_images/Resources.jpeg)

## Non-working days

This functionality is used to highlight and customize the weekends in the Gantt control. By default, Saturday and Sunday are considered as weekends.

* [`ShowNonWorkingDays`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.SfGantt.html#Syncfusion_UI_Xaml_Gantt_SfGantt_ShowNonWorkingDays): Enables or disables the non-working days.
* [`NonWorkingDays`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.SfGantt.html#Syncfusion_UI_Xaml_Gantt_SfGantt_NonWorkingDays): Customizes the weekends.
* [`NonWorkingDaysBackground`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.SfGantt.html#Syncfusion_UI_Xaml_Gantt_SfGantt_NonWorkingDaysBackground): Changes the weekends highlighting color.

The following code sample demonstrates how to display Friday as weekend.

{% tabs %}

{% highlight xaml %}

<gantt:SfGantt ItemsSource="{Binding TaskCollection}" NonWorkingDays="Friday" NonWorkingDaysBackground="Blue" >
        <gantt:SfGantt.TimescaleSettings>
            <gantt:TimescaleSettings>
                <gantt:TimescaleSettings.TopTier>
                    <gantt:TimescaleTier IntervalType="Weeks"></gantt:TimescaleTier>
                </gantt:TimescaleSettings.TopTier>
                <gantt:TimescaleSettings.BottomTier>
                    <gantt:TimescaleTier IntervalType="Days"></gantt:TimescaleTier>
                </gantt:TimescaleSettings.BottomTier>
            </gantt:TimescaleSettings>
        </gantt:SfGantt.TimescaleSettings>
</gantt:SfGantt>

{% endhighlight %}

{% highlight C# %}

SfGantt sfGantt = new SfGantt();

sfGantt.ItemsSource = (this.DataContext as ProjectTrackerViewModel).TaskCollection;

sfGantt.NonWorkingDays = Days.Friday;

sfGantt.NonWorkingDaysBackground = new SolidColorBrush(Colors.Blue);

sfGantt.TimescaleSettings.TopTier.IntervalType = IntervalType.Weeks;

sfGantt.TimescaleSettings.BottomTier.IntervalType = IntervalType.Days;

{% endhighlight %}

{% endtabs %}

![UWP Gantt with non-working days feature](SfGantt_images/NonWorkingDays.jpeg)

N> To display the non-working days, either the interval type must be set to week or the less interval type set to days, hours, and minutes.
