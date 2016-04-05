---
layout: post
title: Check Box and Radio Button
description: Check Box and Radio Buttonn Support in SfMenuItem for Syncfusion SfMenu control
platform: UWP
control: SfMenu
documentation: ug
--- 

# Check Box and Radio Button

`SfMenu` provides a support for selecting several items. `SfMenuItem` can be changed as checkable by setting the `IsCheckable` property of the `SfMenuItem` to “true”. You can change the icon type (Check Box or Radio Button) by using the `CheckIconType` property, also it can be checked by using the `IsChecked` property.

## Add Check Box and Radio Button in SfMenuItem

`SfMenuItem’s` will be grouped based on the value of the GroupName property and it allows to select only one item from the group by setting the `CheckIconType` property of `SfMenuItem` to RadioButton. Similarly `SfMenuItem` can be checked and unchecked by set the `CheckIconType` property of `SfMenuItem` to CheckBox. The Check Box and Radio Button support can be used as shown in the following code snippet.

{% tabs %}

{% highlight XAML %}

<menu:SfMenu  x:Name="Sfmenu"  ExpandMode="ExpandOnClick" Width="176">

<menu:SfMenuItem Header="File"   >

<menu:SfMenuItem  Header="New" IsCheckable="True"
                  CheckIconType="CheckBox" IsChecked="True"/>

<menu:SfMenuItem  Header="Open" IsCheckable="True"
                  CheckIconType="RadioButton" IsChecked="True"/>

<menu:SfMenuItem Header="Close"  IsCheckable="True"
                 CheckIconType="CheckBox" IsChecked="True"/>

</menu:SfMenuItem>

<menu:SfMenuItem Header="Edit">

<menu:SfMenuItem Header="Undo" IsCheckable="True"
                 CheckIconType="CheckBox" IsChecked="True"/>

<menu:SfMenuItem Header="Redo"  IsCheckable="True"
                 CheckIconType="RadioButton" IsChecked="True"/>

<menu:SfMenuItem Header="Cut"  IsCheckable="True"
                 CheckIconType="RadioButton" IsChecked="True"/>

<menu:SfMenuItem Header="Copy" IsCheckable="True"
                 CheckIconType="CheckBox" IsChecked="True"/>

</menu:SfMenuItem>

<menu:SfMenuItem Header="View">

<menu:SfMenuItem Header="Find Results" />

<menu:SfMenuItem Header="Other Windows" />

</menu:SfMenuItem>

</menu:SfMenu>



{% endhighlight %}

{% endtabs %}

![](Check-Box-and-Radio-Button-images/Check-Box-and-Radio-Button-img1.jpg)


