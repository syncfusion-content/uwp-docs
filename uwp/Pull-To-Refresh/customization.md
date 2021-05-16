---
layout: post
title: Customization in UWP Pull To Refresh control | Syncfusion
description: Learn here all about Customization support in Syncfusion UWP Pull To Refresh (SfPullToRefresh) control and more.
platform: UWP
control: PullToRefresh
documentation: ug
--- 

# Customization in UWP Pull To Refresh (SfPullToRefresh)

## PullingThreshold

Gets or sets the threshold value from the edges for easy panning from the edges. The default value of TouchThreshold is 3 times the RefreshContentHeight.

{% tabs %}

{%highlight Xaml %}

    <syncfusion:SfPullToRefresh x:Name="pullToRefresh" PullingThreshold="225"/>

{%endhighlight%} 

{% highlight c# %}

    pullToRefresh.PullingThreshold = 225d;

{% endhighlight %}

{% endtabs %} 

## PullableContent

PullableContent is the main view of the PullToRefresh control on which the desired items can be placed.

{%highlight Xaml%}
    
    <syncfusion:SfPullToRefresh Refreshing="SfPullToRefresh_Refreshing" PullingThreshold="200" x:Name="pullToRefresh"  Transition="SlideOnTop" Position="Top">
           
            <syncfusion:SfPullToRefresh.PullableContent>
                <StackPanel Orientation="Vertical" HorizontalAlignment="Center" VerticalAlignment="Center">
                    <TextBlock  FontSize="25" Foreground="White"   Text = "Temperature"/>

                    <TextBlock FontSize="25"  Foreground="White" HorizontalAlignment="Center" Text ="{Binding Temp}" />
                </StackPanel>
            </syncfusion:SfPullToRefresh.PullableContent>

    </syncfusion:SfPullToRefresh>
{%endhighlight%}

## RefreshContentHeight

`RefreshContentHeight` sets the height of the refresh content.

{% tabs %}

{%highlight Xaml%}

    <syncfusion:SfPullToRefresh x:Name="pulltorefresh" RefreshContentHeight="200"/>

{%endhighlight%}

{% highlight c# %}

    pullToRefresh.RefreshContentHeight = 200d;

{% endhighlight %}

{% endtabs %}

## Refresh ()

Refresh method is used to Refresh the `PullableContent` and also hides the `RefreshContent`.

{% highlight c# %}

    pullToRefresh.Refresh();

{% endhighlight %}

## Transition

The Transition property specifies the animations for the RefreshContent. Transition property has the following two options:

* `SlideOnTop`
* `Push`

The default transition is `SlideOnTop`. That draws the `RefreshContent` on top of the `PullableContent`.

{% tabs %}

{%highlight Xaml%}

    <syncfusion:SfPullToRefresh x:Name="pullToRefresh" Transition="SlideOnTop" />

{%endhighlight%}

{% highlight c# %}

    pullToRefresh.Transition = Transition.SlideOnTop;

{% endhighlight %}

{% endtabs %}

![Overview_img3](Overview_images/Overview_img3.png)


The following code example shows how to set `Transition` as `Push` to SfPullToRefresh. This transition moves the refresh content and main content simultaneously.

{% tabs %}

{%highlight Xaml%}

    <syncfusion:SfPullToRefresh x:Name=" pullToRefresh" Transition="Push" />

{%endhighlight%}

{% highlight c# %}

    pullToRefresh.Transition = Transition.Push;

{% endhighlight %}

{% endtabs %}


![Overview_img4](Overview_images/Overview_img4.png)

## PullDirection

PullDirection property specifies the position of the transition to take place.PullDirection property has the following two options:
* `Top`
* `Bottom`

The default PullDirection is `Top`. That draws the `RefreshContent` on top of the `pullableContent`.

{% tabs %}

{% highlight C# %}

    pullToRefresh.PullDirection=PullDirection.Top;


{% endhighlight %}

{%highlight Xaml%}

    <syncfusion:SfPullToRefresh x:Name=" pullToRefresh" PullDirection="Top" />

{%endhighlight%}


{% endtabs %}


The following code example shows how to set `PullDirection` as `Bottom` to SfPullToRefresh.That draws the `RefreshContent` on Bottom of the `pullableContent`.

{% tabs %}

{% highlight C# %}

    pullToRefresh.PullDirection=PullDirection.Bottom;

{% endhighlight %}

{%highlight Xaml%}

    <syncfusion:SfPullToRefresh x:Name=" pullToRefresh" PullDirection="Bottom" />

{%endhighlight%}

{% endtabs %}


