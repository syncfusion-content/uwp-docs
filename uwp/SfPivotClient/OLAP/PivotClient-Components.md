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

Cube Selector allows to select any one of the cube from the cubes available in the connected database. This can be achieved by selecting the **Data Connection** menu item from the Reports menu. Cube selector dialog will be opened with a drop-down list, displaying the list of cubes available in the current connection. SfPivotClient will load the corresponding cube elements while changing the cube from the drop-down list.

![](PivotClient-Components_images/toolBar_ReportMenu_1.png)

![](PivotClient-Components_images/toolBar_ReportMenu_2.png)

![](PivotClient-Components_images/cubeSelector.png)

## Cube Dimension Browser

Cube Dimension Browser is a tree-view like structure that organizes the cube elements such as dimensions, hierarchies, measures, etc., from the selected cube into independent, logical groups.

### Node Types

* Display Folder - Folder that contains a set of similar elements.
* Measure - Quantity available for analysis.
* Dimension - A name given to the parts of the cube that categorize the data.
* Attribute Hierarchy - Level of attributes down the hierarchy.
* User-Defined Hierarchy - Members of a dimension in a hierarchical structure.
* Level - Denotes a specific level in the category.
* Named Set - A collection of tuples and members, which can be defined and saved as a part of the cube definition.

**Attribute Hierarchy**

Attribute hierarchy contains the following levels.

* Leaf level contains each distinct attribute member called leaf member with each member of the leaf level.
* Intermediate level if the attribute hierarchy is a parent-child hierarchy.

**User-Defined Hierarchy**

User-defined hierarchy organizes the members of a dimension into hierarchical structure and provides navigation paths in a cube. For example, take a dimension table that supports three attributes such as Year, Quarter and Month. The Year, Quarter and Month attributes are used to construct a user-defined hierarchy, named Calendar, in the time dimension which relates all the levels.

**Differentiating User-defined Hierarchy and Attribute Hierarchy**

* User-defined hierarchy may contain more than one level whereas attribute hierarchy contains only one level.
* User-defined hierarchy provides the navigation path between the levels taken from attribute hierarchies of the same dimension.

### Symbolic Representation of Nodes

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

## Axis Element Builder

Axis Element Builder allows you to build elements in the axes of SfPivotClient. It supports four axes namely Categorical, Series, Filter(Slicer) and Value. Based on the construction of axes, the SfPivotGrid and SfPivotChart will display the resultant data.

### Categorical Axis (Columns)

The categorical axis defines one or more elements that are displayed in columns of SfPivotGrid and as labels of y-axis in SfPivotChart. If more than one dimension is on the categorical axis, then the SfPivotGrid and SfPivotChart will stack each dimension based on the order that they appear on the categorical axis.

### Series Axis (Rows)

The series axis defines one or more dimensions that are displayed in rows of SfPivotGrid and as labels of x-axis in SfPivotChart. If more than one dimension is on the series axis, then the SfPivotGrid and SfPivotChart will stack each dimension based on the order that they appear on the series axis.

### Filter Axis (Filters)

The filter axis lets you analyze any member of a dimension, in-depth and it is used as a slicer to narrow the focus of the multidimensional data displayed in the SfPivotGrid and SfPivotChart.

N> For the slicer to display the member’s data, that member should not exist on both categorical and series axis.

### Value Axis (Values)

The value axis represents the measures elements present in the current OLAP report.

### Split Button

Split button highlights the elements in the Axis Element Builder. It holds measures, dimensions and named set elements which can be dragged and dropped from Cube Dimensional Browser into Axis Element Builder.

While doing drag and drop operation, a split button is created along with displaying the caption of corresponding dimension or named set.

When a measure node is dragged and dropped, a split button is created to maintain the measure collection and it is maintained for holding all the measures added in the report.

![](PivotClient-Components_images/axisElementBuilder.png)

### Operations in Axis Element Builder

**Adding Elements to Axis**

The measure, dimension, hierarchy, level and named set elements can be dragged from the Cube Dimension Browser and dropped into the desired Axis Element Builder using drag-and-drop operation. Also, the measure, dimension, hierarchy, level and named set elements can be moved from one axis to another by dragging an appropriate element and dropping them at desired position.

**Removing Elements from Axis**

