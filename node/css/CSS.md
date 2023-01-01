# 								    CSS

## 1.CSS规则

一个css规则由一个选择器（要定义样式的HTML元素）和一个声明块（包含一个或多个声明；每个声明包括一个CSS属性名称和一个值中间用:隔开，多个声明之间用;隔开，声明块用{}包裹起来）构成

选择器和花括号之间、花括号与属性名之间、冒号、分号前后都可以添加任何多个空格或换行

属性名和属性值之间不能有空格或换行

## 2.CSS样式

### 2.1.内联CSS(行内样式)

被用来为一个单一的元素应用一个独特的样式

要使用内联样式需要将样式属性添加到相关的元素中，样式属性可以包含任何CSS属性

### 2.2.内部CSS

内部样式表一般定义在head元素里，通过style元素来定义

页面的样式声明均需要添加在style元素内部

CSS选择器:用来寻找或选择你想要定义样式的html元素

元素选择器:根据元素名来选择HTML元素

margin-left用于定义"盒子"元素位于父容器左侧的距离

### 2.3.外部CSS:外部样式

通过改变一个文件来改变整个网站的外观

外部样式将CSS代码放在一个独立的以.css为后缀名的文件中，使html页面结构文件和css样式文件完全独立开来

每个html文件都必须在head元素里添加<link>元素

<head>
    <link rel="stylesheet" href="mystyle.css">
</head>

### 2.4.样式表的优先级

内联样式>内部样式/外部样式

内部样式和外部样式，浏览器后读取的优先级高

## 3.CSS选择器

### 3.1.CSS简单选择器

根据名称、ID、类别来选择元素

```html
<style>
    h1{
        text-align: center;
        color: darkred;
    }

    p{
        color: red;
    }

    #para2{
        text-align: center;
    }

    h1,#para2{
        font-style: italic;
    }
    p.deco {
        text-decoration: underline;
    }
</style>
	<h1 class="italic">CSS</h1>
	<p id="para2" class="italic deco">hello,css</p>
```

分组选择器:选择所有具有相同样式的html元素

### 3.2..组合选择器

根据元素之间的类别关系来选择元素

通过一些特殊符号将多个简单选择器连接起来就构成了组合选择器

#### 3.2.1.后代选择器

通过空格连接

匹配作为指定元素后代的所有元素

div p {                                    //选择了<div>元素内的所有<p>元素

​	background-color: yellow;

}

#### 3.2.2.子选择器

通过">"连接

只能选择作为某元素的子元素，不能选择到孙辈的元素。

#### 3.2.3.相邻的兄弟选择器

通过"+"连接

#### 3.2.4.一般兄弟选择器

通过"~"连接

### 3.3.伪类选择器

根据特定状态来选择元素

selector:鼠标行为{}   //selector为其他基础选择器，“:鼠标行为”为伪类选择器 

#### 3.3.1.鼠标点击前  :link

代表鼠标没有操作时元素的默认样式

#### 3.3.2.鼠标点击后  :visited

代表鼠标点击并离开元素之后的样式

#### 3.3.3.鼠标悬停时  :hover

代表鼠标悬停或者是划过元素时元素的样式

#### 3.3.4.鼠标点击时  :active

代表鼠标点击元素瞬间，元素显示的样式

#### 3.3.5.注意

1.冒号和后面的鼠标行为没有任何空格，必须连接在一起

2.四个伪类选择器必须按照(:link,:visited,:hover,:active)，否则在浏览器中部    分样式不能实现

3.伪类选择器全部一起使用的情况，主要是应用在超连接上，偶尔也会独立 使用在其他标签上

4.伪类选择器也可以应用在其他元素上，但是只能实现active激活瞬间和hover鼠标悬停效果

### 3.4.伪元素选择器

通过伪元素选择器，可以设置元素指定部分的样式。主要用来设置元素内文本的首字母，首行的样式、或是在元素内容之前或之后插入其他内容

selector::pseudo-element{}

selector为目标元素 “::pseudo-element”代表向目标元素内，添加伪元素，并对伪元素的内容进行修饰

#### 3.4.1. ::first-letter

向文本的首个字符添加特殊样式

