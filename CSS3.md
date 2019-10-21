## CSS3

### 选择器

- 子元素选择器：father >chlid

- 兄弟选择器：+

- 通用兄弟选择器：~	

- 群组选择器：，

- 属性选择器：element[属性]/element[属性=‘’]	/开头element[属性^=‘’]/结尾element[属性$=‘’]/包含element[属性*=‘’]			

- 动态伪类：1、锚点伪类 : :link :visited
  2、行为伪类：:hover :active :fouse

  ：link	设置未被点击  
  ：visited 设置被点击过  
  ：hover 设置鼠标悬停时候  
  ：active 设置点击时

  - 

- UI状态伪类：
  1、 :enabled 可输入 2、：disabled	不可输入 3、checked

- nth选择器：:first-child 父元素首个子元素
  :last-child 父元素最后一个子元素
  :nth-child（n/odd/even）父元素第n个元素	odd下标为奇数 even下标为偶数（注：nth-last-child（n）倒数）
  ：nth-of-type（n）直接第n元素）（nth-last-of-child）
  :first-of-type		last-of-type 直接第一个
  ：only-child	其父元素只有自己唯一个子元素
  ：only-of-type其父元素只需自己类型只有一个元素即可
  ：empty 没有子元素
  :not 否定选择器 

- 伪元素：  
  ：：first-line 文本第一行
  ：：first-letter 文本第一个字
  ：：before   任何元素前
  ：：after 	任何元素后 
  ：：selection 选中变化

  - 注意：伪元素只能用于双标签

### 边框与圆角

- border-radius：px/em/%   
- 盒阴影：box-shadow：水平 竖直 模糊 颜色
- 边界图片：border-image：

### 背景与渐变

- 绘制区域：background-clip:border-box/padding-box/content-box

- 背景图像相对位置：background-origin：border-box/padding-box/content-box

- 背景图片大小：background-size：px/%/cover/contain

  cover最小边拉长到满框，等比例缩放  
  contain最大边拉长到满框，等比例缩放

- 线性渐变：background：linear-gradient

  background：linear-gradient（方向（可用N deg），颜色 0%，颜色 n % 。。。100%）默认从上而下  

  repeat-linear-gradient 重复

- 径向渐变：radial-gradient

  background：radial-gradient(位置，形状，颜色 %，颜色 % .....)  

  位置默认：center	（n% n%）  

  大小形状默认：size	ellipse (椭圆)   

  ```
  				circle  
  ```

  size：closest/farthest-side/conner  

  注：高宽一样也是圆

- 重复径向渐变：repeating-radial-gradient

- 浏览器兼容问题

  例：  

  ```css
  background：-webkit-radial-gradient  
              -moz-radial-gradient  
    
  								-o-radial-gradient  
    
  										radial-gradient  
  ```

  微软  

  火狐  

  opear  

  兼容

### 文本与字体

- 文本阴影：text-shadow

  text-shadow:水平偏移 竖直偏移 模糊距离 颜色

- 文本轮廓：text-outline

  text-outline：宽度值 模糊值 颜色

- 处理自动换行：word-break
  word-wrap(长单词或url)

  word-wrap 属性用来标明是否允许浏览器在单词内进行断句  
    word-wrap: normal|break-word;   
  word-wrap 属性用来标明是否允许浏览器在单词内进行断句  
  normal: 只在允许的断字点换行(浏览器保持默认处理)   
  break-word:在长单词或URL地址内部进行换行，  
  /*内容将在边界内换行。如果需要，单词内部允许断行。*/  

  word-break 属性用来标明怎么样进行单词内的断句  
   word-break: normal|break-all|keep-all;  
  normal：使用浏览器默认的换行规则。   
  break-all:允许在单词内换行 ， 允许任意非CJK(Chinese/Japanese/Korean)文本间的单词断行。  
  keep-all:只能在半角空格或连字符处换行，  
  不允许CJK(Chinese/Japanese/Korean)文本中的单词换行，只能在半角空格或连字符处换行。非CJK文本的行为实际上和normal一致。

- 强制不换行：white-space:normal/nowrap

  white-space 属性设置如何处理元素内的空白   
   white-space: normal|pre|nowrap|pre-wrap|pre-line|inherit;   
  normal默认。空白会被浏览器忽略。   
  pre 空白会被浏览器保留。其行为方式类似 HTML 中的 pre 标签。   
  nowrap文本不会换行，文本会在在同一行上继续，直到遇到 br 标签为止。   
  pre-wrap 保留空白符序列，但是正常地进行换行。   
  pre-line 合并空白符序列，但是保留换行符。   
  inherit 规定应该从父元素继承 white-space 属性的值。

