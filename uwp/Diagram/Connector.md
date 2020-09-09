---
layout: post
title: UWP Diagram supports for connecting two nodes | Syncfusion
description: How to draw a line to connect points, nodes, or ports and describe the connector types, its customization of appearance and functions
platform: uwp
control: SfDiagram
documentation: ug
---

# Connector creation and customization

Connectors are objects used to create link between two Points, Nodes or ports to represent the relationships between them.

![link between two nodes and ports](Connector_images/Connector_img1.PNG)

## Define Connector

Connector can be created by defining the start and end points. The Path to be drawn can be defined with a collection of segments. The `SourcePoint` and `TargetPoint` properties of Connector allow you to define the end points of a Connector.

{% tabs %}
{% highlight xaml %}
<!--Style for the Connector-->
<Style TargetType="syncfusion:Connector">
  <Setter Property="ConnectorGeometryStyle">
    <Setter.Value>
      <Style TargetType="Path">
        <Setter Property="Stroke" Value="CornflowerBlue"></Setter>
        <Setter Property="StrokeThickness" Value="1"></Setter>
      </Style>
    </Setter.Value>
  </Setter>
  <Setter Property="TargetDecoratorStyle">
    <Setter.Value>
      <Style TargetType="Path">
        <Setter Property="Fill" Value="CornflowerBlue"></Setter>
        <Setter Property="StrokeThickness" Value="1"></Setter>
      </Style>
    </Setter.Value>
  </Setter>
</Style>

<!--Initialize the Sfdiagram-->
<syncfusion:SfDiagram x:Name="diagram" DefaultConnectorType="Line">
  <syncfusion:SfDiagram.Connectors>
  <!--Initialize the ConnectorCollection-->
    <syncfusion:ConnectorCollection>
    <!--Initialize the Connector-->
      <syncfusion:ConnectorViewModel SourcePoint="100,100" TargetPoint="200,200">
      </syncfusion:ConnectorViewModel>
    </syncfusion:ConnectorCollection>
  </syncfusion:SfDiagram.Connectors>
</syncfusion:SfDiagram>

{% endhighlight %}