To remove measures, dimension, hierarchy, level and named set element from the Axis Element Builder, right-click the element and select the *Remove* option from the context menu.

The below screenshot illustrates the element being removed from the Axis Element Builder.

![](PivotClient-Components_images/removingElements.png)

**Rearranging Elements in Axis**

Rearranging can be done with the help of context menu available in the Axis Element Builder. Right-click the desired element and then select the required option like *Move Up* or *Move Down* or *Move First* or *Move Last* from the menu items to rearrange the selected element.

The below screenshot illustrates the element being rearranged in the Axis Element Builder.

![](PivotClient-Components_images/moveUpElements.png)

## Element Editors

### Measure Editor

Measure Editor is a dialog that displays the collection of measures in the current report. It can be opened by clicking the *filter icon* present over right corner of the measure node in Axis Element Builder.

![](PivotClient-Components_images/measureEditor.png)

### Member Editor

Member Editor is a dialog that displays the collection of members available in the selected hierarchy and the members are represented in a tree-view structure. It can be opened by clicking the *filter icon* present over right corner of the Member node in Axis Element Builder.

The *Select All* option in the dialog lets the user to select and un-select entire nodes for filtering.

![](PivotClient-Components_images/memberEditor.png)

## Toolbar

By default the following options are available in the toolbar.

![](PivotClient-Components_images/Toolbar.png)

* Report Menu - The menu button that contains options with respect to all OLAP report manipulations.
* Report List - The drop-down list that displays the list of OLAP reports loaded in SfPivotClient.
* Toggle Pivot - The toggle button that toggles the elements from categorical axis to series axis and vice versa.
* Show/Hide Expanders - The toggle button that toggles the visibility of expanders used for drilling operations.
* Show MDX Dialog - The button used to display the MDX query parsed from the current OLAP report.
* Enable/Disable Paging - The toggle button used to enable or disable the paging feature in SfPivotClient.

## Report Manipulations

OLAP reports can be manipulated with the help of options available under the report menu and the options will be displayed by clicking the **Report Menu** button in the SfPivotClient's toolbar.

![](PivotClient-Components_images/toolBar_ReportMenu_1.png)

![](PivotClient-Components_images/toolBar_ReportMenu_2.png)

**New Report**

New report option helps the user to clear the existing report collection and to create a new report collection with a single report. On clicking the new report menu item, a Report dialog is prompted for specifying the name for the OLAP report. On clicking OK button, only one empty report with the specified name is loaded in SfPivotClient.

![](PivotClient-Components_images/newReport.png)

**Add Report**

Add report option lets the user to add a report to the existing report collection. On clicking the add report menu item, a Report dialog is prompted for specifying the name for the OLAP report. On clicking OK button, a report with the specified name is added to the existing collection.

![](PivotClient-Components_images/addReport.png)

**Remove Report**

Remove report option removes the current/active report from the report collection. This option works only if the report collection has more than one report.

**Rename Report**

Rename report option lets the user to rename the current report. On clicking the rename report menu item, a Report dialog is prompted for specifying the new name for the current report. On clicking OK button, the active report gets refreshed with the new name.

![](PivotClient-Components_images/renameReport.png)

**Save Report**

Save Report option saves the report in local system. The SaveAs dialog opens only once prompting for a name with which the report needs to be stored. It stores the report collection by only one name in a database

![](PivotClient-Components_images/saveAsReport.png)

**SaveAs Report**

SaveAs Report option saves the report in local system. The SaveAs dialog opens prompting for a name with which the report needs to be stored. It stores the report collection by more than one name in a database.

**Load Report**

Load report option loads a report from local system. Click on Load Report menu item displays the open dialog to load a report into the SfPivotClient.

![](PivotClient-Components_images/loadReport.png)

**Report List**

It is the drop-down list that contains the names of all the reports in the report collection. On selecting the required report from the report list, the selected report will be set as active report and gets loaded.

![](PivotClient-Components_images/reportList.png)

## SfPivotGrid and SfPivotChart

The [SfPivotGrid](http://help.syncfusion.com/uwp/sfpivotgrid/overview/) and [SfPivotChart](http://help.syncfusion.com/uwp/sfpivotchart/overview) controls will be rendered with respect to the operations done at Axis Element Builder.