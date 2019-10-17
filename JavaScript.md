# JavaScript


## Javascript基础

### js语法

- 数据类型

- 检测变量类型：typeof（变量）/typeof 变量

- number：表示整数和浮点数

- NaN 	面试可能会问

- 检测数值n是否是非数值：isNaN（n）

- 把非数值转化为数值：number（）/ parseInt（）/parseFloat（）

- 转化为字符串：element.toString（）/ String(element)

- 转化为Boolean型：Boolean（element）

- 操作符种类5种

### js流程控制语句

- if语句

	- 弹出警告框：alert（“提示信息”）

	- 弹出输入框：prompt（ “提示信息”，"输入信息"）

	- 输入框：confirm（"提示信息"）

	- 获取字符串长度：string.length

- switch

- 循环：while/for

- break/continue

- forEach：遍历数组

### js函数

- 可以看成一个函数的参数数组:arguments

### js内置对象

- 数组：new Array()

- 数组对象方法

	- arrayObject.push(newele1,newele2....)

	- arrayObject.unshift(newele1,newele2....)

	- arrayObject.pop()

	- arrayObject.shift()

	- arrayObject.join(“separator”)

	- arrayObject.reverse()

	- arrayObject.sort()

	- arrayObject.concat(array，array....array)

	- arrayObject.slice(start，end)

	- 强大的方法：arrayObject.splice( index，count)

	- arrayObject.indexOf(searchvalue，starIndex)

	- arrayObject.lastIndexOf(searchvalue，starIndex)

	- arrayObject.filter(function(item,index,arr){返回条件})

	- arrayObject.findIndex(function(){返回条件})

	- arrayObject.forEach(function(){})   //遍历

	- arrayObj.reduce(function(){})  //迭代累加，回调函数与sort的回调函数使用差不多

	- 返回一个迭代器：arrObj.entries()/.keys()/value()

- 字符串对象方法

	- stringObject.charAt(index)

	- stringObject.charCodeAt(index)

	- stringObject.search("searchstring")

	- stringObject.indexOf(“searchstring”)

	- stringObject.lastIndexOf(“searchstring”)

	- stringObject.slice(start，end)

	- stringObject.substring(start，end)

	- stringObject.substr(start，len)

	- stringObject.split(“separator”)

	- stringObject.replace(“被替换字符串/正则表达式”，“替换字符串”)

	- stringObject.toUpperCase()

	- stringObject.toLowerCase()

	- stringObject.trim() //去掉前后空格

	- stringObject.match(正则表达式)

	- srtingObj.include("子串",第几个开始匹配)  //存在返回true，反之false

	- .startWith（"字符串"） //判断字符串是否以字符串开始

	- .endsWith（"字符串"） //判断字符串是否以字符串结尾

- Math对象方法

	- Math.min(num,num,...)

	- Math.max(num,num,...)

	- Math.ceil(num)

	- Math.floor(num)

	- Math.round(num)

	- Math.abs(num)

	- Math.random

- date对象方法

	- 获取时间方法

		- deteobject.getFullYear()

		- deteobject.getMonth()

		- deteobject.getHours()

		- deteobject.getDate()

		- deteobject.getMinutes()

		- deteobject.getSeconds()

		- deteobject.getDay()

		- 时间戳

			- deteobject.getTime()

			- Date.now()

	- 设置时间方法

		- 将上述获取时间方法中get改为set

### 错误调试与处理

- 运行时错误

- 语法错误

- 逻辑错误

- try catch finally

### DOM

- 操作

	- document.write()

	- 创建节点

		- create创建节点

			- 标签：document.createElement(“标签名”)

			- 文本：document.createTextNode(“文本”)

			- 注释：document.createComment(“ 文本”)

			- 片段：document.createDocumentFragment()

		- 高效创建节点

			- innerHTML

			- outerHTML

			- innerText

			- outerText

	- 查找节点

		- 获得文档根节点：document.documentElement

		- 根据后代节点获得文档节点：Node.ownerDocument == document

		- 第一子节点：Node.firstChild

		- 最后一个子节点：Node.lastChild

		- 第n子节点：Node.childNodes[n]或Node.childNodes.item(n)

		- 子节点数组长度：Node.childNodes.length

		- 判断该节点是否有子节点：Node.hasChildNodes()

		- 父节点：Node.parentNode

		- 下一个兄弟节点：Node.nextSibling

		- 上一个兄弟节点：Node.previousSibling

		- 因为两节点之间有空白节点，以上节点可以去加个Element，这样就不会遍历空节点，例：node.nextElementSibling、(子节点个数，不包括空白节点)childElementCount。(不包括空白节点的子节点数组)Node.children[]

		- 类数组对象

			- nodeList

			- HTMLCollection

			- NamedNodeMap

			- 具有动态性

	- 获取节点

		- getElementById()

		- getElementsByName（）

		- getElementsByClassName()

		- getElementsByTagName()

		- 返回css选择器一个元素：querySelector（）

		- 返回css选择器一组元素：querySelectorAll()

	- 操作节点

		- 为节点添加子节点：Node.appendChild（）

		- 在指定已有的节点之前插入新的子节点：Node.insertBefore（新节点，旧节点）

		- 节点添加：node.insertAdjacentHTML(位置，节点)

		- 节点替换：Node.replaceChild(newNode,oldNode)

		- 克隆节点：Node.cloneNode(true/false)

		- 合并节点中相邻的文本节点：node.normalize()

		- 按照指点位置把文本节点分割两份：Node.splitText(number)

	- 删除节点

		- 删除节点子节点：Node.removeChild(子节点)

		- 删除节点：node.removeNode（true/false）

		- removeChild与innerHTMl比较

