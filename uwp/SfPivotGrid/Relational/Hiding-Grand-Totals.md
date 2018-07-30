---
layout: post
title: Hiding-Sub-Totals
description: hiding sub-totals
platform: uwp
control: SfPivotGrid
documentation: ug
---

# Hiding Grand totals

It can be achieved by setting the property 'ShowGrandTotals' to false. By default, SfPivotGrid displays the grand total for both rows and columns.

Please refer the below code sample.

{% highlight c# %}

    public partial class MainPage : Windows.UI.Xaml.Controls.Page
    {
        public MainPage()
        {
            this.InitializeComponent();
            this.pivotGrid.PivotEngine.ShowGrandTotals = false;
        }
    }

    {% endhighlight %}

    {% highlight vb %}

	Partial Public Class MainPage
		Inherits Windows.UI.Xaml.Controls.Page
		Public Sub New()
			Me.InitializeComponent()
			Me.pivotGrid.PivotEngine.ShowGrandTotals = False
		End Sub
	End Class

    {% endhighlight %}


![](Hiding-Sub-Totals_images/Hiding-Sub-Totals_image5.png)