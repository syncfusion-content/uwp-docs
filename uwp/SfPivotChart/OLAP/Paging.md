---
layout: post
title: Paging | SfPivotChart | UWP | Syncfusion
description: Paging
platform: UWP
control: SfPivotChart
documentation: ug
---

# Paging

SfPivotGrid provides support for loading and rendering large amount of data without any performance constraint. The below code snippet illustrates the paging using the current OLAP report.

SfPivotPager (custom control) is included and bound with the `OlapDataManager` of the respective SfPivotChart. To enable paging, set the “EnablePaging” property of `OlapDataManager` to true.

When you process a large CellSet, it is split into several number of segments and each segment is assigned and rendered in a separate page. You can navigate back and forth in all possible ways by using the UI options and you can also change the page size and the page number dynamically with the help of settings button available in SfPivotPager.

N > The assembly **Syncfusion.SfPivotShared.UWP** needs to be included from the installed location in-order to add the SfPivotPager with SfPivotChart. You can also get the assemblies by browsing to the default assembly location i.e., 
{System Drive}:\Program Files (x86)\Syncfusion\Essential Studio\\&lt;Version Number&gt;\Assemblies for Universal Windows\10.0\

{% tabs %}

{% highlight xaml %}

<Grid Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">
    <Grid.DataContext>
        <local:ViewModel/>
    </Grid.DataContext>

    <Grid.RowDefinitions>
        <RowDefinition Height="*"/>
        <RowDefinition Height="Auto"/>
    </Grid.RowDefinitions>

    <pivotChart:SfPivotChart x:Name="PivotChart1" OlapDataManager="{Binding OlapDataManager}"/>

    <pivotShared:SfPivotPager Grid.Row="1" OlapDataManager="{Binding OlapDataManager}"/>
</Grid>

{% endhighlight %}

{% highlight c# %}

private void PivotChart1_Loaded(object sender, Windows.UI.Xaml.RoutedEventArgs e)
{
    PivotChart1.OlapDataManager.CurrentReport.EnablePaging = true;
    PivotChart1.OlapDataManager.CurrentReport.PagerOptions.CategoricalPageSize = 2;
    PivotChart1.OlapDataManager.CurrentReport.PagerOptions.SeriesPageSize = 10;
    PivotChart1.OlapDataManager.RaiseGetOlapDataWithTotalCount(new GetOlapDataWithTotalCountEventArgs
    {
        SerializedReport = Syncfusion.Olap.UWP.Common.Common.SerializeObject(PivotChart1.OlapDataManager.CurrentReport)
    });
    PivotChart1.OlapDataManager.NotifyElementChanged();
}

{% endhighlight %}

{% highlight vb %}

Private Sub PivotChart1_Loaded(sender As Object, e As Windows.UI.Xaml.RoutedEventArgs)
	PivotChart1.OlapDataManager.CurrentReport.EnablePaging = True
	PivotChart1.OlapDataManager.CurrentReport.PagerOptions.CategoricalPageSize = 2
	PivotChart1.OlapDataManager.CurrentReport.PagerOptions.SeriesPageSize = 10
	PivotChart1.OlapDataManager.RaiseGetOlapDataWithTotalCount(New GetOlapDataWithTotalCountEventArgs() With { _
		Key .SerializedReport = Syncfusion.Olap.UWP.Common.Common.SerializeObject(PivotChart1.OlapDataManager.CurrentReport) _
	})
	PivotChart1.OlapDataManager.NotifyElementChanged()
End Sub

{% endhighlight %}

{% endtabs %}

![](Paging_images/enablePaging.png)