- 属性

	- property（固有属性/）

		- 直接通过点就可以直接访问

			- 布尔属性

				- checked

				- selected

				- 多选：multiple

				- 在获取readonly属性时, node.readOnly  O需要大写

				- input 设置 readOnly 与disabled 除了表面显示不同外，最主要是disabled被设置的元素不会提交到服务器

			- 字符串属性

				- id / title / href / src / lang / dir / accesskey / name / value / class

				- class属性 在js 为className属性

					- 节点属性：classList可以简化对类名的操作

						- node.classList.add("类名“)

						- node.classList.remove("类名“)

						- 判断类名是否存在：node.classList.contains("类名“)

						- 判断类名是否存在，存在删除，不存在添加：node.classList.toggle("类名“)

			- data属性

				- 以data-开头的私有属性

				- 设置data属性直接：node.dataset.属性名= “值”

	- Attribute（自定义属性）

		- 获取节点所有属性（类数组对象NamedNodeMap）：Node.attributes

		- 获取单个属性值：node.getAttribute("属性")；

		- 设置属性值：node.setAttribute("属性名","属性值")

		- 删除属性:node.removeAttribute("属性名")

		- 获得属性值进行操作:Node.attributes.getNamedItem('属性名').nodeValue / Node.attributes['属性名'].nodeValue

		- 删除节点属性：Node.attributes.removeNamedItem('属性名')   / node.removeAttrbute[' 属性名'];

		- 创建属性：var 属性对象 = ducument.createAttribute('属性名')；属性对象 .value = '属性值'

		- 属性加入节点：Node.attributes.setNamedItem(创建的属性对象)

- 事件

	- HTML事件

		- 页面加载完成时加载脚本：onload

		- 鼠标事件

		- 键盘事件

	- DOM0级事件

### JS事件

- 事件定义监听函数

	- 直接在HTML中定义相关属性

	- DOM0级事件

	- DOM2事件

		- 事件绑定：element.addEventLister('event'，function， useCapture)

		- 事件解绑：element.removeEventListener('event'，function， useCapture)    //需要指定函数名

		- IE事件流（兼容）

			- 事件绑定：attachEvent（"on"+'event'，function）

			- 移除事件：element.detachEvent("on'+event'，function)

			- 而外补充：在绑定IE匿名函数中this指定的是window

- 事件周期：解释器会创建一个event对象

	- 第一阶段：事件捕获

	- 第二阶段：目标触发

	- 第三阶段：事件冒泡

- event对象

	- event.type//现在的事件类型

	- event.target//点击谁就是谁，事件源对象

	- event.currentTarget//事件绑定谁，就是谁

	- event.preventDefault（）//阻止默认行为

	- event.stopPropagation()//阻止事件冒泡或捕获

	- event.clientY //浏览器顶部底边到鼠标位置的距离

## event.pageY //文档顶部底边到鼠标位置的距离，随页面向下滚动距离变长

## screenY 屏幕顶边到鼠标的距离

### IE8特有

- 阻止事件冒泡：evnet.cancelBubble= true

- 阻止默认行为：event.returnValue =false

- 同target ：event.scrElement

## 事件类型

### UI事件

- load  

- unload

- resize

### 焦点事件

- blur失焦、focus获得焦点

- focusout 失焦、focusin获得焦点

### 鼠标事件

- click 、dbclick

- mousedown鼠标按下

- mouseup鼠标松开

### 特殊事件

- DOMNodeRemoved//绑定元素中任意元素被删除就会触发

- DOMNodeInserted//任意元素被添加就会触发

- DOMSubtreeModified//元素中任何变化都会触发

- DOMNodeRemoveFromDocument//从文档移除前触发

- 重要：DOMContentLoaded    //只要dom树完成后就会触发

- readystatechange  //兼容性需要注意

- hashchange //只能给window添加，#后面的值变化触发

### 移动端事件

- 触摸绑定元素屏幕时触发：touchstart

- 手指绑定元素在屏幕上滑动触发：touchmove

- 手指离开绑定元素屏幕触发：touchend

- event具有三个属性：touches触摸点数组、changedTouches引起事件的触摸点数组(检测手指离开时触摸点所有信息)、targetTouches只包含放在元素上的触摸点数组

## BOM事件

### BOM对象

- window

	- Global对象

	- js访问浏览器的接口 

	- 方法

		- alert（"text"）

		- prompt（"text"）

		- confirm（"text, defaultText“）

		- 打开新窗口：open(pegeURL, name,parameters)

		- 关闭窗口：close()

		- 超时调用：setTimeout(code,millisec)

		- 清除超时调用：clearTimeout(id_of_settimeout)

		- 间歇调用：setInterval(code,millisec)

- location

	- 属性

		- 返回页面的URL：location.href

		- 返回URL#号后(包括#)字符串：location.hash

		- 返回URL中服务器名称与端口号：location.host

		- 返回URL中服务器名称：location.hostname

		- 返回URL中端口：location.post

		- 返回URL中目录：location.pathname

		- 返回协议：location.protocol

		- 返回URL查询字符串(从?开始)：location.search

	- 方法

		- 不生成新的URL,直接更改: location.replace（url）

		- 重新加载当前页面：location.reload()

- localStorage

	- 方法

		- localStorage.setItem(键，值)；

		- localStorage.getItem(键)   

		- localStorage.removeItem(键)

		- localStorage.clear() ;  全部清空

- history

	- 方法

		- history.back():回到历史记录的上一步

		- history.forwark():回到历史记录的下一步

		- history.go(n)

- screen

	- 属性

		- screen.availWidth //页面的宽

		- screen.availHeight //页面的高

		- 补充:window.innerWidth/innerHeight  //窗口文档显示区的宽高

- Navigator

	- 属性

		- userAgent //识别浏览器的类别,判断是移动端还是PC端

