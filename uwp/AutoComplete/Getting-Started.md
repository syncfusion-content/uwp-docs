---
layout: post
title: Getting Started with UWP AutoComplete control | Syncfusion
description: Learn here about getting started with Syncfusion UWP AutoComplete (SfTextBoxExt) control, its elements and more.
platform: uwp
control: SfTextBoxExt
documentation: ug
---

# Getting Started with UWP AutoComplete (SfTextBoxExt)

Namespace:  Syncfusion.UI.Xaml.Controls.Input

Assembly:  Syncfusion.SfInput.UWP

Dependent assembly: Syncfusion.SfShared.UWP

The following code sample shows how to create the SfTextBoxExt from code-behind and XAML:

{% tabs %}

{% highlight xaml %}

<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:editors="using:Syncfusion.UI.Xaml.Controls.Input" >

    <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

      <editors:SfTextBoxExt HorizontalAlignment="Center" 

                            VerticalAlignment="Center" 

                            Width="200"

                            Text="Hello! World..."/>
    </Grid>
</Page>

{% endhighlight %}


{% highlight c# %}

SfTextBoxExt textBox = new SfTextBoxExt();

{% endhighlight %}

{% highlight VB %}

Dim textBox As New SfTextBoxExt()

{% endhighlight %}

{% endtabs %}


