---
layout: post
title: Overview of SfPivotClient control for UWP
description: Overview of SfPivotClient control for UWP
platform: uwp
control: SfPivotClient
documentation: ug
---

# Overview 

The SfPivotClient control supports browsing multidimensional data that is organized in the form of dimensions, measures, named sets and KPIs in a Cube format. You can visualize the results in graphical (PivotChart) and tabular (PivotGrid) formats. The control can also be used to create and edit reports on-the-fly that are stored for later use. 

## Key Features

The key features of **SfPivotClient** control are: 

* **Data Source** - Binds the SfPivotClient control with the Microsoft SQL Server Analysis Services (SSAS), XML/A data sources and Relational data sources.
* **OLAP** - OLAP DB related features like KPI, Named Sets, Member Properties etc., are supported.
* **Relational** - Relational DB related features like expression fields, custom summaries etc., are supported.
* **Slice and Dice** - You can slice and dice the cube database.
* **Save and Load** - The current session of the report can be saved in an XML file or as a stream for future use and reload it whenever needed.
* **Chart** - A Chart is a graphical representation of data, in which “the data is represented by symbols, such as bars in a bar chart, lines in a line chart, or slices in a pie chart”.
* **Grid** - A Grid is a tabular representation of data, arranged in the form of rows and columns and categorized accordingly.
* **Cube Selector** - Comprises multiple cubes obtained from data source.
* **Cube Dimension Browser** - Tree-view structure that comprises measures, dimensions, hierarchies, named sets, KPI and so on, belonging to the current cube into independent logical groups.
* **AxisElementBuilder** - Allows to build an OlapReport by placing elements in different axes of the SfPivotClient. There are three axes that are supported namely column, row and slicer.
* **Member Editor** - A tree-view control that displays the member elements of the selected dimension.
* **Measure Editor** - Displays a collection of Measures from the current OlapReport.   
* **Toolbar** - Toolbar provides options to toggle the pivot axis, exporting and for manipulating the OlapReport. 
* **Export** - Allows the user to export the PivotGrid and PivotChart to PDF, Excel, Word, CSV and other supported image formats.
