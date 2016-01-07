---
layout: post
title: Dealing with Value and PreviewValue of SfRating control for UWP
description: Dealing with Value and PreviewValue of SfRating control for UWP
platform: uwp
control: SfRating
documentation: ug
---

# Dealing with Value and PreviewValue

## Value

`Value` property is used to get or set the rate value in `SfRating` control.

{% tabs %}

{% highlight XAML %}

<input:SfRating ItemsCount="5" Value="2" x:Name="rating"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

rating.ItemsCount = 5;

rating.Value = 2;

{% endhighlight %}

{% endtabs %}

![](Dealing-with-Value-and-PreviewValue-images/Dealing-with-Value-and-PreviewValue-img1.jpeg)


## PreviewValue

`PreviewValue` property is used to get the pointer over value in SfRating control, and this value is displayed as tool tip content.

![](Dealing-with-Value-and-PreviewValue-images/Dealing-with-Value-and-PreviewValue-img2.jpeg)


## ValueChanged event

`ValueChanged` event fires whenever the value is changed in rating control. Event arguments contain old value and new value.

{% tabs %}

{% highlight XAML %}

<input:SfRating ItemsCount="5" ValueChanged="rating_ValueChanged"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

private void rating_ValueChanged(object sender, ValueChangedEventArgs e)

{
            
}

{% endhighlight %}

{% endtabs %}


## Read-only

`SfRating` can also restrict user from changing the rates in control using the `IsReadOnly` property. But preview value changes when pointer moves over the control.

{% tabs %}

{% highlight XAML %}

<input:SfRating ItemsCount="5" Value="2" IsReadOnly="true" x:Name="rating"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

rating.ItemsCount = 5;

rating.Value = 2;

rating.IsReadOnly = true;

{% endhighlight %}

{% endtabs %}
