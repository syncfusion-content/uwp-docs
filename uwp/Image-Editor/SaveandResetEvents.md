---
layout: post
title: Save and Events | SfImageEditor | uwp | Syncfusion
description:  Learn how to save the image in different ways and use of different events in ImageEditor for UWP platform.
platform: uwp
control: SfImageEditor
documentation: ug
---

# Save edited image in SfImageEditor

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


## Events

The SfImageEditor has Events namely, [`ImageSaving`](https://help.syncfusion.com/cr/uwp/sfimageeditor) and [`ImageSaved`](https://help.syncfusion.com/cr/uwp/sfimageeditor).

## ImageSaving

This event occurs before saving the image. Described the ImageSaving event arguments below.

`Cancel` : You can control the save functionality using the `Cancel` argument.

It restricts saving image to the default location when set `Cancel` value to `true`.

{% tabs %}

{% highlight xaml %}

            <imageeditor:SfImageEditor ImageSaving="SfImageEditor_ImageSaving" />

{% endhighlight %}

{% highlight C# %}
           
  		    private void SfImageEditor_ImageSaving(object sender, Syncfusion.UI.Xaml.ImageEditor.ImageSavingEventArgs args)
            {
                args.Cancel = true;  
            }

{% endhighlight %}

{% endtabs %}

`Stream` : You can get current image edits as stream using this argument.

{% highlight C# %}
           
            private void SfImageEditor_ImageSaving(object sender, Syncfusion.UI.Xaml.ImageEditor.ImageSavingEventArgs args)
            {
                var stream = args.Stream;
            }

{% endhighlight %}

`FileName`: You can save the edited image in the specified name. 

{% highlight c# %}

          private void SfImageEditor_ImageSaving(object sender, Syncfusion.UI.Xaml.ImageEditor.ImageSavingEventArgs args)
          {
             args.FileName = "SavedImage";
          }

{% endhighlight %}

## ImageSaved

This event occurs after the image has been saved. To get the location of the saved image, use the `Location` argument as shown below,

{% highlight C# %}

    string savedLocation = args.Location;

{% endhighlight %}

## Reset

You can `reset` the changes which has been made in the image.

### From Toolbar

To reset the changes from the toolbar, click the `Reset` button in the top toolbar. The changes will be reset and the initial loaded image will appear.

### Using Code

The `Reset` method resets the all changes which has been made in the image and resets the original loaded image to the Image Editor control.


{% highlight C# %}

    imageEditor.Reset();

{% endhighlight %}

## Events

The SfImageEditor has Events namely, [`BeginReset`](https://help.syncfusion.com/cr/uwp/sfimageeditor) and [`EndReset`](https://help.syncfusion.com/cr/uwp/sfimageeditor).

## BeginReset

This event occurs before resetting the changes in an image. You can control the reset functionality by using the `Cancel` argument.

{% highlight C# %}

    args.Cancel = true;

{% endhighlight %}

## EndReset

This event occurs when reset has been completed.

## See also

[How to change the image saving location in the image editor control for uwp](https://www.syncfusion.com/kb/10077/how-to-change-the-image-saving-location-in-the-image-editor-control-for-uwp)

[How to retrieve an image from the saved location in uwp](https://www.syncfusion.com/kb/10060/how-to-retrieve-an-image-from-the-saved-location-in-uwp)

[How to save image to stream in uwp image editor](https://www.syncfusion.com/kb/9463/how-to-save-image-to-stream-in-uwp-imageeditor)

[How to change the image saving location in uwp](https://www.syncfusion.com/kb/8927/how-to-change-the-image-saving-location-in-uwp)