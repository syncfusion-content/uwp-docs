---
layout: post
title: Getting Started | SfKanban | uwp | Syncfusion
description: getting started
platform: uwp
control: SfKanban
documentation: ug
---
# Getting started 

The following section provides an assistance to create a simple Kanban application and to configure it. 

## Referencing Essential Studio Components in your Solution

### Adding SDK reference

1. Open the Reference Manager window from project.
2. Choose Windows > Extensions > Syncfusion Controls for UWP XAML.

![](SfKanban_images/new_kanban_img1.jpeg)


### Adding assembly reference

Individual reference can be added to the project instead of SDK “Syncfusion Controls for UWP XAML” which refers all the controls in the Syncfusion control library.

![](SfKanban_images/new_kanban_img2.jpeg)


In the Add Reference window, browse and choose the reference assembly from the following location. 

Installed location\Syncfusion\Essential Studio\Installed version\Assemblies for Universal Windows\10.0\Syncfusion.SfKanban.UWP.dll

## Create a simple Kanban

In this walk through, you will create a new application that contains the SfKanban which includes the below topics.

* Adding SfKanban 
* Create data model
* Binding data
* Defining columns
* Working with Workflows
* Work In-Progress Limit

### Adding SfKanban


1. Add the required assembly references to the project as discussed in the Reference Essential Studio Components in your Solution section.
2. Add the “Syncfusion.UI.Xaml.Kanban” namespace to the application as shown below.

{% tabs %}

{% highlight xaml %}
xmlns:syncfusion="using:Syncfusion.UI.Xaml.Kanban"
{% endhighlight %}

