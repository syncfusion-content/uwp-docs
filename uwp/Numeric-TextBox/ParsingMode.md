---
layout: post
title: ParsingMode in UWP SfNumericTextBox | Syncfusion®
description: The ParsingMode in SfNumericTextBox specifies how the value is parsed using the ParsingMode property with Double and Decimal enum values, defaulting to Double.
platform: uwp
control: SfNumericTextBox
documentation: ug
---

# ParsingMode in UWP Numeric TextBox

Value of the UWP Numeric TextBox gets parsed based on ParsingMode property. ParsingMode is of type Parsers which is enum of Double and Decimal. DefaultValue for ParsingMode is Double.



{% tabs %}
{% highlight XAML %}

<Page xmlns:editors="using:Syncfusion.UI.Xaml.Controls.Input">



    <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">



        <editors:SfNumericTextBox x:Name="numericTextBox"

                               HorizontalAlignment="Center"

                               VerticalAlignment="Center"

                               Width="250" 

                               ParsingMode="Decimal"

                               Value="123.459999999999999999"/>

    </Grid>

</Page>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

 numericTextBox.ParsingMode = Syncfusion.UI.Xaml.Controls.Input.Parsers.Decimal;

{% endhighlight %}

{% highlight VB %}

 numericTextBox.ParsingMode = Syncfusion.UI.Xaml.Controls.Input.Parsers.Decimal

{% endhighlight %}

{% endtabs %}

N>The `ParsingMode` should be set based on the data type. For example, if a `Decimal` type property is bound to Value property of UWP Numeric TextBox, then the `ParsingMode` should be set as `Decimal`.

![Parsingmode view](Concepts_images/Concepts_img7.png)
