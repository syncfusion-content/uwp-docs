---
layout: post
title: Populate Diagram from external data sources.
description: How to populate the Diagram from the local data?
platform: uwp
control: SfDiagram
documentation: ug
---

#DataSource

SfDiagram is populated with the Node taken from an external hierarchical data source. SfDiagram exposes its specific, data-related properties and allows you to specify the data source fields where the node information is retrieved from.

##DataSource Settings

Two mapping fields are necessary to map a hierarchical datasource with the diagram. Id property is used for unique identification of a record. ParentId property is used to identify the parent object to which a particular object is connected.

| Properties | Description | Value |
|---|---|---|
| DataSource | Data source based on the diagram that is to be generated. | Object |
| ParentId | Specifies the mapping parent id property of the data source items. | String |
| Id | Specified the mapping unique id property of data source items. | String |
| Root | Specifies the root element of the data source items. | String |

###DataSource

The following code example illustrates how to bind data to SfDiagram.

{% highlight C# %}

//Creates the Node and Connector collection
diagram.Nodes = new ObservableCollection<Node>();
diagram.Connectors = new ObservableCollection<Connector>();

//Initializes the DataSourceSettings
DataSourceSettings dataSourceSetttings = new DataSourceSettings();
     
//Sets ParentId-For Relation                
dataSourceSetttings.ParentId = "ParentId";

//Sets ID-for Mapping
dataSourceSetttings.Id = "EmpId";

//Specifies the root element 
dataSourceSetttings.Root = "1";

//Creates Data
ObservableCollection<Employee> employee = new ObservableCollection<Employee>();
            employee.Add(new Employee() { Name = "Steve", EmpId = 1, ParentId = "",
                                          Designation = "CEO" });
            employee.Add(new Employee() { Name = "Kevin", EmpId = 2, ParentId = "1", 
                                          Designation = "Manager" });
            employee.Add(new Employee() { Name = "John", EmpId = 3, ParentId = "1", 
                                          Designation = "Manager" });
            employee.Add(new Employee() { Name = "Raj", EmpId = 4, ParentId = "2", 
                                          Designation = "Team Lead" });
            employee.Add(new Employee() { Name = "Will", EmpId = 5, ParentId = "2", 
                                          Designation = "S/w Developer" });
            employee.Add(new Employee() { Name = "Sarah", EmpId = 6, ParentId = "3", 
                                          Designation = "TeamLead" });
            employee.Add(new Employee() { Name = "Mike", EmpId = 7, ParentId = "3",
                                          Designation = "Testing Engineer" });
 
//Assigns Collection         
dataSourceSetttings.DataSource = employee;
diagram.DataSourceSettings = dataSourceSetttings;

{% endhighlight %}

![](DataSource_images/DataSource_img1.jpeg)

##DataSource Root

During Automatic Layout, Node without parent is treated as Root of the layout. But, now we have provided the option to specify this Root by using the DataSource settings.

The following code illustrates how to specify the root object for the Diagram**.**

{% highlight C# %}

//Object with id “CEO”, is considered as root of tree layout.
diagram.DataSourceSettings.Root = “CEO”;

{% endhighlight %}

![](DataSource_images/DataSource_img2.jpeg)
