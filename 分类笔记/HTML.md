## HTML

### 列表

- 有序列表：`<ol><li></li></ol>`

- 无序列表:`<ul><li></li></ul>`

- 自定义列表:`<dl><dt><dt><dd><dd></dl>`

### 表格

- ``table>tr/caption>th/td``

	
	```html
	<table>  
	  <tr>  
			<th></th>  
		</tr>  
		<tr>  
			<td><td>//单元格  
		</tr>//	行  
	</table>//表格容器
	```
	
- 属性：
  	
  - border 边框	
  - cellspacing 单元格之间距离
  - cellpadding 内容与单元格之间距离
  - width 宽度	height 高度
- aligin:left/center/right  
	- 跨行：rowspan	跨列：colspan
	
	
	```html
	<table>  
		<caption></caption>  
	  
		<thead></thead>  
	  
		<tbody></tbody>  
	  
	<tfoot></tfoot>  
	</table>
	```
	
	
	
	- `emmet`语法：快捷方式
	  	标签*n	+ tab
	    	标签*n>子标签*n>子孙标签*n。。。。+tab
	    	兄弟标签+兄弟标签 +tab
	    	标签{内容}	+tab
	    	标签{内容$}	+tab	（产生标号）

### 表单

- 表单标签：`<from></from>`

- `input`标签

	- readonly属性--无论什么值，文本只能读

	- size属性--设置文本宽度

	- value属性文本框中的数据

	- maxlength属性--文本框输入的最大字符数

	- type属性

		- text文本框

		- password--密码框

		- radio--单选按钮

			​	需要相同class值

			​	默认选择 checked=“checked”

			​	`<lable for="id">`文本`</lable>	`关联的按钮id

		- checkbox--复选框

		- button--普通按钮

		- submit--提交按钮

			`<button></button>`  作用相同，都有提交表单功能

		- reset--重置按钮

		- image--图片提交按钮

		- file--文件域

			​	文件可选择：`accept`="文件后缀"

			​	多选：`multiple`

			​	js获取所有选择文件：`filenode.files`伪数组，对象类型
	​	配合：Ajax使用
		
	​		创建临时路径：`URL.creatObjectURL(filenode.files[0])`
		
- hidden--隐藏域.   与`disable`对比同样是隐藏，但会提交给服务器
		

- 下拉列表：select标签

  `<select> `

   	 `<option></option>  `

  ​	  `<option></option>  `

    	`option selected="selected"></option>默认  
  		......  `

   	`<option></option>  
  </select>  `

  可分组：`<optgroup lable=描述"></optgroup>`  

  select的value值为选中的option的value值，假如没有的话便option的内容给select的value值

  


  属性值：cols=“列数”		roes=“行数”  
  resize:none;不可拖动大小  
  outline：none  获得焦点高亮

### 布局标签

- span

	- 行内元素

- div

	- 块级元素

- 行内块元素

	- display：inline-block /block/inline

	- 清除图片底部间隙

		因为行内块默认是以基线对齐：所以可以中线对齐：vertical-align：middle；   
		//img也可以使用：display：block；

### iframe标签

可以在当前页面里，开启嵌入新页面
		获取父窗口：`windom.parent`
		获取嵌套窗口：`document.queryselect('iframe').contentWindom`
	`<iframe name= ""  src="默认地址"></iframe>
	<a treget="iframe的name值" href="新地址">`
	还可以做隐藏帧（最初ajax实现）