---
banner: "https://api.dujin.org/bing/1920.php"
cssclass: noyaml,noscroll,myhome
obsidianUIMode: preview
banner_x: 0.5
banner_y: 0.5
---

#前端  #CSS

参考教程：[CSS 教程 ](https://www.w3school.com.cn/css/index.asp)

---
以下是我的个人笔记：
# 什么是 CSS
CSS：层叠样式表（Cascading Style Sheets）
它不是编程语言
是控制与显示 HTML 元素的声明式语言，控制网页的显示效果，CSS 和 [[HTML|HTML]] 是一对无法分开的。
# CSS 规则
一个 CSS 规则由一个==选择器==和一个==声明块==组成。
选择器：用来寻找或选择你要定义样式的 HTML 元素
声明块：包含一个或多个声明，每个声明包括一个 CSS 属性名称和一个值，中间要用冒号隔开，多个 CSS 声明要用分号隔开，声明块要用大括号包裹起来
# CSS 注释
使用 `/* */` 来添加注释
# CSS 选择器
CSS 选择器：用来寻找或选择你要定义样式的 HTML 元素的
## 简单选择器
根据名称、ID、类别来选择元素
+ 元素选择器
根据元素名称来选择 HTML 元素
+ ID 选择器
使用一个 HTML 元素的 id 属性来选择一个特定的元素
==元素的 id 是唯一的，不能使用数字开头==
使用 `#` 来选择这个 id
+ 类选择器
可以选择具有特定 class 属性的 HTML 元素
使用 `.` 来选择类别名称
class 属性可以实现多个样式的叠加（在 class 属性里使用空格隔开）
+ 分组选择器
选择所有具有相同样式的 HTML 元素
使用 `,` 将多个选择器隔开
+ 通用选择器
选择页面上的所有 HTML 元素
使用 `*` 来选择
总结：

| 选择器分类           | 选择器定义语法  | 例子        | 例子说明                                   |
| -------------------- | --------------- | ----------- | ------------------------------------------ |
| ID 选择器             | `#id`           | `#firstname` | 选择 id=“firstname”的元素                   |
| 类选择器             | `.class`        | `.intro`      | 选择所有带有 class=“introduction”的元素     |
| 类选择器（带有元素） | `element class` | `p.intro`     | 只选择带有 class=“introduction”的 < p > 元素 |
| 通用选择器           | `*`             | `*`           | 选择所有元素                               |
| 元素选择器           | `element`         | `p`           | 选择所有 < p > 元素                          |
| 分组选择器                     |       `element，element，...`          |  `div,p`         |         选择所有 < div > 元素和所有 < p > 元素                                   |

## 组合选择器
根据元素之间的特定关系来选择元素
+ 后代选择器
中间使用 `空格` 隔开
匹配作为指定元素==后代==的所有元素
+ 子选择器
中间使用 `>` 隔开
只能选择作为某元素的子元素，==不能选择到孙辈==的元素
+ 相邻的兄弟选择器
中间使用 `+` 隔开
+ 一般兄弟选择器
中间使用 `~` 隔开
总结：

| 选择器分类 | 选择器定义语法    | 例子    | 例子说明                         |
| ---------- | ----------------- | ------- | -------------------------------- |
| 后代选择器 | `element element` | `div p` | 选择 < div > 元素内的所有 < p > 元素 |
| 子选择器           |    `element>element`               |   `div>p`      |选择所有父元素是 < div > 元素的 < p > 元素                                 |

## 伪类选择器
根据某种状态来选择元素
属于类选择器中的一种，根据特定状态选取元素
使用 `selector:鼠标行为`
常用的伪类选择器有四个：
1. 鼠标点击前 `:link` 代表鼠标没有操作元素时元素的默认样式
2. 鼠标点击后 `:visited` 代表鼠标点击并离开元素之后的样式
3. 鼠标悬停时 `:hover` 代表鼠标悬停或者是划过元素时元素的样式
4. 鼠标点击时 `:active` 代表鼠标点击元素瞬间，元素显示的样式

>
>注意：
>1. 冒号和后面的鼠标行为，没有任何空格，必须连接在一起
>2. 四个伪类选择器必须按照以上介绍的顺序书写（: link,: visited,: hover,:active）, 否则在浏览器中部分样式不能实现
>3. 伪类选择器全部一起使用的情况，主要是应用在超链接上，偶尔也会独立使用在其他标签上面
>4. 伪类选择器也可以应用在其他元素上，但是只能实现 active 激活瞬间和 hover 鼠标悬停效果

## 伪元素选择器
为一个元素的指定部分设置样式。主要用来设置元素内文本的首字母，首行的样式、或是在元素内容之前或之后插入其他内容
使用 `selector::pseudo-element` 其中 `selector` 为目标元素 `::pseudo-element` 代表向目标元素内，添加伪元素，并对伪元素的内容进行修饰
共五种：
+ `::first-letter` 用来向文本的首个字符添加特殊样式
+ `::first-line` 用来向文本的首行添加特殊样式
+ `::before` 用来实现在元素内容之前插入内容
+ `::after` 用来实现在元素内容之后插入内容

> 在实现向前向后添加内容时，必须配合 content 才能实现效果

+ `::selection` 用来更改选中文本的样式

> selection 伪元素选择器只支持以下几个样式声明：color（文本颜色），background（背景），cursor（鼠标样式），outline（描边效果）

总结：

| 选择器           | 例子              | 例子描述                    |
| ---------------- | ----------------- | --------------------------- |
| `::first-letter` | `p::first-letter` | 选择每个 < p > 元素的首字母   |
| `::first-line`   | `p::first-line`   | 选择每个 < p > 元素的首行     |
| `::after`        | `p::after`        | 在每个 < p > 元素之后插入内容 |
| `::before`       | `p::before`       | 在每个 < p > 元素之前插入内容 |
|     `::selection`             |    `p::selection`                 |选择用户选中的元素部分                             |

## 属性选择器
根据一个属性或属性值来选择元素
使用 `Element[attribute]或Element[attribute="value"]`
其中 `Element` 表示元素，`attribute` 表示属性，表示查找带有该属性的元素，然后添加样式声明
CSS 选择器的四种属性：
+ `[attribute]` 来查找 HTML 结构中，带有 attribute 属性的所有元素
+ `[attribute="value"]` 来查找 HTML 结构中，带有 attribute 属性，并且属性值为 value 的元素
+ `[attribute~="value"]` 来查找 HTML 结构中，带有 attribute 属性，并且在多个属性值中包含 value 的元素
+ `[attribute|="value"]` 来查找 HTML 结构中，带有 attribute 属性，并且属性值以 value 或者是 value-开头的元素
总结：

| 选择器   | 例子  | 例子描述    |
| ------------- | ----- | --------------------------- |
| [attribute] | [target] | 选择带有 target 属性的所有元素   |
| [attribute="value"]| [target="_blank"] | 选择带有 target="_ blank"属性的所有元素 |
| [attribute~="value"] | [title~="flower"] | 选择带有包含"flower"一词的 title 属性的所有元素 |
| attribute&#124;="value" |[ang&#124;="en"]|选择带有以"en"开头的 lang 属性的所有元素|
|attribute^="value"] | a[href^="https"]  | 选择其 href 属性值以"https"开头的每个 < a > 元素  |
| [attribute $="value"] | a[href$ =". pdf"]| 选择其 href 属性值以". pdf"结尾的每个 < a > 元素   |
| [attribute*="value"]|  a[href*="w3school"]| 选择其 href 属性值包含字串"w3school"的每个 < a > 元素|