{% highlight c# %}
using Syncfusion.UI.Xaml.Kanban;
{% endhighlight %}

{% endtabs %}

3. Create an instance of SfKanban control.

{% tabs %}

{% highlight xaml %}
<syncfusion:SfKanban>

</syncfusion:SfKanban>
{% endhighlight %}

{% highlight c# %}

SfKanban kanban = new SfKanban();

{% endhighlight %}

{% endtabs %}

### Adding SfKanban from toolbox

Drag and drop the Kanban control from the toolbox to your application.

![](SfKanban_images/new_kanban_img3.jpeg)


Now the “Syncfusion Controls for UWP XAML” reference is added to the application references and the xmlns namespace code is generated in MainWindow.xaml as below.

![](SfKanban_images/new_kanban_img4.jpeg)


![](SfKanban_images/new_kanban_img5.jpeg)


### Create data model

You need to create a collection of KanbanModel objects for populating SfKanban.

{% highlight c# %}
   
    public class TaskDetails
    {
        public TaskDetails()
        {

            Tasks = new ObservableCollection<KanbanModel>();

            Tasks.Add(new KanbanModel()
            {

                Title = "Universal App",

                ID = "27654",

                Description = "Incorporate feedback into functional specifications",

                Category = "Open",

                ColorKey = "Low",

                Tags = new string[] { "Deployment" },

                ImageURL = new Uri("ms-appx:///images/icon.jpg"),
            });


            Tasks.Add(new KanbanModel()
            {

                Title = "Universal App",

                ID = "29477",

                Description = "Design functional specifications",

                Category = "In Progress",

                ColorKey = "Normal",

                Tags = new string[] { "Design" },

                ImageURL = new Uri("ms-appx:///images/icon.jpg"),
            });


            Tasks.Add(new KanbanModel()
            {
                Title = "Universal App",

                ID = "25678",

                Description = "Review preliminary software specifications",

                Category = "Done",

                ColorKey = "Low",

                Tags = new string[] { "Analysis" },

                ImageURL = new Uri("ms-appx:///images/icon.jpg"),
            });


            Tasks.Add(new KanbanModel()
            {
                Title = "Universal App",

                ID = "6593",

                Description = "Draft preliminary software specifications",

                Category = "Review",

                ColorKey = "High",

                Tags = new string[] { "Analysis" },

                ImageURL = new Uri("ms-appx:///images/icon.jpg"),

            });
        }
        public ObservableCollection<KanbanModel> Tasks { get; set; }
    }

{% endhighlight %}

### Binding data

In order to bind the data source of the SfKanban, set ItemsSource property as shown below.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfKanban ItemsSource="{Binding Tasks}" />

{% endhighlight %}

{% highlight c# %}

SfKanban kanban = new SfKanban()
{
    ItemsSource = new TaskDetails().Tasks
};

{% endhighlight %}


{% endtabs %}

### Defining columns

By default, we need to define the columns manually by adding the KanbanColumn object to the Columns collection property in SfKanban.

ItemsSource which was bound to the Kanban will be added to the respective columns using ColumnMappingPath property in SfKanban and Categories property in KanbanColumn.

We need to set the required property name to ColumnMappingPath which will be essential to add the data to the respective columns.

In this example, the data whose Category property’s value is set as Open will be added to the ‘To Do’ Column and other data will be added to the respective columns.

The following code example illustrates how this can be done.

{% tabs %}

{% highlight xaml %}

  <syncfusion:SfKanban MinColumnWidth="150" 
                       ColumnMappingPath="Category" 
                       ItemsSource="{Binding Tasks}"
                       AutoGenerateColumns="False">

            <syncfusion:KanbanColumn Categories="Open" Title="To Do"></syncfusion:KanbanColumn>

            <syncfusion:KanbanColumn Categories="In Progress" Title="Progress"></syncfusion:KanbanColumn>

            <syncfusion:KanbanColumn Categories="Review,Done" Title="Done"></syncfusion:KanbanColumn>

</syncfusion:SfKanban>


{% endhighlight %}

{% highlight c# %}

SfKanban kanban = new SfKanban()
{
    AutoGenerateColumns = false,
    ItemsSource = new TaskDetails().Tasks
};

kanban.Columns.Add(new KanbanColumn()
{
    Categories = "Open",
    Title = "To Do",
    MinimumLimit = 1,
    MaximumLimit = 2,
});

kanban.Columns.Add(new KanbanColumn()
{
    Categories = "In Progress",
    Title = "Progress",
    MinimumLimit = 1,
    MaximumLimit = 2
});

kanban.Columns.Add(new KanbanColumn()
{
    Categories = "Review,Done",
    Title = "Done",
    MinimumLimit = 1,
    MaximumLimit = 2
});

grid.Children.Add(kanban);


{% endhighlight %}

{% endtabs %}

![](SfKanban_images/column.png)


You can also set AutoGenerateColumns property to true in which you don’t need to define the columns as mentioned in the above example. This will create columns depending on the ColumnMappingPath property for all the distinct values in ItemsSource.

N> When the columns are auto-generated, you can handle the ColumnsGenerated event to customize the columns.

### Workflow configuration

A Kanban workflow is a set of Category and AllowedTransitions that an item moves through its life cycle and typically represents processes within your organization.

* Category – It represents a state of an item at a particular point in a specific workflow.

* AllowedTransitions – It is a list of categories to where the card can be moved from the current category.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfKanban.Workflows>
    <syncfusion:KanbanWorkflow Category="Open">
        <syncfusion:KanbanWorkflow.AllowedTransitions>
            <x:String>In Progress</x:String>
        </syncfusion:KanbanWorkflow.AllowedTransitions>
    </syncfusion:KanbanWorkflow>

    <syncfusion:KanbanWorkflow Category="In Progress">
        <syncfusion:KanbanWorkflow.AllowedTransitions>
            <x:String>Review</x:String>
            <x:String>Done</x:String>
        </syncfusion:KanbanWorkflow.AllowedTransitions>
    </syncfusion:KanbanWorkflow>
</syncfusion:SfKanban.Workflows>

{% endhighlight %}

{% highlight c# %}

WorkflowCollection workflows = new WorkflowCollection();

workflows.Add(new KanbanWorkflow()
{
    Category = "Open",
    AllowedTransitions = new List<object>() {"In Progress"}
});

workflows.Add(new KanbanWorkflow()
{
    Category = "In Progress",
    AllowedTransitions = new List<object>() {"Review", "Done"}
});

Kanban.Workflows = workflows;

{% endhighlight %}

{% endtabs %}

![](SfKanban_images/workflow.png)


### Work In-Progress limit

MinimumLimit and MaximumLimit properties are used to limit the minimum and maximum items in the Kanban column. However, this will not restrict moving the items from one column to another column. But the violation of the limit can be indicated by changing the color of the error bar.

Following properties are used to customize the error bar.

* Color – used to set the default color of the error bar.

* MinValidationColor – used to set the color of the error bar when the items count is lesser than MinimumLimit.

* MaxValidationColor – used to set the color of the error bar when the items count is greater than MaximumLimit.

{% tabs %}

{% highlight xaml %}

<syncfusion:KanbanColumn x:Name="column1" Categories="Review,Done"
                         Title="Done"
                         MinimumLimit="1"
                         MaximumLimit="2">
	     <syncfusion:KanbanColumn.ErrorBarSettings>
			   <syncfusion:ErrorBarSettings Color="Gray" MaxValidationColor="Red"
                                            MinValidationColor="Green">
			   </syncfusion:ErrorBarSettings>
         </syncfusion:KanbanColumn.ErrorBarSettings>
</syncfusion:KanbanColumn>

{% endhighlight %}

{% highlight c# %}

column1.MinimumLimit = 1;
column1.MaximumLimit = 2;
column1.ErrorBarSettings = new ErrorBarSettings()
{
    Color = new SolidColorBrush(Colors.Gray),
    MinValidationColor = new SolidColorBrush(Colors.Green),
    MaxValidationColor = new SolidColorBrush(Colors.Red)
};


{% endhighlight %}

{% endtabs %}

![](SfKanban_images/wiplimit.png)


