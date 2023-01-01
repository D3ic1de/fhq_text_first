HTML表单

表单控件：分组控件、单（多）行文本框、单选框、多选框、下拉框、按钮、文件选择控件.

单行文本框：让用户输入文本

<form action="">
	<input type="text">
</form>

密码框

<form action="">
	<input type="password">
</form>

多行文本框（也可以设置成只读的）

cols:文本区可见宽度

rows:文本中可见行数

<form action="">
	<textarea cols="" rows=""></textarea>    
</form>

单选按钮

单选框控件必须成组使用才有意义，每组至少需要2个单选框

组是通过name属性来建立，凡是name值相同的就是一组

同组的单选框，只有一个会处在选中状态，其他的会自动呈现为未选中状态

若没有给单选框设置name属性，默认每个单选框自成一组

<form>
    <input type="radio">
</form>

多选框

<form>
    <input type="checkbox">
</form>

默认选中效果

<form>
    <input type="radio" checked>
</form>

下拉菜单

<select>
    <option value="">1991</option>
    <option value="">1992</option>
    <option value="">1993</option>
    <option value="">1994</option>
    <option value="">1995</option>
    <option value="">1996</option>
    <option value="">1997</option>
    <option value="">1998</option>
    <option value="" selected>1999</option>
</select>

多选下拉菜单

<select name="" id="" multiple size="5">
    <option value="">范特西</option>
    <option value="">JAY</option>
    <option value="">叶惠美</option>
    <option value="">最伟大的作品</option>
    <option value="">跨时代</option>
    <option value="">魔杰座</option>
    <option value="">八度空间</option>
</select>

选择文件

<input type="file">

label标签

<form>
    <lable for="username">JAY CHOU</lable>
    <input type="text" id="username">
</form>

只读控件

只读控件的值可以被收集并发送给后端

<input type="text" readonly>

禁用控件

禁用的表单控件值是不会被收集和发送给后端的

<input type="radio" disabled>

disabled可以添加给任何的表单控件

分组控件

<fieldset>

​    <legend>标题</legend>

</fieldset>

表单按钮：提交按钮、重置按钮、普通按钮、图像按钮、双标签button按钮

提交按钮:点击确认信息同时发送表单数据给后台服务器

后台服务器将数据保存到数据库中，服务器会给表单提供一个访问地址

//<form action="服务器地址" target="_self || _blank">

<form action=“”>
    <input type="submit">
</form>

重置按钮

<form>
    <input type="reset">
</form>

普通按钮

<form>
    <input type="button" value="普通按钮">
</form>

图像按钮

<input type="image" src="">

双标签button按钮

也能实现表单的提交功能

<form>
    <button>button按钮</button>
</form>
表单数据采集与提交

```html
<form action="服务器地址" method="post">
    手机/邮箱/账号<input type="text" name="pnumber"><br>
    请输入密码：<input type="password" name="password"><br>
    <input type="submit" value="登录">
</form>
```

