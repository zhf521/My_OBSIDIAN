---
banner: "https://api.dujin.org/bing/1920.php"
cssclass: noyaml,noscroll,myhome
obsidianUIMode: preview
banner_x: 0.5
banner_y: 0.5
---

#VSCode  #C语言 #Python #HTML  #开发工具 #vim #CSS #CPP 
# 下载与安装

官网：[Visual Studio Code ](https://code.visualstudio.com/)

![](https://obsidian-picture.oss-cn-qingdao.aliyuncs.com/my-img/VSCode1.png)

下载安装包，并打开，一路下一步即可

# 配置 C/C++环境

## GCC 编译器下载和配置

> GCC 中 C 语言编译器是 gcc，c++编译器是 g++，调试器是 gdb

下载 TDM-GCC
联想应用商店下载链接：[TDM-GCC-联想应用商店](https://lestore.lenovo.com/detail/L101412)
下载安装即可
## VSCode 配置 C/C++

1. 下载 C/C++插件（==建议使用 v1.8.4 版本==）插件

![](https://obsidian-picture.oss-cn-qingdao.aliyuncs.com/my-img/VSCode2.png)

下载完成后重启 VSCode

2. 配置
  新建文件夹（用来放 VSCode 的项目，==必须是中文==） 
3. 在文件夹下创建一个 `test1.c` 文件
  代码如下：
```c
#include <stdio.h>
#include <stdlib.h>
int main()
{
    printf("hello world\n");
    printf("你好\n");
    system("pause");
    return 0;
}
```
创建一个 `test2.cpp` 文件
代码如下：
```cpp
int main()
{
	std::cout << "Hello World 哈哈\n";
	system("pause");
	return 0;
}
```
运行,==选择 g++编译器==，会在文件夹中自动创建 `.vscode` 文件夹
4. 测试是否成功
5. 设置外部窗口执行
点击右上角齿轮按钮
![](https://obsidian-picture.oss-cn-qingdao.aliyuncs.com/my-img/VSCode3.png)
点击生成和调试活动文件
![](https://obsidian-picture.oss-cn-qingdao.aliyuncs.com/my-img/VSCode4.png)
此时 `.vscode` 文件夹中出现 `launch.json` 文件
在 `launch.json` 文件中设置 `"externalConsole": false,` 将 false 改为 true
6. 中文乱码解决
在 `tasks.json` 文件中找到 `"${fileDirname}\\${fileBasenameNoExtension}.exe"`, 在其后面添加 `,` 然后下一行添加 `"-fexec-charset=GBK"` 即可
9. 设置隐藏. exe 文件
点击设置，搜索：Files: Exclude

![](https://obsidian-picture.oss-cn-qingdao.aliyuncs.com/my-img/VSCode5.png)

点击添加模式，添加

例如：`**/*.exe` `**/*.class`

# 配置 Python 环境

1. 下载 Python

打开 Python 官网：https://www.python.org/ ，点击 “Download”下载最新 python 版本。


![](https://obsidian-picture.oss-cn-qingdao.aliyuncs.com/my-img/VSCode6.png)


下载完成后自动弹出安装界面，务必先把下方两个对勾打上，把想要安装的文件夹路径复制下来，再点击 “Install Now”安装。

等待 Python 安装完成。

2. 在 VSCode 中安装 Python 扩展

点击 VSCode 界面左边的 “扩展”，在扩展搜索框中输入 Python，选中第一个框后点击 “安装”。


![](https://obsidian-picture.oss-cn-qingdao.aliyuncs.com/my-img/VSCode7.png)


3. 添加环境变量

右键点击 “此电脑”，选择 “属性”，点击 “高级系统设置–环境变量”。在系统变量中找到 “Path”，然后点击 “编辑”。



![](https://obsidian-picture.oss-cn-qingdao.aliyuncs.com/my-img/VSCode8.png)


进入后，点击 “新建”，把复制的 python. exe 路径粘贴上去，点击 “确定”就完成了 Python 环境的配置。



![](https://obsidian-picture.oss-cn-qingdao.aliyuncs.com/my-img/VSCode9.png)

4. 测试 Python

打开 VSCode，点击“新建文件”，并选择保存为 python 类型。


![](https://obsidian-picture.oss-cn-qingdao.aliyuncs.com/my-img/VSCode10.png)

输入 print (“hello!”) 并运行。


![](https://obsidian-picture.oss-cn-qingdao.aliyuncs.com/my-img/VSCode11.png)

如果终端出现 “hello!”，表示 Python 程序测试正常。

这样就配置成功了。

# 写 HTML/CSS 文件
新建一个文件，名为 test. html, 输入如下代码：
```html
<html>
<body>

<h1>这是第一个标题</h1>

<p>这是第一个段落</p>

</body>
</html>
```

然后保存，运行：
![](https://obsidian-picture.oss-cn-qingdao.aliyuncs.com/my-img/VSCode12.png)
推荐使用 Live Server 插件，可以实时查看效果。以及 HTML CSS Support 插件，支持 HTML 和 CSS；Auto Rename Tag 插件（左侧标签修改时自动修改右侧标签）
# 回车键代码补全
在 （一般都是这个路径）C:\Users\你的用户名\AppData\Roaming\Code\User 下的 keybindings. json 文件中添加一段代码。

```json
{ 
     "key": "enter", 
     "command": "acceptSelectedSuggestion",
     "when": "editorTextFocus && suggestWidgetVisible" 
}    
```

然后重启即可。
# 配合 vim 提高编码效率
使用 [vim](vim.md) 可以大幅提高编码效率
找到扩展，安装 vim 扩展即可
添加如下代码到 setting. json 文件中即可设置 `jj` 键替代 `esc` 键
```json
{  
"vim.insertModeKeyBindings": [  
{  
"before": ["j", "j"],  
"after": ["<Esc>"]  
}  
],  
```
添加如下代码到 setting. json 文件中即可设置相对行号
```json
"editor.lineNumbers": "relative",
```