iframe:用来在一个网页中显示另一个网页
<iframe src="" width="" height="" frameborder="" scrolling=""></iframe>

src:用以引入其它网站的页面值为页面路径

width:用以控制引入页面的宽度

height:用以控制引入页面的高度

frameborder:默认引入的框架带有边框，通常情况下将该属性的值设置为0来取消框架的边框、

scrolling:用来控制是否显示框架的滚动条，值有三个：auto(在需要的情况下出现滚动条，也是默认值)，				yes(始终显示滚动条)，no(从不显示滚动条)

iframe也可以作为一个链接的目标框架，链接的target属性必须设置为iframe的name属性