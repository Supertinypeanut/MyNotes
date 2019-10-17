# HTML


## HTML

### 列表

- 有序列表：<ol><li></li></ol>

- 无序列表:<ul><li></li></ul>

- 自定义列表:<dl><dt><dt><dd><dd></dl>

### 表格

- table>tr/caption>th/td

- 属性：border 边框

### cellspacing 单元格之间距离

### cellpadding 内容与单元格之间距离

### width 宽度	height 高度

### aligin:left/center/right

### 跨行：rowspan	跨列：colspan

- emmet语法：快捷方式

## 标签*n	+ tab

## 标签*n>子标签*n>子孙标签*n。。。。+tab

## 兄弟标签+兄弟标签 +tab

## 标签{内容}	+tab

## 标签{内容$}	+tab	（产生标号）

## 表单

### 表单标签：<from></from>

### input标签

- type属性

	- text

		- 文本框

			- value属性

				- 文本框中的数据

			- maxlength属性

				- 文本框输入的最大字符数

			- readonly属性

				- 无论什么值，文本只能读

			- size属性

				- 设置文本宽度

	- password

		- 密码框

	- radio

		- 单选按钮

			- 需要相同class值

			- 默认选择 checked=“checked”

			- <lable for=“id”>文本</lable>	关联的按钮id

	- checkbox

		- 复选框

	- button

		- 普通按钮

	- submit

		- 提交按钮

			- <buttom>  作用相同，都有提交表单功能

	- reset

		- 重置按钮

	- image

		- 图片提交按钮

	- file

		- 文件可选择：accept="文件后缀"

		- 多选：multiple

		- js获取所有选择文件：filenode.files

## 配合：Ajax使用

### 创建临时路径：URL.creatObjectURL(filenode.files[0])

## hidden

### 隐藏域

## 下拉列表：select标签

## <textarea><teatarea>文本域标签

## 布局标签

### span

- 行内元素

### div

- 块级元素

### 行内块元素

- display：inline-block /block/inline

- 清除图片底部间隙

## iframe标签

