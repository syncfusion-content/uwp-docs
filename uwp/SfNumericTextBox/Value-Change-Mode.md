---
layout: post
title:  Value Change Mode on SfNumericTextBox control for UWP
description: Value Change Mode on SfNumericTextBox control for UWP
platform: uwp
control: SfNumeric TextBox
documentation: ug
---

# Value Change Mode

The ValueChangeMode property is used to update the Value property when a key is pressed or focus is lost. When the ValueChangeMode is OnKeyFocus, the value will be changed for each key press. When ValueChangeMode is OnLostFocus, the value will be changed only when the control is no longer focused on the text box. ValueChangeMode includes the following options:

1. OnKeyFocus
2. OnLostFocus



The following code samples show how to use the ValueChangeMode property.



{% highlight XAML %}

<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

            <syncfusion:SfNumericTextBox

                 HorizontalAlignment="Center"

                  VerticalAlignment="Center"

                                    Width="200"

ValueChangeMode="OnKeyFocus"/>

</Grid>

{% endhighlight %}








{% highlight XAML %}

<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

            <syncfusion:SfNumericTextBox

                 HorizontalAlignment="Center"

                  VerticalAlignment="Center"

                                    Width="200"

ValueChangeMode="OnLostFocus"/>

</Grid>

{% endhighlight %}