#### 3.4.2. ::first-line

向文本的首行添加特殊样式

#### 3.4.3. ::before

在元素内容之前插入内容

before(after)要添加的内容作为content属性的值来使用

#### 3.4.4. ::after

在元素内容之后插入内容

#### 3.4.5. ::selection

更改选中文本的样式

selection选择器只支持: color , background , cursor(鼠标样式) , outline(描边效果).

### 3.5.属性选择器

根据一个属性或属性值来选择元素

Element(元素)[attribute(属性)]

Element[sttribute="value"]

查找带有该属性的元素，然后添加样式声明

a[target] {          //查找带有target属性的a元素

​	background-color: yellow     //为a元素添加背景颜色为黄色的样式声明

}

#### 3.5.1.CSS选择器的四种属性

1.[attribute]:来查找HTML结构中，带有attribute属性的所有元素

2.[attribute="value"]:来查找HTML结构中，带有attribute属性，并且属性值为value的元素。

3.[attribute~="value"]:来查找HTML结构中，带有attribute属性，并且在多个属性值中包含value的元素

4.[attribute|="value"]:来查找HTML结构中带有attribute属性，并且属性值以

value或者是value-开头的元素

### 3.6.CSS选择器的权重

行内选择器(权重1000)>ID选择器(权重100)>类选择器(权重10)>元素选择器(权重1)>通用选择器(权重0)

## 4.CSS文本样式

### 4.1.文本颜色

一个页面的默认文本颜色是在body选择器中定义的

body {

​	color: blue;

}

### 4.2.大小写转化

p.transform {

​	text-transform:uppercase(文本被转换为大写),lowercase(文本被转换为小写),capitalize（每个单词的首字母被转换为大写）

}

### 4.3.文本对齐

水平对齐

text-align:center,left,right;

垂直对齐

vertical-align:

baseline(基线对齐)

基于四线三格倒数第二行对齐，对于英文文本才有意义

text-top(文本顶部对齐)，text-bottom(文本底部对齐)

sub(下角标对齐)，super(上角标对齐)

### 4.4文本间距

使用长度值或者百分比来设置文本缩进，长度值可以使用绝对单位(px)或相对单位(最常用em缩进的宽度为字符宽度的倍数)，字符宽度通过font-size属性来设置；百分比缩进：根据父元素的宽度计算得到

p {}	

text-indent;

}

letter-spacing属性用于指定中文文字或英文字母之间的空隙

line-height属性用于指定行与行之间的高度，也就是行高，两条基线的距离。

属性值：normal:也是默认值，浏览器会根据字符大小自动设置一个行高

一个数字：此数字与当前字符大小相乘计算得到

绝对值：设置固定的行间距

word-spacing用于指定文本中单词的间距，只对英文有效

white-space指定了如何处理元素内部的空白

属性值:nowrap:不管包含文本的元素宽度是多少，文本都不会换行，直到遇见br标签为止。

### 4.5.文本修饰

通过CSS文本装饰可以为文本添加装饰线，为装饰线设置颜色，为装饰线指定风格，为装饰线设置厚度等效果

为文本添加装饰线通过text-decoration-line属性实现，可以结合一个以上的值，如上划线和下划线，来显示文本上方和下方的线条，可以同时给文本添加多个线条（给text-decoration-line属性设置多个值，每个值通过空格分开）添加了连接的文本不要使用underline下划线装饰

overline:在文本上方添加线条修饰

line-through:在文本中间添加

underline:在文本下方添加

为文本设置装饰线的颜色通过text-decoration-color属性实现

装饰线指定风格通过text-decoration-style属性实现

solid:实线

double:双实线

dotted:圆点线

dashed:虚线

wavy:波浪线

通过text-decoration-thickness属性为线条设置厚度

auto:默认值（这个值不确定和所修饰的文字大小有关系）

px:像素大小，是一个绝对值

%:是一个相对值（根据修饰文字的高度计算出来）

以上属性都可以简写为text-decoration

text-decoration-line必须设置

h4 {

​	text-decoration: underline red double 5px;

}

