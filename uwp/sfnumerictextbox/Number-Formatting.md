---
layout: post
title: NumberFormatting of SfNumericTextBox control for UWP
description: NumberFormatting of SfNumericTextBox control for UWP
platform: uwp
control: SfNumeric TextBox
documentation: ug
---

# Number Formatting

Number formatting functionality allows formatting the text based on the FormatString of the control. The control will format the display text on lost focus. 

## Format String

The FormatString property determines the format specifier by which the display text has to be formatted.

Default Value of FormatString is N. 

The following code sample shows how to display numeric text with currency format.

{% tabs %}

{% highlight XAML %}

<Page xmlns:editors="using:Syncfusion.UI.Xaml.Controls.Input">



    <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

        <editors:SfNumericTextBox HorizontalAlignment="Center"

                               VerticalAlignment="Center"

                               Width="200" x:Name="numericTextBox"

FormatString="C"

                               Value="123.45"/>

    </Grid>

</Page>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

 numericTextBox.FormatString = "C";

{% endhighlight %}

{% highlight VB %}

 numericTextBox.FormatString = "C"

{% endhighlight %}

{% endtabs %}

![](Concepts_images/Concepts_img1.png)

N>  A detailed explanation of Numeric formatting is available [here](http://msdn.microsoft.com/en-us/library/dwhawy9k.aspx). 
The result string produced by these format specifiers are influenced by the settings in the Regional Options control panel. Computers with different cultures or different numeric settings will generate different result strings.
