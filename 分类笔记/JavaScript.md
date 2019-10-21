## Javascript基础

### js语法

- 数据类型

  7种  

  简单的数据类型：undefined 、null、boolean、string 、 number   symbol(ES6)  

  复杂：object  

  null == undefined  //true  

  typeof (null)          //object      这是js创建之初的错误，背后沿用下来，不存在的对象占位符  

  简单类型数据存储在内存的栈空间中，复杂类型的数据存储在内存的堆空间中，而其堆空间的地址是存放在栈空间；  

  所以在进行复杂数据类型的复制时，只将在栈空间开辟的堆地址数据存放在新开辟的栈空间中，一改复杂类型数据，其他的都会随之改变。

- 检测变量类型：typeof（变量）/typeof 变量

  返回类型：  

  undefined 、null、boolean、string 、 number  、object、function

- number：表示整数和浮点数

- NaN 	面试可能会问

  NaN：即非数值（not  a number） 是个特殊的数值,属于number型  

  注：任何与NaN操作都会返回NaN  

  ```
  NaN与任何值都不相等，包括NaN本身
  ```

- 检测数值n是否是非数值：isNaN（n）

  返回类型：Boolean型  

  注：对接收的数值先尝试转换为数值，再检测是否为非数值

- 把非数值转化为数值：number（）/ parseInt（）/parseFloat（）

  number（）可以应用任何数据类型  

  parseInt（）和parseFloat（）则专门用于把字符串转成数值,其他都为NaN  

  如果字符串非“数字”，则返回类型为NaN  

  parseInt():必须数值开头，否则为NaN，但true，  

  parseFloat：必须数值开头字符串，否则任何类型都为NaN，第二个小数点失效

- 转化为字符串：element.toString（）/ String(element)

- 转化为Boolean型：Boolean（element）

  1、除0之外的数字，转为Boolean类型都为true  

  2、除“”之外的字符，转为Boolean类型都为true，包括空格  

  3、null和underfined转为Boolean类型都为false

- 操作符种类5种

  算数操作符：+-*/% ++  -- (当字符串遇到非+，就会隐式转换)  

  赋值操作符：= 、+=、-=、%=、*=、/=  

  比较操作符：>、<、>=、<=、==、===、！=、！==  

  ```
  返回值为Boolean型  
  ```

  三元操作符：条件？执行代码1：执行代码2  

  逻辑操作符：&&、||、！  

  注：&& 当有一个操作数为null、NaN、undefined返回值就是null、NaN、undefined  

  || 当判断到最后操作数为null、NaN、undefined返回值就是null、NaN、undefined  

  理解：会返回使等式成立的值  

  1. 第一优先级： [] . ()  
  2. 第二优先级： ++ -- !  
  3. 第三优先级： *  /  %  
  4. 第四优先级： +  -  
  5. 第五优先级： >   >=   <   <=  
  6. 第六优先级： ==   !=    ===    !==    
  7. 第七优先级： &&  
  8. 第八优先级： ||   
  9. 第九优先级： = += -= *= /= %=

### js流程控制语句

- if语句

  if（ 条件）{  

  ```js
  执行语句  
  ```

  }else{  

  ```
  执行语句  
  ```

  }

  - 弹出警告框：alert（“提示信息”）

  - 弹出输入框：prompt（ “提示信息”，"输入信息"）

    点击确认，输入内容  

    点击取消，返回null

  - 输入框：confirm（"提示信息"）

  - 获取字符串长度：string.length

- switch

  var week=new Date().getDay();  

  ```js
    switch(week){  
  
       case 0:weekday="天";break;  
    
       case 1:weekday="一";break;  
    
       case 2:weekday="二";break;  
    
       case 3:weekday="三";break;  
    
       case 4:weekday="四";break;  
    
       case 5:weekday="五";break;  
    
       case 6:weekday="六";break;  
    
       default:;  
    
    }  
    
    document.write("今天星期"+weekday);
  ```

- 循环：while/for

- break/continue

