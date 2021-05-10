---
layout: post
title: Dealing with Value in UWP Progress Bar control | Syncfusion
description: Learn here all about Dealing with Value support in Syncfusion UWP Progress Bar (SfProgressBar) control and more.
platform: UWP
control: SfProgressBar
documentation: ug
--- 

# Dealing with Value in UWP Progress Bar (SfProgressBar)

## Setting Progress Value

`Value` property is used to set the progress in `SfProgressBar` control. Value should fall in between `Minimum` and `Maximum` values.

{% tabs %}

{% highlight XAML %}

<notification:SfProgressBar x:Name="progressBar" Value="35"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

progressBar.Value = 35.0;

{% endhighlight %}

{% endtabs %}

![Dealing-with-Value-img1](Dealing-with-Value-images/Dealing-with-Value-img1.jpeg)


## Setting Progress Range 

`Minimum` and `Maximum` properties are used to set a range for the progress Value. By default, `Minimum` is 1 and `Maximum` is 100.

{% tabs %}

{% highlight XAML %}

<notification:SfProgressBar x:Name="progressBar" Minimum="100"  Maximum="200"  Value="50"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

progressBar.Minimum = 100.0;

progressBar.Maximum = 200.0;

progressBar.Value = 50.0;

{% endhighlight %}

{% endtabs %}

![Dealing-with-Value-img2](Dealing-with-Value-images/Dealing-with-Value-img2.jpeg)

{% tabs %}

{% highlight XAML %}

<notification:SfProgressBar x:Name="progressBar" Minimum="100"  Maximum="200"  Value="150"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

progressBar.Minimum = 100.0;

progressBar.Maximum = 200.0;

progressBar.Value = 150.0;

{% endhighlight %}

{% endtabs %}

![Dealing-with-Value-img3](Dealing-with-Value-images/Dealing-with-Value-img3.jpeg)


## Retrieving Progress Percentage

`Percentage` property is used to get the progress in terms of percentage. It is computed from Value, `Minimum` and `Maximum` properties. 

{% tabs %}

{% highlight XAML %}

<notification:SfProgressBar Minimum="100" Maximum="200" Value="50"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

progressBar.Minimum = 100.0;

progressBar.Maximum = 200.0;

progressBar.Value = 50.0;

{% endhighlight %}

{% endtabs %}

The above code yields a result of zero Percentage (Value is not in `Minimum` and `Maximum` range).

{% tabs %}

{% highlight XAML %}

<notification:SfProgressBar Minimum="100" Maximum="200" Value="150"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

progressBar.Minimum = 100.0;

progressBar.Maximum = 200.0;

progressBar.Value = 150.0;

{% endhighlight %}

{% endtabs %}

The above code yields a result of fifty Percentage (Value is not in Minimum and Maximum range).

