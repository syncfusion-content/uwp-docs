---
layout: post
title: PivotClient Components | SfPivotClient | UWP | Syncfusion
description: PivotClient Components
platform: UWP
control: SfPivotClient
documentation: ug
---

# PivotClient: Components

## Cube Selector

Cube selector allows you to select any one of the cube from cubes available in the connected database. This can be achieved by selecting the **Data Connection** menu item from the reports menu. The cube selector dialog will be opened with a drop-down list, displaying the list of cubes available in the current connection. The SfPivotClient will load the corresponding cube elements while changing the cube from the drop-down list.

![](PivotClient-Components_images/toolBar_ReportMenu_1.png)

![](PivotClient-Components_images/toolBar_ReportMenu_2.png)

![](PivotClient-Components_images/cubeSelector.png)

## Cube dimension browser

Cube dimension browser is a tree-view like structure that organizes the cube elements such as dimensions, hierarchies, measures, etc., from the selected cube into independent and logical groups.

### Node types

* Display folder - Folder that contains a set of similar elements.
* Measure - Quantity available for analysis.
* Dimension - A name given to the parts of the cube that categorize the data.
* Attribute hierarchy - Level of attributes down the hierarchy.
* User-defined hierarchy - Members of a dimension in a hierarchical structure.
* Level - Denotes a specific level in the category.
* Named set - A collection of tuples and members, which can be defined and saved as a part of the cube definition.

**Attribute hierarchy**

Attribute hierarchy contains the following levels:

* Leaf level contains each distinct attribute member, which are called leaf.
* Intermediate level if the attribute hierarchy is a parent-child hierarchy.

**User-defined hierarchy**

User-defined hierarchy organizes the members of a dimension into hierarchical structure and provides navigation paths in a cube. For example, take a dimension table that supports three attributes such as year, quarter, and month. The year, quarter and month attributes are used to construct a user-defined hierarchy and named calendar in the time dimension which relates all the levels.

**Differentiating user-defined hierarchy and attribute hierarchy**

* User-defined hierarchy contains more than one level whereas attribute hierarchy contains only one level.
* User-defined hierarchy provides the navigation path between the levels taken from attribute hierarchies of the same dimension.

### Symbolic representation of nodes

| Icon | Name | Node type | Is Draggable |
| -------- | -------- | -------- | -------- |
| ![](PivotClient-Components_images/displayFolder.ico) | Display Forlder | Display Folder | False |
| ![](PivotClient-Components_images/measures.ico) | Measure | Measure | True |
| ![](PivotClient-Components_images/dimensions.ico) | Dimension | Dimension | True |
| ![](PivotClient-Components_images/userDefinedHierarchy.ico) | User Defined Hierarchy | Hierarchy | True |
| ![](PivotClient-Components_images/attributeHierarchy.ico) | Attribute Hierarchy | Hierarchy | True |
| ![](PivotClient-Components_images/levelsInOrder.ico) | Levels (in order) | Level Element | True |
| ![](PivotClient-Components_images/namedSets.ico) | Named Set | Named Set | True |
| ![](PivotClient-Components_images/calculatedMembers.ico) | Calculated Members | Calculated Member | True|
| ![](PivotClient-Components_images/kpi.ico) | Virtual KPI | VirtualKpi Member | True|
| ![](PivotClient-Components_images/kpi.ico) | KPI | Kpi Member | True|

## Axis element builder

Axis element builder allows you to build elements in the axes of the SfPivotClient. It supports four axes namely categorical, series, filter(slicer), and value. Based on the construction of axes, the SfPivotGrid and the SfPivotChart will display the resultant data.

### Categorical axis (columns)

The categorical axis defines one or more elements that are displayed in columns of the SfPivotGrid and as labels of y-axis in the SfPivotChart. If more than one dimension is present on the categorical axis, then the SfPivotGrid and the SfPivotChart will stack each dimension based on the order that they appear on the categorical axis.

### Series axis (rows)

The series axis defines one or more dimensions that are displayed in rows of the SfPivotGrid and as labels of x-axis in the SfPivotChart. If more than one dimension is present on the series axis, then the SfPivotGrid and the SfPivotChart will stack each dimension based on the order that they appear on the series axis.

### Filter axis (filters)

The filter axis allows you to analyze any member of a dimension in depth, and it is used as a slicer to narrow the focus of the multidimensional data that is displayed in the SfPivotGrid and SfPivotChart.

N> To display the member’s data for the slicer, the corresponding member should not exist on both categorical and series axes.

### Value axis (values)

The value axis represents the measures elements present in the current OLAP report.

### Split button

Split button highlights the elements in the axis element builder. It holds measures, dimensions, and named set elements which can be dragged and dropped from the cube dimensional browser into the axis element builder.