- forEach：遍历数组

  // forEach方法需要一个参数是一个函数，这个函数也接收3个参数，  

  // item是数组中的每个元素，index是item的索引,arr表示当前数组；  

  // 对本数组操作，没有返回值；  

  arrayObject.forEach(function(item,index,arr){  

    console.log(item,index);  

  });

### js函数

function  函数名(参数、参数.....){  

```
执行代码  
```

}

- 可以看成一个函数的参数数组:arguments

  ```js
  function banfa(ban){  
       console.log(arguments.length); //1  
    
       console.log(arguments[arguments.length-1]);//ban的值  
    
       console.log(ban);//ban的值  
    }  
  ```

  注：`arguments`管理函数传进的参数，类似数组的东西

### js内置对象

- 数组：new Array()

- 数组对象方法

  - arrayObject.push(newele1,newele2....)

    把参数顺序添加到arrayobject尾部：arrayobject.push(newele1,newele2....)  

    返回值：添加后数组

  - arrayObject.unshift(newele1,newele2....)

    把参数顺序添加到arrayobject开头：arrayobject.unshift(newele1,newele2....)  

    返回值：添加后数组

  - arrayObject.pop()

    删除arrayobject末尾一个元素：arrayobject.pop()  

    返回值：被删除的元素

  - arrayObject.shift()

    删除arrayobject开头一个元素：arrayobject.pop()  

    返回值：被删除的元素

  - arrayObject.join(“separator”)

    把数组放入一个字符串  

    返回值：字符串  

    注：separator是指数组元素转字符串后之间的分割符，默认为 逗号 ，

  - arrayObject.reverse()

    将数组反序

  - arrayObject.sort()

    数组排序，按首字符从小到大   

    要想按数字大小排序，可以在括号里加一个函数，进行正反排序；  

    正：myarray.sort(function (a,b){return a-b});  

    反：myarray.sort(function (a,b){return b-a});  

    注：因为sort是按String类型进行排序，所以需要加入函数进行

  - arrayObject.concat(array，array....array)

    连接两个或多个数组

  - arrayObject.slice(start，end)

    从已有的数组返回选定的元素  

    start（必须）如果是负数，则从尾部开始计算  

    end（可选）如果不写，默认为数组长度  

    参数为负数确定的位置是等于加上数组长度的值

  - 强大的方法：arrayObject.splice( index，count)

    //删除  

    index 为起始位置下标  

    count 为从起始下标删除的个数  

    返回值为删除项数组  

    //插入  

    arrayObject.splice( index，0，itme1，item2，。。。)  

    index 为插入位置  

    item 插入元素  

    返回值为空  

    //替换  

    arrayObject.splice( index，count，itme1，item2，。。。)  

    index 为开始替换位置  

    count 为替换个数，如果为零等同插入  

    item 替换元素  

    返回值为删除项数组

  - arrayObject.indexOf(searchvalue，starIndex)

    从数组开头开始查找  
    searchvalue：必需，查找的项；  
    startIndex：可选，起点位置索引，默认为0  
    返回值：查找项的下标，没找到返回-1  
    查找是全等，否则不相等

  - arrayObject.lastIndexOf(searchvalue，starIndex)

    从数组末尾向前查找  

    searchvalue：必需，查找的项；  

    startIndex：可选，起点位置索引，默认为数组长度-1  

    返回值：查找项的下标，没找到返回-1  

    查找是全等，否则不相等

  - arrayObject.filter(function(item,index,arr){返回条件})

    filter 筛选出数组中满足条件的数组，返回是一个新的数组；  
    // 数组的filter方法用于将数组中满足条件的元素筛选出来  
    // 筛选出数组中 小于 2000 的数据  
    var arr_1 = [1500,1800,2200,300,2600,800];  
    var res = arr_1.filter(function(item,index,arr){  
      return item < 2000;  
    });  
    // fitler方法的的参数要求是一个函数，这个函数接收2个参数：item是数组中的每个元素，index是item对应的索引,arr代表当前的数组

  - arrayObject.findIndex(function(){返回条件})

    返回第一个满足条件的下标  
    var arr = [10, 20, 30];  
    var res1 = arr.findIndex(function (item) {  
      return item >= 20;  
    });  
    // 返回 满足条件的第一个元素的的索引  
    find //则为值

  - arrayObject.forEach(function(){})   //遍历

  - arrayObj.reduce(function(){})  //迭代累加，回调函数与sort的回调函数使用差不多

  - 返回一个迭代器：arrObj.entries()/.keys()/value()

    entries  ：  
    返回值.next();      //  value:键值对   done：false/true  
    keys:  
    返回值.next();      //  value:数组索引   done：false/true  
    values:  
    返回值.next();      //  value:数组值   done：false/true  
    注释：done表示是否没有下一个迭代器，true表示没有

