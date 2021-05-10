---
layout: post
title: Save and Reset Events in UWP Image Editor control | Syncfusion
description: Learn here all about Save and Reset Events support in Syncfusion UWP Image Editor (SfImageEditor) control and more.
platform: uwp
control: SfImageEditor
documentation: ug
---

# Save and Reset Events in UWP Image Editor (SfImageEditor)

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

## Saving image with custom size and format

The [`Save`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html#Syncfusion_UI_Xaml_ImageEditor_SfImageEditor_Save_System_String_Windows_Foundation_Size_) method in the SfImageEditor control allows user to save an image in different format such as `png`, `jpg`, and `bmp`.

You can choose the format while saving the image.

{% tabs %}

{% highlight C# %}

   imageEditor.Save(".png");

{% endhighlight %}

{% endtabs %}

You can choose the format and size while saving the image as follows.

{% tabs %}

{% highlight C# %}

   imageEditor.Save(".png",new Size(913,764));

{% endhighlight %}

{% endtabs %} 

N> Supported formats are `.png`, `.jpg`, and `.bmp`.

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

        public MainPage()
            {               
                            . . .

                         imageEditor.BeginReset += editor_BeginReset;

                            . . .
            }

        private void editor_BeginReset(object sender, BeginResetEventArgs args)
            {
                args.Cancel = true; //It restricts resetting image to initial loaded image.
            }

{% endhighlight %}

## EndReset

This event occurs when reset has been completed.

{% highlight C# %}

        public MainPage()
            {               
                            . . .

                             imageEditor.EndReset += editor_EndReset;

                            . . .
            }

        private void editor_EndReset(object sender, EndResetEventArgs args)
            {
             
                this.Frame.Navigate(typeof(NewPage)); //Navigates to new page after completing the reset action.
            }

{% endhighlight %}

## ImageLoaded event

This event will be triggered after the image has been loaded. By this event you can add any shapes or text over an image or crop an image while initially loading the image. 

{% highlight C# %}

        public MainPage()
            {               
                            . . .

                imageEditor.ImageLoaded += Editor_ImageLoaded;

                            . . .
            }

        private void Editor_ImageLoaded(object sender, ImageLoadedEventArgs args)
            {
                imageEditor.AddShape(ShapeType.Circle, new PenSettings() { });
            }

{% endhighlight %}


## ItemSelected event

This event will be triggered whenever you tap the selected shapes (rectangle, circle, and arrow), text or custom view. You can get the settings of each selected shapes, text or custom view using the ItemSelected argument. You can also change the settings that will affect the selected shapes.

{% highlight C# %}

        public MainPage()
            {               
                            . . .

                imageEditor.ImageLoaded += Editor_ImageLoaded;
                imageEditor.ItemSelected += Editor_ItemSelected;

                            . . .
            }

        private void Editor_ImageLoaded(object sender, ImageLoadedEventArgs args)
            {
                imageEditor.AddShape(ShapeType.Circle, new PenSettings() {Mode = Mode.Stroke });
            }

        private void Editor_ItemSelected(object sender, ItemSelectedEventArgs args)
            {
                var settings = args.Settings;

                if (settings is PenSettings)
                {
                    (settings as PenSettings).Color = new SolidColorBrush(Colors.Blue);
                }
                else
                {
                    (settings as TextSettings).Color = new SolidColorBrush(Colors.Blue);
                }
     
            }

{% endhighlight %}

## ItemUnselected event

This event will be triggered whenever you change the shape selections from one shape to another shape (rectangle, circle, arrow, and text). You can get the settings of previous selected shapes, text or custom view using the ItemUnselected event. You can also change the settings of previous selected shapes.

{% highlight C# %}

public MainPage()
{
    imageEditor.ItemUnselected += Editor_ItemUnselected;
}

private void Editor_ItemUnselected(object sender, ItemUnselectedEventArgs args)
{
            var settings = args.Settings;

            if (settings is PenSettings)
            {
                (settings as PenSettings).Color = new SolidColorBrush(Colors.Green);
            }
            else
            {
                (settings as TextSettings).Color = new SolidColorBrush(Colors.Green);
            }
}

{% endhighlight %}

## ImageEdited event

This event occurs whenever you start to edit an image. You can know whether the current image is edited or not using the IsImageEdited argument.

{% highlight c# %}

public MainPage()
{               
    . . .
    imageEditor.ImageEdited += ImageEditor_ImageEdited;
    . . .
}

private void ImageEditor_ImageEdited(object sender, ImageEditedEventArgs e)
{
    if (args.IsImageEdited)
    {
    }            
}

{% endhighlight %}

## See also

[How to change the image saving location in the image editor control for uwp](https://www.syncfusion.com/kb/10077/how-to-change-the-image-saving-location-in-the-image-editor-control-for-uwp)

[How to retrieve an image from the saved location in uwp](https://www.syncfusion.com/kb/10060/how-to-retrieve-an-image-from-the-saved-location-in-uwp)

[How to save image to stream in uwp image editor](https://www.syncfusion.com/kb/9463/how-to-save-image-to-stream-in-uwp-imageeditor)

[How to change the image saving location in uwp](https://www.syncfusion.com/kb/8927/how-to-change-the-image-saving-location-in-uwp)
