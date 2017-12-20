---
layout: post
title: Data Exploration | SfPivotClient | UWP | Syncfusion
description: Data Exploration
platform: UWP
control: SfPivotClient
documentation: ug
---

# Data Exploration

## Filtering

Filtering can be done in the SfPivotClient by using the **Member Editor** dialog. This dialog will be opened by clicking the desired member's *filter icon* ![](Data-Exploration_images/filterIcon.ico) (from the axis element builder), through which members are filtered by checking and unchecking the check boxes corresponding to the members. By clicking “OK”, the OlapReport gets updated and refreshes the PivotGrid and PivotChart controls based on selected members in the member editor dialog.

The following screenshots illustrate that the members of Canada, France, and Germany are excluded from the SfPivotClient control:

![](Data-Exploration_images/memberFilter_InitialSelection.png)

![](Data-Exploration_images/memeberFilter_Filtered.png)

### Paging in member editor

Paging feature helps to improve the rendering performance of the member editor which is opened by clicking the filter icon of a member in the axis element builder. This feature allows member editor to display large amount of data by dividing the data into sections. You can enable paging in the member editor by setting the `EnableMemberEditorPaging` property to true. The size of the data to be displayed per page can be customized with the help of `MemberEditorPageSize` property. Please refer the below code snippet:

{% tabs %}

{% highlight xaml %}

<pivotclient:SfPivotClient x:Name="PivotClient1" EnableMemberEditorPaging="True" MemberEditorPageSize="3"
                           OlapDataManager="{Binding OlapDataManager}"/>

{% endhighlight %}

{% highlight c# %}

PivotClient1.EnableMemberEditorPaging = true;
PivotClient1.MemberEditorPageSize = 3;

{% endhighlight %}

{% highlight vb %}

PivotClient1.EnableMemberEditorPaging = True
PivotClient1.MemberEditorPageSize = 3

{% endhighlight %}

{% endtabs %}

![](Data-Exploration_images/memberEditor_PagingEnabled.png)

## Grouping

The data can be grouped when more than one dimensional element is added to column or row section in the axis element builder. Based on the order of addition, the data is grouped and the OlapReport gets updated. In the following example, members of the **Date** dimension is grouped with respect to members of the **Customer** dimension. Likewise, multiple dimension members can be grouped by dragging the elements from the cube dimension browser to the axis element builder.

![](Data-Exploration_images/groupedMembers.png)