# 如何添加 CSS 样式
CSS 中有三种插入样式表的方法：内联 CSS、内部 CSS、外部 CSS
## 内联 CSS
内联 CSS：也称之为内联样式，又称行内样式
它被用来为一个单一的元素应用一个独特的样式
在行内元素标签中使用 `style` 属性即可
==不推荐使用==
## 内部 CSS
内部样式表：一般定义在 head 元素里，通过 `<style> </style>` 元素来定义。
需要使用==选择器==
## 外部 CSS
外部样式：将 CSS 代码放在一个独立的，以. css 为后缀的文件中，使 html 页面结构文件和 css 样式文件完全独立开来，同时每个 HTML 页面都必须在 head 元素里添加 `<link>` 元素，在 `<link>` 中定义 rel 属性，值为 stylesheet，再定义一个 href 属性，来引用外部. css 文件
# CSS 样式表的优先级
+ 内联样式优先级最高，会覆盖外部样式和内部样式以及浏览器默认样式
+ 在 head 里添加的内部样式和引入的外部样式，后添加和引入的优先级高
+ 浏览器默认样式优先级最低
# CSS 文本样式
## 添加颜色
通过声明 color 属性来设置文本的颜色
颜色为合法的颜色值即可
## 大小写转换
使用 text-transform 属性来实现这个功能，属性值有：uppercase，文本被转换为大写；lower case，文本被转换为小写；capitalize，每个单词的首字母被转换为大写。这个属性主要用来设置英文的文本，对中文无效
## 设置文本对齐方式
+ 水平对齐
使用 text-align 属性，属性值有三个，left，水平居左；right，水平居右；center，水平居中
当被设置成 justify 时，每一行都被拉长使每一行都有相等的宽度，而且左右的边界是对齐的
+ 垂直对齐
使用 vertical-align 属性，属性值有五个，baseline，基线对齐；text-top，文本顶部对齐；text-bottom，文本底部对齐；sub，下角标对齐；super，上角标对齐
## 设置文本间距
使用 text-indent 属性来实现，使用长度值或百分比来设置文本缩进，长度值可以使用绝对单位（如 px）和相对单位（如 em，一般设为==2em==）或百分比缩进（很少使用）
letter-spacing 属性用于指定中文文字或英文字母之间的空隙
line-height 属性用于指定行与行之间的高度，即行高，属性值有三个，normal，默认值；一个数字，此数字与当前的字符大小相乘计算得到（推荐）；绝对值，如 20px，设置固定的行间距
word-spacing 属性用于指定文本中单词的间距，只对英文有效
white-spacing 属性指定了如何处理元素内部的空白，属性值 nowrap，表示不管包含文本的元素宽度是多少，文本都不会换行，直到遇见 `<br>` 标签为止