- 字符串对象方法

  原则：字符串特别，新组成的字符串，会放入a在内存上的空间，栈上面的空间。  

  但是 原来的字符串“abc”，不会被覆盖掉；处于游离状态  

  所以尽量避免大量使用字符串的拼接；这算性能优化的一点

  - stringObject.charAt(index)

    返回index位置的字符

  - stringObject.charCodeAt(index)

    返回index位置的字符的编码

  - stringObject.search("searchstring")

  - stringObject.indexOf(“searchstring”)

    返回searchstring该字串的位置，未找到-1

  - stringObject.lastIndexOf(“searchstring”)

  - stringObject.slice(start，end)

  - stringObject.substring(start，end)

    与slice功能一样  

    唯一不同点：当索引值为负数时，直接等于0，会自动将两个参数中较小的参数作为起始位置  

      

    而slice会将其加上字符长度使其变为正值

  - stringObject.substr(start，len)

  - stringObject.split(“separator”)

    将字符串转化为数组，按字符串中separaotr进行分割转化，与数组join方法相反。

  - stringObject.replace(“被替换字符串/正则表达式”，“替换字符串”)

    不更改原对象，返回字符串

  - stringObject.toUpperCase()

    把字符串转化为大写

  - stringObject.toLowerCase()

    把字符串转化为小写

  - stringObject.trim() //去掉前后空格

  - stringObject.match(正则表达式)

  - srtingObj.include("子串",第几个开始匹配)  //存在返回true，反之false

  - .startWith（"字符串"） //判断字符串是否以字符串开始

  - .endsWith（"字符串"） //判断字符串是否以字符串结尾

- Math对象方法

  Math.min(number，number，number，number,......)  

  如果number中有一个不是number类型，返回值为NaN

  - Math.min(num,num,...)

  - Math.max(num,num,...)

  - Math.ceil(num)

    向上取整，大于本身的最小整数

  - Math.floor(num)

    向下取整，小于本身的最大整数

  - Math.round(num)

    四舍五入取整

  - Math.abs(num)

    返回num的绝对值

  - Math.random

    生成0~1之间的随机浮点数

- date对象方法

  var weeks=["日","一","二","三","四","五","六"],  

  ```
       today = new Date(),  
    
      year= today.getFullYear(),  
    
          month=today.getMonth()+1,  
    
          date=today.getDate(),  
    
          week= today.getDay(),  
    
          hours=today.getHours(),  
    
          minutes=today.getMinutes(),  
    
          seconds=today.getSeconds(),  
    
          time =today.getTime(),  
    
          times=year+'年'+month+'月'+date+'日'+hours+'时'+minutes+'分'+seconds+'秒'+"星期"+weeks[week];  
    
      console.log(time);//从1970年1月1号00：00：00到现在毫秒数  
    
      console.log(times);
  ```

  - 获取时间方法

    - deteobject.getFullYear()

    - deteobject.getMonth()

      0~11  

      得到月份需要加一

    - deteobject.getHours()

    - deteobject.getDate()

    - deteobject.getMinutes()

    - deteobject.getSeconds()

    - deteobject.getDay()

      返回值：0-6   

      星期

    - 时间戳

      - deteobject.getTime()

        返回日期毫秒数

      - Date.now()

  - 设置时间方法

    - 将上述获取时间方法中get改为set

### 错误调试与处理

- 运行时错误

  ReferenceError变量引用错误  

  typeError  调用类型错误  

  RangeError 递归深度太大

