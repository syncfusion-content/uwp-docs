---
layout: post
title: Paging in UWP Pivot Client control | Syncfusion®
description: Learn here all about Paging support in Syncfusion® UWP Pivot Client (SfPivotClient) control and more.
platform: UWP
control: SfPivotClient
documentation: ug
---

# Paging in UWP Pivot Client (SfPivotClient)

Paging in the SfPivotClient supports loading and rendering the large amounts of data without any performance constraint.

When you process the large CellSet, it is split into several segments and each segment is assigned and rendered in a separate page. You can navigate back and forth in all possible ways by using the UI options available in the SfPivotPager.

Paging can be enabled in any of the following ways as illustrated below.

**Using 'EnablePaging' Property**

To enable paging, the `EnablePaging` property should be set to true. The SfPivotPager is included and the OlapDataManager object of the SfPivotClient is bounded to respective instance of the SfPivotPager. The following code snippet and screenshot illustrate how to enable the paging option in the SfPivotClient.

{% tabs %}

{% highlight xaml %}

<pivotclient:SfPivotClient x:Name="PivotClient1" EnablePaging="True" OlapDataManager="{Binding OlapDataManager}"/>

{% endhighlight %}

{% highlight c# %}

PivotClient1.EnablePaging = true;

{% endhighlight %}

{% highlight vb %}

PivotClient1.EnablePaging = True

{% endhighlight %}

{% endtabs %}

N> Paging can be enabled or disabled at runtime by using the *Pivot Pager* icon ![](Paging_images/Pager-button.png) in the SfPivotClient's toolbar. The visibility of the pager button in the toolbar can be modified with the help of the `PagerButtonVisibility` property.

![pagerEnabled_UI](Paging_images/pagerEnabled_UI.png)

**Using OLAP report**

The current OLAP report can be specified with paging options to enable the SfPivotPager that is bounded with the SfPivotClient. The following code snippet shows how to enable the paging through the OLAP report.

{% tabs %}

{% highlight c# %}

private OlapReport CreateOlapReport()
{
    OlapReport olapReport = new OlapReport
    {
        Name = "Paging Report",
        CurrentCubeName = "Adventure Works"
    };

    olapReport.EnablePaging = true;
    olapReport.PagerOptions.CategorialPageSize = 3;
    olapReport.PagerOptions.SeriesPageSize = 3;

    DimensionElement dimensionElementColumn = new DimensionElement();
    dimensionElementColumn.Name = "Customer";
    dimensionElementColumn.HierarchyName = "Customer Geography";
    dimensionElementColumn.AddLevel("Customer Geography", "Country");

    MeasureElements measureElementColumn = new MeasureElements();
    measureElementColumn.Elements.Add(new MeasureElement { Name = "Internet Sales Amount" });
    measureElementColumn.Elements.Add(new MeasureElement { Name = "Sales Amount" });

    DimensionElement dimensionElementRow = new DimensionElement();
    dimensionElementRow.Name = "Date";
    dimensionElementRow.AddLevel("Fiscal", "Fiscal Year");

    // Adding column members
    olapReport.CategoricalElements.Add(dimensionElementColumn);

    // Adding measure element
    olapReport.CategoricalElements.Add(measureElementColumn);

    // Adding row members
    olapReport.SeriesElements.Add(dimensionElementRow);

    return olapReport;
}

{% endhighlight %}

{% highlight vb %}

Private Function CreateOlapReport() As OlapReport
    Dim olapReport As New OlapReport() With { _
        Key .Name = "Paging Report", _
        Key .CurrentCubeName = "Adventure Works" _
    }

    olapReport.EnablePaging = True
    olapReport.PagerOptions.CategorialPageSize = 3
    olapReport.PagerOptions.SeriesPageSize = 3

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

    Dim dimensionElementRow As New DimensionElement()
    dimensionElementRow.Name = "Date"
    dimensionElementRow.AddLevel("Fiscal", "Fiscal Year")

    ' Adding column members
    olapReport.CategoricalElements.Add(dimensionElementColumn)

    ' Adding measure element
    olapReport.CategoricalElements.Add(measureElementColumn)

    ' Adding row members
    olapReport.SeriesElements.Add(dimensionElementRow)

    Return olapReport
End Function

{% endhighlight %}

{% endtabs %}

![pagerEnabled_OlapReport](Paging_images/pagerEnabled_OlapReport.png)

## Pager settings

The page size and current page of both column and row sections can be modified by using the options available in the pager settings dialog. The pager settings dialog can be opened by clicking the settings button in the pager.

![pagerSettingsPopup](Paging_images/pagerSettingsPopup.png)

A demo sample is available in the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\Samples\Universal
Windows\SampleBrowser\PivotClient\PivotClient\View\Paging.xaml
