---
layout: post
title: Populating pages of SfDataPager control in UWP.
description: Populating pages of SfDataPager control in UWP.
platform: uwp
control: SfDataPager
documentation: ug
---

# Populating pages

## Binding with data

You can use [Source](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlControlsDataPagerSfDataPagerClassSourceTopic.html#) property to bind collection of data with [SfDataPager](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlControlsDataPagerSfDataPagerClassTopic.html#). Based on number of items in collection and [PageSize](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlControlsDataPagerSfDataPagerClassPageSizeTopic.html#), the [PageCount](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlControlsDataPagerSfDataPagerClassPageCountTopic.html#) will be calculated. 

Below code snippet shows, how to bind `SfDataPager` with data. 

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
        <syncfusion:SfDataGrid x:Name="sfGrid"
                                Grid.Row="0" 
                                ItemsSource="{Binding
                                ElementName=sfDataPager,Path=PagedSource}"/>
                                <datapager:SfDataPager x:Name="sfDataPager" 
                                                        Grid.Row="1" 
                                                        PageSize="5" 
                                                        NumericButtonCount="5"
                                                        Source="{Binding Orders}" />    
    </Grid>
</Page>
{% endhighlight %}
{% endtabs %}

Based on number of items in the collection and `PageSize` and the `PageCount` is calculated for `SfDataPager`.

![](Populating-Pages_images/Populating-Pages_img1.jpeg)

## Unbound Mode

You can define the [PageCount](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlControlsDataPagerSfDataPagerClassPageCountTopic.html#) of `SfDataPager` by setting [UseOnDemandPaging](https://help.syncfusion.com/cr/cref_files/uwp/sfdatagrid/frlrfSyncfusionUIXamlControlsDataPagerSfDataPagerClassUseOnDemandPagingPropertyTopic.html#) to `true` and `PageCount` property.

{% tabs %}
{% highlight xaml %}
<datapager:SfDataPager x:Name="sfDataPager" 
                         PageCount="2"
                         UseOnDemandPaging="True"/>
{% endhighlight %}
{% endtabs %}

![](Populating-Pages_images/Populating-Pages_img2.jpeg)