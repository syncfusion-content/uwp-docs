---
layout: post
title: Using ListView with SfDataPager control in UWP.
description: Using ListView with SfDataPager control in UWP.
platform: uwp
control: SfDataPager
documentation: ug
---

# Using ListView with SfDataPager

[SfDataPager](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/Syncfusion.SfGrid.UWP~Syncfusion.UI.Xaml.Controls.DataPager.SfDataPager.html#) automatically wraps the collection in [PagedCollectionView](https://help.syncfusion.com/cr/cref_files/uwp/data/Syncfusion.Data.UWP~Syncfusion.Data.PagedCollectionView.html) and exposes to the [PagedSource](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/Syncfusion.SfGrid.UWP~Syncfusion.UI.Xaml.Controls.DataPager.SfDataPager~PagedSource.html#) property. You can pass the `PagedSource` property to bind with any ItemsControl’s ItemsSource property. Here, the `PagesSource` property is bound to the ListBox.

The following code explains how to use Source and `PagedSource` property in ListBox.

{% tabs %}
{% highlight xaml %}
<Page>
    <Page.DataContext>
        <local:ViewModel />
    </Page.DataContext>
    <Grid>
        <Grid.RowDefinitions>
            <RowDefinition Height="300"/>
            <RowDefinition Height="*"/>
        </Grid.RowDefinitions>
        <ListBox ItemsSource="{Binding ElementName=sfDataPager, Path=PagedSource}"/>
        
        <datapager:SfDataPager x:Name="sfDataPager" 
                                Grid.Row="1" 
                                PageSize="5" 
                                NumericButtonCount="5"
                                Source="{Binding Orders}" />
    </Grid>
</Page>
{% endhighlight %}
{% endtabs %}

The following screenshot displays the output for `ListView` bound with `PagedCollection`.

![](Using-ListView-With-SfDataPager_images/Using-ListView-With-SfDataPager_img1.jpeg)