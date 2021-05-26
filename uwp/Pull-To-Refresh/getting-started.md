---
layout: post
title: Getting Started with UWP Pull To Refresh control | Syncfusion
description: Learn here about getting started with Syncfusion UWP Pull To Refresh (SfPullToRefresh) control, its elements and more.
platform: UWP
control: PullToRefresh
documentation: ug
--- 

# Getting Started with UWP Pull To Refresh (SfPullToRefresh)

## Create your first SfPullToRefresh in Universal Windows Platform

This section encompasses on how to create a PullToRefresh that lets you to refresh the current content of the application. 

`SfPullToRefresh` is available in the following assembly and namespace:

Assembly: `Syncfusion.SfPullToRefresh.UWP`

Namespace: `Syncfusion.UI.Xaml.PullToRefresh`

Refer to the following code to add the SfPullToRefresh control:

{% tabs %}

{%highlight Xaml%}

    <Page
    x:Class="PullToRefresh.MainPage"
    xmlns:syncfusion="using:Syncfusion.UI.Xaml.PullToRefresh">

    <Grid x:Name="LayoutRoot">
        <syncfusion:SfPullToRefresh />
    </Grid> 
    
    </Page>

{%endhighlight%}

{% highlight c# %}

    SfPullToRefresh pullToRefresh = new SfPullToRefresh();

{% endhighlight %}

{% endtabs %}

## Customizing a simple SfPullToRefresh sample

To develop an application with UWP PullToRefresh is simple. The following steps explains how to create and configure its properties.

* Create the `PullableContent` for the `SfPullToRefresh`

You can set the `PullableContent` for the `SfPullToRefresh` by adding the desired UIElement.

{%highlight Xaml%}

    <syncfusion:SfPullToRefresh x:Name="pullToRefresh" PullingThreshold="150" >
        <syncfusion:SfPullToRefresh.PullableContent>
            <Grid Background="#039be5" Name="controlView" >
            </Grid>
        </syncfusion:SfPullToRefresh.PullableContent>
    </syncfusion:SfPullToRefresh>
    
{%endhighlight%}
 
 ## Events

The pulling event will be notified whenever the swipe gesture is started. This event will notify the listener each and every time until the refresh content height exceeds. When we release the gesture from pullable content, Refreshing event will be triggered. Now user can proceed to fetching the data from web or database. Once the data is fetched, we should call Refresh to method to complete all animations.

There are three built-in events in the PullToRefresh control namely:

1. `Pulling`
2. `Refreshing`
3. `Refreshed`

## Pulling

`Pulling` event is triggered when we start pulling down the PullableContent. It is triggered as long as the pointer or finger is pressed and the progress is less than 100 and not equal to 0 . The arguments for the event are:

* SfPullToRefresh
* Progress

{% tabs %}

{%highlight Xaml%}

    <syncfusion:SfPullToRefresh x:Name="pullToRefresh" Pulling="pullToRefresh_Pulling" />

{%endhighlight%}

{% highlight c# %}

    private void pullToRefresh_Pulling(object sender, PullingEventArgs args)
    {
        (sender as SfPullToRefresh).RefreshText = args.PulledDistance.ToString();
    }
{% endhighlight %}

{% endtabs %}

## Refreshing

`Refreshing` event is triggered once the content is pulled through the PullingThreshold or Progress reaches 100. This event is triggered till the Refresh() method is called.

{% tabs %}

{%highlight Xaml%}

    <syncfusion:SfPullToRefresh x:Name="pullToRefresh" Refreshing="pullToRefresh_Refreshing" />

{%endhighlight%}

{% highlight c# %}
    
    DispatcherTimer timer = new DispatcherTimer { Interval = TimeSpan.FromSeconds(7) };

    private void pullToRefresh_Refreshing(object sender)
    {
        timer.Start();
        timer.Tick += Timer_Tick;
    }
    
    private void Timer_Tick(object sender, object e)
    {
        timer.Stop();
        pullToRefresh.Refresh();          
    }
    
{% endhighlight %}

{% endtabs %}

## Refreshed

`Refreshed` event is triggered once the refreshing and all the animations associated with the control are completed.

{% tabs %}

{%highlight Xaml%}

    <syncfusion:SfPullToRefresh x:Name=" pullToRefresh" Refreshed="pullToRefresh_Refreshed" />

{%endhighlight%}

{% highlight c# %}

    private async void pullToRefresh_Refreshed(object sender)
    {
        var dialog = new MessageDialog("Content has been refreshed");
        await dialog.ShowAsync();
    }

{% endhighlight %}

{% endtabs %}
        
