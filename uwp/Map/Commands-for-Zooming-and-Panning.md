---
layout: post
title: Commands for Zooming and Panning in UWP Map control | Syncfusion
description: Learn here all about Commands for Zooming and Panning support in Syncfusion UWP Map (SfMaps) control and more.
platform: UWP
control: Maps
documentation: ug
---

# Commands for Zooming and Panning in UWP Map (SfMaps)

The Map control contains the following commands:

* ZoomIn Command
* ZoomOut Command
* Pan Command
* ZoomReset Command
* PanReset Command



## ZoomIn Command

`ZoomIn` command zooms in the map.

{% highlight xml %}

        <maps:SfMap  x:Name="Map" >
             <maps:SfMap.Layers>	
                <maps:ShapeFileLayer  x:Name="shapeControl" Uri="CommandsDemo.ShapeFiles.wv.shp">
                </maps:ShapeFileLayer>
              </maps:SfMap.Layers>
        </maps:SfMap >
        
         <Button Content="ZoomIn" Name="zoomIn" Grid.Row="0" Command="{Binding ElementName=Map,Path=ZoomInCommand}" VerticalAlignment="Bottom"/>

{% endhighlight  %}

## ZoomOut Command

`ZoomOut` command zooms out the map.

{% highlight xml %}

       <maps:SfMap  x:Name="Map" >
             <maps:SfMap.Layers>	
                <maps:ShapeFileLayer  x:Name="shapeControl" Uri="CommandsDemo.ShapeFiles.wv.shp">
                </maps:ShapeFileLayer>
              </maps:SfMap.Layers>
        </maps:SfMap >
        
        <Button Content="ZoomOut" Name="zoomOut" Grid.Row="2"  Command="{Binding ElementName=Map,Path=ZoomOutCommand}"/>

{% endhighlight %}

## Pan Command

`Pan` Command is used to navigate on the Map control. The direction of the navigation is the Command parameter for the Pan Command.

{% highlight xml %}


        <maps:SfMap  x:Name="Map" >
             <maps:SfMap.Layers>	
                <maps:ShapeFileLayer  x:Name="shapeControl" Uri="CommandsDemo.ShapeFiles.wv.shp">
                </maps:ShapeFileLayer>
              </maps:SfMap.Layers>
        </maps:SfMap >

        <Button Width="50" Height="20" Grid.Row="1" Grid.Column="0" Content="Left" Name="LeftPanButton" Command="{Binding ElementName=Map,Path=PanCommand}" CommandParameter="left" />
        <Button Width="50" Height="20" Grid.Row="1" Grid.Column="2" Content="Right"  Name="RightPanButton"  Command="{Binding ElementName=Map,Path=PanCommand}" CommandParameter="right"/>
        <Button Width="50" Height="20"  Grid.Row="0" Grid.Column="1" Content="Top" Name="topPan" Command="{Binding ElementName=Map,Path=PanCommand}" CommandParameter="top"/>
        <Button Width="75" Height="20" Grid.Row="2" Grid.Column="1" Content="Bottom" Name="bottomPan" Command="{Binding ElementName=Map,Path=PanCommand}" CommandParameter="bottom"/> 

{% endhighlight  %}

## ZoomReset Command

The `ZoomReset` command resets the ZoomLevel value of the Map control.

{% highlight xml %}

        <maps:SfMap  x:Name="Map" >
             <maps:SfMap.Layers>	
                <maps:ShapeFileLayer  x:Name="shapeControl" Uri="CommandsDemo.ShapeFiles.wv.shp">
                </maps:ShapeFileLayer>
              </maps:SfMap.Layers>
        </maps:SfMap >

       <Button Grid.Column="0" Grid.Row="0"  Content="ZoomRest" Command="{Binding ElementName=Map,Path=ZoomResetCommand}"/>

{% endhighlight  %}

## PanReset Command

The `PanReset` command resets the map at its initial position; it resets the pan values.

{% highlight xml %}

    <maps:SfMap  x:Name="Map" >
             <maps:SfMap.Layers>	
                <maps:ShapeFileLayer  x:Name="shapeControl" Uri="CommandsDemo.ShapeFiles.wv.shp">
                </maps:ShapeFileLayer>
              </maps:SfMap.Layers>
        </maps:SfMap >

    <Button Grid.Column="2" Grid.Row="0" Content="PanRest" Command="{Binding ElementName=Map,Path=PanResetCommand}"/>

{% endhighlight  %}