- 语法错误

- 逻辑错误

  开发者工具查看  

  debugger；  

  断点于单步调试

- try catch finally

  可以使用   

  try{//捕获异常  

  ```
  	throw new Error（）；  
    
  //要注意的是，throw 抛出的只能够是可抛出类Throwable 或者其子类的实例对象。  
  ```

  //抛出后被最近的try捕获  

  }catch（e）{  

  //抛出的异常会赋值给变量 e  

  //处理try捕获的异常，只有捕获到异常才会进入  

  } finally{  

  //做一些清理工作  

  //finally块一定会执行  

  }  

  例：

  ```js
  function getRectArea(width, height) {  
  
    if (isNaN(width) || isNaN(height)) {  
  throw "Parameter is not a number!";  
    }  
  
  }  
  
  try {  
  
    getRectArea(3, 'A');  
  
  }  
  
  catch(e) {  
  
    console.log(e);  
  
    // expected output: "Parameter is not a number!"  
  
  }
  ```

  

### DOM

- 操作

  - document.write()

  - 创建节点

    - create创建节点

      ```js
      (function() {  
         if (!   
        
          /*@cc_on!@*/  
        
          0) return;  
        
          var e = "abbr, article, aside, audio, canvas, datalist, details, dialog, eventsource, figure, footer, header, hgroup, mark, menu, meter, nav, output, progress, section, time, video".split(', ');  
        
          var i = e.length;  
        
          while (i--){  
        
            document.createElement(e[i]);  
        
          }  
        
        })();  
      ```

      兼容低版本IE，会解析第三行内容

      - 标签：document.createElement(“标签名”)
      - 文本：document.createTextNode(“文本”)
      - 注释：document.createComment(“ 文本”)
      - 片段：document.createDocumentFragment()

    - 高效创建节点

      - innerHTML

        用来设置或获取当前标签的起始和结束里面的内容  

        ```js
        myReady(function(){  
            var content = document.getElementById("content");  
          
            var str = "<p>This is a <strong>paragraph</strong> with a list following it.</p>"  
          
                        + "<ul>"  
          
                        + "<li>Item 1</li>"  
          
                        + "<li>Item 2</li>"  
          
                        + "<li>Item 3</li>"  
          
                        + "</ul>";  
          
            content.innerHTML = str;  
          
            alert(content.innerHTML);  
          
          });  
        ```

        当是插入脚本时：var str = "<input type=\"hidden\"><script defer>alert('hi');<\/script>";  

        否则不执行

      - outerHTML

        用来设置或获取当前标签的起始和结束里面的内容包括自己本身

      - innerText

        火狐浏览器可能不兼容，所以需要textContent来进行设置；  

        ```js
        var content = document.getElementById("content");  
            function getInnerText(element){  
          
              return  (typeof element.textContent == "string") ? element.textContent : element.innerText;  
          
            }  
          
            function setInnerText(element, text){  
          
              if (typeof element.textContent == "string"){  
          
                element.textContent = text;  
          
              } else {  
          
                element.innerText = text;  
              }  
            }
        ```

      - outerText

        不建议用，本身标签会被替代

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

        var box = document.getElementById("box");  
              var nodes = box.childNodes;//获得类数组对象  
              function getArray(nodeList){  
                try {  
                  return Array.prototype.slice.call(nodeList);  
                } catch (error) {//兼容低版本  
                  var arr =new Array();  
                for(var i =0 ; i <nodeList.length;i++){  
                  arr.push(nodeList[i]);  
                }  
                return arr;  
                }  
              }  
              var newnodelist = getArray(nodes);  
              newnodelist.push("qwqwqwqw")  
              console.log(newnodelist);

      - HTMLCollection

        var scripts = document.scripts;  
                var links = document.links;  
                var cells = document.getElementById("tr").cells;  
                var imgs = document.images;  
                var forms = document.forms;  
                var options = document.getElementById("select").options;  
                var ps = document.getElementsByTagName("p");  
        //比nodeList多一个下面方法  
        console.log(cells.namedItem('td'));//只返回一个值，id > class

      - NamedNodeMap

        返回该节点的所有属性的集合  
        var box = document.getElementById("box");  
                var attrs = box.attributes;  
                console.log(attrs);//三个属性  
        	console.log(attrs.length);//3  
                console.log(attrs[0]);//根据attrs排序  
                console.log(attrs.item(1));  

        <ul id="box" data-url="index.html" node-action="submit">  
              <li>节点一</li>  
              <li>节点二</li>  
              <li>节点三</li>  
            </ul>

      - 具有动态性

        实时监测document

  - 获取节点

    - getElementById()

      解决ById的bug：  

      ```js
         function(){  
         var getElementById = function(id) {  
        
            var el = document.getElementById(id);  
        
            if(!+"\v1") {//IE浏览器并未转义,得v1；而其他浏览器转义相当于空格1  
        
              if(el && el.id === id) {  
        
                return el;  
        
              } else {  
        
                var els = document.all[id],  
        
                    n = els.length;//.all方法只有IE浏览器有效  
        
                for (var i = 0; i < n; i++) {  
        
                  if (els[i].id === id) {  
        
                    return els[i];  
        
                  }  
        
                }  
        
              }  
        
            }  
        
            return el;  
        
          };
      ```

    - getElementsByName（）

    - getElementsByClassName()

      兼容性：  

      

      ```js
      var getElementsByClassName = function(opts) {  
      var searchClass = opts.searchClass; // 存储要查找的类名  
        
      var node = opts.node || document;  // 存储要出查找的范围  
        
      var tag = opts.tag || '*'; // 存储一定范围内要查找的标签  
        
      var result = [];  
        
      	// 判断浏览器支不支持getElementsByClassName方法  
        
      if (document.getElementsByClassName) { // 如果浏览器支持  
        
      	var nodes = node.getElementsByClassName(searchClass);  
        
      	if (tag !== "*") {  
        
      		for (var i = 0; node = nodes[i++];) {  
        
      			if (node.tagName === tag.toUpperCase()) {  
        
      				result.push(node);  
        
      			}  
        
      		}  
        
      	} else {   
        
      		result = nodes;  
        
      	}  
        
      	return result;  
        
      } else { // 使用IE8以下的浏览器能够支持该属性  
        
      	var els = node.getElementsByTagName(tag);  
        
      	var elsLen = els.length;  
        
      	var i, j;  
        
      	var pattern = new RegExp("(^|\\s)" + searchClass + "(\\s|$)");  
        
      	for (i = 0, j = 0; i < elsLen; i++) {  
        
      		if (pattern.test(els[i].className)) { // 检测正则表达式  
        
      			result[j] = els[i];  
        
      			j++;  
        
      		}  
        
      	}  
        
      	return result;  
        
      }  
      }
      ```

      

    - getElementsByTagName()

    - 返回css选择器一个元素：querySelector（）

      没有查找到返回为：null  

      如果有违规字符：需要转义  

      例：var input = document.querySelector('.foo\\:bar');

    - 返回css选择器一组元素：querySelectorAll()

      返回的是：StaticNodeList  

      是一个类数组对象  

      与NodeList有所不同，不具有动态性  

      没有查找到返回为(空数组)：[]

  - 操作节点

    - 为节点添加子节点：Node.appendChild（）

    - 在指定已有的节点之前插入新的子节点：Node.insertBefore（新节点，旧节点）

    - 节点添加：node.insertAdjacentHTML(位置，节点)

      element.insertAdjacentHTML(position, text);  

      position是相对于元素的位置，并且必须是以下字符串之一：  
      'beforebegin'  
      元素自身的前面。  
      'afterbegin'  
      插入元素内部的第一个子节点之前。  
      'beforeend'  
      插入元素内部的最后一个子节点之后。  
      'afterend'  
      元素自身的后面。  
      text是要被解析为HTML或XML,并插入到DOM树中的字符串。

    - 节点替换：Node.replaceChild(newNode,oldNode)

    - 克隆节点：Node.cloneNode(true/false)

      默认：false  

      true深度克隆，包括所有子节点  

      返回的是副本

    - 合并节点中相邻的文本节点：node.normalize()

    - 按照指点位置把文本节点分割两份：Node.splitText(number)

      number指定位置

  - 删除节点

    - 删除节点子节点：Node.removeChild(子节点)

      返回:删除掉的节点

    - 删除节点：node.removeNode（true/false）

      返回：目标节点  

      默认：false只删除本身节点  

      ```
      true删除本身及子元素
      ```

    - removeChild与innerHTMl比较

