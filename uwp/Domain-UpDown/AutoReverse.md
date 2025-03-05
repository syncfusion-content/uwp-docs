---
layout: post
title: Autoreverse in UWP Domain UpDown control | Syncfusion®
description: Learn here all about Autoreverse support in Syncfusion® UWP Domain UpDown (SfDomainUpDown) control and more.
platform: uwp
control: SfDomainUpDown
documentation: ug
---

# Autoreverse in UWP Domain UpDown (SfDomainUpDown)

Incrementing the value starts from the maximum value once it has reached the minimum value and starts from the minimum value once it has reached the maximum value.

{% tabs %}

{% highlight xaml %}



<editors:SfDomainUpDown x:Name="domainUpDown"

                               HorizontalAlignment="Center"

                               VerticalAlignment="Center"

                               Width="200" 

AutoReverse="True"

                               ItemsSource="{Binding Employees}">

</editors:SfDomainUpDown >

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

domainUpDown.AutoReverse = true;

{% endhighlight %}

{% highlight VB %}

domainUpDown.AutoReverse = True

{% endhighlight %}

{% endtabs %}
