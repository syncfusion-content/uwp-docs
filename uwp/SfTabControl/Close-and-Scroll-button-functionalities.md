---
layout: post
title: Explains about Close and Scroll button functionalities of SfTabControl control for UWP
description: Explains about Close and Scroll button functionalities of SfTabControl control for UWP
platform: uwp
control: SfTabControl
documentation: ug
---

# Close and Scroll button functionalities

SfTabControl provides buttons to scroll and close tab items. 

## Tab scroll buttons

Visibility of the scroll buttons can be changed. Events to notify the tab panel scrolling are also provided.

### Setting TabScrollButtonVisibility

Tab scroll buttons can be enabled or disabled for SfTabControl using the TabScrollButtonVisibility property. The possible visibility options are Auto, Visible and Collapsed.

{% tabs %}

{% highlight XAML %}

<navigation:SfTabControl x:Name="tabControl" TabScrollButtonVisibility="Visible">

<navigation:SfTabItem Header="Paul Vent" Content="Description about Paul Vent"/>

<navigation:SfTabItem Header="Niko" Content="Description about Niko"/>

<navigation:SfTabItem Header="James" Content="Description about James"/>

<navigation:SfTabItem Header="Carl" Content="Description about Carl"/>

</navigation:SfTabControl>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

tabControl.TabScrollButtonVisibility = Syncfusion.UI.Xaml.Controls.Navigation.TabScrollButtonVisibility.Visible;

{% endhighlight %}

{% highlight VB %}

tabControl.TabScrollButtonVisibility = Syncfusion.UI.Xaml.Controls.Navigation.TabScrollButtonVisibility.Visible

{% endhighlight %}

{% endtabs %}

![](Close-and-Scroll-button-functionalities-images/Close-and-Scroll-button-functionalities-img1.jpeg)


### PreviousTab event

PreviousTab event is fired when tab item is scrolled to view previous item i.e., by clicking the previous button.

{% tabs %}

{% highlight XAML %}

<navigation:SfTabControl Width="400" TabScrollButtonVisibility="Visible"
                         PreviousTab="tabControl_PreviousTab">

<navigation:SfTabItem Header="Paul Vent" Content="Description about Paul Vent"/>

<navigation:SfTabItem Header="Niko" Content="Description about Niko" />

<navigation:SfTabItem Header="James" Content="Description about James"/>

<navigation:SfTabItem Header="Carl" Content="Description about Carl"/>

</navigation:SfTabControl>


{% endhighlight %}


{% endtabs %}

{% tabs %}

