---
layout: post
title: Viewing Suggestions on SfTextBoxExt control focus
description: Viewing Suggestions on SfTextBoxExt control focus
platform: uwp
control: SfTextBoxExt
documentation: ug
---

# Viewing Suggestions on Control Focus

You can turn on the ShowSuggestionsOnFocus property to view suggestions for auto completion when the SfTextBoxExt control is in focus. The following code example and screen shot illustrate this.

{% tabs %}

{% highlight xaml %}

<editors:SfTextBoxExt x:Name="textBox" HorizontalAlignment="Center" VerticalAlignment="Center" Width="400" SearchItemPath="Name" ShowSuggestionsOnFocus="True" AutoCompleteMode="Suggest" AutoCompleteSource="{Binding Employees}"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

textBox.ShowSuggestionsOnFocus = true;

{% endhighlight %}

{% highlight VB %}

textBox.ShowSuggestionsOnFocus = True

{% endhighlight %}

{% endtabs %}

![ Viewing Suggestions on Control Focus](Viewing-Suggestions-on-Control-Focus_images/Viewing-Suggestions-on-Control-Focus_img1.png)





