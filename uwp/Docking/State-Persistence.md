---
layout: post
title: State Persistence in UWP SfDockingManager | Syncfusion®
description: The State Persistence feature in SfDockingManager saves and loads the layout across sessions using serialization and deserialization.
platform: uwp
control: SfDockingManager
documentation: ug
---

# State Persistence in UWP Docking Control

State persistence is the combined process of `serialization` and `deserialization`.

`UWP Docking Control` provides built-in state persistence functionality to save and load the layout across sessions, preserving the dock states and sides of its child windows. It also provides the `ResetDockState()` method to reset the layout to its initial state.

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

The `UWP Docking Control` state can be reset using the `ResetDockState()` method.

{% tabs %}

{% highlight C# %}

dockingManager.ResetDockState();

{% endhighlight %}

{% endtabs %}

## Serializing Dynamically Added Children

By default, `UWP Docking Control` cannot de-serialize its saved layout properly when its child collection is modified after the DockState is saved.

The `UWP Docking Control` state persistence feature matches the saved layout with the current child collection and restores the layout accordingly. State persistence works correctly when the child collection remains unchanged between save and load operations. If the collection is modified dynamically, the layout may not be restored as expected. To avoid this issue, ensure that the child collection remains the same during both save and load operations.

