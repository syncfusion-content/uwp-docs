---
layout: post
title: KPI in UWP Pivot Client control | Syncfusion
description: Learn here all about KPI support in Syncfusion UWP Pivot Client (SfPivotClient) control and more.
platform: UWP
control: SfPivotClient
documentation: ug
---

# KPI in UWP Pivot Client (SfPivotClient)

Key Performance Indicator (KPI) is a business metric that helps to figure out the progress of an enterprise when meeting its business goals. Typically, these calculations are a combination of Multi-Dimensional Expressions (MDX) or calculated members. The KPIs also have an additional metadata that provides information about how the client applications should display the results of KPI’s calculations.

## Indicator types

There are four types of indicators available in the KPI as listed below:

* KPI goal.
* KPI status.
* KPI trend.
* KPI value.

## Adding KPI elements

There are two ways to define KPI elements in the SfPivotClient as follows.

**Using drag and drop**

You can dynamically drag and drop the KPI elements from the cube dimension browser to the axis element builder to add a KPI in the current report.

N> If the current report does not contain a measure element, then the KPI element cannot be added to the current report.

The following screenshot illustrates the collection of KPI elements available in the connected OLAP cube.

![kpi_Drag_Drop](KPI_images/kpi_Drag_Drop.png)

**Using OLAP report**

You can define KPI elements in the OLAP report along with its associated measures and it can be added to any axis of the current OLAP report. The following code specifies how to define KPI elements in the OLAP report.

N> KPI elements must be specified in the same axis containing measure elements.

{% tabs %}

{% highlight C# %}

OlapReport kpiReport = new OlapReport
{
    Name = "KPI Report",
    CurrentCubeName = "Adventure Works"
};

DimensionElement dimensionElementColumn = new DimensionElement();
dimensionElementColumn.Name = "Customer";
dimensionElementColumn.HierarchyName = "Customer Geography";
dimensionElementColumn.AddLevel("Customer Geography", "Country");

MeasureElements measureElementColumn = new MeasureElements();
measureElementColumn.Elements.Add(new MeasureElement { Name = "Internet Sales Amount" });
measureElementColumn.Elements.Add(new MeasureElement { Name = "Sales Amount" });

KpiElements kpiElements = new KpiElements();
kpiElements.Elements.Add(new KpiElement() { Name = "Internet Revenue" });

DimensionElement dimensionElementRow = new DimensionElement();
dimensionElementRow.Name = "Date";
dimensionElementRow.AddLevel("Fiscal", "Fiscal Year");

// Adding column members
kpiReport.CategoricalElements.Add(dimensionElementColumn);

// Adding measure element
kpiReport.CategoricalElements.Add(measureElementColumn);

kpiReport.CategoricalElements.Add(kpiElements);

// Adding row members
kpiReport.SeriesElements.Add(dimensionElementRow);

PivotClient1.OlapDataManager.SetCurrentReport(kpiReport);

{% endhighlight %}

{% highlight vb %}

Dim kpiReport As New OlapReport() With { _
    Key .Name = "KPI Report", _
    Key .CurrentCubeName = "Adventure Works" _
}

Dim dimensionElementColumn As New DimensionElement()
dimensionElementColumn.Name = "Customer"
dimensionElementColumn.HierarchyName = "Customer Geography"
dimensionElementColumn.AddLevel("Customer Geography", "Country")

Dim measureElementColumn As New MeasureElements()
measureElementColumn.Elements.Add(New MeasureElement() With { _
    Key .Name = "Internet Sales Amount" _
})
measureElementColumn.Elements.Add(New MeasureElement() With { _
    Key .Name = "Sales Amount" _
})

Dim kpiElements As New KpiElements()
kpiElements.Elements.Add(New KpiElement() With { _
    Key .Name = "Internet Revenue" _
})

Dim dimensionElementRow As New DimensionElement()
dimensionElementRow.Name = "Date"
dimensionElementRow.AddLevel("Fiscal", "Fiscal Year")

' Adding column members
kpiReport.CategoricalElements.Add(dimensionElementColumn)

' Adding measure element
kpiReport.CategoricalElements.Add(measureElementColumn)

kpiReport.CategoricalElements.Add(kpiElements)

' Adding row members
kpiReport.SeriesElements.Add(dimensionElementRow)

PivotClient1.OlapDataManager.SetCurrentReport(kpiReport)

{% endhighlight %}

{% endtabs %}

![kpiElementsLoaded](KPI_images/kpiElementsLoaded.png)