## 总结

| 属性             | 说明                           |
| ---------------- | ------------------------------ |
| `text-align`     | 指定文本的水平对齐方式         |
| `vertical-align` | 设置一个元素的垂直对齐方式     |
| `letter-spacing` | 指定文本中字符之间的间隙       |
| `line-height`    | 指定行高                       |
| `text-indent`    | 指定文本块中第一行的缩进       |
| `white-space`    | 指定如何处理一个元素内部的空白 |
| `word-spacing`   | 指定文本中单词之间的空隙       |

# CSS 文本修饰
## 添加装饰线
使用 text-decoration-line 属性，有 overline，在文本上方添加；line-through，在文本中间添加线条修饰；underline，在文本下方添加线条修饰
## 设置装饰线的颜色
使用 text-decoration-color 属性，属性值为任意合法的颜色值
## 设置装饰线的风格
使用 text-decoration-style 属性，属性值有 solid，实线；double，双实线；dotted，圆点线；dashed，虚线；wavy，波浪线
## 设置线条厚度
使用 text-decoration-thickness 属性，属性值有 auto，默认值；px，表示像素大小，是一个绝对值；%，是一个相对值
## 简化写法
使用 text-decoration 属性，使用空格隔开每个属性，属性值为上面四类
## 总结

| 属性                    | 说明                                           |
| ----------------------- | ---------------------------------------------- |
| `text-decoration`       | 在一个声明中设置所有的文字装饰属性             |
| `text-decoration-color` | 指定文本装饰的颜色                             |
| `text-decoration-line`  | 指定要使用的文本装饰的种类（下划线、上划线等） |
| `text-decoration-style` | 指定文本装饰的样式（实心、点状等）             |
| `text-decoration-thickness`                        | 指定文本修饰线的厚度                                               |

