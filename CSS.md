## css

### 选择器优先级及权值

/* 继承性  <  通配符  <  标签选择器  <  类选择器  <  id选择器  <  行内式  <  !important */

- 标签选择器

  ```css
  <style>  
  	div{  
  		color：red；  
  		}  
  </style>
  ```

- 类名选择器

  ```css
  <style>
     .div{  
          color: blue;  
      }  
  </style>
  ```

- id选择器

  ```css
  <style>  
      #div{  
          color: blue;  
      }  
  </style>
  ```

- 通配符选择器

  ```css
  <style> 
  	*{  
          color: blue;  
      }  
  </style>  
  ```

  注：性能不好---性能浪费  

  ```
  并集选择器可以顶替通配符
  ```

- 后代选择器

  ```css
  <style>   
      .father .son.sun{  
          color: blue; 
      }  
  </style>  
  ```

  /*  

  选择器名之间用空格隔开  

  最终效果作用在最后一个元素  

  中间辈分可以省略3-5层级*/

- 子代选择器

  

  ```
  .father>.sun {  
         color: red;  
      }  
    
      /* 子代选择器中间的辈分不能省略,例如你有十八层级就得写十八个选择器名 */  
  ```

  /* 选择器名之间用>隔开 */  

  ```
      /* 后面的元素是前面的子代 */  
    
      /* 最终效果作用在最后一个元素身上 */
  ```

- 交集选择器

  ```css
  <style>      
      /* 交集选择器 */  
    
      /* 选择器名之间没有任何链接符号-----后代用空格,子代用> */  
    
      .father.son.sun {  
    
          /* 找到一个标签,这个标签身上拥有三个类名:  
    
          father son sun才可以被我控制到 */  
    
          /* 缺一不可 */  
    
          /* 多多益善 */  
    
          color: red;  
    
      }  
    
      p.father.son.sun {  
    
          /* 找到一个p标签,这个p标签拥有三个类名:   
    
          father son sun才可以被控制 */  
    
          color: blue;  
    
      }  
    
  </style>  
  ```

  ```html
  <div class="father son sun">  
      控制的是我,你说气不气 红色  
  </div>
  ```

- 并集选择器

  /* 并集选择器就是用来替代通配符 */  

  ```css
      /* 选择器名用逗号隔开,一个条件单独一行---代码规范 */  
      div,  
      span,  
      del,  
      em,  
      .nav,  
      #first{  
          color: gold;  
      }
  ```

### 文本样式

- font：weight style size family

  字体大小必须在字体前

- 水平居中：text-align：center/left/right

- 垂直居中：line-height：容器高度

- 文本修饰属性：text-decoration

  text-decoration：none  

  /*清除 a标签的下划线*/  

  underline/ overline / line-through

- 首行缩进：text-indent：px / % / em

- 字体图标可以去阿里妈妈上下载，导入工程

### 盒子模型

- 边框border

  border-color: blue;  

  ```
          /* 边框颜色 */  
    
          border-width: 1px;  
    
          /* 边框宽度 */  
    
          border-style: none;  
    
          /* 边框的样式----最重要的属性----默认值none */  
    
          border-style: solid;  
    
          /* 实线---最常用的边框样式 */  
    
          border-style: double;  
    
          /* 双实线 */  
    
          border-style: dashed;  
    
          /* 虚线 */  
    
          border-style: dotted;  
    
          /* 点线 */
  ```

  - border-width：px
  - border-color：颜色
  - boder-style：none/solid/double/dashed/dotted
  - 连写：border : border-width border-style  border-color 

- 内边距：padding

- 外边距：margin

  水平margin可以相加，竖直maigin不可以相加

  - 包含塌陷

    1、存在父子关系的盒子，给子元素加margin-top，可能会把父元素带跑；  

    原因：margin溢出到外部  

    解决：设顶部边框 、或 顶部padding  

    建议使用：overflow：hidden；  

    //BFC机制------块级格式化上下文  

    //让内部布局不影响外部---一层隐形屏障

  - 垂直塌陷

  - margin的百分比只会参照父元素的宽度，所以竖直方向的margin不会根据父元素的高度改变而改变

### 背景与列表

- 背景

  - background-color：transparent（透明）|color_name|十六进制|rgb|inherit（继承父元素）

    全局透明使用属性：opacity：0~1值  
    注包括内容；  
    其他：只透明背景；  
    /* background-color: rgba(255, 0, 0, .3); */  
                /* a: 控制颜色的半透明程度: 0-1 */  
                /* 1:代表完全不透明 */  
                /* 0:代表完全透明 */  
                /* background-color: green;  
                opacity: .1; */  
                /* 控制背景与内容的透明程度:0-1 */  
                background-color: transparent;  
                /* transparent:完全透明 */

  - background-image：url（地址）

    背景图片必须设置宽高

  - background-repeat：repeat | no-repeat |repeat-x|repeat-y

  - background-position：x% y% |xpos ypos |top/left/bottom/right/center  top/left/bottom/right/center （俩个参数，只写一个，第二个默认center）

  - background-attachment：scroll |fixed 

  - 简写：background：无序

- 列表

  - list-style-type：disc| circle| square |none |decimal |lower/upper-roman/alpha
  - list-style-image：url（地址）
  - list-style-position：outside |inside 
  - 简写：list-style：type image  position

### float浮动

- 浮动语法float：none |left |right

- 清除浮动:clear：none|left |right |both

