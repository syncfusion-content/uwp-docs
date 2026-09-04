---
layout: post
title: Dealing with Value in UWP SfRating | Syncfusion®
description: The dealing with value feature in SfRating allows getting or setting the rate value using the Value property to track the user's rating.
platform: uwp
control: SfRating
documentation: ug
---

# Dealing with Value in UWP Rating

## Setting the rated value

`Value` property is used to get or set the rate value in `UWP Rating` control.

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

{% highlight VB %}

rating.ItemsCount = 5

rating.Value = 2

{% endhighlight %}

{% endtabs %}

![Setting the rated value view](Dealing-with-Value-and-PreviewValue-images/Dealing-with-Value-and-PreviewValue-img1.jpeg)


## Previewing the rate

`PreviewValue` property is used to get the pointer over value in UWP Rating control, and this value is displayed as tool tip content.

![Rating PreviewValue view](Dealing-with-Value-and-PreviewValue-images/Dealing-with-Value-and-PreviewValue-img2.jpeg)


## ValueChanged event

`ValueChanged` event fires whenever the value is changed in UWP Rating control. Event arguments contain old value and new value.

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

{% highlight VB %}

Private Sub rating_ValueChanged(ByVal sender As Object, ByVal e As ValueChangedEventArgs)


End Sub

{% endhighlight %}

{% endtabs %}


## Read only UWP Rating control

`UWP Rating` can also restrict user from changing the rates in control using the `IsReadOnly` property. But preview value changes when pointer moves over the control.

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

{% highlight VB %}

rating.ItemsCount = 5

rating.Value = 2

rating.IsReadOnly = True

{% endhighlight %}

{% endtabs %}
