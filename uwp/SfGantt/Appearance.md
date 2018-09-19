# Appearance
## Customization
This topic gives an overview on how to customize the TaskBar in the Gantt chart. 
### Visual Customization
The following properties are used for visual customization of the TaskBar. 
* ParentTaskBarBrush – To customize the parent taskbar brush.
* ParentProgressIndicatorBrush – To customize the parent progress brush.
* TaskBarBrush – To customize the taskbar brush. 
* TaskProgressIndicatorBrush – To customize the task progress brush.
* MilestoneBrush – To customize the milestone brush.
Following code snippet shows how to use these properties for the visual customization of the TaskBar.
<table>
<tr>
<td>
        <gantt:SfGantt x:Name="GanttControl" ItemsSource="{Binding TaskCollection}"
                       ParentTaskBarBrush="#33ffbe06" 
                       ParentProgressIndicatorBrush="#FFffbe06"
                       TaskBarBrush="#3390a84e" 
                       TaskProgressIndicatorBrush="#FF90a84e"
                       MilestoneBrush="#999999">
        &lt;/gantt:SfGantt&gt;
</td>
</tr>
</table>
### Template Customization
The following properties are used for customizing the template of the TaskBar. 
* ParentTaskBarTemplate – To customize the header task in the Gantt chart.
* TaskBarTemplate – To customize the child task in the Gantt chart.
* MilestoneTemplate – To customize the milestone task in the Gantt chart.
**Note:**The basic functionalities of the TaskBar like resizing, drag and drop and tooltip are available only when the template has the predefined name and the drag and drop/resizing thumbs. Otherwise the custom TaskBar will appear with the defined template, but you cannot access these features of Gantt.
**Xaml**
<table>
<tr>
<td>
&lt;Grid&gt;
  &lt;Grid.Resources&gt;
            &lt;local:TextConverter x:Key="TextConverter"&gt;&lt;/local:TextConverter&gt;
            &lt;local:ProgressColorConverter x:Key="ProgressFillConverter"&gt;&lt;/local:ProgressColorConverter&gt;
            &lt;local:ColorConverter x:Key="TaskFillConverter"&gt;&lt;/local:ColorConverter&gt;

            &lt;!--TaskBar Template--&gt;
            &lt;ControlTemplate x:Key="TaskBarTemplate"&gt;
                &lt;Grid x:Name="PART_TaskGrid"&gt;
                    &lt;Grid.ColumnDefinitions&gt;
                        &lt;ColumnDefinition Width="Auto"/&gt;
                        &lt;ColumnDefinition Width="Auto"/&gt;
                        &lt;ColumnDefinition Width="*"/&gt;
                        &lt;ColumnDefinition Width="Auto"/&gt;
                        &lt;ColumnDefinition Width="Auto"/&gt;
                    &lt;/Grid.ColumnDefinitions&gt;
                    &lt;Grid Grid.Column="2"&gt;
                        <Rectangle x:Name="PART_TaskBar" HorizontalAlignment="Left"
                                           Height="{Binding ActualTaskHeight}"   
                                           Width="{Binding TaskWidth}"
                                           Fill="{Binding Converter={StaticResource TaskFillConverter}}" 
                                           RadiusX="10" RadiusY="10" >&lt;/Rectangle&gt;
                        <Rectangle x:Name="PART_ProgressBar" Width="{Binding ProgressWidth}"
                                           HorizontalAlignment="Left" RadiusX="10" 
                                           RadiusY="10"
                                           Height="{Binding ActualTaskHeight}"
                                           Fill="{Binding Converter={StaticResource ProgressFillConverter}}"/>
                    &lt;/Grid&gt;
                &lt;/Grid&gt;
            &lt;/ControlTemplate&gt;
            &lt;!--Parent task template--&gt;
            &lt;ControlTemplate x:Key="ParentTaskBarTemplate"&gt;
                &lt;Grid&gt;
                    &lt;TextBlock Margin="-150,0,150,0"  FontWeight="Bold" Text="{Binding Converter={StaticResource TextConverter}}"&gt;&lt;/TextBlock&gt;
                    &lt;Grid &gt;
                        <Rectangle x:Name="PART_TaskBar" HorizontalAlignment="Left"
                                           Height="{Binding ActualTaskHeight}" 
                                           Width="{Binding TaskWidth}"
                                           Fill="{Binding Converter={StaticResource TaskFillConverter}}"
                                           RadiusX="10" RadiusY="10" >&lt;/Rectangle&gt;
                        <Rectangle x:Name="PART_ProgressBar" Width="{Binding ProgressWidth}"
                                           HorizontalAlignment="Left" RadiusX="10" 
                                           RadiusY="10"
                                           Height="{Binding ActualTaskHeight}"
                                           Fill="{Binding Converter={StaticResource ProgressFillConverter}}"/>
                    &lt;/Grid&gt;
                &lt;/Grid&gt;
            &lt;/ControlTemplate&gt;
            &lt;!--Milestone Template--&gt;
            &lt;ControlTemplate x:Key="MilestoneTemplate"&gt;
                &lt;Grid&gt;
                    &lt;Grid.ColumnDefinitions&gt;
                        &lt;ColumnDefinition Width="Auto"/&gt;
                        &lt;ColumnDefinition Width="*"/&gt;
                        &lt;ColumnDefinition Width="Auto"/&gt;
                    &lt;/Grid.ColumnDefinitions&gt;
                    &lt;Viewbox Grid.Column="1"&gt;
                        <Path x:Name="PART_TaskBar" HorizontalAlignment="Left"
                                      Data="M1540.22,2082.07L1546.95,2102.78 1568.73,2102.78 1551.11,2115.58 1557.84,2136.29 1540.22,2123.49 1522.6,2136.29 1529.33,2115.58 1511.71,2102.78 1533.49,2102.78 1540.22,2082.07z"
                                      Stretch="Uniform" Width="{Binding TaskWidth}" Height="{Binding ActualTaskHeight}"
                                      Fill="#4773b5">
                        &lt;/Path&gt;
                    &lt;/Viewbox&gt;
                &lt;/Grid&gt;
            &lt;/ControlTemplate&gt;
        &lt;/Grid.Resources&gt;
        <gantt:SfGantt x:Name="GanttControl" ItemsSource="{Binding TaskCollection}"
                       DisplayTaskNames="False" 
                       MilestoneTemplate="{StaticResource MilestoneTemplate}"
                       ParentTaskBarTemplate="{StaticResource ParentTaskBarTemplate}" 
                       TaskBarTemplate="{StaticResource TaskBarTemplate}">
        &lt;/gantt:SfGantt&gt;
&lt;/Grid&gt;
</td>
</tr>
</table>
![](Appearance_images/Appearance_img1.jpeg)

Please find the demo sample from the following link [Template Demo](http://www.syncfusion.com/downloads/support/directtrac/general/ze/TemplateSupport1085883211.zip# ""). 
