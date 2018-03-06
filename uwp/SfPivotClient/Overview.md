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

The key features of **SfPivotClient** control are listed as follows:

* **Data source** - Supports data binding with OLAP data source (such as Microsoft SQL Server Analysis Services (SSAS), XML/A) and relational data source (such as IList, IEnumerable, etc.).
* **OLAP** - Supports OLAP DB related features like KPI, named sets, member properties, etc.
* **Relational** - Supports relational DB related features like expression fields, custom summaries, etc.
* **Slice and dice** - You can slice and dice the cube database.
* **Save and load** - Saves the current session of the report in a XML file or as a stream for future use and reloads it whenever needed.
* **Chart** - Graphical representation of the data, represented by symbols such as bars in a bar chart, lines in a line chart, or slices in a pie chart.
* **Grid** - Tabular representation of data, arranged in the form of rows and columns and categorized accordingly.
* **Cube selector** - Comprises multiple cubes obtained from the data source.
* **Cube dimension browser** - Tree-view structure, organizes the cube elements such as measures, dimensions, hierarchies, named sets, KPI, etc., from the selected cube into independent logical groups.
* **Axis element builder** - Allows to build an OlapReport by placing elements in three different axes namely column, row, and slicer.
* **Member editor** - Displays the member elements of the selected dimension in tree-view structure.
* **Measure editor** - Displays the collection of measures from the current OlapReport.
* **Toolbar** - Provides options to toggle the pivot axis, and to export and manipulate the OlapReport.
* **Export** - Allows to export the PivotGrid and PivotChart to PDF, Excel, Word, CSV and other supported image formats.