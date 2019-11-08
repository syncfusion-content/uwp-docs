---
layout: post
title: Explains about Animation of Syncfusion SfGroupBar control 
description: Explains about Animation of Syncfusion SfGroupBar control 
platform: UWP
control: SfGroupBar
documentation: ug
---

# Animation

While the collapsed content popup is opening, transition effects can be applied using the property `PopupAnimation`. The values of Enumeration `ContentPopupAnimationTypes` are

* Fade
* Scale
* None

## Fading Transition

The content popup looks like fading in `ContentPopupAnimationTypes.Fade` mode

{% tabs %}

{% highlight XAML %}

<navigation:SfGroupBar PopupAnimation="Fade" VerticalAlignment="Stretch">

<navigation:SfGroupBar/>

{% endhighlight %}

{% endtabs %}

## Scaling Transition

The content popup looks like scaling along X-axis in `ContentPopupAnimationTypes.Scale` mode.

{% tabs %}

{% highlight XAML %}

<navigation:SfGroupBar PopupAnimation="Scale" VerticalAlignment="Stretch">

<navigation:SfGroupBar/>

{% endhighlight %}

{% endtabs %}

## No Transition

No transition effects are applied in this `ContentPopupAnimationTypes.None` mode.

{% tabs %}

{% highlight XAML %}

<navigation:SfGroupBar PopupAnimation="None" VerticalAlignment="Stretch">

<navigation:SfGroupBar/>

{% endhighlight %}

{% endtabs %}

## Changing Animation Speed

Animation speed can be adjusted using the property `AnimationSpeed`. It is necessary to choose an animation mode other than None.

{% tabs %}

{% highlight XAML %}

<navigation:SfGroupBar PopupAnimation="Fade" AnimationSpeed="500" VerticalAlignment="Stretch">

<navigation:SfGroupBar/>

{% endhighlight %}

{% endtabs %}