- 属性

  - property（固有属性/）

    - 直接通过点就可以直接访问

      - 布尔属性

        布尔属性会自动对属性值进行布尔类型装换 可以看成 属性值 =Boolean（“属性值”）

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

        近年来刚出来的属性，有兼容问题  

        获取属性值，例：  

        <... id= 'id'  data-xxx-yyy data-toggle ....>  

        var node = document.getElementById('id');  

        console.log(node.dataset.toggle)  

        console.log(node.dataset.xxxYyy)//需要驼峰形式

        - 以data-开头的私有属性
        - 设置data属性直接：node.dataset.属性名= “值”

  - Attribute（自定义属性）

    可以通过attributes获得节点属性（类数组对象NamedNodeMap），从而获得自定义属性

    - 获取节点所有属性（类数组对象NamedNodeMap）：Node.attributes

    - 获取单个属性值：node.getAttribute("属性")；

    - 设置属性值：node.setAttribute("属性名","属性值")

    - 删除属性:node.removeAttribute("属性名")

    - 获得属性值进行操作:Node.attributes.getNamedItem('属性名').nodeValue / Node.attributes['属性名'].nodeValue

      只有取自定义属性值的时候才用这个方法，在js操作时候还是得选择 node.属性 进行操作  

      //因为通过node.getAttribute('属性')与node.属性 得到的结果是不一样的

    - 删除节点属性：Node.attributes.removeNamedItem('属性名')   / node.removeAttrbute[' 属性名'];

    - 创建属性：var 属性对象 = ducument.createAttribute('属性名')；属性对象 .value = '属性值'

    - 属性加入节点：Node.attributes.setNamedItem(创建的属性对象)

      IE7以及更早版本不支持

