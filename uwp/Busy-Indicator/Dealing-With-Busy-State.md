---
layout: post
title: Dealing with Busy State in UWP Busy Indicator control | Syncfusion
description: Learn here all about Dealing with Busy State support in Syncfusion UWP Busy Indicator (SfBusyIndicator) control and more.
platform: uwp
control: SfBusyIndicator
documentation: ug
---

# Dealing with Busy State in UWP Busy Indicator (SfBusyIndicator)

`SfBusyIndicator` can be shown/hidden using the `IsBusy` property. By default, `IsBusy` is `true`.

* IsBusy=True –  shows the indicator 
* IsBusy=False –  collapses the indicator

{% tabs %}

{% highlight XAML %}

<Grid Background="CornflowerBlue">

<Notification:SfBusyIndicator IsBusy="True"/>

</Grid>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

SfBusyIndicator busyIndicator = new SfBusyIndicator();
busyIndicator.IsBusy = true;

{% endhighlight %}

{% highlight VB %}

Dim busyIndicator As New SfBusyIndicator()
busyIndicator.IsBusy = True

{% endhighlight %}

{% endtabs %}

![Enable the Animation to Show](SfBusyIndicator1/Busy.png)

## Busy Caption

`SfBusyIndicator` can be captioned along with the attractive animation. Header is displayed below the animation and it can be a text, image etc. Header is collapsed along with the animation when `IsBusy` is set to `false`.

{% tabs %}

{% highlight XAML %}

<Grid Background="CornFlowerBlue"/>

<notification:SfBusyIndicator Header="Loading..."/>

</Grid>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

SfBusyIndicator busyIndicator = new SfBusyIndicator();

busyIndicator.Header = "Loading...";

{% endhighlight %}

{% highlight VB %}

Dim busyIndicator As New SfBusyIndicator()

busyIndicator.Header = "Loading..."

{% endhighlight %}


{% endtabs %}

![Provide the Animation Header](SfBusyIndicator1/Load.png)

## Customizing Busy Caption

`SfBusyIndicator` header can be customized using the `HeaderTemplate` property.

{% tabs %}

{% highlight XAML %}

<Grid Background="CornflowerBlue">

<notification:SfBusyIndicator Header="Loading...">

<notification:SfBusyIndicator.HeaderTemplate>

<DataTemplate>

<Grid Margin="50 0 0 18">

<TextBlock Text="{Binding}" FontSize="16" FontWeight="Bold"/>

</Grid>

</DataTemplate>

</notification:SfBusyIndicator.HeaderTemplate>

</notification:SfBusyIndicator>

</Grid>

{% endhighlight %}

{% endtabs %}

![Provide the Template for Header](SfBusyIndicator1/CustomizeHeader.png)

## Sizing the BusyIndicator

`Width` and `Height` properties which are used for sizing the control does not resize the animating element inside `SfBusyIndicator`. Set the properties `ViewBoxHeight` and `ViewBoxWidth` for sizing the animation inside `SfBusyIndicator`.

Here is an example showing resized `SfBusyIndicator`.

{% tabs %}

{% highlight XAML %}

<Grid Background="CornFlowerBlue"/>

<notification:SfBusyIndicator ViewboxHeight=”70” ViewboxWidth=”70/>

</Grid>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

SfBusyIndicator busyIndicator = new SfBusyIndicator();

busyIndicator.ViewboxHeight = 70.0;

busyIndicator.ViewboxWidth = 70.0;

{% endhighlight %}

{% highlight VB %}

Dim busyIndicator As New SfBusyIndicator()

busyIndicator.ViewboxHeight = 70.0

busyIndicator.ViewboxWidth = 70.0

{% endhighlight %}

{% endtabs %}

![Provide the Size of the Control](SfBusyIndicator1/Sizing.png)

