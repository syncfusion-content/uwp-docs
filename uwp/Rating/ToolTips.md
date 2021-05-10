---
layout: post
title: ToolTips in UWP Rating control | Syncfusion
description: Learn here all about ToolTips support in Syncfusion UWP Rating (SfRating) control and more.
platform: uwp
control: SfRating
documentation: ug
---

# ToolTips in UWP Rating (SfRating)

## Enable/Disable Tooltip

Tooltips in SfRating control shows the rating value. Tooltips can be enabled or disabled using the property `ShowToolTip`.

{% tabs %}

{% highlight XAML %}

<input:SfRating ItemsCount="5" ShowToolTip="true" x:Name="rating"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

rating.ShowToolTip = true;

{% endhighlight %}

{% highlight VB %}

rating.ShowToolTip = True

{% endhighlight %}

{% endtabs %}

![Rating Enable ToolTip view](ToolTips-images/ToolTips-img1.jpeg)


## Tooltip Precision

The number of decimal digits displayed in tooltips is determined by `AutoTooltipPrecision` property. Decimal digits are not possible in Standard precision type and one decimal digit decimal 

{% tabs %}

{% highlight XAML %}

<input:SfRating ItemsCount="5" ShowToolTip="True"
                AutoToolTipPrecision="3" Precision="Exact"
				x:Name="rating"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

rating.ItemsCount = 5;

rating.ShowToolTip = true;

rating.Precision = Syncfusion.UI.Xaml.Primitives.Precision.Exact;

rating.AutoToolTipPrecision = 3;

{% endhighlight %}

{% highlight VB %}

rating.ItemsCount = 5

rating.ShowToolTip = True

rating.Precision = Syncfusion.UI.Xaml.Primitives.Precision.Exact

rating.AutoToolTipPrecision = 3

{% endhighlight %}

{% endtabs %}
