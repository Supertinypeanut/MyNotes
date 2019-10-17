# css


## 选择器优先级及权值

### 标签选择器

### 类名选择器

### id选择器

### 通配符选择器

### 后代选择器

### 子代选择器

### 交集选择器

### 并集选择器

## 文本样式

### font：weight style size family

### 水平居中：text-align：center/left/right

### 垂直居中：line-height：容器高度

### 文本修饰属性：text-decoration

### 首行缩进：text-indent：px / % / em

### 字体图标可以去阿里妈妈上下载，导入工程

## 盒子模型

### 边框border

- border-width：px

- border-color：颜色

- boder-style：none/solid/double/dashed/dotted

- 连写：border : border-width border-style  border-color 

### 内边距：padding

### 外边距：margin

- 包含塌陷

- 垂直塌陷

- margin的百分比只会参照父元素的宽度，所以竖直方向的margin不会根据父元素的高度改变而改变

## 背景与列表

### 背景

- background-color：transparent（透明）|color_name|十六进制|rgb|inherit（继承父元素）

- background-image：url（地址）

- background-repeat：repeat | no-repeat |repeat-x|repeat-y

- background-position：x% y% |xpos ypos |top/left/bottom/right/center  top/left/bottom/right/center （俩个参数，只写一个，第二个默认center）

- background-attachment：scroll |fixed 

- 简写：background：无序

### 列表

- list-style-type：disc| circle| square |none |decimal |lower/upper-roman/alpha

- list-style-image：url（地址）

- list-style-position：outside |inside 

- 简写：list-style：type image  position

## float浮动

### 浮动语法float：none |left |right

### 清除浮动:clear：none|left |right |both

### 防止高度塌陷，清除浮动

### 脱标

## 定位position

### static自然定位

### relative相对定位

- 保留原来位置

- top/right/bottom/left/z-index（层叠顺序）

- 相对自己原来位置

- 后代可以对其进行绝对定位

### absolute绝对定位

- 不保留原来位置

- 相对与最近的祖先元素

### fixed固定定位

- 相对与视口

### sticky磁贴定位

- 相当与relative+fixed，制造吸附效果

- 浏览器兼容性问题：查询www.caniuse.com

## 网页布局基础

### 行布局

### 列布局

### 混合布局

### 圣杯布局

### 双飞翼布局

### 弹性布局（flex）

- 容器属性

	- 父盒子：display:flex;  //设置为弹性盒子

	- 主轴方向：flex-direction

	- 主轴对齐方式：justify-content

	- 侧轴对齐方式：align-items

	- 子元素是否换行：flex-wrap

	- 复合属性：flex-flow：主轴方向 是否换行   //一般不用

	- 多行显示后对齐方式：align-content

- 项目属性

	- flex: n / n%  //把主轴剩余空间按份数或百分比分开

	- align-self：flex-end/flex-start/center/stretch   //单独控制自己侧轴对齐方式

	- order: number    //排列优先级，number越小越前

### rem布局

- 1rem=HTML的font-size大小

- 媒体查询

### less

- 命名规则

### 响应式布局（bootstrap）

- 栅格系统

	- 类前缀

	- 基本使用

		- col-类前缀-份数

	- 特点

	- 列嵌套

		- row

	- 列偏移

		- col-类前缀-offset-偏移份数

		- 使用场景：左右布局、居中布局

	- 列排序

		- col-类前缀-push/pull-份数

		- 与列偏移区别：列排序可以使元素重叠，且不会脱标；而列偏移是实实在在位置移动，会影响下一个同行的元素，而且下一个元素的偏移是参照前一个元素，但偏移值导致该行后面份数不够元素所需份数就会脱标，掉到该行下面

- 响应式工具

	- 显示：visible-类前缀

		- 其他前缀时都隐藏

	- 隐藏：hidden-类前缀

		- 其他前缀都显示

