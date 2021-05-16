---
layout: post
title: Hyperlink Cells in UWP Pivot Grid control | Syncfusion
description: Learn here all about Hyperlink Cells support in Syncfusion UWP Pivot Grid (SfPivotGrid) control and more.
platform: UWP
control: SfPivotGrid
documentation: ug
---

# Hyperlink Cells in UWP Pivot Grid (SfPivotGrid)

The SfPivotGrid allows hyperlinking of cells to retrieve detailed information about a particular cell. Hyperlink can be individually applied to the following cells:

* Column header cells.
* Row header cells.
* Value cells.
* Summary column cells.
* Summary row cells.

The hyperlink options can be enabled or disabled separately for column header cells, row header cells, summary column cells, summary row cells, and value cells by using the `IsHyperlinkCell` property in the `PivotGridCellStyle` class.

**Hyperlink in column header cells**

The following code snippet illustrates how to enable hyperlink in column header cells.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGrid x:Name="PivotGrid1" ItemSource="{Binding ProductSalesData}" PivotRows="{Binding PivotRows}"
                        PivotColumns="{Binding PivotColumns}" PivotCalculations="{Binding PivotCalculations}">
    <syncfusion:SfPivotGrid.ColumnHeaderStyle>
        <syncfusion:PivotGridCellStyle IsHyperlinkCell="True"/>
    </syncfusion:SfPivotGrid.ColumnHeaderStyle>
</syncfusion:SfPivotGrid>

{% endhighlight %}

{% highlight c# %}

this.PivotGrid1.ColumnHeaderStyle.IsHyperlinkCell = true;

{% endhighlight %}

{% highlight vb %}

Me.PivotGrid1.ColumnHeaderStyle.IsHyperlinkCell = True

{% endhighlight %}

{% endtabs %}

![column-header-cell-hyperlink](Hyperlink-Cells_images/column-header-cell-hyperlink.png)

**Hyperlink in row header cells**

The following code snippet illustrates how to enable the hyperlink in row header cells.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGrid x:Name="PivotGrid1" ItemSource="{Binding ProductSalesData}" PivotRows="{Binding PivotRows}"
                        PivotColumns="{Binding PivotColumns}" PivotCalculations="{Binding PivotCalculations}">
    <syncfusion:SfPivotGrid.RowHeaderStyle>
        <syncfusion:PivotGridCellStyle IsHyperlinkCell="True"/>
    </syncfusion:SfPivotGrid.RowHeaderStyle>
</syncfusion:SfPivotGrid>

{% endhighlight %}

{% highlight c# %}

this.PivotGrid1.RowHeaderStyle.IsHyperlinkCell = true;

{% endhighlight %}

{% highlight vb %}

Me.PivotGrid1.RowHeaderStyle.IsHyperlinkCell = True

{% endhighlight %}

{% endtabs %}

![row-header-cell-hyperlink](Hyperlink-Cells_images/row-header-cell-hyperlink.png)

**Hyperlink in value cells**

The following code snippet illustrates how to enable the hyperlink in value cells.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGrid x:Name="PivotGrid1" ItemSource="{Binding ProductSalesData}" PivotRows="{Binding PivotRows}"
                        PivotColumns="{Binding PivotColumns}" PivotCalculations="{Binding PivotCalculations}">
    <syncfusion:SfPivotGrid.ValueCellStyle>
        <syncfusion:PivotGridCellStyle IsHyperlinkCell="True"/>
    </syncfusion:SfPivotGrid.ValueCellStyle>
</syncfusion:SfPivotGrid>

{% endhighlight %}

{% highlight c# %}

this.PivotGrid1.ValueCellStyle.IsHyperlinkCell = true;

{% endhighlight %}

{% highlight vb %}

Me.PivotGrid1.ValueCellStyle.IsHyperlinkCell = True

{% endhighlight %}

{% endtabs %}

![value-cell-hyperlink](Hyperlink-Cells_images/value-cell-hyperlink.png)

**Hyperlink in summary column cells**

The following code snippet illustrates how to enable the hyperlink in summary column cells.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGrid x:Name="PivotGrid1" ItemSource="{Binding ProductSalesData}" PivotRows="{Binding PivotRows}"
                        PivotColumns="{Binding PivotColumns}" PivotCalculations="{Binding PivotCalculations}">
    <syncfusion:SfPivotGrid.SummaryColumnStyle>
        <syncfusion:PivotGridCellStyle IsHyperlinkCell="True"/>
    </syncfusion:SfPivotGrid.SummaryColumnStyle>
</syncfusion:SfPivotGrid>

{% endhighlight %}

{% highlight c# %}

this.PivotGrid1.SummaryColumnStyle.IsHyperlinkCell = true;

{% endhighlight %}

{% highlight vb %}

Me.PivotGrid1.SummaryColumnStyle.IsHyperlinkCell = True

{% endhighlight %}

{% endtabs %}

![summary-column-cell-hyperlink](Hyperlink-Cells_images/summary-column-cell-hyperlink.png)

**Hyperlink in summary row cells**

The following code snippet illustrates how to enable hyperlink in summary row cells.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGrid x:Name="PivotGrid1" ItemSource="{Binding ProductSalesData}" PivotRows="{Binding PivotRows}"
                        PivotColumns="{Binding PivotColumns}" PivotCalculations="{Binding PivotCalculations}">
    <syncfusion:SfPivotGrid.SummaryRowStyle>
        <syncfusion:PivotGridCellStyle IsHyperlinkCell="True"/>
    </syncfusion:SfPivotGrid.SummaryRowStyle>
</syncfusion:SfPivotGrid>

{% endhighlight %}

{% highlight c# %}

this.PivotGrid1.SummaryRowStyle.IsHyperlinkCell = true;

{% endhighlight %}

{% highlight vb %}

Me.PivotGrid1.SummaryRowStyle.IsHyperlinkCell = True

{% endhighlight %}

{% endtabs %}

![summary-row-cell-hyperlink](Hyperlink-Cells_images/summary-row-cell-hyperlink.png)

A demo sample is available in the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\Samples\UWP\SampleBrowser\PivotGrid\PivotGrid\View\Hyperlink.xaml
