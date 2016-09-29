---
layout: post
title: State Persistence of Syncfusion SfDockingManager control for UWP
description: Learn how to serialize and de-serialize the state of SfDockingManager child windows
platform: uwp
control: SfDockingManager
documentation: ug
---

# State Persistence

State persistence is the combined process of `serialization` and `deserialization`.

`SfDockingManager` provides built-in state persistence functionality to save and load at different states and sides. It also provides ResetDockState() method to reset the layout to initial state.

## Saving Current State

The current layout can be serialized in XML file and saved in `IsolatedStorage` using `SaveDockState` method.

{% tabs %}

{% highlight C# %}

private void OnSuspending(object sender, SuspendingEventArgs e)

{

dockingManager.SaveDockState();

var deferral = e.SuspendingOperation.GetDeferral();

//TODO: Save application state and stop any background activity

deferral.Complete();

} 

{% endhighlight %}

{% endtabs %}

## Loading Saved State

The saved layout can be retrieved from `IsolatedStorage`, `de-serialized` and loaded using `LoadDockState` method.

{% tabs %}

{% highlight C# %}

private void Docking_Loaded(object sender, RoutedEventArgs e)

{

dockingManager.LoadDockState();

}


{% endhighlight %}

{% endtabs %}

## Resetting Initial State

To reset the `SfDockingManager` state, call ResetDockState() method of `SfDockingManager` instance. 

{% tabs %}

{% highlight C# %}

dockingManager.ResetDockState();

{% endhighlight %}

{% endtabs %}

## Serialize the dynamically added children

By default, `SfDockingManager` cannot de-serialize its Saved Layout properly, when its child collection is modified after DockState is saved.

Since the `SfDockingManager` state persistence feature implemented in such a way that the `SfDockingManager` matches the child collection of saved layout with current `SfDockingManager` layout internally and loads properly when `SfDockingManager` children collection remains same, so when any child collection changes dynamically, it results in an improper layout.