# CSS 文字
## 字体
使用 font-family 属性指定一个文本的字体
英文字体有五类：
+ Serif
有衬线字体，正式优雅
+ Sans-serif
无衬线字体，现代简约
+ Monospace
等宽字体，机械，一般在代码中使用
+ Cursive
草书字体，模仿手写
+ Fantasy
幻想字体，装饰性，娱乐性字体
中文字体：
+ 微软雅黑
应用于 Windows 字体
+ 苹方简
应用于 Mac 字体
## 字号
使用 font-size 属性设定文本的大小，属性值可以是绝对大小和相对大小（使用 em 或%）可以使用 rem 来想对 heml 这个根元素来设定大小
## 字体风格
使用 font-style 属性，可以设置斜体，属性值 normal 表示文本正常显示；italic 表示文本斜体显示
使用 font-wight 属性，可以设置字体的粗细，属性值设置有两种方式
1. 名称：lighter，细体；normal，正常字体；bold，加粗字体；bolder，更粗字体
2. 数值：100（细体）、200、300、400（正常）、500、600、700（加粗）、800、900（更粗）值越大，字体越粗
font-variant 属性，小型大写字母，只对英文有效，属性值 small-caps，表示小型大写字母
==可以使用 font 属性简写，必须有的是 font-size 和 font-family==
## 谷歌字体
在 `<head></head>` 中添加 link 元素，href 属性值为：https：//fonts. googleapis. com/css? family=字体名称
## Icon 图标
推荐：[iconfont-阿里巴巴矢量图标库](https://www.iconfont.cn/)
Icon 字体图标的强大之处就是，你可以将这个图标当成是文本，任意的添加样式
# CSS 选择器的权重
行内样式（权重值为 1000）>ID 选择器（权重值为 100）>类选择器（权重值为 10）>元素选择器（权重值为 1）>通用选择器（权重值为 0）
# CSS 边框
`border-style` 属性指定了要显示什么样的边框，属性值有：dotted，点状边框；dashed 虚线边框；solid，实线边框；double，双倍边框；none，无边框；hidden，隐藏的边框
在 `border-style` 中添加方向即可控制一边的边框，有 `border-top-style、border-bottom-style、border-left-style、border-right-style`
简写形式：按上、右、下、左方式依次设置
`border-width` 属性设置边框宽度，可以使用数值自定义，也可使用 thin，薄；medium，中；thick，厚定义
`border-color` 属性设置边框颜色
==可使用 border 来速记：其中 border-style 是必须声明的==
#  CSS 列表
使用 `list-style-type` 定义列表项标记，属性值有 circle，空心圆点；disc，实心圆点；square，矩形圆点；decimal，阿拉伯数字；upper-roman，罗马数字；lower-alpha，小写英文字母
使用 `list-style-image` 指定一个图像作为列表项的标记，属性值为 url (图片路径)
使用 `list-style-position` 设置标记的位置，属性值有：outside 表示标记在列表项之外；inside 表示标记在列表项内
==也可使用 list-style 来速记==
使用 background 可以定义颜色
总结：

| 属性                  | 描述                               |
| --------------------- | ---------------------------------- |
| `list-style`          | 在一个声明中设置一个列表的所有属性 |
| `list-style-image`    | 指定一个图像作为列表项的标记       |
| `list-style-position` | 指定列表项标记的位置               |
| `list-style-type`                      |指定 list-item 标记的类型                                    |
# CSS 背景
可以给容器添加背景 
使用 background-image 添加图片，background-repeat 设置是否平铺，repeat 表示平铺，no-repeat 表示不允许平铺
使用 background-position 设置背景图片的位置，需要两个值，第一个值表示水平方向上的对齐方式，值有 left、center、right；第二个值表示垂直方向上的对齐方式，值有 top、center、bottom
使用 background-attachment 来声明容器里的背景图片与内容的依附方式，属性值为 fixed，表示图片固定；scroll，表示同时滚动
使 background-color 设置背景颜色
==使用 rgba 可以设置 rgb 颜色透明度，最后一个值在 0 到 1 之间==
# CSS 精灵图
精灵图，也称雪碧图、妖怪图
测量大概位置，然后使用
# CSS 轮廓
使用 `outline-style` 定义轮廓样式，属性值有 dotted，点状；dashed，虚线；solid，实线；double，双实线；none，无轮廓；hidden，隐藏轮廓
使用 `outline-width` 定义轮廓线宽度属性，属性值有 thin，一般为 1px；medium，一般为 3px；thick，一般为 5px；一个特定尺寸，以 px、em 为单位
使用 `outine-color` 定义轮廓的颜色，值为合法的颜色值
==使用 outline 可以速写，outline-style 是必须的==
使用 `outline-offset` 定义轮廓和元素之间的空隙，这个空隙是透明的
总结：

| 属性             | 解释                                                           |
| ---------------- | -------------------------------------------------------------- |
| `outline`        | 一个速记属性，用于在一个声明中设置轮廓宽度、轮廓样式和轮廓颜色 |
| `outline-color`  | 设置轮廓的颜色                                                 |
| `outline-offset` | 指定轮廓与元素的边缘或边界之间的空间                           |
| `outline-style`  | 设置轮廓的样式                                                 |
| `outline-width`                 | 设置轮廓的宽度                                                               |
# CSS 边距
使用 `margin` 属性设置边距，属性值 auto，浏览器自动计算的边距；length，以 px、pt（磅）、cm 等为单位指定边距；%，以父元素宽度的百分比来指定边距
在两个容器的相邻处有时会出现边距塌陷的问题，不会发生在左右边距上，只会发生在顶部底部边距上
嵌套块元素垂直边距也会发生塌陷
# CSS 填充和宽高
使用 `padding` 属性设置填充，属性值 length，以 length，以 px、pt（磅）、cm 等为单位指定填充；%，以父元素宽度的百分比来指定填充
设置内容，使用 width 和 height，是不包含内填充、边框和外边距的 
# CSS 盒模型
盒子里面可以放置文本、图片和其他元素
标准盒模型：
![](https://obsidian-picture.oss-cn-qingdao.aliyuncs.com/my-img/CSS1.png)
包含 margin、border、padding 和 content 四个部分
content 表示盒子的内容，包含文本图像等等
padding 表示填充内容周围的一个区域，它是透明的
border 表示围绕填充和内容的边框
margin 表示边框以外的区域，它是透明的
怪异盒模型：
使用 `box-sizing：border-box` 来触发
# CSS 布局
## 显示属性
使用 `display` 来控制显示
+ 每个 HTML 元素都有一个默认的显示值
+ 元素类型不同，默认的显示值也不同
属性值：block，显示为块级元素；inline，显示为行内元素; none, 隐藏元素
使用 `visibility`，属性值 hidden，可以隐藏元素，但占用的空间仍存在；使用 visible 来重新显示元素
## 元素类型
+ 行内元素不能设置宽高样式
+ 行内元素可以设置边框线样式
+ 行内元素可以设置内填充样式
+ 行内元素可以设置左右方向的外边距样式
+ 给块元素设置宽高、边框线、内填充、外边距样式，都是有效的
`display：inline-block；` 具备 inline 和 block 两种显示类型的特点
嵌套规则：
1. 块元素可以包含行内元素或某些块元素，但行内元素却不能包含块元素，它只能包含其他的行内元素
2. 块元素不能放在 p 元素里面
3. 有几个特殊的块级元素只能包含行内元素，不能再包含块元素，这几个特殊的元素是：h1、h2、h3、h4、h5、h6、p、dt
4. 块级元素一般与块级元素并列、行内元素一般与行内元素并列
## 溢出处理
使用 `overflow` 属性来处理，属性值，visible，默认值，溢出内容没有被剪掉，内容会在元素的框外呈现；hidden，溢出的内容被剪切；scroll，溢出的内容被剪掉，并且增加了一个滚动条来查看其余的内容；auto，类似于 scroll
使用 `text-overflow:ellipsis;` 将显示溢出的内容表示成省略号
总结：

| 属性         | 解释                                                      |
| ------------ | --------------------------------------------------------- |
| `overflow`   | 指定如果内容溢出元素的盒子会发生什么                      |
| `overflow-x` | 指定如果内容溢出元素的内容区域，该如何处理内容的左/右边缘 |
| `overflow-y` | 指定当内容溢出元素的内容区域时，对内容的上/下边缘的处理   |
| `text-overflow`             |控制文本溢出的样式                                                           |

## 浮动
容器浮动以后会脱离标准文档流，相当于飘起来了
使用 `float` 实现浮动效果，属性值，left，左侧浮动；right，右侧浮动；none，不浮动
## 浮动清理
使用 `clear` 属性来清除浮动，属性值有：left，表示当前元素不受到左浮动的影响；right，表示当前元素不受到右浮动的影响；both，表示当前元素既不受到左浮动的影响，又不受到右浮动的影响
## 定位
使用 `position` 实现，属性值有：static，静态定位；relative，相对定位；fixed，固定定位；absolute，绝对定位；sticky，粘性定位。使用 top、bottom、left、right 定位
+ relative
1. 相对样式需要配合 left、top、right、bottom 这些属性才能生效
2. relative 相对的是容器自身的屏幕坐标 0, 0 点
3. 容器位置发生位移后，原来占据的空间依然保留
4. 默认会覆盖没有定位的容器
+ absolute
1. 绝对定位的元素会脱离文档流
2. 绝对定位的参照点为，有定位设置的离他最近的祖先元素的 0, 0 点坐标
3. 绝对定位的容器默认会覆盖没有定位的容器
+ fixed
1. 固定定位的元素是相对于浏览器视口定位的，这意味着即使页面发生滚动，它也始终保持在同一个位置
2. top、right、bottom 和 left 属性被用来定位元素，但不是必须的
+ sticky
1. 父元素不能添加 overflow：hidden 或者 overflow：auto 属性
2. 元素自身必须声明 top、bottom、left、right 一个或多个属性，否则就相当于静态定位了
3. 父元素的高度不能低于 sticky 定位元素的高度
4. sticky 元素定位仅在其父元素内生效
5. 粘性定位初始状态相当于 static 定位
6. 相对于父容器的定位条件符合时，容器变现为固定定位
7. top、right、bottom 或 left 至少声明一个，粘性定位才能生效
## 定位的堆叠顺序
CSS 为盒模型的布局提供了三种不同的定位方案：正常文档流、浮动、定位
`z-index` 可以放到三维，控制 z 轴
## 宽高自适应
将 width 和 height 的值设置为%，可实现元素的宽高自适应
使用 `max-width和max-height、min-width和min-height` 即可设置最大（小）宽度和最大（小）高度
# CSS 数学函数 calc
CSS 的数学函数允许将数学表达式作为属性值使用
使用 `calc`（可以使用加减乘除运算符）来获取属性值
# CSS 圣杯布局
圣杯布局：中间容器高，旁边两侧的容器低
# BFC
BFC: Block Formatting Context 块格式上下文规则
可以使用 overflow 来触发 BFC
# CSS 表格
使用 `border` 设置表格的边框
使用 `text-align` 设置 th 或 td 中内容的水平对齐方式
使用 `vertical-align` 设置 th 或 td 中内容的垂直对齐方式
使用 `padding` 设置 th 或 td 内填充
使用 `border-bottom` 设置 th 或 td 水平分隔线
使用 `:hover` 设置 tr 鼠标滑过高亮
使用 `color` 设置颜色
# 表单
需要简洁、清晰、方便查看、填写信息即可
# CSS 重排与重绘
+ 重排（回流）
重排（回流）: 当渲染 render 树中的一部分或者全部因为大小边距、布局等问题发生改变而需要 DOM 树重新计算的过程，每个页面至少需要一次重排，就是在页面第一次加载的时候。
+ 重绘
当元素的一部分属性发生改变，如外观、背景、颜色等不会引起布局变化，只需要浏览器根据元素的新属性重新绘制，使元素呈现新的外观叫做重绘
+ 页面渲染过程
浏览器加载，解析，渲染页面，分为五个步骤：
1. 浏览器将获取的 HTML 文档解析成 DOM 树；  
2. 处理 CSS 标记，构成层叠样式表模型（CSSOM）；  
3. 将 DOM 和 CSSOM 合并为渲染树（render tree）；  
4. 渲染树的每个元素的内容都是计算过的，称之为布局 layout；  
5. 将渲染树上的各个节点绘制到屏幕上，称之为绘制 painting；





