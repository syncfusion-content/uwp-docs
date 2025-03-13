---
layout: post
title: Advanced Filtering in UWP Pivot Client control | Syncfusion®
description: Learn here all about Advanced Filtering support in Syncfusion® UWP Pivot Client (SfPivotClient) control and more.
platform: uwp
control: SfPivotClient
documentation: ug
---

# Advanced Filtering in UWP Pivot Client (SfPivotClient)

The SfPivotClient provides an advanced filtering support through which members can be filtered based on value and label fields, and this can be achieved with the help of `EnableAdvancedFilter` property. The following code snippet illustrates how to enable **Advanced Filtering** in the SfPivotClient.

{% tabs %}

{% highlight xaml %}

<pivotclient:SfPivotClient x:Name="PivotClient1" EnableAdvancedFilter="True" OlapDataManager="{Binding OlapDataManager}"/>

{% endhighlight %}

{% highlight c# %}

PivotClient1.EnableAdvancedFilter = true;

{% endhighlight %}

{% highlight vb %}

PivotClient1.EnableAdvancedFilter = True

{% endhighlight %}

{% endtabs %}

![advancedFilteringEnabled](Advanced-Filtering_images/advancedFilteringEnabled.png)

## Label filtering

Label filtering provides an option to filter members of the selected field based on their caption. The following screenshots describe how the label filtering is applied in the SfPivotClient.

![labelFiletring_step1](Advanced-Filtering_images/labelFiletring_step1.png)

![labelFiletring_step2](Advanced-Filtering_images/labelFiletring_step2.png)

![labelFilteredClient](Advanced-Filtering_images/labelFilteredClient.png)
*SfPivotClient applied with label filter*

## Value filtering

Value filtering provides an option to filter members based on total values of the appropriate measure between the level members. The following screenshots describe how the value filtering is applied in the SfPivotClient.

![valueFiltering_step1](Advanced-Filtering_images/valueFiltering_step1.png)

![valueFiltering_step2](Advanced-Filtering_images/valueFiltering_step2.png)

![valueFilteredClient](Advanced-Filtering_images/valueFilteredClient.png)
*SfPivotClient applied with value filter*

A demo sample is available in the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\Samples\UWP\SampleBrowser\PivotClient\PivotClient\View\AdvancedFiltering.xaml