{% highlight C# %}

private void tabControl_PreviousTab(object Sender, ScrollTabEventArgs args)

{

}

{% endhighlight %}

{% highlight VB %}

Private Sub tabControl_PreviousTab(ByVal Sender As Object, ByVal args As ScrollTabEventArgs)


End Sub

{% endhighlight %}

{% endtabs %}

### NextTab event

NextTab event is fired when tab item is scrolled to view next item i.e., by clicking the next button.

{% tabs %}

{% highlight XAML %}

<navigation:SfTabControl Width="400" TabScrollButtonVisibility="Visible"
                         NextTab="tabControl_NextTab">

<navigation:SfTabItem Header="Paul Vent" Content="Description about Paul Vent"/>

<navigation:SfTabItem Header="Niko" Content="Description about Niko" />

<navigation:SfTabItem Header="James" Content="Description about James"/>

<navigation:SfTabItem Header="Carl" Content="Description about Carl"/>

</navigation:SfTabControl>


{% endhighlight %}


{% endtabs %}

{% tabs %}

{% highlight C# %}

private void tabControl_NextTab(object Sender, ScrollTabEventArgs args)

{

}


{% endhighlight %}

{% highlight VB %}

Private Sub tabControl_NextTab(ByVal Sender As Object, ByVal args As ScrollTabEventArgs)


End Sub

{% endhighlight %}

{% endtabs %}

## Tab close buttons

A tab item can be closed with the help of close button in tab header or a common close button.

## Closing a tab item

CanClose property is used to decide whether a tab item can be closed or not even in the existence of common close button. CloseButtonType property has effect in displaying close button even if the CanClose property is set to true.

{% tabs %}

{% highlight XAML %}

<navigation:SfTabItem x:Name="paul" Header="Paul Vent"
                      Content="Description about Paul Vent" CanClose="True"/>


{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

paul.CanClose = true;

{% endhighlight %}

{% highlight VB %}

paul.CanClose = True

{% endhighlight %}

{% endtabs %}

## Setting CloseButtonType

Default close button type is Hide. The possible close button types are:

* Common – A single close button for all the tab  items
* Individual – Individual close button for each tab item
* Both – Both common and individual close buttons for tab item
* Hide – Close button is hidden
* IndividualOnPointerOver – Individual close button is shown on pointer hover
* Extended – Close button displayed for selected item. Show on pointer hover for other tab items 

{% tabs %}

{% highlight XAML %}

<navigation:SfTabControl x:Name="tabControl" CloseButtonType="Both">

<navigation:SfTabItem Header="Paul Vent"
                      Content="Description about Paul Vent" CanClose="True"/>

<navigation:SfTabItem Header="Niko" Content="Description about Niko" CanClose="True"/>

<navigation:SfTabItem Header="James" Content="Description about James" CanClose="True"/>

<navigation:SfTabItem Header="Carl" Content="Description about Carl" CanClose="True"/>

</navigation:SfTabControl>


{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

tabControl.CloseButtonType = Syncfusion.UI.Xaml.Controls.Navigation.CloseButtonType.Both;

{% endhighlight %}

{% highlight VB %}

tabControl.CloseButtonType = Syncfusion.UI.Xaml.Controls.Navigation.CloseButtonType.Both

{% endhighlight %}

{% endtabs %}


**Common**

![](Close-and-Scroll-button-functionalities-images/Close-and-Scroll-button-functionalities-img2.jpeg)


**Individual**

![](Close-and-Scroll-button-functionalities-images/Close-and-Scroll-button-functionalities-img3.jpeg)


**Both**

![](Close-and-Scroll-button-functionalities-images/Close-and-Scroll-button-functionalities-img4.jpeg)


**IndividualOnMouseOver**

![](Close-and-Scroll-button-functionalities-images/Close-and-Scroll-button-functionalities-img5.jpeg)


**Extended**

![](Close-and-Scroll-button-functionalities-images/Close-and-Scroll-button-functionalities-img6.jpeg)


**Hide**

![](Close-and-Scroll-button-functionalities-images/Close-and-Scroll-button-functionalities-img7.jpeg)


## TabClosing event

Whenever the close button is clicked, TabClosing event is fired just before the tab is closed.

{% tabs %}

{% highlight XAML %}

<navigation:SfTabControl TabClosing="tabControl_TabClosing">

{% endhighlight %}


{% endtabs %}

{% tabs %}

{% highlight C# %}

private void tabControl_TabClosing(object Sender, CancelingEventArgs args)

{

}

{% endhighlight %}

{% highlight VB %}

Private Sub tabControl_TabClosing(ByVal Sender As Object, ByVal args As CancelingEventArgs)


End Sub

{% endhighlight %}

{% endtabs %}

## TabClosed event

TabClosed event is fired after the tab item has closed.

{% tabs %}

{% highlight XAML %}

<navigation:SfTabControl TabClosed="tabControl_TabClosed">

{% endhighlight %}


{% endtabs %}

{% tabs %}

{% highlight C# %}

private void tabControl_TabClosed(object Sender, CloseTabEventArgs args)

{

}


{% endhighlight %}

{% highlight VB %}

Private Sub tabControl_TabClosed(ByVal Sender As Object, ByVal args As CloseTabEventArgs)


End Sub

{% endhighlight %}

{% endtabs %}
