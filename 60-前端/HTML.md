---

banner: "https://api.dujin.org/bing/1920.php"

cssclass: noyaml,noscroll,myhome

obsidianUIMode: preview

banner_x: 0.49885
banner_y: 0.5
---

#前端 #HTML 

# 前提条件
1. 安装浏览器
2. 安装 [[VSCode]]
3. VSCode 插件推荐：
+ Live Server
+ HTML CSS Support

# 什么是 HTML
HTML 是超文本标记语言（HyperText Markup Language），不是一门编程语言
# HTML 文件结构
![](https://obsidian-picture.oss-cn-qingdao.aliyuncs.com/my-img/HTML1.png)

我们在网页中看到的内容就是 body 里面的内容
head: 一般用于说明页面的一些信息，不直接显示在页面上
meta charset = "utf-8"告知浏览器，现在文档使用的编码
title: 页面的标题
body: 一般页面的内容，直接显示在网页上

# 元素
HTML 元素（Element）

组成：
![](https://obsidian-picture.oss-cn-qingdao.aliyuncs.com/my-img/HTML2.png)
所有 HTML 开始标签和结束标签都是成对出现的，`<xxx>` `</xxx>`
还有属性：
![](https://obsidian-picture.oss-cn-qingdao.aliyuncs.com/my-img/HTML3.png)

[HTML 标签参考手册](https://www.w3school.com.cn/tags/index.asp)

# 标签
成对出现，中间包裹的内容就是显示的内容
有一些天生闭合的标签，如 `<br>`
标签有属性，属性写在开始标签中，多个属性之间要用空格分隔开。
如：`<h1 属性名=“属性值”  属性名=“属性值”></h1>`
==注意：按照惯例，所有 HTML 标签都应该是小写字母。==
# 快速创建标签小技巧
1. 使用 `tab` 键，输入标签名然后按 `tab` 键
2. 使用==Emmet 语法==（VSCode 已内置），使用 `标签名{标签文本内容}+tab键或回车键`
3. 使用 `CTRL` + `/` 补全注释
4. 如需要多个重复内容，使用 `标签名{标签文本内容} * 标签重复次数+tab键或回车键`
5. 如需依次递增添加内容，使用 `标签$ {标题文 $ 本内容} * 标签重复次数+tab键或回车键`
6. 如果需要多个列表，使用 `父标签名>子标签名{子标签文本} * 子标签重复次数+tab键或回车键`
7. 创建 m 行 n 列表格：使用 `table>tr*m>td*n+tab键或回车键`
# 注释
+ 注释标签
`<!--...--> `
在 VSCode 中，快捷键为 `ctrl+/`
# 标题
+ 标题标签
`<h1> </h1>` 
有 h1 到 h6 六级标题
属性：

| 属性 | 属性值 | 描述 |
| ---- | ------ | ---- |
| title     | `文字`        |鼠标放置时，显示提示内容      |

# 段落
+ 段落标签
`<p> </p>`
在网页上直接写空格或者分行是不起效果的，必须通过标签或者 css 样式进行修改
属性：

| 属性 | 属性值 | 描述 |
| ---- | ------ | ---- |
| title     | `文字`        |鼠标放置时，显示提示内容      |

# 空格
+ 添加空格
代码：`&nbsp;`，英文空格。`&emsp;`，中文空格。
# 图片
+ 图片标签
`<img>`
属性：

| 属性 | 属性值   | 描述                                           |
| ---- | -------- | ---------------------------------------------- |
| src  | `图片地址` | 告知图片的网络地址                             |
| alt  | `文字`     | 图片加载失效时，提示自定义语句，它占用页面空间 |
| title     | `文字`         |鼠标放置时，显示提示内容, 它不占用页面空间                                                |

+ 图片格式
1. gif 图片：支持透明、压缩、交错和多图像图片，是一种无损压缩格式，缺点是画质差
2. jpg 或 jpeg 图片：采用高压缩比技术的图片存储格式
3. png 图片：汲取了 gif 和 jpeg 二者的优点，存储形式丰富，利于网络的传输却不失真
4. bmp 图片：常用于网站注册或登录页面中的验证码，bmp 文件通常是不压缩的
5. webp 图片：支持无损压缩和有损压缩，在谷歌浏览器中经常使用
# 列表

+ 无序列表
	`<ul><li> <li></ul>`
	`<ul>` 是父元素
	`<ul>` 标签属性：

	| 属性 | 属性值 | 描述                             |
	| ---- | ------ | -------------------------------- |
	| type | `disc`   | 设置无序列表的项目符号为实心圆点 |
	| type | `circle` | 设置无序列表的项目符号为圆圈     |
	| type |  `none`      | 设置无序列表的项目符号为隐藏符号         |
	|  type    | `square`        |    设置无序列表的项目符号为实心方块                              |
	
+ 有序列表
	`<ol><li> <li></ol>`
	`<ol>` 是父元素
	`<ol>` 标签属性：
	
	| 属性 | 属性值   | 描述           |
	| ---- | -------- | -------------- |
	| type | `A` 或 `a` | 英文字母顺序   |
	| type | `I` 或 `i` | 罗马数字顺序   |
	| type | `1`      | 阿拉伯数字顺序 |
	| start     | `数字`         |  定义开始的数字或字母              |

+ 自定义列表
	`<dl> </dl>` : 定义列表，是父标签
	`<dt> </dt>` : 定义术语，是子标签，与 `<dd> </dd>` 是兄弟标签
	`<dd> </dd>` : 定义描述，是子标签，与 `<dt> </dt>` 是兄弟标签

例：
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>自定义列表</title
  </head>
  <body>
    <dl>
        <dt>
            问：英文不好，能不能学编程
        </dt>
        <dd>答：当然可以</dd>
    </dl>
  </body>
</html>
```
# 链接
+ 链接标签
`<a> </a>`
用于页面之间跳转和页面内部跳转
属性：

| 属性   | 属性值       | 描述                         |
| ------ | ------------ | ---------------------------- |
| href   | `跳转的地址` | 跳转到指定的地址 (外部或内部) |
| target | `_self`      | 链接的页面在当前页面打开               |
| target       | `_blank`              | 链接的页面在空白页面打开                             |

补充：
1. 跳转内部链接（即锚点链接）时使用==id==来跳转。
需要先在跳转目标处的对应标签添加一个 id 属性，并添加属性值（即锚点），然后在链接处使用 `#` 后携带锚点的名字
例：
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>标签内部跳转</title>
    <style>
      #content1 {
        height: 1000px;
        background-color: aqua;
      }
      #content2 {
        height: 1000px;
        background-color: blueviolet;
      }
      #content3 {
        height: 1000px;
        background-color: pink;
      }
    </style>
  </head>
  <body>
    <a href="#content1">第一部分内容</a>
    <a href="#content2">第二部分内容</a>
    <a href="#content3">第三部分内容</a>
    
    <p id="content1">这是第一部分</p>
    <p id="content2">这是第二部分</p>
    <p id="content3">这是第三部分</p>
  </body>
</html>
```
2. 有时你想为网站添加一个 `a` 元素，但还不确定要将它链接到哪里，可以使用 `#` 来创建链接占位符
# 文本修饰常用标签
+ 加粗标签
`<b> </b>` 或 `<strong> </strong>` 标签里面放置待加粗的文本，其中 `strong` 标签语义化更强，表示该文本比较重要
+ 文本倾斜标签
`<i> </i>` 或 `<em> </em>` 标签里面放置倾斜的文本，其中 `em` 标签可以加强语气
+ 删除线标签
`<s> </s>` 或 `<del> <del>` 标签里面放置删除线文本，HTML5 已经不支持 `s` 标签了，建议使用 `del` 标签
+ 下划线标签
`<u> </u>` 标签里面放置待添加下划线的标签
+ 角标标签
`<sup> </sup>` 上角标
`<sub> </sub>` 下角标

> 标签可以嵌套，实现两个或多个效果

# 表格
`<table><tr><td> </td></tr></table>`
`<tr> </tr>` 表示行
`<td> </td>` 表示列
`<th> </th>`，表示表头，能够加粗，语义更明显，

`table标签` 属性：

| 属性        | 属性值 | 描述                           |
| ----------- | ------ | ------------------------------ |
| border      | `数值`   | 显示表格线，数值大小表示粗细   |
| width       | `数值`   | 设置表格的宽                   |
| height      | `数值`   | 设置表格的高                   |
| cellspacing | `数值`   | 设置单元格之间的距离           |
| cellpadding | `数值`   | 设置单元格边框和文本之间的距离 |
| bgcolor     | `颜色`   | 设置背景颜色                   |
| bordercolor            | `颜色`        |设置边框颜色                                |

`tr标签` 属性：

| 属性    | 属性值   | 描述                  |
| ------- | -------- | --------------------- |
| align   | `left`   | 水平对齐方式: 左侧对齐 |
| align   | `center` | 水平对齐方式: 居中对齐 |
| align   | `right`  | 水平对齐方式: 右侧对齐 |
| valign  | `top`    | 垂直对齐方式: 顶部对齐 |
| valign  | `middle` | 垂直对齐方式: 居中对齐 |
| valign  | `bottom` | 垂直对齐方式: 底部对齐 |
| bgcolor | `颜色`   | 设置背景颜色          |
| height        | `数值`          | 设置表格的高                      |

`td标签` 属性：

| 属性    | 属性值   | 描述                  |
| ------- | -------- | --------------------- |
| align   | `left`   | 水平对齐方式: 左侧对齐 |
| align   | `center` | 水平对齐方式: 居中对齐 |
| align   | `right`  | 水平对齐方式: 右侧对齐 |
| valign  | `top`    | 垂直对齐方式: 顶部对齐 |
| valign  | `middle` | 垂直对齐方式: 居中对齐 |
| valign  | `bottom` | 垂直对齐方式: 底部对齐 |
| bgcolor | `颜色`   | 设置背景颜色          |
| height  | `数值`   | 设置表格的高          |
| width        | `数值`         |设置表格的宽                       |

## 单元格合并
在第一个 td 里使用 rowspan 表示跨多少行合并，使用 colspan 表示多少列合并
例：
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>合并单元格实例</title>
  </head>
  <body>
    <table border="1" height="400" width="600" cellspacing="0" cellpadding="0">
        <tr>
            <td colspan="4"></td>
        </tr>
        <tr>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td rowspan="2"></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td></td>
            <td rowspan="3"></td>
            <td></td>
        </tr>
        <tr>
            <td colspan="2"></td>
            <td></td>
        </tr>
        <tr>
            <td></td>
            <td></td>
            <td></td>
        </tr>
    </table>
  </body>
</html>
```

![](https://obsidian-picture.oss-cn-qingdao.aliyuncs.com/my-img/HTML4.png)
## 表格标题
`<caption> </caption>` 标签，里面放置标题
习惯在 tr 标签之前，在 table 与第一个 tr 之间。
## 表格分组
分为头部、主体、脚部
分别为：`<thead> </thead>`、`<tbody> </tbody>`、`<tfoot> </tfoot>`

# 块级元素和内联元素
HTML 元素对应显示值，有 block（块）和 inline（内联，也称行内元素）两种。
+ 容器标签
`<div> </div>` 可以在里面放内容，是典型的块级元素
+ 范围标签
`<span> </span>` 典型的内联元素，里面不可以嵌套块级元素
## 块级元素
+ 容器标签：`div`
+ 标题标签：`h1 h2 h3 h4 h5 h6`
+ 段落标签：`p`
+ 列表标签：`ul ol li dl dt dd`
+ 表格：`table tr th td thead tbody tfoot`
+ 水平分割线：`hr`
+ 预格式化：`pre`
+ 图像映射：`map`
+ 表单：`form`
## 行内元素
+ 图片标签：`img`
+ 超链接：`a`
+ 文本修饰元素：`sub sup del b strong i em`
+ 折行标签：`br`
+ 容器元素：`span`
+ 输入框：`input`
+ 表格标签：`label`
+ 矢量图：`SVG`
+ 内联框架：`iframe`
# 表单
+ 表单标签
`<form> </form>` 其中可以添加表单控件
## 文本框和密码框
需要嵌入 `<input>`
属性：

| 属性 | 属性值 | 描述 |
| ---- | ------ | ---- |
| type | `text` | 文本框     |
| type     | `password`       | 密码框     |

## 多行文本框
允许用户输入多行
使用 `<textarea> </textarea>`
属性：

| 属性 | 属性值 | 描述 |
| ---- | ------ | ---- |
| cols | `数字`       |指定一个文本区域的可见宽度即列数      |
| rows     |  `数字`      | 指定一个文本区域中的可见行数     |

## 单选和多选
需要嵌入 `<input>`
属性：

| 属性 | 属性值  | 描述 |
| ---- | ------- | ---- |
| type | `radio` | 单选 |
| type     | `checkbox`        |多选     |

==注意：可以使用 checked 属性，来表示默认选择该值==

> 1. 单选框控件必须成组使用才有意义，每组至少需要两个单选框
> 2. “组”是通过 name 属性来建立的，凡是 name 值相同的就是一组
> 3. 同组的单选框，只有一个会处在选中状态，其他的会自动呈现为未选中状态

## 下拉菜单
使用 `<select><option> </option></select>`, 注意：select 标签里面==只能放置 option 标签==

==注意：可以使用 checked 属性，来表示默认选择该值==

属性：

| 属性     | 属性值 | 描述             |
| -------- | ------ | ---------------- |
| multiple |        | 设置可选择多个值 |
| size         | `数字`       | 定义显示的数量                 |

## 文件选择
需要嵌入 `<input>`, 需要添加属性 `type`，属性值为 file
## 表单 label 标签
`<label> </label>` 可以添加标签，需要使用 for 来指定 id
## 只读
需要给控件添加一个 readonly 只读属性，添加一个 value 值，来设置只读内容
## 禁用
需要给控件添加一个 disabled 禁用属性
## 表单分组
`<fieldset><legend>标题</legend>其他内容</fieldset>`
其他内容放在 legend 标签后面
## 表单按钮
+ 提交按钮
需要嵌入 `<input>`, 需要添加属性 `type`，属性值为 submit，还可以添加 value 属性，可以自定义显示内容
可以在 form 标签后使用 action 属性，属性值为服务器地址，使用 target 属性，属性值为_blank 时，表示新打开一个页面，为_self 时，表示在当前页面打开
+ 重置按钮
需要嵌入 `<input>`, 需要添加属性 `type`，属性值为 reset，还可以添加 value 属性，可以自定义显示内容
+ 普通按钮
需要嵌入 `<input>`, 需要添加属性 `type`，属性值为 button，还可以添加 value 属性，可以自定义显示内容
+ 图像按钮
需要嵌入 `<input>`, 需要添加属性 `type`，属性值为 image，还需要添加 src 属性，属性值为图片地址
+ 双标签 button 按钮
`<button>按钮名字</button>`，默认具有提交表单的功能
## 表单数据采集和提交
form 有 action 属性，action 后跟服务器地址，将表单数据提交到服务器，method 属性，属性值有 get：get 是默认值，浏览器会把收集好的表单数据，加到服务器地址的后面，提交给服务器。
post：post 值不但能够收集表单的数据，而且不会在地址栏里暴露隐私数据。
# 水平线
`<hr>` 水平分隔线

属性：

| 属性    | 属性值    | 描述             |
| ------- | --------- | ---------------- |
| width   | `数值`    | 控制水平线的宽度 |
| size    | `数值`    | 控制水平线的高度 |
| noshade | `noshade` | 去掉水平线阴影   |
| color   | `颜色`    | 定义水平线的颜色 |

# 预格式化的文本
`<pre> </pre>` 预格式化文本，文本将严格按 HTML 文件中的格式显示
# 图像映射
`<map> </map>` 图像映射，它有一个必需定义的属性 name，这个属性要与 img 标签的 usemap 属性相关联。有 `<area>` 子标签，用于定义图片上的热点区域，其有 href 属性，用来定义热点区域链接的目标地址；shape 属性，用来定义区域的形状，属性值为 default 时表示所有区域，为 rect 时表示矩形，为 circle 时表示圆形，为 poly 时表示多边形；coords 属性，用来定义可点击区域的坐标。
# iframe
iframe 的作用：用来在一个网页中显示另一个网页
`<iframe> </iframe>`, 有 src 属性，属性值是页面的路径；有 width 属性和 height 属性，表示高度和宽度；frameborder 属性，表示框架边框，默认引用的框架带有边框，通常情况下设置为 0，来取消边框；scrolling 属性，滚动的意思，用来控制是否显示框架的滚动条，属性值有 auto，默认值，在需要的时候显示滚动条，属性值 yes 表示始终显示滚动条，属性值 no 表示从不显示滚动条。

# SVG
SVG（可缩放矢量图）：XML 语法的图像格式，SVG 是用代码实现的，可以用 VSCode 编写。
SVG 中的 `<g></g>` 标签用来组织其他 SVG 元素
## SVG 标签
SVG 标签是 SVG 图形的一个容器。
`<svg> </svg>`
有 width 和 height 属性，用来定义画布的宽度和高度
## 绘制矩形、圆形和椭圆形
+ 矩形
使用 `<rect/>`
重要属性：
1. width 属性，定义矩形的宽度
2. height 属性，定义矩形的高度
3. fill 属性，定义矩形的填充颜色
4. stroke-width 属性，定义了矩形的边框宽度
5. stroke 属性，定义矩形边框的颜色
6. x 属性，定义矩形的左边位置
7. y 属性，定义矩形的顶部位置
8. fill-opacity 属性，定义填充颜色的不透明度（范围在 0~1）
9. stroke-opacity 属性，定义描边颜色的不透明度（范围在 0~1）
10. opacity 属性，定义整个元素的不透明度（范围在 0~1）
11. rx 属性，定义圆角 x 轴方向的半径长度
12. ry 属性，定义圆角 y 轴方向的半径长度
+ 圆形
使用 `<circle/>`
重要属性：
1. cx 属性，定义圆心的 x 坐标
2. cy 属性，定义圆心的 y 坐标
3. r 属性，定义圆形的半径
4. fill 属性，定义圆形的填充颜色
5. stroke-width 属性，定义了圆形的边框宽度
6. stroke 属性，定义圆形边框的颜色
+ 椭圆形
使用 `<ellipse/>`
重要属性：
1. cx 属性，定义椭圆中心的 x 坐标
2. cy 属性，定义椭圆中心的 y 坐标
3. rx 属性，定义水平半径
4. ry 属性，定义垂直半径
5. fill 属性，定义椭圆的填充颜色
6. stroke-width 属性，定义了椭圆的边框宽度
7. stroke 属性，定义椭圆边框的颜色
## 绘制线条、多边形和多线条
+ 线条
使用 `<line/>`
重要属性：
1. x1 属性，定义 x 轴上直线的起点坐标
2. y1 属性，定义 y 轴上直线的起点坐标
3. x2 属性，定义 x 轴上直线的末端坐标
4. y2 属性，定义 y 轴上直线的末端坐标

> svg 绘图时，坐标的起点都在画布的左上角，向右为 x 轴，向下为 y 轴。

+ 多边形
使用 `<polygon/>`
重要属性：
1. points 属性，定义了多边形每个角的 x 和 y 的坐标（它的值至少是三对坐标）
+ 多线条
使用 `<polyline/>`
重要属性：
1. points 属性，定义绘制所需的点（它的值至少是两对坐标）
## 绘制文字
使用 `<text> </text>`
重要属性：
1. x 属性，y 属性，定义文本的位置坐标
2. font-size 属性，定义文本的大小，值为数字
3. text-anchor 属性，定义文本的对齐方式，有三个值：start 以文本左端对齐，middle 以文本中间对齐，end 以文本末尾对齐
4. transform 属性，旋转文字，属性值 rotate，第一个参数表示旋转角度，第二个参数是旋转的中心坐标，例：`<text transform="rotate(30 20,40)">嘻嘻嘻</text>`
5. 有子标签 `<tspan> </tspan>`，每个 tspan 元素可以包含不同的格式和位置
6. 使用 `<a>` 标签包裹 `<text>` 标签可以添加链接
例：
```html
<svg width="200" height="30" xmlns:xlink="https://www.w3.org/1999/xlink">
	<a xlink:href="text2.html" target="_black">
		<text x="10" y="15" fill="red">I love SVG</text>
	</a>
</svg>
```
## 绘制路径
使用 `<path/>`
重要属性：
1. d 属性，用来定义绘制路径的命令，常用命令：M 命令，定义绘制图形的起点坐标；L 命令，用来绘制一条直线；q 命令，用来绘制二次贝塞尔曲线，需要定义控制点和终点的坐标。
2. stroke 笔画属性，值是任何合法的颜色
3. stroke-width 笔画宽度属性，定义一个元素的线条、文本或轮廓的厚度，值是一个数字
4. stroke-linecap 笔画笔帽属性，定义了一个开放路径的不同类型的结束点，值有：butt，没有线帽，默认值；round，圆形线帽；square，方形线帽
5. stroke-dasharray 虚线笔画属性，用来创建虚线，值是一个数字序列，定义虚线的线条与空隙的大小
## 模糊和阴影效果
+ 模糊
使用 `<filter> </filter>`
定义在 `<defs> </defs>` 标签中
重要属性：
1. id 属性，==必要的属性==，通过这个 id 指向要使用的过滤器。
2. `<feGaussianBlur/>` 通过 stdDeviation 属性定义模糊的数量，值是一个数字，值越大模糊的程度就越高。
+ 阴影
使用 `<filter> </filter>`
同时还要使用 `<feBlend/>` 标签在偏移的图像上混合原始图像
定义在 `<defs> </defs>` 标签中
重要属性：
1. `<feOffset/>`，使用 dx 属性，值是一个数字，表示阴影在 x 轴上的偏移量；使用 dy 属性，值是一个数字，表示阴影在 y 轴上的偏移量；in 属性，表示阴影图像的来源，值为 SourceAlpha 表示阴影为黑色，值为 SourceGraphic 表示阴影为该图片。
2. `<feBlend>` 标签有 in 属性，表示图像的来源，值为 SourceAlpha 表示为黑色，值为 SourceGraphic 表示为该图片。
## 线性渐变和径向渐变
+ 线性渐变
使用 `<linearGradient> </linearGradient>`，必须嵌套在 `<defs> </defs>` 中
重要属性：
1. `<linearGradient> </linearGradient>` 有 x1，y1，x2，y2 属性，用于定义线性渐变的开始位置和结束位置
2. `<stop/>` 标签在 `<linearGradient> </linearGradient>` 中，有两个属性：offset 属性，用于定义渐变颜色的开始和结束位置，属性值是一个描述相对位置的百分比；stop-color 属性，用于定义渐变的颜色，取值为一个合法的颜色值
3. `<linearGradient> </linearGradient>` 有 id 属性，将效果应用到图形，被应用的图形使用 fill 属性，属性值为 url (#id 名字)
+ 径向渐变
使用 `<radialGradient> </radialGradient>`，必须嵌套在 `<defs> </defs>` 中
重要属性：
1. `<radialGradient> </radialGradient>` 有 id 属性，定义了渐变的唯一名称，cx、cy 和 r 属性定义了最外面的圆，fx 和 fy 属性定义了最里面的圆
2. `<stop/>` 标签在 `<radialGradient> </radialGradient>` 中，有两个属性：offset 属性，用于定义渐变颜色的开始和结束位置，属性值是一个描述相对位置的百分比；stop-color 属性，用于定义渐变的颜色，取值为一个合法的颜色值


# 颜色值和长度
## 颜色
可以使用颜色名称、十六进制值、RGB 值
+ 颜色名称
有 140 个标准的颜色名称，使用英文表示
+ 十六进制值
使用#RRGGBB 的形式来定义颜色值
RR (表示红色)、GG (表示绿色)、BB (表示蓝色) 取值在 00-FF 之间，值越大，色彩强度越强，字母使用小写
+ RGB 值
使用 RGB (red, green, blue) 的形式来定义颜色值
## 长度单位
绝对长度单位：厘米（cm）、毫米（mm）、英寸（in）、px（pixel）
px（像素）
相对长度单位：指相对于一个长度计算出来的长度，一般用来适配不同的设备

# HTML5
HTML5 引入了很多更具描述性的 HTML 元素，包括 `main`、`header`、`footer`、`nav`、`video`、`article`、`section` 等等。

这些元素让 HTML 更易读，同时有助于搜索引擎优化和无障碍访问。
## main 元素
`main` 元素让搜索引擎和开发者能很快地找到网页的主要内容。
用法：`<main> </main>`

# HTML 美化
使用 [[CSS|css]] 来美化我们的页面