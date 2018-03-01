---
layout: post
title: Save and Events | SfImageEditor | uwp | Syncfusion
description: Save and Events
platform: uwp
control: SfImageEditor
documentation: ug
---

# Save

The image can be saved along with the changes. Saving an image can be done in the following two ways:

* From Toolbar
* Using Code

## From Toolbar

To save an image from the toolbar, click the `Save` button in the top toolbar. The saved image will be added in default pictures library "C:\\Users\\your name\\Pictures\\Saved Pictures".

## Using Code

Programmatically, `Save` method can be used in the SfImageEditor control to save the image.


{% highlight C# %}

    imageEditor.Save();

{% endhighlight %}


# Events

The SfImageEditor has Events namely, [`ImageSaving`](https://help.syncfusion.com/cr/uwp/sfimageeditor) and [`ImageSaved`](https://help.syncfusion.com/cr/uwp/sfimageeditor).

## ImageSaving

This event occurs before saving the image. You can control the save functionality by using the `Cancel` argument.  

{% highlight C# %}

    args.Cancel = true;

{% endhighlight %}

## ImageSaved

This event occurs after the image has been saved. To get the location of the saved image, use the `Location` argument as shown below,

{% highlight C# %}

    string savedLocation = args.Location;

{% endhighlight %}

# Reset

You can `reset` the changes which has been made in the image.

### From Toolbar

To reset the changes from the toolbar, click the `Reset` button in the top toolbar. The changes will be reset and the initial loaded image will appear.

### Using Code

The `Reset` method resets the all changes which has been made in the image and resets the original loaded image to the Image Editor control.


{% highlight C# %}

    imageEditor.Reset();

{% endhighlight %}

# Events

The SfImageEditor has Events namely, [`BeginReset`](https://help.syncfusion.com/cr/uwp/sfimageeditor) and [`EndReset`](https://help.syncfusion.com/cr/uwp/sfimageeditor).

## BeginReset

This event occurs before resetting the changes in an image. You can control the reset functionality by using the `Cancel` argument.

{% highlight C# %}

    args.Cancel = true;

{% endhighlight %}

## EndReset

This event occurs when reset has been completed.