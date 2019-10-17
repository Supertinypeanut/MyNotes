# CSS3


## CSS3

### 选择器

- 子元素选择器：father >chlid

- 兄弟选择器：+

- 通用兄弟选择器：~	

- 群组选择器：，

- 属性选择器：element[属性]/element[属性=‘’]	/开头element[属性^=‘’]/结尾element[属性$=‘’]/包含element[属性*=‘’]			

- 动态伪类：1、锚点伪类 : :link :visited

## 2、行为伪类：:hover :active :fouse

### UI状态伪类：

## 1、 :enabled 可输入 2、：disabled	不可输入 3、checked

### nth选择器：:first-child 父元素首个子元素

## :last-child 父元素最后一个子元素

## :nth-child（n/odd/even）父元素第n个元素	odd下标为奇数 even下标为偶数（注：nth-last-child（n）倒数）

## ：nth-of-type（n）直接第n元素）（nth-last-of-child）

## :first-of-type		last-of-type 直接第一个

## ：only-child	其父元素只有自己唯一个子元素

## ：only-of-type其父元素只需自己类型只有一个元素即可

## ：empty 没有子元素

## :not 否定选择器 

### 伪元素：

## ：：first-line 文本第一行

## ：：first-letter 文本第一个字

## ：：before   任何元素前

## ：：after 	任何元素后 

## ：：selection 选中变化

### 注意：伪元素只能用于双标签

## 边框与圆角

### border-radius：px/em/%   

### 盒阴影：box-shadow：水平 竖直 模糊 颜色

### 边界图片：border-image：

## 背景与渐变

### 绘制区域：background-clip:border-box/padding-box/content-box

### 背景图像相对位置：background-origin：border-box/padding-box/content-box

### 背景图片大小：background-size：px/%/cover/contain

### 线性渐变：background：linear-gradient

### 径向渐变：radial-gradient

### 重复径向渐变：repeating-radial-gradient

### 浏览器兼容问题

## 文本与字体

### 文本阴影：text-shadow

### 文本轮廓：text-outline

### 处理自动换行：word-break

## word-wrap(长单词或url)

### 强制不换行：white-space:normal/nowrap

### 最后一行对齐方式：text-align-last

### 文本溢出：text-overflow

### 引入个性字体：@font-face

## 转换

### 2D转换：transform

### 3D转换：transform

### 更改转换元素的位置：transform-origin

### 矩阵：transform:matrix(%,%,%,%,n,n)

### 3d矩阵：transform：matrix3d(%,%,%,%,%,%,%,%%,%,%,%%,%,%,%)

### 指定嵌套元素三位空间展现：transform-style

### 指定观察者与z=0平面的距离：perspective：none/数值

### 指定透视点的位置：perspective-origin:%,%;

### 元素背面是否可见：backface-visibility:visible/hidden

## 过渡

### transtion

## 动画

### 动画名称：animation-name：keyframename |none

### 动画时间：animation-duration：时间

### 动画过度效果：animation-timing-function

- 补充：steps（n）//n小步

### 动画延迟：animation-delay:时间

### 循环次数：animation-iteration-count：n/infinite

### 在循环中动画是否反方向运动：animation-direction：normal /reverse/alternate/alternate-reverse

### 动画不播放时要应用的元素样式：animation-fill-mode

### 指定动画是否运行或暂停：animation-play-state：pause / running

### 复合属性：animation：name duration timing-function delay iteration-count direction fill-mode

### 关键帧 ：@keyframes

### 提前通知浏览器将要做什么动画，提高性能：will-change：auto /scroll-position / contents / 变化属性，例transform / 可动画特征值，例left

## 盒子

### box-sizing:border-box   //盒子总宽 = 设置宽度   ，padding、border向内挤

