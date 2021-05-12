---
layout: post
title: Appearance and Styling in UWP Domain UpDown control | Syncfusion
description: Learn here all about Appearance and Styling support in Syncfusion UWP Domain UpDown (SfDomainUpDown) control and more.
platform: uwp
control: SfDomainUpDown
documentation: ug
---

# Appearance and Styling in UWP Domain UpDown (SfDomainUpDown)

## Spin Animation

Items will spin up or down with smooth transition. The transition can be disabled using the EnableSpinAnimation property.

{% tabs %}

{% highlight xaml %}


<syncfusion:SfDomainUpDown x:Name="domain"

                                 HorizontalAlignment="Center"

                                 VerticalAlignment="Center"

                                 Width="200" EnableSpinAnimation="True"/>
{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

domain.EnableSpinAnimation = true;

{% endhighlight %}

{% highlight VB %}

domain.EnableSpinAnimation = True

{% endhighlight %}

{% endtabs %}

## Accent Brush

The AccentBrush property is used to decorate the hot spots of a control with a solid color. 

{% tabs %}

{% highlight xaml %}

<Page xmlns:editors="using:Syncfusion.UI.Xaml.Controls.Input">

    <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">



        <editors:SfDomainUpDown x:Name="domainUpDown"

                               HorizontalAlignment="Center"

                               VerticalAlignment="Center"

                               Width="200" 

AccentBrush="Black"

                              Value="James">

        </editors:SfDomainUpDown >



    </Grid>

</Page>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

domainUpDown.AccentBrush = new SolidColorBrush(Colors.Red);

{% endhighlight %}

{% highlight VB %}

domainUpDown.AccentBrush = New SolidColorBrush(Colors.Red)

{% endhighlight %}

{% endtabs %}
