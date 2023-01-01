水平线

<hr width="" size="" noshade="" color="" align="">

使用align的前提是水平线需要有宽度，默认为水平居中对齐

预格式化的文本

<pre>预 格式化 的 文本</pre>

图像映射（一个图片的热点链接）

<map name="">
	<area herf="" shape="" coords="">
</map>

name属性要与img标签的usemap属性相关联，在图像和地图之间创建关系

herf:用来定义热点区域链接的目标地址

shape:用来定义区域的形状-->default:所有区域   rect:热点区域为矩形 circle:圆形 poly:多边形

coords:用来定义可点击区域的坐标（需要与shape属性配合使用）

<area shape="circle" coords="x,y,r">

圆心坐标 (x,y)  半径r 

图像原点位于左上角

<area shape="poly" coords="x1,y1,x2,y2,...,xn,yn">

每一对x,y坐标都定义了多边形的一个顶点，多边形会自动封闭，不用再定义第一个点的坐标

<area shape="rect" coords="x1,y1,x2,y2">

第一个坐标是矩形的一个角的顶点坐标，另一对坐标是对角顶点的坐标