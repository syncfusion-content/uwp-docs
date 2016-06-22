---
layout: post
title: Getting started with Syncfusion Essential Diagram for UWP.
description: Getting started walk through to create your Organizational Chart Diagram.
platform: uwp
control: SfDiagram
documentation: ug
---

# Getting Started

The following section helps you to build your application with SfDiagram. 

## Steps

   * Create new Universal Windows project using Visual Studio.
   * Add the SfDiagram assembly to your application. 
   * Initialize SfDiagram control.
   * Initialize Nodes and Connectors.
   * Create class to store employee information.
   * Initialize Data.   
   * Initialize DataSourceSettings.
   * Visualize Employees.
   * Initialize Layout.

**Creating Simple Diagram**

This section demonstrates how to visualize the Employee details in the Organizational Chart arrangement by using the SfDiagram.

##Adding assembly reference
  
    1. Open the Add reference window from your project.
    2. Choose Windows > Extensions > Syncfusion Controls for UWP XAML.
    
![](Getting-Started_images\Getting_Started_img.png)

###Add the SfDiagram from the Toolbox

Drag and drop the SfDiagram control from the Toolbox to the XAML Page.

![](Getting-Started_images/Getting-Started_img1.jpeg)

The xmlns name space is added to the MainPage.xaml

![](Getting-Started_images/Getting-Started_img2.jpeg)

###Initialize the diagram

The SfDiagram exists in the Syncfusion.UI.Xaml.Diagram namespace. Initialize SfDiagram to the XAML Page as shown in the following code sample.

{% highlight xaml %}

<Grid Background="White">
    <!--Initializes the SfDiagram-->
    <syncfusion:SfDiagram x:Name="diagram">
    </syncfusion:SfDiagram>
</Grid>

{% endhighlight %}

###Initialize nodes and connectors

To initialize the Nodes and Connectors properties of the SfDiagram, Nodes property is assigned with the NodeCollection, that is, ObservableCollection of the Node. Connector’s property is assigned with the ConnectorCollection, that is, ObservableCollection of the Connector.

{% highlight xaml %}

<!--Initializes the NodeCollection-->
<syncfusion:SfDiagram.Nodes>
	<syncfusion:NodeCollection/>
</syncfusion:SfDiagram.Nodes>
<!--Initializes the ConnectorCollection-->
<syncfusion:SfDiagram.Connectors>
	<syncfusion:ConnectorCollection/>
</syncfusion:SfDiagram.Connectors>

{% endhighlight %}

###Create class to store employee information

Now, you have to create a class, Employee with properties to store the employee’s information like name, designation, ID, reporting person ID, etc. You also have to create a collection that stores a collection of the employees.

