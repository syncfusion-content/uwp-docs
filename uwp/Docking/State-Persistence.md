---
layout: post
title: State Persistence in UWP Docking control | Syncfusion®
description: Learn here all about State Persistence support in Syncfusion® UWP Docking (SfDockingManager) control and more.
platform: uwp
control: SfDockingManager
documentation: ug
---

# State Persistence in UWP Docking (SfDockingManager)

State persistence is the combined process of `serialization` and `deserialization`.

`SfDockingManager` provides built-in state persistence functionality to save and load the layout across sessions, preserving the dock states and sides of its child windows. It also provides the `ResetDockState()` method to reset the layout to its initial state.

## Saving Current State

The current layout can be serialized into an XML file and saved in `IsolatedStorage` using the `SaveDockState` method. The following example saves the layout when the application is being suspended.

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

The saved layout can be retrieved from `IsolatedStorage`, de-serialized, and loaded using the `LoadDockState` method. On first launch (when no saved state exists), calling `LoadDockState` has no effect.

{% tabs %}

{% highlight C# %}

private void Docking_Loaded(object sender, RoutedEventArgs e)

{

dockingManager.LoadDockState();

}

{% endhighlight %}

{% endtabs %}

## Resetting Initial State

To reset the `SfDockingManager` state, call the `ResetDockState()` method of the `SfDockingManager` instance. 

{% tabs %}

{% highlight C# %}

dockingManager.ResetDockState();

{% endhighlight %}

{% endtabs %}

## Serializing Dynamically Added Children

By default, `SfDockingManager` cannot de-serialize its saved layout properly when its child collection is modified after the DockState is saved.

The `SfDockingManager` state persistence feature is implemented in such a way that the `SfDockingManager` matches the child collection of the saved layout with the current `SfDockingManager` layout internally and loads properly when the `SfDockingManager` children collection remains the same. Therefore, when any child collection changes dynamically, it results in an improper layout. To avoid this, ensure the children collection of `SfDockingManager` is the same at both save and load time.

