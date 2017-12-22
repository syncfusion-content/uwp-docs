---
layout: post
title: Overview of SfPivotClient control for UWP
description: Overview of SfPivotClient control for UWP
platform: UWP
control: SfPivotClient
documentation: ug
---

# Overview 

The SfPivotClient control supports browsing multidimensional data that is organized in the form of dimensions, measures, named sets, and KPIs in a cube format. You can visualize the results in graphical (PivotChart) and tabular (PivotGrid) formats. The control can also be used to create and edit reports on-the-fly that are stored for later use.

## Key features

The key features of **SfPivotClient** control are:

* **Data source** - Binds the SfPivotClient control with the Microsoft SQL Server Analysis Services (SSAS), XML/A data sources, and relational data sources.
* **OLAP** - Supports OLAP DB related features like KPI, named sets, member properties, etc.
* **Relational** - Supports relational DB related features like expression fields, custom summaries, etc.
* **Slice and dice** - You can slice and dice the cube database.
* **Save and load** - The current session of the report can be saved in an XML file or as a stream for future use and reload it whenever needed.
* **Chart** - A chart is a graphical representation of the data. The data is represented by symbols such as bars in a bar chart, lines in a line chart, or slices in a pie chart.
* **Grid** - A grid is a tabular representation of data, arranged in the form of rows and columns and categorized accordingly.
* **Cube selector** - Comprises multiple cubes obtained from the data source.
* **Cube dimension browser** - A cube dimension browser is a tree-view structure, organizes the cube elements such as measures, dimensions, hierarchies, named sets, KPI, etc., from the selected cube into independent logical groups.
* **AxisElementBuilder** - Allows to build an OlapReport by placing elements in different axes of the SfPivotClient. There are three axes that are supported namely column, row, and slicer.
* **Member editor** - A tree-view control that displays the member elements of the selected dimension.
* **Measure editor** - Displays a collection of measures from the current OlapReport.   
* **Toolbar** - The toolbar provides options to toggle the pivot axis, and to export and manipulate the OlapReport.
* **Export** - Allows the user to export the PivotGrid and PivotChart to PDF, Excel, Word, CSV, and other supported image formats.