{% highlight C# %}

//Employee Business Object
public class Employee
{
    public string ParentId { get; set; }
    public string Name { get; set; }
    public string Designation { get; set; }
    public int EmpId { get; set; }
}

//Employee Collection
public class Employees : ObservableCollection<Employee>
{

}

{% endhighlight %}

###Initialize Data

Create a collection of employees with each employee having an ID in the Emp id and the reporting person’s ID in the Parent ID. This collection is placed in the Window resource and later incorporated in the Diagram. This is explained in the next point.

{% highlight xaml %}

<!-- Initializes the employee colletion-->
<local:Employees x:Key="Employees">
    <local:Employee Name="Elizabeth" EmpId="1" ParentId="" Designation="CEO"/>
    <local:Employee Name="Christina" EmpId="2" ParentId="1" Designation="Manager"/>
    <local:Employee Name="Yang" EmpId="3" ParentId="1" Designation="Manager"/>
    <local:Employee Name="Yoshi" EmpId="4" ParentId="2" Designation="TeamLead"/>
    <local:Employee Name="Philip" EmpId="5" ParentId="2" Designation="TeamLead"/>
    <local:Employee Name="Roland" EmpId="6" ParentId="3" Designation="TeamLead"/>
    <local:Employee Name="Yuonne" EmpId="7" ParentId="3" Designation="TeamLead"/>
</local:Employees>

{% endhighlight %}

###Initialize DataSourceSettings

To populate employee information as Nodes and connectors, configure the DataSourceSettings with the DataSource, ID, and ParentId. The ID property is used as a unique identifier for each Node, and the parent ID represents the parent Node where a Node has to be connected. The following code example illustrates how to define the DataSourceSetting and set it to the Diagram.

{% highlight xaml %}

<!--Initializes the DataSourceSettings-->

<syncfusion:DataSourceSettings x:Key="DataSourceSettings" ParentId="ParentId"							    
                               Id="EmpId">
</syncfusion:DataSourceSettings>

{% endhighlight %}

###Visualize Employees

Now, Diagram is configured to load the employees’ information as a tree of organization chart. Next, give visual appearance for the Node. To visualize the employees’ details in the Node, a Node has to be created for each employee, and then the employee’s details are stored in the Node’s content property. To visualize the employee information, define the appearance as a data template and apply it to the Node’s content template as shown in the following code example.

{% highlight xaml %}

<Page.Resources>
	<ResourceDictionary>
		<!--Style for the Node>-->
		<Style TargetType="syncfusion:Node">
			        <Setter Property="UnitWidth" Value="80" />
	            	<Setter Property="UnitHeight" Value="40" />
		            <Setter Property="FontSize" Value="15"></Setter>
	       		    <Setter Property="Foreground" Value="Black"></Setter>
	                <Setter Property="HorizontalContentAlignment" Value="Stretch"></Setter>
        	        <Setter Property="VerticalContentAlignment" Value="Stretch"></Setter>
                	<Setter Property="ContentTemplate">
                		<Setter.Value>
                        		<DataTemplate>
                            			<Border Background="#008b8b" CornerRadius="5">
	                                		<TextBlock Text="{Binding Name}" Foreground="White"
                                           		   	   HorizontalAlignment="Center" VerticalAlignment="Center"/>
	                            		</Border>
	                        	</DataTemplate>
				       </Setter.Value>
                   </Setter>
		</Style>
		<!--Style for the Connector>-->
		<Style TargetType="syncfusion:Connector">
        		<Setter Property="ConnectorGeometryStyle">
                		<Setter.Value>
                        		<Style TargetType="Path">
                            			<Setter Property="Stroke" Value="Black" />
                            			<Setter Property="StrokeThickness" Value="1" />
	                        	</Style>
                        </Setter.Value>
               </Setter>
		</Style>
	</ResourceDictionary>
</<Page.Resources>

{% endhighlight %}

###Initialize Layout

Employees are initialized, populated in the Diagram, and appearance for employees are defined. Now, place the Nodes and Connector by using the layout manager. The following code example shows how to initialize the LayoutManager, specify the layout as the DirectedTreeLayout and set it to the Diagram.

{% highlight xaml %}

<!--Initializes the Layout-->

<syncfusion:DirectedTreeLayout x:Key="TreeLayout" HorizontalSpacing="80" 
		                       VerticalSpacing="50" SpaceBetweenSubTrees="20" 
		                       Orientation="TopToBottom"/>
<syncfusion:LayoutManager x:Key="LayoutManager"  
                          Layout="{StaticResource TreeLayout}"/>

<Grid Background="White">
    <!--Initializes the SfDiagram-->
	<syncfusion:SfDiagram x:Name="diagram"
	                      LayoutManager="{StaticResource LayoutManager}">
        </syncfusion:SfDiagram>
</Grid>

{% endhighlight %}

The final MainPage.Xaml looks like this.

{% highlight xml %}

<Page
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:local="using:EmployeeDetails"
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
    xmlns:syncfusion="using:Syncfusion.UI.Xaml.Diagram"
    xmlns:layout="using:Syncfusion.UI.Xaml.Diagram.Layout"
    x:Class="EmployeeDetails.MainPage"
    mc:Ignorable="d">

    <Page.Resources>

        <!-- Initializes the employee colletion-->

        <local:Employees x:Key="Employees">

            <local:Employee Name="Elizabeth" EmpId="1" ParentId="" Designation="CEO"/>
            <local:Employee Name="Christina" EmpId="2" ParentId="1" Designation="Manager"/>
            <local:Employee Name="Yang" EmpId="3" ParentId="1" Designation="Manager"/>
            <local:Employee Name="Yoshi" EmpId="4" ParentId="2" Designation="TeamLead"/>
            <local:Employee Name="Philip" EmpId="5" ParentId="2" Designation="TeamLead"/>
            <local:Employee Name="Roland" EmpId="6" ParentId="3" Designation="TeamLead"/>
            <local:Employee Name="Yuonne" EmpId="7" ParentId="3" Designation="TeamLead"/>

        </local:Employees>

        <!--Initializes the DataSourceSettings -->

        <syncfusion:DataSourceSettings x:Key="DataSourceSettings" ParentId="ParentId"							     
                                       Id="EmpId" DataSource="{StaticResource Employees}">
        </syncfusion:DataSourceSettings>

        <!--Style for the Node>-->

        <Style TargetType="syncfusion:Node">
            <Setter Property="UnitWidth" Value="80" />
            <Setter Property="UnitHeight" Value="40" />
            <Setter Property="FontSize" Value="15"></Setter>
            <Setter Property="Foreground" Value="Black"></Setter>
            <Setter Property="HorizontalContentAlignment" Value="Stretch"></Setter>
            <Setter Property="VerticalContentAlignment" Value="Stretch"></Setter>
            <Setter Property="ContentTemplate">
                <Setter.Value>
                    <DataTemplate>
                        <Border Background="#008b8b" 
                                CornerRadius="5">
                            <TextBlock Text="{Binding Name}" Foreground="White"
                                       HorizontalAlignment="Center"  VerticalAlignment="Center"/>
                        </Border>
                    </DataTemplate>
                </Setter.Value>
            </Setter>
        </Style>
        
        <!--Style for the Connector>-->

        <Style TargetType="syncfusion:Connector">
            <Setter Property="ConnectorGeometryStyle">
                <Setter.Value>
                    <Style TargetType="Path">
                        <Setter Property="Stroke" Value="Black" />
                        <Setter Property="StrokeThickness" Value="1" />
                    </Style>
                </Setter.Value>
            </Setter>
        </Style>

        <!--Initializes the Layout-->

        <layout:DirectedTreeLayout x:Key="TreeLayout" 
		                           HorizontalSpacing="80" 
		                           VerticalSpacing="50" 
		                           SpaceBetweenSubTrees="20" 
		                           Orientation="TopToBottom"/>

        <layout:LayoutManager x:Key="LayoutManager"  
		                      Layout="{StaticResource TreeLayout}"/>


    </Page.Resources>

    <Grid Background="White">
        <!--Initializes the SfDiagram-->
        <syncfusion:SfDiagram x:Name="diagram"
	                          DataSourceSettings="{StaticResource DataSourceSettings}"
	                          LayoutManager="{StaticResource LayoutManager}">
            <!--Initializes the NodeCollection-->
            <syncfusion:SfDiagram.Nodes>
                <syncfusion:NodeCollection />
            </syncfusion:SfDiagram.Nodes>
            <!--Initializes the ConnectorCollection-->
            <syncfusion:SfDiagram.Connectors>
                <syncfusion:ConnectorCollection/>
            </syncfusion:SfDiagram.Connectors>
        </syncfusion:SfDiagram>
    </Grid>

</Page>

{% endhighlight %}

The Employee data is displayed in the SfDiagram as follows

![](Getting-Started_images/Getting-Started_img3.jpeg)