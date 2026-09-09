---
layout: post
title: Getting Started with UWP SfDomainUpDown | Syncfusion®
description: Learn how to get started with the Syncfusion® UWP SfDomainUpDown control. Explore setup, features, examples, and customization options.
platform: uwp
control: SfDomainUpDown
documentation: ug
---

# Getting Started with UWP Domain UpDown

Namespace:  Syncfusion.UI.Xaml.Controls.Input

Assembly:  Syncfusion.SfInput.UWP 

Dependent assembly: Syncfusion.SfShared.UWP



The following code sample shows how to create the UWP Domain UpDown from code-behind and XAML:

{% tabs %}

{% highlight xaml %}

<Page xmlns:editors="using:Syncfusion.UI.Xaml.Controls.Input">

    <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">



        <editors:SfDomainUpDown x:Name="domainUpDown"

                               HorizontalAlignment="Center"

                               VerticalAlignment="Center"

                               Width="200"/>

    </Grid>

</Page>
{% endhighlight %}

{% highlight c# %}

SfDomainUpDown domainUpDown = new SfDomainUpDown();

{% endhighlight %}

{% highlight VB %}

Dim domainUpDown As New SfDomainUpDown()

{% endhighlight %}

{% endtabs %}

N> You can refer to our [UWP Domain UpDown](https://www.syncfusion.com/uwp-ui-controls/domain-up-down) feature tour page to know about its other groundbreaking feature representations. You can also explore our [UWP Domain UpDown example](https://apps.microsoft.com/store/detail/syncfusion-essential-studio-for-uwp/9NBLGGH5WNGV) that shows you how the control is rendered and configured.