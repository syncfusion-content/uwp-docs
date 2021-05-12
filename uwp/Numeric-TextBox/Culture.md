---
layout: post
title: Culture in UWP Numeric TextBox control | Syncfusion
description: Learn here all about Culture support in Syncfusion UWP Numeric TextBox (SfNumericTextBox) control and more.
platform: uwp
control: SfNumeric TextBox
documentation: ug
---

# Culture in UWP Numeric TextBox (SfNumericTextBox)

The Culture property helps to localize the SfNumericTextBox. Text will be formatted based on the specified Culture. 

The following code sample shows how to localize the control to German culture.

{% tabs %}

{% highlight c# %}

SfNumericTextBox numericTextBox = new SfNumericTextBox();

numericTextBox.Value = 12345;

numericTextBox.Culture = new CultureInfo("de-DE");

{% endhighlight %}

{% highlight VB %}

Dim numericTextBox As New SfNumericTextBox()

numericTextBox.Value = 12345

numericTextBox.Culture = New CultureInfo("de-DE")

{% endhighlight %}

{% endtabs %}

![Germany Culture view](Concepts_images/Concepts_img3.png)

N> Note that the decimal separator and group separator are affected by the culture in this case.

N>  Since CultureInfo type does not contain a default constructor, it is not possible to set this property from XAML.

## Culture with formatting

SfNumericTextBox respects both Culture and FormatString while formatting Text. In the below Code sample, German Culture and Currency format specifier have been set for Culture and FormatString properties respectively.
{% tabs %}
{% highlight XAML %}

<Page xmlns:editors="using:Syncfusion.UI.Xaml.Controls.Input">



    <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">



        <editors:SfNumericTextBox x:Name="numericTextBox"

                               HorizontalAlignment="Center"

                               VerticalAlignment="Center"

                               Width="200" 

FormatString="C"

                               Value="123.45"/>

    </Grid>

</Page>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

numericTextBox.Culture = new System.Globalization.CultureInfo("de-DE");

{% endhighlight %}

{% highlight VB %}

numericTextBox.Culture = New System.Globalization.CultureInfo("de-DE")

{% endhighlight %}

{% endtabs %}

![Germany Culture Currency view](Concepts_images/Concepts_img5.png)

