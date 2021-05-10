---
layout: post
title: KPI in UWP Pivot Grid control | Syncfusion
description: Learn here all about KPI support in Syncfusion UWP Pivot Grid (SfPivotGrid) control and more.
platform: UWP
control: SfPivotGrid
documentation: ug
---

# KPI in UWP Pivot Grid (SfPivotGrid)

KPI (Key Performance Indicator) is a collection of calculations that are associated with a measure group in a cube and are used to evaluate business success. Typically, these calculations are a combination of multi-dimensional expressions (MDX) or calculated members. KPIs also have additional metadata that provides information about how the applications should display the results of KPIs calculations.

The following are the different types of indicators:

* KPI goal
* KPI status
* KPI trend
* KPI value

The KPI elements can be defined in the OLAP report in the following way.

{% tabs %}

{% highlight c# %}

OlapReport olapReport = new OlapReport();
// Selecting the Cube
olapReport.CurrentCubeName = "Adventure Works";

DimensionElement dimensionElementColumn = new DimensionElement();
// Specifying the Name for Column Dimension Element
dimensionElementColumn.Name = "Product";
// Specifying the Level element
dimensionElementColumn.AddLevel("Product Categories", "Category");
MeasureElements measureElementColumn = new MeasureElements();
// Specifying the Name for the Measure Element
measureElementColumn.Elements.Add(new MeasureElement { Name = "Sales Amount Quota" });
KpiElements kpiElement = new KpiElements();
// Specifying the KPI Element name and configuring its Indicators
kpiElement.Elements.Add(new KpiElement
{
    Name = "Internet Revenue",
    ShowKPIGoal = true,
    ShowKPIStatus = true,
    ShowKPIValue = true,
    ShowKPITrend = true
});
DimensionElement dimensionElementRow = new DimensionElement();
// Specifying the Name for Row Dimension Element
dimensionElementRow.Name = "Date";
// Specifying the Level element
dimensionElementRow.AddLevel("Fiscal", "Fiscal Year");
// Adding Row Elements
olapReport.SeriesElements.Add(dimensionElementRow);
// Adding Column Elements
olapReport.CategoricalElements.Add(dimensionElementColumn);
olapReport.CategoricalElements.Add(kpiElement);
PivotGrid1.OlapDataManager.SetCurrentReport(olapReport);

{% endhighlight %}

{% highlight vb %}

Dim olapReport As New OlapReport()
' Selecting the Cube
olapReport.CurrentCubeName = "Adventure Works"
Dim dimensionElementColumn As New DimensionElement()
' Specifying the Name for Column Dimension Element
dimensionElementColumn.Name = "Product";
' Specifying the Level element
dimensionElementColumn.AddLevel("Product Categories", "Category");
Dim measureElements As New MeasureElements()
measureElements.Add(New MeasureElement With {.Name = " Sales Amount Quota"})
olapReport.SeriesElements.Add(measureElements)
Dim kpiElement As New KpiElements()
' Specifying the KPI Element name and configuring its Indicators
kpiElement.Elements.Add(New KpiElement() With { _
        Key .Name = "Internet Revenue", _
        Key .ShowKPIGoal = True, _
        Key .ShowKPIStatus = True, _
        Key .ShowKPIValue = True, _
        Key .ShowKPITrend = True _
})
Dim dimensionElementRow As New DimensionElement()
' Specifying the Name for Row Dimension Element
dimensionElementRow.Name = "Date"
' Specifying the Level element
dimensionElementRow.AddLevel("Fiscal", "Fiscal Year")
' Adding Row Elements
olapReport.SeriesElements.Add(dimensionElementRow)
' Adding Column Elements
olapReport.CategoricalElements.Add(dimensionElementColumn);
olapReport.CategoricalElements.Add(kpiElement)
PivotGrid1.OlapDataManager.SetCurrentReport(olapReport)

{% endhighlight %}

{% endtabs %}

![KPI_image1](KPI_images/KPI_image1.png)

A sample demo is located in the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\Samples\UWP\SampleBrowser\PivotGrid\PivotGrid\View\KPI.xaml
