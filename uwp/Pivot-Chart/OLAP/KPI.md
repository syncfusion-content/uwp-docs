---
layout: post
title: KPI in UWP Pivot Chart control | Syncfusion
description: Learn here all about KPI support in Syncfusion® UWP Pivot Chart (SfPivotChart) control and more.
platform: UWP
control: SfPivotChart
documentation: ug
---

# KPI in UWP Pivot Chart (SfPivotChart)

KPI (Key Performance Indicator) is a business metric that helps to figure out the progress of an enterprise in meeting its business goals. It is a collection of calculations that are associated with a measure group in a cube. Typically, these calculations are a combination of multi-dimensional expressions (MDX) or calculated members. KPIs also have additional metadata that provides information about how the applications should display the results of KPIs calculations.

The different indicators available in KPI are:

* KPI goal
* KPI status
* KPI trend
* KPI value

The KPI elements can be defined in the OLAP report as follows.

{% tabs %}

{% highlight c# %}

OlapReport olapReport = new OlapReport();
// Selecting the Cube
olapReport.CurrentCubeName = "Adventure Works";
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
olapReport.CategoricalElements.Add(kpiElement);
PivotChart1.OlapDataManager.SetCurrentReport(olapReport);

{% endhighlight %}

{% highlight vb %}

Dim olapReport As New OlapReport()
' Selecting the Cube
olapReport.CurrentCubeName = "Adventure Works"
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
olapReport.CategoricalElements.Add(kpiElement)
PivotChart1.OlapDataManager.SetCurrentReport(olapReport)

{% endhighlight %}

{% endtabs %}

![kpi_image1](Kpi_images/kpi_image1.png)

A demo sample is located in the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\Samples\UWP\SampleBrowser\PivotChart\PivotChart\View\KPI.xaml
