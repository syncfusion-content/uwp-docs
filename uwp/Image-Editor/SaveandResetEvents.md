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

To save an image from the toolbar, click the `Save` button in the top toolbar. The saved image will be added to the default pictures library at `C:\\Users\\your name\\Pictures\\Saved Pictures`.

## Using Code

Programmatically, the `Save` method can be used in the SfImageEditor control to save the image.


{% highlight C# %}

    imageEditor.Save();

{% endhighlight %}


## Events

The SfImageEditor has the following events: [`ImageSaving`](https://help.syncfusion.com/cr/uwp/sfimageeditor) and [`ImageSaved`](https://help.syncfusion.com/cr/uwp/sfimageeditor).

## ImageSaving

This event occurs before saving the image. The `ImageSaving` event arguments are described below.

`Cancel` : You can control the save functionality using the `Cancel` argument.

It restricts saving the image to the default location when the `Cancel` value is set to `true`.

{% tabs %}

{% highlight XAML %}

            xmlns:imageeditor="using:Syncfusion.UI.Xaml.ImageEditor"

            <imageeditor:SfImageEditor ImageSaving="SfImageEditor_ImageSaving" />

{% endhighlight %}

{% highlight C# %}
           
            using Syncfusion.UI.Xaml.ImageEditor;

  		    private void SfImageEditor_ImageSaving(object sender, ImageSavingEventArgs args)
            {
                args.Cancel = true;  
            }

{% endhighlight %}

{% endtabs %}

`Stream` : You can get the current image edits as a stream using this argument.

{% highlight C# %}
           
            using Syncfusion.UI.Xaml.ImageEditor;

            private void SfImageEditor_ImageSaving(object sender, ImageSavingEventArgs args)
            {
                var stream = args.Stream;
            }

{% endhighlight %}

`FileName`: You can save the edited image using the specified file name. 

{% highlight C# %}

          using Syncfusion.UI.Xaml.ImageEditor;

          private void SfImageEditor_ImageSaving(object sender, ImageSavingEventArgs args)
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

The [`Save`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.ImageEditor.SfImageEditor.html#Syncfusion_UI_Xaml_ImageEditor_SfImageEditor_Save_System_String_Windows_Foundation_Size_) method in the SfImageEditor control allows the user to save an image in different formats such as `png`, `jpg`, and `bmp`.

You can choose the format while saving the image.

{% tabs %}

{% highlight C# %}

   using Windows.Foundation;

   imageEditor.Save(".png");

{% endhighlight %}

{% endtabs %}

You can choose the format and size while saving the image as follows.

{% tabs %}

{% highlight C# %}

   using Windows.Foundation;

   imageEditor.Save(".png", new Size(913, 764));

{% endhighlight %}

{% endtabs %} 

N> Supported formats are `.png`, `.jpg`, and `.bmp`.

## Reset

You can reset the changes that have been made in the image.

### From Toolbar

To reset the changes from the toolbar, click the `Reset` button in the top toolbar. The changes will be reset, and the initially loaded image will appear.

### Using Code

The `Reset` method resets all the changes that have been made in the image and restores the originally loaded image to the Image Editor control.


{% highlight C# %}

    imageEditor.Reset();

{% endhighlight %}

## Events

The SfImageEditor has the following events: [`BeginReset`](https://help.syncfusion.com/cr/uwp/sfimageeditor) and [`EndReset`](https://help.syncfusion.com/cr/uwp/sfimageeditor).

## BeginReset

This event occurs before resetting the changes in an image. You can control the reset functionality by using the `Cancel` argument.

{% highlight C# %}

        using Syncfusion.UI.Xaml.ImageEditor;

        public MainPage()
            {               
                            . . .

                         imageEditor.BeginReset += editor_BeginReset;

                            . . .
            }

        private void editor_BeginReset(object sender, BeginResetEventArgs args)
            {
                args.Cancel = true; //It restricts resetting the image to its initial loaded state.
            }

{% endhighlight %}

## EndReset

This event occurs when the reset has been completed.

{% highlight C# %}

        using Windows.UI.Xaml.Controls;

        public MainPage()
            {               
                            . . .

                             imageEditor.EndReset += editor_EndReset;

                            . . .
            }

        private void editor_EndReset(object sender, EndResetEventArgs args)
            {
             
                this.Frame.Navigate(typeof(NewPage)); //Navigates to a new page after completing the reset action.
            }

{% endhighlight %}

## ImageLoaded event

This event will be triggered after the image has been loaded. Using this event, you can add any shapes or text over an image, or crop an image while initially loading the image. 

{% highlight C# %}

        using Syncfusion.UI.Xaml.ImageEditor;

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

This event will be triggered whenever you tap the selected shapes (rectangle, circle, and arrow), text, or custom view. You can get the settings of each selected shape, text, or custom view using the `ItemSelected` argument. You can also change the settings that will affect the selected shapes.

{% highlight C# %}

        using Syncfusion.UI.Xaml.ImageEditor;
        using Windows.UI;
        using Windows.UI.Xaml.Media;

        public MainPage()
            {               
                            . . .

                imageEditor.ImageLoaded += Editor_ImageLoaded;
                imageEditor.ItemSelected += Editor_ItemSelected;

                            . . .
            }

        private void Editor_ImageLoaded(object sender, ImageLoadedEventArgs args)
            {
                imageEditor.AddShape(ShapeType.Circle, new PenSettings() { Mode = Mode.Stroke });
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

This event will be triggered whenever you change the shape selection from one shape to another shape (rectangle, circle, arrow, and text). You can get the settings of the previously selected shape, text, or custom view using the `ItemUnselected` event. You can also change the settings of the previously selected shapes.

{% highlight C# %}

    using Syncfusion.UI.Xaml.ImageEditor;
    using Windows.UI;
    using Windows.UI.Xaml.Media;

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

This event occurs whenever you start to edit an image. You can know whether the current image is edited using the `IsImageEdited` argument.

{% highlight C# %}

    using Syncfusion.UI.Xaml.ImageEditor;

    public MainPage()
    {               
        . . .
        imageEditor.ImageEdited += ImageEditor_ImageEdited;
        . . .
    }

    private void ImageEditor_ImageEdited(object sender, ImageEditedEventArgs e)
    {
        if (e.IsImageEdited)
        {
        }            
    }

{% endhighlight %}

## See also

[How to change the image saving location in the image editor control for uwp](https://www.syncfusion.com/kb/10077/how-to-change-the-image-saving-location-in-the-image-editor-control-for-uwp)

[How to retrieve an image from the saved location in uwp](https://www.syncfusion.com/kb/10060/how-to-retrieve-an-image-from-the-saved-location-in-uwp)

[How to save image to stream in uwp image editor](https://www.syncfusion.com/kb/9463/how-to-save-image-to-stream-in-uwp-imageeditor)

[How to change the image saving location in uwp](https://www.syncfusion.com/kb/8927/how-to-change-the-image-saving-location-in-uwp)