a {       /*去除超链接的下划线*/

​	text-decoration: none;

｝

### 4.6.字体与字号

使用font-family指定一个文本的字体，属性值是一个字体的名称

#### 1:).英文字体

1.Serif(有衬线字体)

2.Sans-serif(无衬线字体)

3.Monospace(单空格字体，也叫等宽字体)

4.Cursive(草书字体，模仿人类的手写体)

5.Fantasy(幻想字体，是装饰性娱乐性字体)

#### 2:)中文字体

1.Microsoft Yahei(微软雅黑 Windows)

2.PingFang SC(平方简 Mac)

定义样式备选

font-family: "备选字体", 字体

#### 3:)字号

通过font-size属性设定文本的大小

属性值可以是绝对大小也可以是相对大小

如果不设置字体大小，正常的文本如段落，会继承祖先元素的大小，如果祖先元素也没有设置字体大小就会使用浏览器的默认字号，大小为16px

##### 1.绝对大小

将文本设置为指定的大小，不允许用户在所有的浏览器中改变文字的大小

##### 2.相对大小

相对于周围元素的大小使用em/ % 来设置，一般情况下会根据继承下来的父元素尺寸计算得到

rem:相对于根元素

### 4.7.字体风格和样式简写

通过CSS可以设置文本倾斜，文本粗细，文本大小写

font-style属性主要用于指定斜体文本

normal:文本正常显示

italic:文本斜体显示

oblique和italic非常相似，但浏览器支持度较低

font-weight属性指定文本的粗细，属性值设置有两种方式:名称、数值

名称:lighter:细体,normal:正常字体,bold:加粗字体,bolder:更粗字体

数值:100,200,300,...,900

100对应lighter，400对应normal，700对应bold，900对应bolder

font-variant属性指定了文本是否应以小型大写字母(小一号的大写字母)显示

normal,small-caps(设置为小型大写字母)，只对英文有效

可以在一个font属性中指定所有单独的字体属性

font-size和font-family这两个值是必须的

p {

​	font: oblique 100 small-caps 30px/30px 华文仿宋

}

### 4.8.谷歌字体和lcon图标

使用谷歌字体需要在<head></head>中添加一个特殊的样式表链接

icon字体图标，可以将这个图标当成是文本，任意的添加样式

## 5.CSS边框

border-style属性指定了要显示什么样的边框

dotted:点状的边框

dashed:虚线边框

solid:实线边框

double:双边框

none:无边框

hidden:隐藏的边框

当表格单元格相邻边框产生冲突时，border-style:hidden优先级最高，border-style:solid优先级次之，border-style:none优先级最低

在border-style中间插入一个表示方位的词就可以设置单个边框线了

border-right-style,border-bottom-style,border-left-style,border-top-sytle

### 5.1borter-style混合的简写方法

#### 1.四个值

分别表示上边，右边，下边，左边的边框样式

#### 2.三个值

分别代表上边，左右边，下边的边框样式

#### 3.两个值

分别表示上下边，左右边的边框样式

#### 4.一个值

表示四个边框的样式



border-width:设置边框宽度

可以被设置为一个特定的尺寸（以px,em等为单位）

或者使用三个欲定义的值: thin、medium、thick、

边框宽度也可以使用混合简写的方法



border-color:设置边框颜色

颜色名称，16进制颜色值，RGB颜色值

也可以通过transparent来显示透明



边框也可以使用速记属性

可以在一个border属性中指定border-width,border-style,border-color等单独的边框属性，border-style必须要声明

通过声明border-top,border-right,border-bottom,border-left四个属性，值为上面简写的方式就可以单独定义元素的某一条边了

样式中给元素设置的宽高，是不包含该元素边框宽高的，它只包含元素内容的宽高



## 6.CSS列表

### 1.列表项标记样式

应用list-style-type属性可以设置不同的列表项标记

circle:空心原点

disc:实心原点

square:小方点

decimal:数字

upper-roman:大写罗马字

lower-alpha:小写字母

list-style-image属性指定了一个图像作为列表项的标记

属性值为url(背景图片路径)

### 2.标记的位置

通过list-style-position属性来设置标记的位置

outside:标记在列表项外

inside:标记在列表项内部

### 3.简写

list-style被用来在一个声明中设置所有的列表属性

属性值按照list-style-type,list-style-position,list-style-image顺序来书写，

某个属性值缺少的话就使用它的默认值

## 7.CSS背景属性

html,body {

 height: 100%;

background-image: url();

background-repeat: repeat/no-repeat;

background-position: 

}

background需要设置两个值，第一个值表示水平方向的对齐方式：left,center,right;第二个值表示垂直方向的对齐方式:top,center,bottom.

background-attachment用来声明容器里的背景图片与内容的依附方式:fixed:图片固定。scroll:同时滚动。

background-color:(颜色名称)/十六进制颜色值/rgb颜色等，rgba：通过一个alpha通道来指定颜色的不透明度，是一个介于0-1的值，0为完全透明，1为完全不透明

background-size: cover 能使背景铺满整个容器，如果应用到简写形式中在它前面则必须添加背景图片位置

也可以使用单一的background属性来指定所有的背景属性

## 8.CSS精灵图

基本原理就是将页面中使用到的各种图片进行分类，整齐划一的摆在一张背景透明的图片上面，通过CSS的背景技术实现图片的引入，从而减少服务器发送和接受请求的次数

## 9.CSS轮廓

轮廓是在边框之外绘制的，并且可能与其他内容重叠，他不是元素尺寸的一部分，元素的总宽度和高度不受轮廓宽度的影响。

### 1.outline-style:轮廓样式

dotted:点状轮廓；dashed:虚线轮廓；solid:实线轮廓；double:双线轮廓；none:无轮廓；hidden:隐藏轮廓

### 2.outline-color:轮廓颜色

颜色名称，十六进制颜色值，RGB颜色值

### 3.outline-width:轮廓宽度

thin(一般为3px),medium(一般为3px),thick(一般为5px),一个特定的尺寸以px,em为单位

### 4.outline-offset:轮廓偏移

用来设置轮廓和元素之间的空隙

### 5.outline:轮廓简写

outline-style必须设置

## 10.CSS边距

css边距属性用来在元素周围创造空间，控制元素边框外的距离

margin-top/right/bottom/left设置元素的上边、右边、下边、左边的外边距

auto:浏览器自动计算的边距

length:以px,pt(point,1pt=0.376mm),cm等为单位指定边距

%:以父元素宽度的百分比来指定边距

length和%都可以取负值，表示减少外边距空间的大小

### margin混合的简写方法

margin: auto使元素在其父元素或其容器内水平居中，该元素会占用指定的宽度，剩余的空间将在左右边距之间平分

#### 1.四个值

分别表示上边，右边，下边，左边的边距

#### 2.三个值

分别代表上边，左右边，下边的边距

#### 3.两个值

分别表示上下边，左右边的边距

### margin塌陷

一般发生在相邻块元素垂直边距和嵌套块元素垂直边距邻接的时候，不会发生在左右边距上，只会发生在顶部和底部的边距上

嵌套块元素垂直边距也会塌陷，两个嵌套关系的块元素有时父元素的上边距与子元素的上边距也会发生合并，合并后的边距也为两者中的较大的值

## 11.CSS填充

css填充属性用于在一个元素的周围产生空间，也就是边框内到内容外之间的距离。如果一个元素有指定的宽度，那么加在该元素上的填充就会加到该元素的总宽度上。通过padding-top/right/bottom/left设置元素的上边、右边、下边、左边的填充

length(以px,pt,cm等为单位指定填充)

%:以父元素宽度的百分比来指定填充

length和%都可以为负值，表示减少内部填充的空间大小

padding的简写方式和margin一致

## 12.元素的宽高

高度和宽度属性不包括margin,border和padding区域，只是用来定义元素的内容尺寸。

auto:默认值，浏览器会计算出宽度和高度

length:以px,pt,cm等为单位定义高度和宽度

%:以父元素宽高的百分比来定义高度和宽度

initial:将高度和宽度设置为默认值，实际上就是auto

## 13.CSS盒模型

本质上说是一个包裹每个HTML元素的盒子，包含margin,border,padding,content四个部分

浏览器就是通过盒模型来计算元素在网页中占据的空间大小的

content表示盒子的内容，包括文本图像等

padding表示填充内容周围的一个区域，它是透明的

border表示围绕填充和内容的边框

margin表示边框以外的区域，也是透明的

### 1.标准盒模型

box-sizing:content-box;(也是默认值)

盒子的宽度=内容宽度+左(右)填充+左(右)边框+左(右)边距

盒子的高度=内容高度+上(下)填充+上(下)边框+上(下)边距

### 2.怪异盒模型

box-sizing:border-box;

盒子的宽度=左(右)边距+CSS样式设置的width值

## 14.CSS布局

### 14.1.显示属性

display指定了一个元素是否显示以及如何显示，每个html元素都有一个默认的显示值。元素类型不同，默认的显示值也不同。

大多数元素的默认显示值为block:元素显示为块级元素/inline:元素显示为行内元素。

none:隐藏元素

通过样式可以改变元素的默认显示类型

visibility:hidden(隐藏元素，且该元素仍将占用它隐藏前相同的空间)/visible（显示）

### 14.2.元素类型

行内元素不能设置宽高样式，行内元素可以设置边框样式，行内元素可以设置内填充样式，行内元素可以设置左右方向的外边距样式

块元素可以设置宽高、边框线、内填充、外边距样式

display:inline-block具备inline和block两种元素的显示特点

两个拥有display:inline-block样式的元素中间会有空隙

设置一个元素的display属性只能改变该元素的显示方式，而不能真正改变html元素的类型

### 14.3.溢出处理

overflow:   指定了当一个元素的内容太大，无法容纳在指定区域时，是否要裁剪内容或添加滚动条

visible:默认,溢出的内容没有被剪掉

hidden:溢出的内容被剪切

scroll:溢出的内容被减掉，并且增加了一个滚条来查看其余的内容

auto:类似于scroll，但是只在必要的时候才添加滚动条

overflow-x,overflow-y指定是否只在水平方向或垂直方向上滚动

white-space:设置如何处理元素的空行

nowrap让文本不会换行(直到遇到br为止)，并且溢出的部分隐藏

text-overflow: 控制文本溢出的样式

### 14.4.浮动

如果给一个容器添加浮动会脱离文档流，并且不占据原来的位置

float:left/right/none

为了是父元素的高度保持正常

1.给父元素添加样式overflow: auto

2.使用clear样式属性，当我们不希望当前元素受到前面浮动元素影响的时候，就给当前元素增加clear这个样式。clear:left(不受左浮动的影响)/right(不受右浮动影响)/both(既不受左浮动影响也不受右浮动影响)

### 14.5.定位

position:指定了一个元素的定位方式

#### static:静态定位

#### relative:相对定位

需要配合left,top,right,bottom这些定位属性才能生效

relative相对的是容器自身的屏幕坐标(0,0)点

容器位置发生位移后，原来占据的空间依然保留

默认会覆盖没有定位的容器

#### fixed:固定定位

固定定位的元素时相对于浏览器视口定位的，即使页面发生滚动，它也保持在同一个位置

top,right,bottom和left属性被用来定位元素，但不是必须的

#### absolute:绝对定位

当一个容器做绝对定位时，它会脱离文档流

参照点为:有定位设置的离他最近的祖先元素的(0,0)点坐标

绝对定位的容器默认会覆盖没有默认的容器

#### sticky:粘性定位

会产生动态效果，很像static和fixed的结合

父元素不能添加overflow:hidden或者oberflow:auto属性；自身必须声明top,bottom,left,right一个或多个属性，否则就相当于静态定位；父元素的高度不能低于sticky定位元素的高度；sticky定位元素仅在其父元素内生效

粘性定位初始状态相当于static定位

相对于父容器的定位条件符合时，容器变现为固定定位

top,right,bottom或left至少声明一个，粘性定位才能生效

#### CSS定位的堆叠顺序

CSS允许我们只用z-index属性把它放置在三维空间中

z轴代表我们的目光向页面或屏幕看进去的时候各元素的布局情况

可以为z-index属性设置一个整数值，可以是一个正整数、负整数或0，值越大元素就离我们“越近”，值越小离我们就“越远”

容器的对的顺序计算，是先比较同级容器的。子容器是不会超出父容器的对的顺序的

### 14.6.宽高自适应

元素的宽或高能够随着屏幕的宽高变化而变化的能力

将width和height的值设置为%，可实现元素的宽高自适应

min/max-width(height)可以设置元素宽高自适应的临界值

## 15.CSS数学函数

calc(数学表达式)执行一个计算，作为属性值使用

width: calc(100% - 100px);

## 16.圣杯布局

中间容器高，旁边两侧的容器低

由于三个子元素都是浮动元素，撑不开父元素的高度，需要给父元素设置固定高度或者做浮动的清理

## 17.BFC

块格式上下文，一个BFC区域和另一个BFC区域是相互独立互不影响的，即如果容器内部的子元素出现了上下边距，边距不会跑到外面去影响其他元素而是在内部拉开距离，使父元素成为了一个独立的区域

如果元素被触发了BFC规则，那么浏览器在计算这个元素高度的时候会把浮动元素也考虑进去

### 如何触发元素的BFC规则

1.给元素增加浮动: float:letf/right;

2.给元素增加绝对定位: position: absolute/fixed;

3.改变元素的类型为inline-block:(display: inline-block/tabl-cell等;)

4.改变元素的overflow样式: overflow: auto/hidden(不等于默认值);

无论是浮动、定位或更改元素类型，都有可能大幅度的影响页面布局，而overflow这个属性则没有这方面的问题

## 18.CSS表格

table,th,td元素都有独立的样式

可以应用border-dollapse属性把表格的边框折叠成一个单一的边框border-collapse:collapse;

text-align:设置th或td中内容的水平对齐方式，默认情况下th元素的内容是居中对齐的，td元素的内容是左对齐的

vertical-align:设置th或td中内容的垂直对齐方式，默认情况下对于th和td元素表格中内容的对齐方式是居中对齐

要控制表格中边框和内容之间的空间，可以给td和th元素设置padding属性

## 19.CSS表单

```css
* {
  padding: 0;
  margin: 0;
}

form {
  width: 600px;
  border: 3px solid skyblue;
  border-radius: 15px;
  padding: 20px;
  margin: 50px;
}

form > label {       /*独占一行，纵向排列，并设置每行间距离*/
  display: block;
  margin-bottom: 20px;
}

form > label > span {    /*实现span文本右对齐*/
  display: inline-block;
  width: 90px;
  text-align: right;
}

form > label > input {   /*单行文本框距离*/
  padding: 5px 10px;
}

form > input[type=reset],
form > input[type=button] {  /*设置按钮高度和宽度*/
  width: 130px;
  height: 30px;
  font-size: 18px;
  cursor: pointer;
  color: #fff;
  border: none;
}

form > input[type=reset] {  /*设置按钮颜色*/
  background-color: orange;
}

form > input[type=button] {
  background-color: lightgreen;
}
```

## 20.页面的重排和重绘

首先，浏览器会捕获到html结构，生成一个html树结构，这个结构内的所有标签是没有样式出现的，只是标明了标签和标签之间的父子关系而已。接下来，浏览器会拿到写的css样式，解析后生成一个css树结构，这个结构没有和html结合，只是一个css样式说明的树状结构。然后浏览器就会把拿到的html树和css树相结合，将两个树慢慢的融合在一起，组成一个rander树，这里就会把标签和样式结合在一起，呈现页面中的效果

### 重排:重新排列元素

当通过后期的操作让页面中的节点发生了尺寸变化，那么会因为一个元素的改变而导致整个页面发生变化，可能后续的元素位置都会发生改变，这时就会重新排列所有元素，触发重排，重新用html树和css树结合，去生成新的rander树，进行新一次的绘制。

### 重绘:重新绘制元素

当通过后期的操作让页面的节点发生一些外观上的变化，比如改变背景颜色、文字颜色、边框颜色的时候，不会导致页面排列元素的变化只是当前一个节点发生变化对其他节点没有影响，那么这是就不需要重新排列元素只需要重新绘制当前一个节点即可

## 21.色块搭建

在编写完整的页面前，需要先将页面进行色块搭建，完成区块划分。完成色块搭建，就是对页面的基础构建
