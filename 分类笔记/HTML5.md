## HTML5

### 标签变化

- `<article>`  标记定义一篇文章

- `<header >`	头部或某一个区域头部

- `<nav>`	导航链接

- `<section>`	一块区域

- `<aside>`		页面内容部分的侧边栏

- `<hgroup>`	文件中一个区块的相关信息

- `<figure>`	一组媒体内容以及他们的标签

- `<figcaption>`	定义figure标题

- `<footer>`	页面底部

- `<dialog>`	对话框

- 补充：  
  1、header/section/aside/article/footer	不建议嵌套
  2、header/section/footer > aside/article/figure/hgroup/nav > figcaption/div

- 多媒体标签

  - `<video src=“” controls=“” type="">`	视频

  - `<audio src=“” controls=“” type="">`	音频

  - `<source src="" controls="" type="">`	媒体资源

  - `<canvas>	` JavaScript 在网页上绘制图像

    - 获取 context 对象

      - canvasObj.getContext("2d")

        getContext("2d") 对象是内建的 HTML5 对象，拥有多种绘制路径、矩形、圆形、字符以及添加图像的方法。  

        下面的两行代码绘制一个红色的矩形：

    - 方法

      - contextObj.fillStyle //颜色

      - contextObj.fillRect()   //规定了形状、位置和尺寸

        fillRect 方法拥有参数 (0,0,150,75)。  

          

        意思是：在画布上绘制 150x75 的矩形，从左上角开始 (0,0)。

      - cxt.moveTo(100,10);   //起始位置
        cxt.lineTo(150,50);     //绘制到的位置
        cxt.lineTo(10,50)；
        cxt.stroke();    //结束绘制

      - cxt.beginPath();  
        cxt.arc(70,18,15,0,Math.PI*2,true);  //绘制圆
        cxt.closePath();

  - <embed>	定义外部的可交互的内容或插件	如flash

- 状态标签

  - <meter>	显示：气压、气温
  - <progress>	任务过程：安装、加载

- 列表标签

  - `<datalist>`	定义一个下拉列表，配合`option`
  - `<details>`	详细内容，配合`<summary>`

- 注释标签

  - `<ruby>...我<rp>(</rp><rt>wo</rt><rp>)</rp></ruby>`	注释 rp是考虑兼容问题
  - `<mark>`	标记的文本为黄色
  - `<output>`	输出类型  配合表单`oninput`

### 属性变化

- `<input>` 
  时间`type:email/url/tel/number/date/month/time/datetime-local`
  范围`type:rang`	查询`type:search`	颜色`type：color`

- 表单属性`<form>or<input>`
  autocomplete="on / off"	保留上次提交的值
  应用于<input>:
  autofocus=“autofocus”	自动获取焦点	
  multiple="multiple"	输入域中可以输入多个值
  placeholder=“描述”	描述输入域期待值
  required=“required”	提交表单之前判断不能为空

- 链接属性

  - `sizes ` 
    例：`<link rel="icon" href="icon.gif" type="image/gif" sizes="16*16">`

  - `target  `
    默认：_self,_blank

  - 超链接：  
    a:media=“”	表示对设备进行优化
    a:hreflang="zh"	设置语言
    a:rel=“external”	描述引用的超链接 语义化

    <base target="_blank/_self"> 控制所有a链接打开方式 （在head中）

- script

  - defer	内容加载完再执行js

    <script defer=“defer” src="">

  - async	异步执行

    <script async=“async” src="">

- 有序列表ol

  - `start`	起始值 start=“值”
  - `reversed`	倒叙排序 reversed=“reversed”

- `manifest=“cache.manifest”`	离线应用
