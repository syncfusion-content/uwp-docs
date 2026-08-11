---
layout: post
title: How to add labels for track ball in UWP Sparkline | Syncfusion®
description: Add labels for the track ball in the UWP Sparkline to display data values and customize label appearance during data interaction.
platform: uwp
control: SfSparkline
documentation: ug
---

# How to add labels for track ball in UWP Sparkline

We can add labels for the track ball to show the corresponding values. In order to add labels for the trackball, you need to subscribe to the OnSparklineMouseMove event and you can get the following data from the event argument.

{% highlight c# %}

private void SfLineSparkline_OnSparklineMouseMove(object src, Syncfusion.UI.Xaml.Charts.SparklineMouseMoveEventArgs args)
{
    if (!args.RootPanel.Children.Contains(info))
    {
        info = new ContentPresenter();
        args.RootPanel.Children.Add(info);
    }

    info.Content = args.Value.Y;
    info.Arrange(new Rect(args.Coordinate.X, args.Coordinate.Y, info.ActualWidth, info.ActualHeight));
}

{% endhighlight %}

{% highlight xaml %}

<Syncfusion:SfLineSparkline Interior="#4a4a4a"

BorderBrush="DarkGray" BorderThickness="1"

OnSparklineMouseMove="SfLineSparkline_OnSparklineMouseMove"

ItemsSource="{Binding UsersList}" ShowTrackBall="True"

YBindingPath="NoOfUsers"/>

{% endhighlight %}

![Add Label For Trackball](Add-labels-for-track-ball_images/AddLabelsForTrackball_img1.jpeg)