- 最后一行对齐方式：text-align-last

- 文本溢出：text-overflow

- 引入个性字体：@font-face

  

  ```css
  @font-face{//标准模板  
      font-family: 'myFont';  
    
      src: url('myFont.eot');  
    
      src: url('myFont.eot?#iefix') format('embedded-opentype'),  
    
           url('myFont.ttf') format('truetype'),  
    
           url('myFont.woff') format('woff'),  
    
           url('myFont.svg#myFont') format('svg'),  
    
  }  
  ```

  获取特殊字体：www.fontsquirrel.com/tools/webfont-generator

### 转换

- 2D转换：transform

  transform：rotation(n deg)	旋转角度  //改变初始化轴向  

  ```
  translateX（平移水平距离）  
    
  translateY（平移垂直距离）  
    
  translate（水平，垂直）X,Y  
    
  scale（水平缩放，垂直缩放）X,Y  
    
  skew（n deg,n deg）斜切变换 X,Y
  ```

- 3D转换：transform

  transform：rotateX(n deg)	旋转角度  

  ```
  rotateY(n deg)	旋转角度  
    
  rotateZ(n deg)	旋转角度  
    
  rotate3d(%,%,%,n deg)	各轴旋转角度% *n  
    
  translateX（平移水平距离）  
    
  translateY（平移垂直距离）  
    
  translateZ（平移垂直距离）  
    
  translate3d（水平，垂直，Z）X,Y，Z  
    
  scale3d（水平缩放，垂直缩放，Z）X,Y,Z  
  ```

  ​	  

  注：集合表示方法不可以省略参数

- 更改转换元素的位置：transform-origin

  transform-origin：水平点 竖直点

- 矩阵：transform:matrix(%,%,%,%,n,n)

  镜像对称效果：matrix((1-k*k)/(1+k*k),2k/(1+k*k),2k/(1+k*k),(k*k-1)/(1+k*k),0,0)  

  注：k为对称直线斜率

- 3d矩阵：transform：matrix3d(%,%,%,%,%,%,%,%%,%,%,%%,%,%,%)

  transform：matrix3d(sx,%,%,%,%,sy,%,%,%,%,sz,%,%,%,%,1)  

  等同：scale3d（x,y,z）;

- 指定嵌套元素三位空间展现：transform-style

  transform-style：flat(默认)/preserve-3d

- 指定观察者与z=0平面的距离：perspective：none/数值

- 指定透视点的位置：perspective-origin:%,%;

- 元素背面是否可见：backface-visibility:visible/hidden

### 过渡

- transtion

  检索或设置对象参与过度的属性：transtion-property：none|all|property;  
  对象过度时间：transition-duration：时间  
  过度动画类型：transition-timing-function:ease-in-out  
  延时：transition-delay：时间  
  transition：property duration timing-function delay；  
  注意兼容问题

### 动画

- 动画名称：animation-name：keyframename |none

- 动画时间：animation-duration：时间

- 动画过度效果：animation-timing-function

  贝塞尔曲线

  - 补充：steps（n）//n小步

- 动画延迟：animation-delay:时间

  定义动画之外的时间，要是

- 循环次数：animation-iteration-count：n/infinite

  默认为“1”；infinite为无限次数循环

- 在循环中动画是否反方向运动：animation-direction：normal /reverse/alternate/alternate-reverse

- 动画不播放时要应用的元素样式：animation-fill-mode

  语法：  

  animation-fill-mode：none | forwards | backwards | both  

  默认：none  

  设置对象状态为动画结束时的状态：forwards；  

  开始时：backwarkds  

  开始或结束：both

- 指定动画是否运行或暂停：animation-play-state：pause / running

- 复合属性：animation：name duration timing-function delay iteration-count direction fill-mode

- 关键帧 ：@keyframes

  例：  

  

  ```css
  @keyframes animationname {  
  from { transform: rotateX(0deg);   }  
    
  25%   { transform: rotateX(360deg); }  
    
  75%   { transform: rotateX(360deg); }  
    
  to   { transform: rotateX(360deg); }  
  }  
  ```

  

  from代替0%	to代替100%  

  手机端：  

  @-webkit-keyframes

- 提前通知浏览器将要做什么动画，提高性能：will-change：auto /scroll-position / contents / 变化属性，例transform / 可动画特征值，例left

  ```css
  -webkit-will-change: transform;  
  	-moz-will-change: transform;  
    
          will-change: transform;  
  ```

  opera兼容

### 盒子

- 

### box-sizing:border-box   //盒子总宽 = 设置宽度   ，padding、border向内挤

