---
layout: post
title: AutoReverse options of SfDomainUpDown control for UWP
description:  AutoReverse options of SfDomainUpDown control for UWP
platform: uwp
control: SfDomainUpDown
documentation: ug
---

# AutoReverse

Incrementing the value starts from the maximum value once it has reached the minimum value and starts from the minimum value once it has reached the maximum value.

{% highlight xaml %}



<editors:SfDomainUpDown x:Name="domainUpDown"

                               HorizontalAlignment="Center"

                               VerticalAlignment="Center"

                               Width="200" 

AutoReverse="True"

                               ItemsSource="{Binding Employees}">

</editors:SfDomainUpDown >

{% endhighlight %}