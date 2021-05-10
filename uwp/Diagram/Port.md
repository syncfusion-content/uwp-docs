---
layout: post
title: Port in UWP Diagram control | Syncfusion
description: Learn here all about Port support in Syncfusion UWP Diagram (SfDiagram) control and more.
platform: uwp
control: SfDiagram
documentation: ug
---

# Port in UWP Diagram (SfDiagram)

Essential Diagram for UWP provides support to define custom ports for making connections.

![Node Port](Port_images/Port_img1.jpeg)![Connector Port](Port_images/Port_img2.jpeg)

When a Connector is connected between two Nodes, its end points are automatically docked to Node’s nearest boundary as shown in the following image.

![Connect to node wihout port](Port_images/Port_img3.jpeg)

Port act as the connection points of node and allows to create connections with only specific points as shown in the following image.

![Connect to node with port](Port_images/Port_img4.jpeg)![Connector port](Port_images/Port_img5.jpeg)

## Node Port

### Add ports to Node

To add a collection port, you need to define the port object and add it to Ports property of Node. The `NodeOffsetX` and `NodeOffsetY` property of Port accepts an object of fractions and used to determine the position of Ports. The following code illustrates how to add ports when initializing the Node.

The following code illustrates how to add ports to Node.

[XAML]

{% highlight xaml %}

<!--Style for Node-->
<Style TargetType="syncfusion:Node">
	<Setter Property="ShapeStyle">
    	<Setter.Value>
        	<Style TargetType="Path">
            	<Setter Property="Fill" Value="DarkCyan"></Setter>
				<Setter Property="Stroke" Value="Black"></Setter>
       	        <Setter Property="StrokeThickness" Value="2"></Setter>
				<Setter Property="Stretch" Value="Fill"></Setter>
            </Style>
		</Setter.Value>
	</Setter>
    <Setter Property="Shape">
    	<Setter.Value>
        	<RectangleGeometry Rect="0,0,10,10"/>
        </Setter.Value>
    </Setter>
</Style>

<!--Style for NodePort-->
<Style TargetType="syncfusion:NodePort">
	<Setter Property="ShapeStyle">
    	<Setter.Value>
        	<Style TargetType="Path">
            	<Setter Property="Fill" Value="Black"></Setter>
                <Setter Property="Stretch" Value="Fill"></Setter>
            </Style>
		</Setter.Value>
	</Setter>
    <Setter Property="Shape">
    	<Setter.Value>
    		<RectangleGeometry Rect="0,0,10,10"/>
         </Setter.Value>
	</Setter>
</Style>

{% endhighlight %}