While dragging and dropping, a split button is created along with the caption, which is displaying correspond to dimension, or named set.

When a measure node is dragged and dropped, a split button is created to maintain the measure collection and it is maintained for holding all the measures added in the report.

![](PivotClient-Components_images/axisElementBuilder.png)

### Operations in axis element builder

**Adding elements to axis**

The measure, dimension, hierarchy, level, and named set elements can be dragged from the cube dimension browser and dropped into the desired axis element builder by using the drag-and-drop operation. Also, the measure, dimension, hierarchy, level, and named set elements can be moved from one axis to another by dragging an appropriate element and dropping them at desired position.

**Removing elements from axis**

To remove measures, dimension, hierarchy, level, and named set element from the axis element builder, right-click the element and select the *Remove* from the context menu.

The below screenshot illustrates the element being removed from the axis element builder:

![](PivotClient-Components_images/removingElements.png)

**Rearranging elements in axis**

Rearranging can be done with the help of context menu available in the axis element builder. Right-click the desired element, and then select the required option like *Move Up* or *Move Down* or *Move First* or *Move Last* from the menu items to rearrange the selected element.

The below screenshot illustrates the element being rearranged in the axis element builder:

![](PivotClient-Components_images/moveUpElements.png)

## Element editors

### Measure editor

Measure editor is a dialog that displays the collection of measures in the current report. It can be opened by clicking the *filter icon* that is present over the right corner of the measure node in the axis element builder.

![](PivotClient-Components_images/measureEditor.png)

### Member editor

Member editor is a dialog that displays the collection of members available in the selected hierarchy, and the members are represented in a tree-view structure. It can be opened by clicking the *filter icon* present over the right corner of the member node in the axis element builder.

The *Select All* in the dialog allows the user to select and unselect entire nodes for filtering.

![](PivotClient-Components_images/memberEditor.png)

## Toolbar

By default the following options are available in the toolbar.

![](PivotClient-Components_images/Toolbar.png)

* Report menu - The menu button that contains options with respect to all OLAP report manipulations.
* Report list - The drop-down list that displays the list of OLAP reports that are loaded in the SfPivotClient.
* Toggle pivot - The toggle button that toggles the elements from the categorical axis to the series axis and vice versa.
* Show/Hide expanders - The toggle button that toggles the visibility of expanders used for drilling operations.
* Show MDX dialog - The button used to display the MDX query that is parsed from the current OLAP report.
* Enable/Disable paging - The toggle button used to enable or disable the paging feature in the SfPivotClient.

## Report manipulations

OLAP reports can be manipulated with the help of options available under the report menu and the options will be displayed by clicking the **Report Menu** in the SfPivotClient's toolbar.

![](PivotClient-Components_images/toolBar_ReportMenu_1.png)

![](PivotClient-Components_images/toolBar_ReportMenu_2.png)

**New report**

New report option helps the user to clear the existing report collection and to create a new report collection with a single report. By clicking the new report menu item, a report dialog is prompted to specify the name for the OLAP report. By clicking OK, the only one empty report with the specified name is loaded in the SfPivotClient.

![](PivotClient-Components_images/newReport.png)

**Add report**

Add report option helps the user to add a report to the existing report collection. By clicking the add report menu item, a report dialog is prompted to specify the name for the OLAP report. By clicking OK, a report with the specified name is added to the existing collection.

![](PivotClient-Components_images/addReport.png)

**Remove report**

Remove report option removes the current/active report from the report collection. This option works only if the report collection has more than one report.

**Rename report**

Rename report option helps the user to rename the current report. By clicking the rename report menu item, a report dialog is prompted for specifying the new name for the current report. By clicking OK, the active report gets refreshed with the new name.

![](PivotClient-Components_images/renameReport.png)

**Save report**

Save report option saves the report in the local system. The Save As dialog opens only once for prompting a name with the report, which needs to be stored. It stores the report collection by only one name in a database.

![](PivotClient-Components_images/saveAsReport.png)

**Save As report**

Save As report option saves the report in the local system. The Save As dialog opens for prompting a name with the report, which needs to be stored. It stores the report collection by more than one name in a database.

**Load report**

Load report option loads a report from the local system. By clicking the load report menu item, the dialog box opens to load a report into the SfPivotClient.

![](PivotClient-Components_images/loadReport.png)

**Report list**

It is the drop-down list that contains the names of all reports in the report collection. By selecting the required report from the report list, the selected report will be set as active report and gets loaded.

![](PivotClient-Components_images/reportList.png)

## SfPivotGrid and SfPivotChart

The [SfPivotGrid](http://help.syncfusion.com/uwp/sfpivotgrid/overview/) and [SfPivotChart](http://help.syncfusion.com/uwp/sfpivotchart/overview) controls will be rendered with respect to operations done at the axis element builder.