---
layout: post
title: State Persistence in UWP Ribbon control | Syncfusion
description: Learn here all about State Persistence support in Syncfusion UWP Ribbon (SfRibbon(Touch Ribbon)) control and more.
platform: uwp
control: SfRibbon (Touch Ribbon)
documentation: ug
---

# State Persistence in UWP Ribbon (SfRibbon(Touch Ribbon))

State Persistence is the combined process of Serialization and Deserialization. Serialization is the process of converting the state of an object to a format where it can be persisted as a file in the memory. The serialized format contains the object’s state information. Deserialization is the complement process of Serialization that converts into the object from the stored state information. user can save and load the

* RibbonState (Normal, Adorner, Hide)
* Selected Ribbon Tab
* QuickAccessToolbar items
* QuickAccessToolBar State (Above or Below Ribbon)

The Ribbon State Persistence feature helps users to load the state of the Ribbon control that existed when the application was closed. State Persistence feature gives a more consistent workflow for an application that is executed for a long time. Serialize() and DeSerialize() public methods are provided for state persistence. It can be called whenever required. State Persistence is not done internally.

The following code snippet shows how to achieve the serialization and deserialization

{% tabs %}

{% highlight xaml %}
<StackPanel>

<StackPanel>

<TextBlock Margin="5" Text="Serialize" />

<Button Click="OnSerialize" Content="Save" />

</StackPanel>

<StackPanel>

<TextBlock Margin="5" Text="DeSerialize " />

<Button Click="OnDeserialize" Content="Load" />

</StackPanel>

</StackPanel>

{% endhighlight %}

{% endtabs %}


{% tabs %}

{% highlight c# %}

private void OnSerialize(object sender, RoutedEventArgs args)

{

try

{

this.ribbon.Serialize();

}

catch (Exception)

{

}

}

private async void OnDeserialize(object sender, RoutedEventArgs args)

{

try

{

this.ribbon.DeSerialize();

}

catch (Exception)

{

}

}



{% endhighlight %}

{% highlight VB %}

Private Sub OnSerialize(ByVal sender As Object, ByVal args As RoutedEventArgs)


Try


Me.ribbon.Serialize()


Catch e1 As Exception


End Try

End Sub

Private Async Sub OnDeserialize(ByVal sender As Object, ByVal args As RoutedEventArgs)


Try


Me.ribbon.DeSerialize()


Catch e1 As Exception


End Try

End Sub

{% endhighlight %}

{% endtabs %}
