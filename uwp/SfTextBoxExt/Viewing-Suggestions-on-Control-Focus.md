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

{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" VerticalAlignment="Center" Width="400" SearchItemPath="Name" ShowSuggestionsOnFocus="True" AutoCompleteMode="Suggest" AutoCompleteSource="{Binding Employees}"/>

{% endhighlight %}

![](Viewing-Suggestions-on-Control-Focus_images/Viewing-Suggestions-on-Control-Focus_img1.png)





