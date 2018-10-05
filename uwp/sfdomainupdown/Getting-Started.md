---
layout: post
title: Getting Started with SfDomainUpDown control for UWP
description:  A quick tour to initial users on SfDomainUpDown control for for Universal Windows Platform project in Visual Studio 
platform: uwp
control: SfDomainUpDown
documentation: ug
---

# Getting Started

Namespace:  Syncfusion.UI.Xaml.Controls.Input

Assembly:  Syncfusion.SfInput.UWP 

Dependent assembly: Syncfusion.SfShared.UWP



The following code sample shows how to create the SfDomainUpDown from code-behind and XAML:

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