{% highlight C# %}
//Define the ConnectorType
diagram.DefaultConnectorType = ConnectorType.Line;
//Define the ConnectorCollection
diagram.Connectors = new ConnectorCollection();
//Define the Connector
ConnectorViewModel connector = new ConnectorViewModel()
{
    //Define the Source and TargetPoint
    SourcePoint = new Point(100, 100),
    TargetPoint = new Point(200, 200),
};
//Adding Connector to Collection
(diagram.Connectors as ConnectorCollection).Add(connector);

{% endhighlight %}
{% endtabs %}

![Straightline with source and target points](Connector_images/Connector_img2.PNG)

### Connectors from stencil

Connectors can be predefined and added to the stencil. You can drop those Connectors into the Diagram, when required. 

For more information about adding Connectors from stencil, refer to [Stencil](/uwp/sfdiagram/stencil "Stencil").

### Connectors through data source

Connectors are automatically generated based on the relationships defined through the data source. For more information about data source, refer to [Data Source](/uwp/sfdiagram/datasource "DataSource").

### Draw Connectors

Connectors can be interactively drawn by clicking and dragging on the Diagram surface by using Drawing Tool. For more information about drawing Connectors, refer to [Draw Connectors](/uwp/sfdiagram/tools#drawing-tools:connectors "Draw Connectors").

## Connect Nodes

The `SourceNode` and `TargetNode` properties allow to define the Nodes to be connected.

{% tabs %}
{% highlight C# %}

//Define the NodeCollection
diagram.Nodes = new NodeCollection();
//Defining the Node
NodeViewModel node1 = AddNode(100,"Node1");
NodeViewModel node2 = AddNode(250,"Node2");
//Adding Node to Collection
(diagram.Nodes as NodeCollection).Add(node1);
(diagram.Nodes as NodeCollection).Add(node2);
//Define the ConnectorCollection
diagram.Connectors = new ConnectorCollection();
//Define the Connector
ConnectorViewModel connector1 = new ConnectorViewModel()
{
    SourceNode=node1,
    TargetNode=node2,
    ConnectorGeometryStyle = this.Resources["ConnectorStyle"] as Style,
};
//Adding Connector to Collection
(diagram.Connectors as ConnectorCollection).Add(connector1);


//Creating NodeViewModel
public NodeViewModel AddNode(double offsetX, string text)
{
    NodeViewModel node = new NodeViewModel();
    node.UnitHeight = 60;
    node.UnitWidth = 100;
    node.OffsetX = offsetX;
    node.OffsetY = 100;
    node.Shape = new RectangleGeometry { Rect = new Rect(0, 0, 10, 10) };   
    return node;
}

{% endhighlight %}
{% endtabs %}

The `SourceNodeID` and `TargetNodeID` properties also allows to define the nodes to be connected.

![Orthogonal connector with source and target nodes](Connector_images/Connector_img3.PNG)

N> By default, connections are created at the intersecting point of Segments and Node bounds. The connection between any specific point of Source and Target Nodes can be achieved with Ports.

## Connections with Ports

The `SourcePort`/`SourcePortID` and `TargetPort`/`TargetPortID` properties allow to create connections between some specific points of Source/Target Nodes. 

For Connections with Ports, please refer to [Port](https://help.syncfusion.com/uwp/sfdiagram/port "Port").

## Segments

The path of the Connector is defined with a collection of `Segments`.

![Orthogonal connector with source and target ports](Connector_images/Connector_img31.PNG)

### Straight

Straight segment allows to create a straight line. To create a straight line, you should specify the segment as `StraightSegment` and add a straight segment to collection.

{% tabs %}
{% highlight C# %}
//Define the ConnectorCollection
diagram.Connectors = new ConnectorCollection();
//Define the Connector
ConnectorViewModel connector = new ConnectorViewModel()
{
    SourcePoint = new Point(100, 100),
    TargetPoint = new Point(200, 200),
    //Define the SegmentCollection
    Segments = new ObservableCollection<IConnectorSegment>()
    {
        new StraightSegment()      
    }
};
//Adding Connector to Collection
(diagram.Connectors as ConnectorCollection).Add(connector);

{% endhighlight %}
{% endtabs %}

![Straightline with source and target points](Connector_images/Connector_img6.PNG)

### Orthogonal

Orthogonal segments are used to create segments that are perpendicular to each other. Set the segment as `OrthogonalSegment` to create the default orthogonal segment.

{% tabs %}
{% highlight C# %}
//Define the ConnectorCollection
diagram.Connectors = new ConnectorCollection();
//Define the Connector
ConnectorViewModel connector = new ConnectorViewModel()
{
    SourcePoint = new Point(100, 100),
    TargetPoint = new Point(200, 200),
    //Define the SegmentCollection
    Segments = new ObservableCollection<IConnectorSegment>()
    {
        new OrthogonalSegment()      
    }
};
//Adding Connector to CollectionS
(diagram.Connectors as ConnectorCollection).Add(connector);

{% endhighlight %}
{% endtabs %}

![Orthogonal connector with source and target points along with segment thumbs](Connector_images/Connector_img8.PNG)

### CubicCurveSegment

Cubic curve segments are used to create curve segments and the curves are configurable with the control points.To create a Curve line, you should specify the segment as `CubicCurveSegment` and add a CubicCurveSegment  to collection.

{% tabs %}
{% highlight C# %}

//Adding Connector to Collection
(diagram.Connectors as ConnectorCollection).Add(connector);
//Define the ConnectorCollection
diagram.Connectors = new ConnectorCollection();
//Define the Connector
ConnectorViewModel connector = new ConnectorViewModel()
{
    SourcePoint = new Point(100, 100),
    TargetPoint = new Point(200, 200),
    //Define the SegmentCollection
    Segments = new ObservableCollection<IConnectorSegment>()
    {
        new CubicCurveSegment()      
    }
};
//Adding Connector to Collection
(diagram.Connectors as ConnectorCollection).Add(connector);

{% endhighlight %}
{% endtabs %}

![cubic curve connector with source and target points along with segment thumbs](Connector_images/Connector_img12.PNG)

#### Avoid overlapping

Orthogonal segments are automatically re-routed, in order to avoid overlapping with the source and target Nodes.

![When placing the source and target node of the connector in some distance](Connector_images/Connector_img10.PNG)

![when placing the source and target node of the connector with intersection](Connector_images/Connector_img11.PNG)

N> Overlapping with Source and Target nodes are only avoided. Other nodes are not considered as obstacles.

## Decorator

Start and end points of a Connector can be decorated with some customizable shapes like arrows, circles, diamond or path. You can decorate the connection end points with the `SourceDecorator` and `TargetDecorator` properties of Connector. 

The `SourceDecoratorStyle` and `TargetDecoratorStyle` properties allows to define the shape of the decorators.

![Connector with source and target decorator](Connector_images/Connector_img15.PNG)

The `SourceDecoratorPivot` and `TargetDecoratorPivot` properties allows to Customize the position of the decorators in the connector.

## SegmentDecorators
 
 `SegmentDecorator` property allows to customize the shape within the Connector. `SegmentDecoratorStyle` property allows to customize the Style of SegmentDecorator.
 
 {% tabs %}
 {% highlight c# %}
 
 //Define the collection of SegmentDecorator
SegmentDecorators = new ObservableCollection<ISegmentDecorator>()
{
    //Define the SegmentDecorator
    new SegmentDecorator()
    {
        //Define the Shape of SegmentDecorator
        Shape = "M0,0 L10,5 L0,10",
        Length =0.4
    }
}

 {% endhighlight %}
 {% endtabs %}
 

 ![Connector with segment decorator](Connector_images/SegmentDecorator.PNG)

## Corner radius

Corner radius allows to create Connectors with rounded corners. The radius of the rounded corner is set with `CornerRadius` property.

{% tabs %}
{% highlight xaml %}

<!--Initialize the Sfdiagram-->
<syncfusion:SfDiagram x:Name="diagram">
  <syncfusion:SfDiagram.Connectors>
    <syncfusion:ConnectorCollection>
      <!--Initialize the Connector-->
      <syncfusion:ConnectorViewModel SourcePoint="100,100" TargetPoint="200,200" CornerRadius="10">
      </syncfusion:ConnectorViewModel>
    </syncfusion:ConnectorCollection>
  </syncfusion:SfDiagram.Connectors>
</syncfusion:SfDiagram>

{% endhighlight %}

{% highlight C# %}

//Define the ConnectorCollection
diagram.Connectors = new ConnectorCollection();
//Define the Connector
ConnectorViewModel connector1 = new ConnectorViewModel()
{
    //Define the CornerRadius
    CornerRadius = 10,
    SourcePoint = new Point(100, 100),
    TargetPoint = new Point(200, 200),
};
//Adding Connector to Collection
(diagram.Connectors as ConnectorCollection).Add(connector1);

{% endhighlight %}
{% endtabs %}

![connector with corner radius](Connector_images/Connector_img21.PNG)

## Padding

Padding is used to leave space between the Connector’s end point and the object to where it is connected. The `SourcePadding` and `TargetPadding` properties of Connector define the space to be left between the connection end points and the source and target Nodes of Connector.

{% tabs %}
{% highlight C# %}

//Define the ConnectorCollection
diagram.Connectors = new ConnectorCollection();
//Define the Connector
ConnectorViewModel connector1 = new ConnectorViewModel()
{
    SourceNode=node1,
    TargetNode=node2,
    //Space between SourceNode and SourceObject
    SourcePadding=5,
    //Space between TargetNode and TargetObject
    TargetPadding = 5,
    ConnectorGeometryStyle = this.Resources["ConnectorStyle"] as Style,
};
//Adding Connector to Collection
(diagram.Connectors as ConnectorCollection).Add(connector1);

{% endhighlight %}
{% endtabs %}

![padding or gap between connector ends and its source and target node](Connector_images/Connector_img16.PNG)

## Bridging

Line Bridging creates a bridge for lines to smartly cross over other lines, at points of interaction. When two lines Connectors meet each other, the line with higher z-order (upper one) draws an arc over the underlying Connector. Bridging can be enabled/disabled either with the `Constraints` property of Connector or with `GraphConstraints`.

The Direction of Bridge can be customized with property `BridgeDirection`.

{% tabs %}
{% highlight xaml %}
<Grid>
  <!--Initialize the SfDiagram with Constraints and BridgeDirection-->
  <syncfusion:SfDiagram x:Name="diagram" BridgeDirection="Bottom" Constraints="Bridging">
    <syncfusion:SfDiagram.Connectors>
      <!--Initialize the ConnectorCollection-->
      <syncfusion:ConnectorCollection>
        <!--Initialize the Connector-->
        <syncfusion:ConnectorViewModel SourcePoint="88,183" TargetPoint="250,300">
        </syncfusion:ConnectorViewModel>
        <syncfusion:ConnectorViewModel SourcePoint="150,156" TargetPoint="150,300">
        </syncfusion:ConnectorViewModel>
      </syncfusion:ConnectorCollection>
    </syncfusion:SfDiagram.Connectors>
  </syncfusion:SfDiagram>
</Grid>

{% endhighlight %}

{% highlight C# %}

//Define the BridgeDirection
diagram.BridgeDirection = BridgeDirection.Bottom;
//Define Constraints
diagram.Constraints = diagram.Constraints | GraphConstraints.Bridging;
//Define the ConnectorCollection
diagram.Connectors = new ConnectorCollection();
//Define the Connector
ConnectorViewModel connector = new ConnectorViewModel()
{
    SourcePoint = new Point(88, 183),
    TargetPoint = new Point(250, 300)
};
//Adding Connector to Collection
(diagram.Connectors as ConnectorCollection).Add(connector);
ConnectorViewModel connector1 = new ConnectorViewModel()
{
    SourcePoint = new Point(150, 156),
    TargetPoint = new Point(150, 300),
};
(diagram.Connectors as ConnectorCollection).Add(connector1);

{% endhighlight %}
{% endtabs %}

![bridging will be shown when two connectors are intersecting](Connector_images/bridging.png)

N> Bezier segments do not support Bridging.

#### BridgeSpace

The `BridgeSpace` property allows to customize the size of bridge in a connector.

{% tabs %}
{% highlight c# %}

//Define the BridgeDirection
diagram.BridgeDirection = BridgeDirection.Bottom;
//Define Constraints
diagram.Constraints = diagram.Constraints | GraphConstraints.Bridging;
//Define the ConnectorCollection
diagram.Connectors = new ConnectorCollection();
//Define the Connector
ConnectorViewModel connector = new ConnectorViewModel()
{
    //Define the Bridge space of the connector
    BridgeSpace=30,
    SourcePoint = new Point(88, 183),
    TargetPoint = new Point(250, 300),
};
//Adding Connector to Collection
(diagram.Connectors as ConnectorCollection).Add(connector);
ConnectorViewModel connector1 = new ConnectorViewModel()
{
    SourcePoint = new Point(150, 156),
    TargetPoint = new Point(150, 300),
};
(diagram.Connectors as ConnectorCollection).Add(connector1);

{% endhighlight %}
{% endtabs %}

![customize the size the bridge of the connector](Connector_images/bridgespace.png)

## Appearance

StrokeThickness, Stroke and style of the Connector and Decorators can be customized with a set of defined properties.

{% tabs %}
{% highlight xaml %}

<!--Style for ConnectorGeometryStyle-->
<Style TargetType="Path" x:Key="ConnectorStyle">
  <Setter Property="Stroke" Value="CornflowerBlue"/>
  <Setter Property="StrokeThickness" Value="2"/>
  <Setter Property="StrokeDashArray" Value="2"/>
  <Setter Property="Opacity" Value="0.8"/>
</Style>

{% endhighlight %}

{% highlight c# %}

//Define the ConnectorCollection
diagram.Connectors = new ConnectorCollection();
//Define the Connector
ConnectorViewModel connector1 = new ConnectorViewModel()
{
    SourcePoint = new Point(100, 100),
    TargetPoint = new Point(200, 200),
    ConnectorGeometryStyle=this.Resources["ConnectorStyle"] as Style,
};
//Adding Connector to Collection
(diagram.Connectors as ConnectorCollection).Add(connector1);

{% endhighlight %}
{% endtabs %}

![custom appearence of the connector](Connector_images/Connector_img22.PNG)

## Interaction

#### Draw Connector

* On drawing a connector, `ObjectDrawn` event will notify the DragState and Item. To explore about arguments, please refer to [ObjectDrawn](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Diagram.ObjectDrawnEventArgs.html) . 

### Connection Editing

* Each segment and end points of a selected Connector is editable with some specific handles/thumbs.

### End point handles

Source and target points of the selected connectors are represented with two handles. Clicking and dragging those handles help you to adjust the source and target points.

![straight connector with editing end thumbs](Connector_images/StraightEditing.PNG)

* If any changes made in the source thumb of the connector ,`ConnectorSourceChangedEvent` will notify the DragState, Connector Item with its old and new values.To explore about arguments ,please refer to [ChangedEventArgs](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Diagram.ConnectorChangedEventArgs.html) .

* If any changes made in the target thumb of the connector ,`ConnectorTargetChangedEvent` will notify the DragState and CauseValue Connector Item with its old and new values.
* Unknown- On dragging the target thumb of available connector, will notify the Cause as `UnKnown`.
* Drawing- On drawing a connector in an Element will notify the Cause as `Drawing`.

To explore about arguments, please refer to [ChangedEventArgs](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Diagram.ConnectorChangedEventArgs.html) . 

* If any changes made in the segment of the connector,`ConnectorEditingEvent` will notify the DragState, Item and ThumbType.To explore about arguments, please refer to [ConnectorEditingEventArgs](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Diagram.ConnectorEditingEventArgs.html) .

### Straight segment editing

* End point of each straight segment is represented by a thumb that enables to edit the segment.

### Orthogonal thumbs

* Orthogonal thumbs allow to adjust the length of adjacent segments by clicking and dragging it.
* When necessary, some segments are added or removed automatically, when dragging the segment. This is to maintain proper routing of orthogonality between segments.

![orthogonal connector with segment thumbs](Connector_images//SegmentEditing.png)

### Bezier thumbs

* Bezier segments are annotated with two thumbs to represent the control points. Control points of the curve can be configured by clicking and dragging the control thumbs.

![bezier connector with control thumbs](Connector_images/Bezier3.gif)

## Constraints

The `Constraints` property of Connector allows to enable/disable certain features of Connectors. For more information about	constraints, refer to [Connector Constraints](/uwp/sfdiagram/constraints#connector-constraints "Connector Constraints").

{% seealso %}

[How to get or set the positions of the segments by programmatically?](https://www.syncfusion.com/kb/11345/how-to-get-or-set-the-positions-of-the-segments-by-programmatically-in-uwp-diagramsfdiagram)

{% endseealso %}