[C#]

{% highlight C# %}

//Create port collection
public class PortCollection : ObservableCollection<IPort>
{

}

{% endhighlight %}

[XAML]

{% highlight xaml %}

<!--Initializes the SfDiagram-->
<syncfusion:SfDiagram x:Name="diagram" PortVisibility="Visible">
	<!--Initializes the NodeCollection-->
	<syncfusion:SfDiagram.Nodes>
		<syncfusion:NodeCollection>
		        <!--Initializes the Node-->
              	<syncfusion:NodeViewModel x:Name="node" OffsetX="100" 
				                          OffsetY="100" UnitHeight="100"
										  UnitWidth="100">   
				<!--Initializes the PortCollection-->						                                   
				<syncfusion:NodeViewModel.Ports>
					<local:PortCollection>
					    <!--Initializes the NodePort-->
						<syncfusion:NodePortViewModel x:Name="port" UnitWidth="10"
                                                      UnitHeight="10" NodeOffsetX="0.5"
                                                      NodeOffsetY="0.5">
						</syncfusion:NodePortViewModel>
					</local:PortCollection>
                     	</syncfusion:NodeViewModel.Ports>
              	</syncfusion:NodeViewModel>
       	</syncfusion:NodeCollection>
	</syncfusion:SfDiagram.Nodes>
</syncfusion:SfDiagram>

{% endhighlight %}

![Add port](Port_images/Port_img6.jpeg)

## Connection to Boundary with Port

By default, Port will make connection to specific Point on Node. Now, We have provided `Dynamic` constraint for `NodePort` to establish the connection at a relative point on Node’s boundary and direction of the Connector is dependent with that Port.

We can enable the `Dynamic` constraint in PortConstraints to achieve this behavior.

Following code illustrates how to enable the `Dynamic` constraint to the NodePort.

{% highlight xaml %}

//Enable the Dynamic constraints to the Port
port.Constraints |= PortConstraints.Dynamic;

{% endhighlight %}

To know more about bitwise operators, refer to [Bitwise Operations](/uwp/sfdiagram/constraints#bitwise-operations).

![Dynamic port](Port_images/Port_img9.jpeg)

## Connector Port

### Add Port to Connector
To add a collection port, you need to define the port object and add it to `Ports` property of Connector. The `Length` property of Port accepts an object of fractions and used to determine the position of Ports. The following code illustrates how to add ports to the Connector.

The following code illustrates how to add ports to Connector.

[XAML]

{% highlight xaml %}

<!--Style for Connector-->
<Style TargetType="syncfusion:Connector">
	<Setter Property="TargetDecoratorStyle">
    	<Setter.Value>
        	<Style TargetType="Path">
            	<Setter Property="Fill" Value="Black" />
                <Setter Property="Stretch" Value="Fill" />
            </Style>
		</Setter.Value>
	</Setter>
</Style>

<!--Style for ConnectorPort-->
<Style TargetType="syncfusion:ConnectorPort">
	<Setter Property="ShapeStyle">
    	<Setter.Value>
        	<Style TargetType="Path">
            	<Setter Property="Fill" Value="Black"></Setter>
                <Setter Property="Stretch" Value="Fill"></Setter>
            </Style>
       	</Setter.Value>
   	</Setter>
   	<Setter Property="Shape">
    	<Setter.Value>
        	<RectangleGeometry Rect="0,0,10,10"/>
        </Setter.Value>
   	</Setter>
</Style>

{% endhighlight %}

[C#]

{% highlight C# %}

//Create port collection
public class PortCollection : ObservableCollection<IPort>
{

}

{% endhighlight %}

[XAML]

{% highlight xaml %}

<!--Initializes the SfDiagram-->
<syncfusion:SfDiagram x:Name="diagram" PortVisibility="Visible" DefaultConnectorType="Line">
	<!--Initializes the ConnectorCollection-->
	<syncfusion:SfDiagram.Connectors>
    	<syncfusion:ConnectorCollection>
		    <!--Initializes the Connector-->
        	<syncfusion:ConnectorViewModel x:Name="connector" SourcePoint="100,100" TargetPoint="300,300">
			    <!--Initializes the PortCollection-->
				<syncfusion:ConnectorViewModel.Ports>
                	<local:PortCollection>
					    <!--Initializes the ConnectorPort-->
                    	<syncfusion:ConnectorPortViewModel x:Name="port" UnitWidth="7"
                                                           UnitHeight="7" 
                                                           Length="0.5">
						</syncfusion:ConnectorPortViewModel>
                	</local:PortCollection>
				</syncfusion:ConnectorViewModel.Ports>
			</syncfusion:ConnectorViewModel>
       	</syncfusion:ConnectorCollection>
	</syncfusion:SfDiagram.Connectors>
</syncfusion:SfDiagram>

{% endhighlight %}

![Connector port](Port_images/Port_img7.jpeg)

## Connect with ports

Connector’s `SourcePort` and `TargetPort` properties allow to create connections between some specific points of Source/Target Nodes. For more information about creating connections with port, refer to [Connections with Ports](/uwp/sfdiagram/connector#connections-with-ports "Connections with Ports").

##Appearance

You can change the shape of port by using its shape property. The appearance of ports can be customized with a set of style specific properties.

The following code illustrates how to change the appearance of port.

[XAML]

{% highlight xaml %}

<!--Style for NodePort-->
<Style TargetType="syncfusion:NodePort">
	<Setter Property="ShapeStyle">
    	<Setter.Value>
        	<Style TargetType="Path">
            	<Setter Property="Fill" Value="Yellow"></Setter>
                <Setter Property="Stretch" Value="Fill"></Setter>
            </Style>
        </Setter.Value>
	</Setter>
    <Setter Property="Shape">
    	<Setter.Value>
        	<EllipseGeometry RadiusX="10" RadiusY="10"/>
        </Setter.Value>
	</Setter>
</Style>

{% endhighlight %}

[XAML]

{% highlight xaml %}

<!--Initializes the SfDiagram-->
<syncfusion:SfDiagram x:Name="diagram" PortVisibility="Visible">
	<!--Initializes the NodeCollection-->
	<syncfusion:SfDiagram.Nodes>
		<syncfusion:NodeCollection>
		    <!--Initializes the Node-->
        	<syncfusion:NodeViewModel x:Name="node" OffsetX="100" OffsetY="100" 	
				  		              UnitHeight="100" UnitWidth="100">   
				<!--Initializes the PortCollection-->						                                 
				<syncfusion:NodeViewModel.Ports>
					<local:PortCollection>
					    <!--Initializes the NodePort-->
						<syncfusion:NodePortViewModel x:Name="port" UnitWidth="7"
                                                      UnitHeight="7"
                                                      NodeOffsetX="1"
                                                      NodeOffsetY="0.5">
						</syncfusion:NodePortViewModel>
					</local:PortCollection>
        		</syncfusion:NodeViewModel.Ports>
        	</syncfusion:NodeViewModel>
       	</syncfusion:NodeCollection>
	</syncfusion:SfDiagram.Nodes>
</syncfusion:SfDiagram>

{% endhighlight %}

![Node port](Port_images/Port_img8.jpeg)

## Constraints

The Constraints property allows to enable/disable certain behaviors of ports. For more information about port constraints, refer to [Port Constraints](/uwp/sfdiagram/constraints#port-constraints "Port Constraints").
