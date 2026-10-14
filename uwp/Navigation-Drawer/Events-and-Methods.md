---
layout: post
title: Events and Methods in UWP Navigation Drawer | Syncfusion®
description: Handle drawer open and close events and control drawer visibility programmatically using built-in methods in the UWP Navigation Drawer control.
platform: uwp
control: NavigationDrawer
documentation: ug
---

# Events and Methods in UWP Navigation Drawer (SfNavigationDrawer)

The SfNavigationDrawer control exposes the following two events, which are raised when the drawer is opened or closed:

* Opened
* Closed

## Opened

The Opened event will be raised when the DrawerContentView is opened in the UWP NavigationDrawer.


  {% highlight c# %}

    public event DrawerEventHandler Opened;
        
   {% endhighlight %}

## Closed

The Closed event will be raised when the DrawerContentView is closed in the UWP NavigationDrawer.



{% highlight c# %}

    public event DrawerEventHandler Closed;
	
{% endhighlight %}

## Toggle Drawer

Represents the opening and closing of the UWP Navigation Drawer


{% highlight c# %}

     drawer.ToggleDrawer();
	
{% endhighlight %}
