---
layout: post
title: Number Formatting in UWP SfNumericTextBox | Syncfusion®
description: The Number Formatting feature in SfNumericTextBox formats the display text on lost focus using the FormatString property for currency and other formats.
platform: uwp
control: SfNumericTextBox
documentation: ug
---

# Number Formatting in UWP SfNumericTextBox

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

![FormatString view](Concepts_images/Concepts_img1.png)

N>  A detailed explanation of Numeric formatting is available [here](https://learn.microsoft.com/en-us/dotnet/standard/base-types/standard-numeric-format-strings). 
The result string produced by these format specifiers are influenced by the settings in the Regional Options control panel. Computers with different cultures or different numeric settings will generate different result strings.

## Group separator modes

[`GroupSeparatorMode`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.Input.SfNumericTextBox.html#Syncfusion_UI_Xaml_Controls_Input_SfNumericTextBox_GroupSeparatorMode) provides 2 states to display the group separator. 
When the mode is set as `Always`, it will display separator while typing itself on the other hand when the mode is set as `LostFocus` it will enable the separator when the control lost its focus.

N> [`EnableGroupSeparator`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.Input.SfNumericTextBox.html#Syncfusion_UI_Xaml_Controls_Input_SfNumericTextBox_EnableGroupSeparator) property must be enabled to use the [`GroupSeparatorMode`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.Input.SfNumericTextBox.html#Syncfusion_UI_Xaml_Controls_Input_SfNumericTextBox_GroupSeparatorMode).

{% tabs %}

{% highlight xaml %}
 
  <numeric:SfNumericTextBox Value="123456" FormatString="n" GroupSeparatorMode="Always"
                                  EnableGroupSeparator="True">
            
        </numeric:SfNumericTextBox>

{% endhighlight %}

{% highlight c# %}

     SfNumericTextBox numericTextBox = new SfNumericTextBox();
            numericTextBox.Value = 123456;
            numericTextBox.FormatString = "n";
            numericTextBox.GroupSeparatorMode = GroupSeparatorMode.Always;
            numericTextBox.EnableGroupSeparator = true;
            this.Content = numericTextBox;

{% endhighlight %}

{% endtabs %}

![Display the value with enable group separator](Concepts_images/GroupSeparatorMode.png)

