---
layout: post
title: Rating Precisions of SfRating control for UWP
description: Explains about Rating Precisions of SfRating control for UWP
platform: uwp
control: SfRating
documentation: ug
---

# Rating Precisions

`Precision` specifies the level of accuracy in rating value. `SfRating` has three different precision types and they are:

* Standard
* Half
* Exact

## Rating the item completely


Rating item fills completely when pointer enters the rating item. In the following example, 2.3 has been set as the value and the rating item has been filled completely.

{% tabs %}

{% highlight XAML %}

<input:SfRating ItemsCount="5" Value="2.3"
                Precision="Standard" x:Name="rating"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

rating.ItemsCount = 5;

rating.Value = 2.3;

rating.Precision = Syncfusion.UI.Xaml.Primitives.Precision.Standard;

{% endhighlight %}

{% endtabs %}

![](Rating-Precisions-images/Rating-Precisions-img1.jpeg)


## Rating the item partially

Rating item fills partially when pointer enters the rating item. In the following example, 2.3 has been set as the value and the rating item has been filled partially.

{% tabs %}

{% highlight XAML %}

<input:SfRating ItemsCount="5" Value="2.3"
                Precision="Half" x:Name="rating"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

rating.ItemsCount = 5;

rating.Value = 2.3;

rating.Precision = Syncfusion.UI.Xaml.Primitives.Precision.Half;

{% endhighlight %}

{% endtabs %}

![](Rating-Precisions-images/Rating-Precisions-img2.jpeg)


## Rating the item exactly

Rating item fills exactly when the pointer enters the rating item. In the following example, 2.3 has been set as the value and the rating item is filled to the exact value.

{% tabs %}

{% highlight XAML %}

<input:SfRating ItemsCount="5" Value="2.3"
                Precision="Exact" x:Name="rating"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

rating.ItemsCount = 5;

rating.Value = 2.3;

rating.Precision = Syncfusion.UI.Xaml.Primitives.Precision.Exact;

{% endhighlight %}

{% endtabs %}

![](Rating-Precisions-images/Rating-Precisions-img3.jpeg)


