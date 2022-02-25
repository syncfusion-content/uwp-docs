---
layout: post
title: Events and Methods in UWP Navigation Drawer control | Syncfusion
description: Learn here all about Events and Methods support in Syncfusion UWP Navigation Drawer (SfNavigationDrawer) control and more.
platform: UWP
control: NavigationDrawer
documentation: ug
---

# Events and Methods in UWP Navigation Drawer (SfNavigationDrawer)

The below two events are implemented in Transition.

* Opened
* Closed

## Opened

Opened event will be raised when the DrawerContentView is opened in NavigationDrawer.


  {% highlight c# %}

    public event DrawerEventHandler Opened;
        
   {% endhighlight %}

## Closed

Closed event will be raised when the DrawerContentView is closed in NavigationDrawer.



{% highlight c# %}

    public event DrawerEventHandler Closed;
	
{% endhighlight %}

## Toggle Drawer

Represents the opening and closing of the navigation drawer


{% highlight c# %}

     drawer.ToggleDrawer();
	
{% endhighlight %}
