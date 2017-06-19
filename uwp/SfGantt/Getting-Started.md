---
layout: post
title: Getting Started for SfGantt
description: The following section provides an assistance to create a simple Gantt application and to configure it.
platform: uwp
control: SfGantt
documentation: ug
---
# Getting started

The following section provides an assistance to create a simple Gantt application and to configure it.

## Referencing Essential Studio Components in your Solution

### Adding SDK reference

1.Open the Reference Manager window from project.
2.Choose Windows > Extensions > Syncfusion Controls for UWP XAML.

![](SfGantt_images/SDK_Reference.jpeg)

### Adding assembly reference

Individual reference can be added to the project instead of SDK “Syncfusion Controls for UWP XAML” which refers all the controls in the Syncfusion control library.

![](SfGantt_images/Gantt_dll_reference.jpeg)

In the Add Reference window, browse and choose the reference assembly from the following location.

**[Installed location]**\Syncfusion\Essential Studio\\**[Installed version]**\Assemblies for Universal Windows\10.0\

The following list of assemblies needs to be added as reference to use SfGantt control in any application,

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
Syncfusion.SfGantt.UWP assembly contains classes that handles all the operations in Gantt.
</td>
</tr>
<tr>
<td>
Syncfusion.Data.UWP
</td>
<td>
Syncfusion.Data.UWP assembly is dependent assembly for Syncfusion.SfGrid.UWP
</td>
</tr>
<tr>
<td>
Syncfusion.SfGrid.UWP
</td>
<td>
Syncfusion.SfGrid.UWP assembly contains classes that handles all UI operations of tree grid view in the Gantt.
</td>
</tr>
<tr>
<td>
Syncfusion.SfInput.UWP
</td>
<td>
Syncfusion.SfInput.UWP contains various editor controls (such as SfNumericTextBox, SfDateTimeEdit and etc) which are used in the tree grid view.
</td>
</tr>
<tr>
<td>
Syncfusion.SfShared.UWP
</td>
<td>
Syncfusion.SfShared.UWP is dependent assembly for Syncfusion.SfInput.UWP.
</td>
</tr>
</table>

## Adding SfGantt manually

1.After adding the required assembly references to the project as discussed in the Reference Essential Studio Components in your Solution section.

2.Add the “Syncfusion.UI.Xaml.Gantt” namespace to the application as shown below.

{% tabs %}

{% highlight xaml %}

xmlns:gantt="using:Syncfusion.UI.Xaml.Gantt"

{% endhighlight %}

