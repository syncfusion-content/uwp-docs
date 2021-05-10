---
layout: post
title: Displaying Progress Text in UWP Progress Bar control | Syncfusion
description: Learn here all about Displaying Progress Text support in Syncfusion UWP Progress Bar (SfProgressBar) control and more.
platform: UWP
control: SfProgressBar
documentation: ug
--- 

# Displaying Progress Text in UWP Progress Bar (SfProgressBar)

`SfProgressBar` can display either `Value` or `Percentage` or `Custom Text` as display content using the property `DisplayContentMode`. The values of `DisplayContentMode` are

* None
* Value
* Percentage
* Custom

## Showing Value as Display Text

`SfProgressBar` can display Value as display content by set the property `DisplayContentMode` to Value.

{% tabs %}

{% highlight XAML %}

<notification:SfProgressBar x:Name="progressBar" DisplayContentMode="Value"  />

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

progressBar.DisplayContentMode = DisplayContentMode.Value;

{% endhighlight %}

{% endtabs %}

![Displaying-Progress-Text-img1](Displaying-Progress-Text-images/Displaying-Progress-Text-img1.jpeg)


The above code displays the Value as display content.

## Showing Percentage as Display Text

`SfProgressBar` can display `Percentage` as display content by set the property `DisplayContentMode` to `Percentage`.

{% tabs %}

{% highlight xml %}

<notification:SfProgressBar x:Name="progressBar" DisplayContentMode="Percentage"  />

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

progressBar.DisplayContentMode = DisplayContentMode.Percentage;

{% endhighlight %}

{% endtabs %}

![Displaying-Progress-Text-img2](Displaying-Progress-Text-images/Displaying-Progress-Text-img2.jpeg)


The above code displays the computed Percentage value as display content.

## Showing Custom Content as Display Text

`SfProgressBar` can display Custom Text as display content by set the property `DisplayContentMode` to Custom.

{% tabs %}

{% highlight XAML %}

<notification:SfProgressBar x:Name="progressBar" DisplayContentMode="Custom" CustomContent="Loading.." />

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

progressBar.DisplayContentMode = DisplayContentMode.Custom;

{% endhighlight %}

{% endtabs %}

![Displaying-Progress-Text-img3](Displaying-Progress-Text-images/Displaying-Progress-Text-img3.jpeg)


The above code displays the custom content as display content.

## Disabling the Display Text

`SfProgressBar` display content can be disabled by set the property `DisplayContentMode` to None.

{% tabs %}

{% highlight XAML %}

<notification:SfProgressBar x:Name="progressBar" DisplayContentMode="None"  />

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

progressBar.DisplayContentMode = DisplayContentMode.None;

{% endhighlight %}

{% endtabs %}

![Displaying-Progress-Text-img4](Displaying-Progress-Text-images/Displaying-Progress-Text-img4.jpeg)


The above code displays nothing in display content.

## Customizing the Display Content

`DisplayContentStyle` property is used to customize the display content. It can be set as follows:

{% tabs %}

{% highlight XAML %}

<notification:SfProgressBar Value="50" DisplayContentMode="Percentage">

<notification:SfProgressBar.DisplayContentStyle>

<Style TargetType="ContentControl">

<Setter Property="Foreground" Value="Red"/>

</Style>

</notification:SfProgressBar.DisplayContentStyle>

</notification:SfProgressBar>

{% endhighlight %}

{% endtabs %}

![Displaying-Progress-Text-img5](Displaying-Progress-Text-images/Displaying-Progress-Text-img5.jpeg)


