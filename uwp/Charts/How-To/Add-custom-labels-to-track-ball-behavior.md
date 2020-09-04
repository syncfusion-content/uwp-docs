---
layout: post
title: Add custom labels to track ball behavior | SfChart | Winrt | Syncfusion
description: add custom labels to track ball behavior
platform: wpf
control: SfChart
documentation: ug
---

# Add custom labels to track ball behavior

In the [`ChartTrackBallBehavior`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html), each data point will have a label aligned vertically and horizontally using the [`LabelVerticalAlignment`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTrackBallBehavior_LabelVerticalAlignment) and [`LabelHorizontalAlignment`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTrackBallBehavior_LabelHorizontalAlignment) properties by default. However, you can also add custom labels to the [`ChartTrackBallBehavior`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html).

In order to add a custom label, you need to write a class derived from [`ChartTrackBallBehavior`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html). You need to override [`GenerateLabels`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartTrackBallBehavior.html#Syncfusion_UI_Xaml_Charts_ChartTrackBallBehavior_AddLabel_System_Object_Syncfusion_UI_Xaml_Charts_ChartAlignment_Syncfusion_UI_Xaml_Charts_ChartAlignment_Windows_UI_Xaml_DataTemplate_System_Double_System_Double_) method, which will be called whenever new labels are going to be generated, and add the labels using AddLabel method. The following code sample demonstrates this:


{% highlight c# %}


public class CustomTrackBallBehavior: ChartTrackBallBehavior

    {

        public DataTemplate CustomLabelTemplate

        {

            get { return (DataTemplate)GetValue(CustomLabelTemplateProperty); }

            set { SetValue(CustomLabelTemplateProperty, value); }

        }



        // Using a DependencyProperty as the backing store for CustomLabelTemplate.  This enables animation, styling, binding, etc.

        public static readonly DependencyProperty CustomLabelTemplateProperty =

            DependencyProperty.Register("CustomLabelTemplate", typeof(DataTemplate), typeof(CustomTrackBallBehavior), new PropertyMetadata(null));



        protected override void GenerateLabels()

        {

            AddLabel(PointInfos[0], LabelVerticalAlignment, LabelHorizontalAlignment, PointInfos[0].Series.TrackBallLabelTemplate);

            AddLabel(PointInfos[1], LabelVerticalAlignment, LabelHorizontalAlignment, PointInfos[1].Series.TrackBallLabelTemplate);



            ChartPointInfo pointInfo1 = PointInfos[2];

            ChartPointInfo pointInfo2 = PointInfos[3];



            CustomLabel label = new CustomLabel();

            label.Value1 = pointInfo2.ValueY;

            label.Value2 = pointInfo1.ValueY;



            Rect rect = pointInfo1.Series.YAxis.ArrangeRect;



            //Custom label.

            AddLabel(label, LabelVerticalAlignment, LabelHorizontalAlignment, CustomLabelTemplate, pointInfo1.X, rect.Bottom);

        }

    }



    public class CustomLabel

    {

        public string Value1 { get; set; }

        public string Value2 { get; set; } }

{% endhighlight %}