- 事件

  - HTML事件

    直接在HTML上进行事件的绑定

    - 页面加载完成时加载脚本：onload

    - 鼠标事件

      域内容改变时：onchange  
      鼠标点击：onclick  
      鼠标滑过：onmouseover/onmouseenter  
      鼠标离开：onmouseout/onmouseleave  
      获得焦点：onfoucs  
      失去焦点：onblur  
      表单确认按钮点击触发：onsubmit （绑定在from标签上）  
      鼠标按下：onmousedown  
      鼠标松开：onmouseup  
      鼠标移动时：onmousemove  
      浏览器大小变化：onresize  
      拖动滚动条触发：onscroll  
      页面右键事件：oncontextmenu

    - 键盘事件

      键盘按下：onkeydown  

      键盘按下：onkeypress（只相应字母与数字ASCII码）  

      键盘松开：onkeyup  

      event.keyCode：返回以上触发的键值的字符代码，或者 键的值  

      event.charCode:   

      (当用户与web页面进行交互时，解释器就会创建响应的event对象以描述事件)  

      例：document.onkeydown = function( event){  

      console.log(event.keyCode);  

      }   

        

      补充ctrl键：ctrlKey:true/false

  - DOM0级事件

    通过dom获取节点，进行事件绑定  

    例：ele .事件  =  执行脚本

### JS事件

