---
layout: post
title: Diacritic sensitivity of AutoComplete in Syncfusion SfTextBoxExt control
description: Learn how to enable and disable Diacritic sensitivity in AutoComplete
platform: uwp
control: SfTextBoxExt
documentation: ug
---

# Diacritic Sensitivity

The control does not stick with one type of keyboard, so you can populate items from a language with letters containing diacritics, and search for them with English characters from an en-US keyboard. Users can enable or disable the diacritic sensitivity with the `IgnoreDiacritic` property. In the below code example we have illustrate how to enables the diacritic sensitivity so that items in the suggestion list get populated by entering any diacritic character of that alphabet.

{% tabs %}

{% highlight xaml %}

<Page
    x:Class="TextBoxExtSample.MainPage"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:local="using:TextBoxExtSample"
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
    mc:Ignorable="d"
    xmlns:editors="using:Syncfusion.UI.Xaml.Controls.Input"
    Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">

    <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

        <editors:SfTextBoxExt x:Name="textBoxExt" 
                              HorizontalAlignment="Center" 
                              VerticalAlignment="Center" 
                              AutoCompleteMode="Suggest"
                              SuggestionMode="Contains"
                              IgnoreDiacritic="False"
                              HighlightedTextColor="Red"
                              TextHighlightMode="MultipleOccurence"
                              Width="200">
        </editors:SfTextBoxExt>
    </Grid>
</Page>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.UI.Xaml.Controls.Input;
using System;
using System.Collections.Generic;
using Windows.UI;
using Windows.UI.Xaml;
using Windows.UI.Xaml.Controls;
using Windows.UI.Xaml.Media;

// The Blank Page item template is documented at https://go.microsoft.com/fwlink/?LinkId=402352&clcid=0x409

namespace TextBoxExtSample
{
    /// <summary>
    /// An empty page that can be used on its own or navigated to within a Frame.
    /// </summary>
    public sealed partial class MainPage : Page
    {
        public MainPage()
        {
            this.InitializeComponent();
            SfTextBoxExt textBoxExt = new SfTextBoxExt()
            {
                HorizontalAlignment = HorizontalAlignment.Center,
                VerticalAlignment = VerticalAlignment.Center,
                Width = 200,
                AutoCompleteMode = AutoCompleteMode.Suggest,
                SuggestionMode = SuggestionMode.Contains,
                TextHighlightMode = OccurenceMode.MultipleOccurence,
                HighlightedTextColor = new SolidColorBrush(Colors.Red),
                IgnoreDiacritic = false
            };

            List<string> list = new List<string>()
            {
                "Hów tó gâin wéight?",
                "Hów tó drâw ân éléphânt?",
                "Whéré cân I buy â câmérâ?",
                "Guidé mé âll thé wây",
                "Hów tó mâké â câké?",
                "Sây, Hélló Wórld!",
                "Hów tó mâké â róbót?",
                "Whât timé nów in Indiâ?"
            };

            textBoxExt.AutoCompleteSource = list;
            this.Content = textBoxExt;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![Diacritic-Sensitivity](images/Diacritic-Sensitivity/Diacritic.png)