{% highlight C# %}

using Syncfusion.UI.Xaml.Gantt;

{% endhighlight %}

{% endtabs %}

3.Instance the Gantt as like in the below code.

{% tabs %}

{% highlight xaml %}

<gantt:SfGantt></gantt:SfGantt>

{% endhighlight %}

{% highlight C# %}

SfGantt gantt = new SfGantt();

{% endhighlight %}

{% endtabs %}

## Adding SfGantt from toolbox

Drag and drop the Gantt control from the toolbox to your application.

![](SfGantt_images/Tool_Box.jpeg)

Now the “Syncfusion Controls for UWP XAML” reference is added to the application references and the xmlns namespace code is generated in MainWindow.xaml as below.

![](SfGantt_images/Added_SDK.jpeg)

![](SfGantt_images/XAML_Reference.jpeg)

## Create data model

You need to create a collection of TaskDetails objects to populate task in SfGantt.

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
            StartDate = new DateTime(2014, 2, 3),
            FinishDate = new DateTime(2014, 3, 6),
            Name = "Project Schedule",
            ID = "1"
        });

        ObservableCollection<TaskDetail> ScheduleProcess = new ObservableCollection<TaskDetail>();

        ScheduleProcess.Add(new TaskDetail
        {
            StartDate = new DateTime(2014, 3, 20),
            FinishDate = new DateTime(2014, 3, 27),
            Name = "Planning",
            ID = "2"
        });

        ScheduleProcess.Add(new TaskDetail
        {
            StartDate = new DateTime(2014, 3, 20),
            FinishDate = new DateTime(2014, 4, 4),
            Name = "Design",
            ID = "7"
        });

        ScheduleProcess.Add(new TaskDetail
        {
            StartDate = new DateTime(2014, 3, 9),
            FinishDate = new DateTime(2014, 4, 8),
            Name = "Implementation Phase",
            ID = "12"
        });

        ScheduleProcess.Add(new TaskDetail
        {
            StartDate = new DateTime(2014, 3, 27),
            FinishDate = new DateTime(2014, 4, 28),
            Name = "Integration",
            ID = "37"
        });

        ScheduleProcess.Add(new TaskDetail
        {
            StartDate = new DateTime(2014, 3, 25),
            FinishDate = new DateTime(2014, 4, 26),
            Name = "Final Testing",
            ID = "38"
        });

        ScheduleProcess.Add(new TaskDetail
        {
            StartDate = new DateTime(2014, 3, 26),
            FinishDate = new DateTime(2014, 3, 26),
            Name = "Final Delivery",
            ID = "39"
        });

        Schedule[0].Children = ScheduleProcess;

        ObservableCollection<TaskDetail> Planning = new ObservableCollection<TaskDetail>();

        Planning.Add(new TaskDetail
        {
            StartDate = new DateTime(2014, 3, 27),
            FinishDate = new DateTime(2014, 4, 7),
            Name = "Plan timeline",
            ID = "3",
            Progress = 100
        });

        Planning.Add(new TaskDetail
        {
            StartDate = new DateTime(2014, 3, 28),
            FinishDate = new DateTime(2014, 4, 10),
            Name = "Plan budget",
            ID = "4",
            Progress = 100
        });

        Planning.Add(new TaskDetail
        {
            StartDate = new DateTime(2014, 3, 27),
            FinishDate = new DateTime(2014, 4, 8),
            Name = "Allocate resources",
            ID = "5",
            Progress = 100
        });

        Planning.Add(new TaskDetail
        {
            StartDate = new DateTime(2014, 3, 27),
            FinishDate = new DateTime(2014, 3, 27),
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

To bind the data source of the SfGantt, set **ItemsSource** property as shown below.

{% tabs %}

{% highlight xaml %}

<gantt:SfGantt ItemsSource="{Binding TaskCollection}" />

{% endhighlight %}

{% highlight C# %}

SfGantt gantt = new SfGantt() { ItemsSource = this.taskDetails.TaskCollection };

{% endhighlight %}

{% endtabs %}

## Defining visible columns

By default, the grid view is manipulated with Name, Start Date, Finish Date, Duration, Progress, Predecessor and Resources columns.

You can also customize the visible columns of grid view using **VisibleGridColumns** property in SfGantt.

The following code example illustrates how this can be done.

{% tabs %}

{% highlight xaml %}

<gantt:SfGantt VisibleGridColumns="Id,Name,StartDate,FinishDate,Progress" 
               ItemsSource="{Binding TaskCollection}" >
</gantt:SfGantt>

{% endhighlight %}

{% highlight C# %}

SfGantt gantt = new SfGantt();

gantt.ItemsSource = this.taskDetails.TaskCollection;

gantt.VisibleGridColumns = TaskAttributes.ID | TaskAttributes.Name | TaskAttributes.StartDate |
                           TaskAttributes.FinishDate | TaskAttributes.Progress;
						   
{% endhighlight %}

{% endtabs %}

![](SfGantt_images/Getting_Started.jpeg)

## Sorting

The Gantt control has sorting functionality to arrange the tasks in ascending or descending order based on a column.

The below code illustrates how to enable sorting in the Gantt control.

{% tabs %}

{% highlight xaml %}

<gantt:SfGantt ItemsSource="{Binding TaskCollection}" AllowSorting="True" >

</gantt:SfGantt>

{% endhighlight %}

{% highlight C# %}

SfGantt gantt=new SfGantt();

gantt.ItemsSource = this.taskDetails.TaskCollection;

gantt.AllowSorting = true;

{% endhighlight %}

{% endtabs %}

![](SfGantt_images/Sorting.jpeg)

## Editing

You can enable editing using **AllowEditing** property in the Gantt. Editing can be done by cell editing in grid or drag/resize the task bar or progress bar in chart view, also drag and drop to establish relationship between the two tasks.

The below code illustrates enabling the editing in Gantt.

{% tabs %}

{% highlight xaml %}

<gantt:SfGantt ItemsSource="{Binding TaskCollection}" AllowEditing="True" >

</gantt:SfGantt>

{% endhighlight %}

{% highlight C# %}

SfGantt gantt = new SfGantt();

gantt.ItemsSource = this.taskDetails.TaskCollection;

gantt.AllowEditing = true;

{% endhighlight %}

{% endtabs %}

## Task relationships

You can visualize the relationship between two tasks in the Gantt. These relationships are categorized into four types based on the start and finish date of the task.

* Start to Start(SS) - You cannot start a task until the other task also starts.
* Start to Finish(SF) - You cannot finish a task until the other task finishes.
* Finish to Start(FS) - You cannot start a task until the other task completes.
* Finish to Finish(FF) - You cannot finish a task until the other task completes.

The relationship can be created between two tasks, by adding the task relationship in predecessor collection for the task in the TaskDetails.

The below code illustrates adding the predecessor in the tasks.

{% highlight C# %}

Planning[3].Predecessors.Add(new TaskRelationship()
{
    ID = "7",
    Relationship = Relationship.FinishToStart
});

ScheduleProcess[1].Predecessors.Add(new TaskRelationship()
{
    ID = "12",
    Relationship = Relationship.FinishToStart
});

ScheduleProcess[2].Predecessors.Add(new TaskRelationship()
{
    ID = "37",
    Relationship = Relationship.FinishToStart
});

ScheduleProcess[3].Predecessors.Add(new TaskRelationship()
{
    ID = "38",
    Relationship = Relationship.FinishToStart
});

{% endhighlight %}

![](SfGantt_images/Task_Relationships.jpeg)

## Resources

In Gantt control, you can display and assign the resource for each task.

1.Create the resource collection to be displayed in Gantt.

{% highlight C# %}

private GanttResourceCollection _resourceCollection;

/// <summary>
/// Gets or sets the gantt resources.
/// </summary>
/// <value>The gantt resources.</value>
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
    Resources.Add(new GanttResource { ID = "1", Name = "Leslie" });
    Resources.Add(new GanttResource { ID = "2", Name = "John" });
    Resources.Add(new GanttResource { ID = "3", Name = "David" });
    Resources.Add(new GanttResource { ID = "4", Name = "Peter" });
    Resources.Add(new GanttResource { ID = "5", Name = "David" });
    return Resources;
}

{% endhighlight %}

2.Bind the resource collection to the property **ProjectResources** property in SfGantt.

{% tabs %}

{% highlight xaml %}

<gantt:SfGantt ItemsSource="{Binding TaskCollection}" ProjectResources="{Binding ResourceCollection}" >

</gantt:SfGantt>

{% endhighlight %}

{% highlight C# %}

SfGantt gantt = new SfGantt();

gantt.ItemsSource = this.taskDetails.TaskCollection;

gantt.ProjectResources = this.taskDetails.ResourceCollection;

{% endhighlight %}

{% endtabs %}

3.Assign the resource to the tasks.

{% highlight C# %}

public ObservableCollection<TaskDetail> GetData()
{
    this._resourceCollection = this.GetResources();

    //To define resource for a task.
    ScheduleProcess[0].Resources.Add("0");
    ScheduleProcess[1].Resources.Add("1");
    ScheduleProcess[2].Resources.Add("2");
    ScheduleProcess[3].Resources.Add("3");
    ScheduleProcess[4].Resources.Add("4");
    ScheduleProcess[5].Resources.Add("5");
}

{% endhighlight %}

![](SfGantt_images/Resources.jpeg)

## Non-working days

To highlight and customize the weekends in the Gantt. By default, Saturday and Sunday is considered as weekends.

* **ShowNonWorkingDays** property can be used to enable or disable the non-working 
* **NonWorkingDays** property can be used to customize the weekends.
* **NonWorkingDaysBackground** property can be used change the weekends highlighting color.

The below code illustrates how to display the weekend as Friday.

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

SfGantt gantt = new SfGantt();

gantt.ItemsSource = this.taskDetails.TaskCollection;

gantt.NonWorkingDays = Days.Friday;

gantt.NonWorkingDaysBackground = new SolidColorBrush(Colors.Blue);

gantt.TimescaleSettings.TopTier.IntervalType = IntervalType.Weeks;

gantt.TimescaleSettings.BottomTier.IntervalType = IntervalType.Days;

{% endhighlight %}

{% endtabs %}

![](SfGantt_images/NonWorkingDays.jpeg)

N>To display non-working days the interval type must be week or lesser interval type as days, hours and minutes.