- 事件定义监听函数

  - 直接在HTML中定义相关属性

    不建议用：内容未与行为相分离

  - DOM0级事件

    var bt1 = document.getElementById("bt1");  
            bt1.onclick = function (){  
                alert("我想点击");  
            }  
    //只能绑定一个监听函数  
    兼容所有

  - DOM2事件

    event：代表要移除的事件名称  

    function：指定要移除的函数  

    useCapture：可选，布尔值 默认false， 指定事件是在捕获还是在冒泡阶段执行；  

    false：为冒泡	true：为捕获  

    所以IE没有事件捕获

    - 事件绑定：element.addEventLister('event'，function， useCapture)

      element.addEvenLister('click', function (){}, false)  
      //默认false  
      //可以绑定多个事件，事件捕获和事件冒泡  

      addEventListener()的工作原理是将实现EventListener的函数或对象添加到调用它的EventTarget上的指定事件类型的事件侦听器列表中。

    - 事件解绑：element.removeEventListener('event'，function， useCapture)    //需要指定函数名

      useCapture 布尔值，指定移除阶段

    - IE事件流（兼容）

      event前必须加上 on   前缀  

      兼容封装：  

      ```js
      <script>  
        
          var EventUtil =  {  
        
              addHandler: function (element, type, header){  
        
                  if(element.addEventListener){  
        
                      element.addEventListener(type, header,false);  
        
                  }else if( element.attachEvent){  
        
                      element.attachEvent("on"+type, header)  
        
                  }else{  
        
                      element["on"+type] = null;  
        
                  }  
        
              },  
        
              removeHandler: function (element, type, header){  
        
                      if(element.removeEventListener){  
        
                          element.removeEventListener(type, header, false)  
        
                      }else if(element.detachEvent){  
        
                          element.detachEvent("on"+type, header)  
        
                      }else{  
        
                          element["on"+type] = null;  
        
                      }  
        
              }  
        
          }  
      ```

      ```js
          var  btn = document.getElementById("myBtn");  
        
          var fa = function(){  
        
              prompt("点什么点")  
        
          }  
        
          EventUtil.addHandler(btn,"click" , fa );  
        
          EventUtil.removeHandler(btn, "click", fa);
      ```

      - 事件绑定：attachEvent（"on"+'event'，function）
      - 移除事件：element.detachEvent("on'+event'，function)
      - 而外补充：在绑定IE匿名函数中this指定的是window

- 事件周期：解释器会创建一个event对象

  - 第一阶段：事件捕获

    事件对象向DOM树向下传播，  

    IE没有事件捕获，因为IE没有第三个参数

  - 第二阶段：目标触发

    运行事件监听函数

  - 第三阶段：事件冒泡

    事件沿DOM树向上传播，如果父元素上有事件绑定也会被触发 （事件委托）

- event对象

  - event.type//现在的事件类型
  - event.target//点击谁就是谁，事件源对象
  - event.currentTarget//事件绑定谁，就是谁
  - event.preventDefault（）//阻止默认行为
  - event.stopPropagation()//阻止事件冒泡或捕获
  - event.clientY //浏览器顶部底边到鼠标位置的距离
    event.pageY //文档顶部底边到鼠标位置的距离，随页面向下滚动距离变长
    screenY 屏幕顶边到鼠标的距离
  - IE8特有
    - 阻止事件冒泡：evnet.cancelBubble= true
    - 阻止默认行为：event.returnValue =false
    - 同target ：event.scrElement

- 事件类型

  - UI事件

    - load  

      当加载完毕后执行  可以动态加载js文件 css文件 图片

    - unload

    - resize

      当窗口变化触发

  - 焦点事件

    - blur失焦、focus获得焦点

      fousc不支持冒泡

    - focusout 失焦、focusin获得焦点

  - 鼠标事件

    - click 、dbclick

      dbclick双击事件

    - mousedown鼠标按下

    - mouseup鼠标松开

  - 特殊事件

    - DOMNodeRemoved//绑定元素中任意元素被删除就会触发

    - DOMNodeInserted//任意元素被添加就会触发

    - DOMSubtreeModified//元素中任何变化都会触发

    - DOMNodeRemoveFromDocument//从文档移除前触发

    - 重要：DOMContentLoaded    //只要dom树完成后就会触发

      经常面试中会与load比较

    - readystatechange  //兼容性需要注意

      四个阶段：(0~1)尚未初始化  、(1~2) 加载数据、(2~3)可以操作数据，但还没加载完 、(3~4) 对象加载完毕  

      //情绪化 不好控制   

      在ajax 时候用，监听配合readystate状态（0～4），一改变readystatechange就会执行；

    - hashchange //只能给window添加，#后面的值变化触发

      有两个属性：event.oldURL 与 event.newURL

  - 移动端事件

    - 触摸绑定元素屏幕时触发：touchstart
    - 手指绑定元素在屏幕上滑动触发：touchmove
    - 手指离开绑定元素屏幕触发：touchend
    - event具有三个属性：touches触摸点数组、changedTouches引起事件的触摸点数组(检测手指离开时触摸点所有信息)、targetTouches只包含放在元素上的触摸点数组

### BOM事件

- BOM对象

  - window

    - Global对象

      es规定的Global对象  

      全局变量时，用window.变量名/方法名= 值/方法  等价于  var 变量名/方法名 = 值 /方法  

      因为var是绑定在window上，var定义的变量可以用window.变量名访问   

        

      不使用var声明的变量，都是隐式全局变量，这个方式是不推荐的，因为如果不使用var声明，是不会变量提升的

    - js访问浏览器的接口 

    - 方法

      使用方法时，我们经常省略window，所以在很多情况下我们未申明的变量，都会直接绑定在window对象上

      - alert（"text"）

      - prompt（"text"）

        确认：true 取消：false

      - confirm（"text, defaultText“）

        点确认返回：文本值	取消返回：null

      - 打开新窗口：open(pegeURL, name,parameters)

        子窗口路径  

        子窗口句柄  

        窗口参数：设置高、宽、位置。。。。

      - 关闭窗口：close()

      - 超时调用：setTimeout(code,millisec)

        code:要调用的函数或执行的js代码串（建议使用自定义函数或者匿名函数）  

        millisec：等待的毫秒数

      - 清除超时调用：clearTimeout(id_of_settimeout)

        id_of_settimeout:setTimeout()返回的ID值

      - 间歇调用：setInterval(code,millisec)

        code:执行代码或函数 millisec：间隔时间  

        返回值： ID

  - location

    是window对象属性，也是document对象属性

    - 属性

      - 返回页面的URL：location.href

        location.href  等价 window.location.href  

          

        需要：加协议才会更改跳转，否者将直接加到url尾部

      - 返回URL#号后(包括#)字符串：location.hash

        例如页面定位中的锚定位

      - 返回URL中服务器名称与端口号：location.host

      - 返回URL中服务器名称：location.hostname

      - 返回URL中端口：location.post

      - 返回URL中目录：location.pathname

      - 返回协议：location.protocol

      - 返回URL查询字符串(从?开始)：location.search

    - 方法

      - 不生成新的URL,直接更改: location.replace（url）

        导致不可以回退，没有历史记录

      - 重新加载当前页面：location.reload()

        location.reload()；从浏览器缓存中刷新  
        location.reload(true) 从服务器中刷新

  - localStorage

    - 以前：我们在页面上操作一些，一刷新没有了。现在本地储存，刷新还是操作后的样子；  

    - 本地储存：本地指浏览器，储存指浏览器可以储存数据；

    - 方法

      - localStorage.setItem(键，值)；

        // 存储 设在存上一条数据  

        // 后面的值 前面可以放入任何数据类型，保存后为字符串  

        // 注意： 如果存储的是对象之类的复杂类型，需要先把复杂类型转换为JSON格式的字符串，再存进去，因为本地存储只能存储字符串

      - localStorage.getItem(键)   

        // 读取数据  

        // 返回值：就是我们存入的的数据的值（字符串形式）  

          

        如果不存在的数据，则返回null

      - localStorage.removeItem(键)

      - localStorage.clear() ;  全部清空

  - history

    - 方法

      - history.back():回到历史记录的上一步

        相当于使用了history.go(-1)

      - history.forwark():回到历史记录的下一步

        相当于使用了history.go(1)

      - history.go(n)

  - screen

    - 属性
      - screen.availWidth //页面的宽
      - screen.availHeight //页面的高
      - 补充:window.innerWidth/innerHeight  //窗口文档显示区的宽高

  - Navigator

    - 属性

      - userAgent //识别浏览器的类别,判断是移动端还是PC端

        返回一串浏览器信息字符串