- 防止高度塌陷，清除浮动

  高度法：直接给定高度不合适动态盒子,可能会造成溢出。  

  overflow：hidden；//不建议使用，不够稳定，处理溢出  

  额外标签法:在子元素最后添加一个标签，  

  再给标签添加clear:both属性//不建议用  

  双伪元素：  

  .clearfix:before,.clearfix:after {   

    content:"";  

    display:table;   

  }  

  .clearfix:after {  

   clear:both;  

  }  

  .clearfix {  

    *zoom:1;  

  }  

  或者css3的：after伪元素：类名：after{  

  content：‘.’;height：0；visibility：hidden；display：block；clear：both；  

  }  

  在父类容器中使用；zoom：1；/*触发haslayout兼容IE6、7

- 脱标

  脱离标准流，不占标准流位置  

  上升到浮动流

### 定位position

- static自然定位
- relative相对定位
  - 保留原来位置
  - top/right/bottom/left/z-index（层叠顺序）
  - 相对自己原来位置
  - 后代可以对其进行绝对定位
- absolute绝对定位
  - 不保留原来位置
  - 相对与最近的祖先元素
- fixed固定定位
  - 相对与视口
- sticky磁贴定位
  - 相当与relative+fixed，制造吸附效果
  - [浏览器兼容性问题：查询www.caniuse.com](http://www.caniuse.com)

### 网页布局基础

- 行布局

- 列布局

- 混合布局

- 圣杯布局

- 双飞翼布局

- 弹性布局（flex）

  - 容器属性

    - 父盒子：display:flex;  //设置为弹性盒子

    - 主轴方向：flex-direction

      flex-direction: row;  
      默认水平从左往右排布(类似左浮动)  
      flex-direction: row-reverse;  
      水平从右到左排布(类似右浮动)  
      flex-direction: column;  
      垂直从上到下排布  
      flex-direction: column-reverse;  
      垂直从下到上排布  
      注意：当主轴方向调整后，侧轴的方向也会随之修改，记住，两轴相互垂直。

    - 主轴对齐方式：justify-content

      justify-content: flex-start;  
      默认从主轴开始位置排布；  
      justify-content: center;  
      居中显示；  
      justify-content: flex-end;  
      靠主轴结束位置排布；  
      justify-content: space-between;  
      盒子平均分布，例如左中右排布；  
      justify-content: space-around;  
      盒子左右的距离平分；  
      justify-content: space-evenly;  
      盒子将剩余空间等分

    - 侧轴对齐方式：align-items

      align-items: stretch; 
      默认子盒子没有高度的情况，那么拉伸至于父盒子同高； 
      align-items: flex-start; 
      从侧轴开始位置排布，默认顶部； 
      align-items: flex-end; 
      从侧轴结束位置排布，默认底部； 
      align-items: center; 
      垂直居中排布；

    - 子元素是否换行：flex-wrap

      flex-wrap: nowrap; 
      默认子元素强制一行显示； 
      flex-wrap: wrap; 
      父元素宽度不够时换行；

    - 复合属性：flex-flow：主轴方向 是否换行   //一般不用

    - 多行显示后对齐方式：align-content

      align-content: stretch; 
      子盒子没有高度的时候，默认拉伸填满 
      align-content: flex-start; 
      靠顶部排布 
      align-content: flex-end; 
      靠底部排布 
      align-content: center; 
      居中显示 
      align-content: space-between; 
      平均分布，例如上下，上中下； 
      align-content: space-around; 
      行间距平分；

  - 项目属性

    - flex: n / n%  //把主轴剩余空间按份数或百分比分开

    - align-self：flex-end/flex-start/center/stretch   //单独控制自己侧轴对齐方式

      align-self默认值为 auto，表示继承父元素的 align-items 属性。  

      但如果父级没有设置align-items，align-self的默认值为 auto就为strecth；

    - order: number    //排列优先级，number越小越前

- rem布局

  - 1rem=HTML的font-size大小

  - 媒体查询

    @media mediatype and|not|only (media feature) {  

    ```
    CSS-Code;  
    ```

    }  

    mediatype：all（所有设备）/print（用于打印机与预览）/screen（移动设备）  

    media feature：对于屏幕 screen，屏幕的宽度就是一个特性；

- less

  Less（Leaner Style Sheets 的缩写）是一门 CSS 扩展语言，它扩展了CSS的动态特性。 CSS 预处理器。  
  常见的CSS预处理器：Sass、Less、Stylus 。

  - 命名规则
    - 必须有@为前缀  
    - 不能包含特殊字符~=+、不能以数字开头  
    - 大小写敏感区分；

- 响应式布局（bootstrap）

  - 栅格系统

    在各个档位下，控制子元素布局不同；将版心宽度均分为12份

    - 类前缀

      - 超小屏（xs : extra small）：手机；   
      - 小屏（sm : small） ：平板；   
      - 中屏（md: medium）：桌面；  
      - 大屏（lg: large）：大桌面；

    - 基本使用

      - col-类前缀-份数

    - 特点

      - 单一类前缀：各个档位下的类前缀，为包括当前且向上生效；例如：.col-md-6为中屏和以上占有6份；  
      - 多个类前缀：分别按照各个档位列划分生效；  
      - 每个子项：默认左右15px的padding；  
      - 行（.row） 可以去除父容器左右15px的padding值：.row的左右margin为-15px；如果是在子元素中使用，高度自动与父级一样，内部可以继续列划分12份

    - 列嵌套

      <!-- 直接嵌套 -->  

      ```html
      <div class="col-sm-4">  
      <div class="col-sm-6">小列</div>  
        
      <div class="col-sm-6">小列</div>  
      </div>    
      ```

      <!-- 使用row嵌套 -->  

      ```html
      <div class="col-sm-4">  
      	<!-- 加1个行 row 这样可以取消父元素的padding值 而且高度自动和父级一样高； -->  
      	<div class="row">  
           <div class="col-sm-6">小列</div>  
           <div class="col-sm-6">小列</div>  
      	</div>  
      </div>
      ```

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

