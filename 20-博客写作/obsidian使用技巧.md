---
banner: "https://api.dujin.org/bing/1920.php"
cssclass: noyaml,noscroll,myhome
obsidianUIMode: preview
banner_x: 0.5
banner_y: 0.5
---

#Obsidian #博客写作 

# 使用 OneDrive 进行多端同步
## 电脑端
1. 安装第三方插件 Remotely Save
2. 在本地建立一个文件夹，按步骤操作即可
## 安卓端
1. 安装第三方插件 Remotely Save
2. 在本地建立一个文件夹==（注意，要与在电脑端建立的文件夹同名）==，然后按步骤操作即可
# 常用的第三方插件
1. Activity History
生成一个像 GitHub 历史记录看板一样的历史记录看板
2. Advanced  Tables
高级表格工具
3. Banners
头图插件
4. Calendar
日历插件
5. Charts View
生成词云
6. Dataview
数据处理
7. Easy Typing
自动格式化文章
8. Homepage
设置打开时的主页
9. Image auto upload Plugin
图片上传图床
10. obsidian floating toc
悬浮目录
11. Privacy Glasses
隐私浏览，模糊效果
12. QuickAdd
快速添加页面
13. Quiet Outline
显示大纲
14. React Components
实现 react 效果
15. Recent Files
最近打开的文件
16. Remotely Save
多端同步
17. Style Settings
界面设置
18. Templater
模板插件
19. Workspaces Plus
工作区管理高级版
20. Zoottelkeeper Plugin
自动生成文件夹内文件的目录
# 双向链接
1. 链接到笔记 `[[笔记名称]]`
2. 链接到标题 `[[笔记名称#标题]]`
3. 链接到段落（块）`[[笔记名称^段落]]`
4. 链接别名 `[[笔记名称^段落|别名]]` `[[笔记名称#标题|别名]]`
5. 显示当前链接 `![[笔记名称^段落]]`
6. 显示当前链接 `[关键词]（链接）`

# Banners

头图插件
代码：

```
---
banner: "https://api.dujin.org/bing/1920.php"

cssclass: noyaml,noscroll,myhome

obsidianUIMode: preview
---
```

# 涂黑和挖空效果（三种语法）
- `删除+高亮组合：==~~xx~~==` 鼠标悬浮触发
- `删除+高亮+斜体组合：*==~~xx~~==*` 点击触发
- `删除+斜体组合：*~~xx~~*` 点击触发无背景颜色
例如：
三更灯火五更鸡，*==~~正是男儿读书时~~==*。
==~~黑发不知勤学早~~==，白首方悔读书迟。

碧玉妆成一树高，万条垂下绿丝绦。
*~~不知细叶谁裁出~~*，二月春风似剪刀

# style settings 设置

导出的代码为：
```json
{
  "memo-heatmap@@heatmap-dark": "ice-dark",
  "memo-heatmap@@heatmap-light": "grass-light",
  "time@@time-color@@light": "#1FAC8B",
  "time@@time-color@@dark": "#11765E",
  "hover-editor@@he-title-bar-height": "22px",
  "hover-editor@@he-title-bar-font-size": "14px",
  "hover-editor@@he-title-bar-active-action@@light": "#FDEC08",
  "obsidian-indentation-guides@@indentation-guide-adjust": 3,
  "obsidian-indentation-guides@@indentation-guide-color@@light": "#D13030AB",
  "modular-css-layout-wv@@normal-max-width": 750,
  "customizable-page-header-buttons@@page-header-spacing-mobile": 12,
  "dataview-cards-view@@image-aspect-ratio": "3 / 4",
  "dataview-cards-view@@cards-width": 138,
  "quick-explorer@@qe-obsidian-title": "qe-title-center",
  "customizable-page-header-buttons@@page-header-spacing-desktop": 19,
  "CodeMirror Options@@cm-theme-selection": "cm-theme-solarized-light",
  "CodeMirror Options@@cm5-minimal-embeds": false,
  "mk-absolve@@mk-design-scheme": "mk-viridian",
  "mk-absolve@@mk-brimwats-prism": false,
  "mk-absolve@@mk-highlighter": false,
  "mk-absolve@@mk-admonition-columns": true,
  "mk-absolve@@mk-admonition-compact": true,
  "mk-absolve@@mk-image-desaturation": false,
  "mk-absolve@@mk-hide-titlebar": false,
  "mk-absolve@@mk-note-embed-clean": false,
  "mk-absolve@@mk-resize-mermaid": false,
  "mk-absolve@@mk-wrap-filename": false,
  "mk-absolve@@mk-brimwats-blockquote": false,
  "mk-absolve@@mk-alternate-cite": false,
  "mk-absolve@@mk-workspace-colours-scheme-light": "mk-notepad",
  "mk-absolve@@mk-workspace-colours-scheme-dark": "mk-gruvbox-dark",
  "mk-absolve@@mk-caret-animation": "ease-in-out",
  "mk-absolve@@mk-aside-styling": true,
  "mk-absolve@@mk-minimal-checkbox": false,
  "obsidian-prism-theme@@pt-minimal-right-sidebar": true,
  "obsidian-prism-theme@@color-schemes-lt": "pt-color-scheme-swan-lt",
  "hover-editor@@he-title-bar-active-fg@@light": "#B6DAFF",
  "checkbox@@check-color": true,
  "checkbox@@check-bg": false,
  "checkbox@@check-strike": false,
  "checkbox@@chst-info": false,
  "checkbox@@chst-book": false,
  "checkbox@@chst-brn": false,
  "checkbox@@check-text": false,
  "checkbox@@chck-pad": true,
  "checkbox@@chst-q": false,
  "blue-topaz-theme@@background-primary-bg-4-bt@@dark": "#333333",
  "blue-topaz-theme@@text-normal@@dark": "#BDB6D5",
  "blue-topaz-theme@@background-primary-alt-bg-4-bt@@dark": "#333333",
  "blue-topaz-theme@@background-secondary-bg-4-bt@@dark": "#333333",
  "blue-topaz-theme@@background-secondary-alt-bg-4-bt@@dark": "#333333",
  "blue-topaz-theme@@background-modifier-border@@dark": "#333333",
  "blue-topaz-theme@@custom-titlebar-bg@@dark": "#333333",
  "blue-topaz-theme@@interactive-accent@@dark": "#BDB6D5",
  "blue-topaz-theme@@text-accent@@dark": "#BDB6D5",
  "blue-topaz-theme@@text-highlight-bg-h-dark": 57,
  "blue-topaz-theme@@text-highlight-bg-s-dark": 40,
  "blue-topaz-theme@@text-highlight-bg-l-dark": 38,
  "blue-topaz-theme@@text-highlight-bg-a-dark": 0.55,
  "blue-topaz-theme@@remove-colorful-highlight-bg": false,
  "blue-topaz-theme@@bg-color-highlight-1@@dark": "#F0EBD8",
  "blue-topaz-theme@@color-highlight-1@@dark": "#FBD1FF",
  "blue-topaz-theme@@font-weight-highlight-1": "lighter",
  "blue-topaz-theme@@bg-color-highlight-2@@dark": "#54B9476F",
  "blue-topaz-theme@@accent-strong@@dark": "#B6A8DB",
  "blue-topaz-theme@@accent-em@@dark": "#8888BB",
  "blue-topaz-theme@@funny-header-anim": true,
  "blue-topaz-theme@@retain-header-color": false,
  "blue-topaz-theme@@print-h1-color@@dark": "#906F9A",
  "blue-topaz-theme@@print-h2-color@@dark": "#E968A0",
  "blue-topaz-theme@@h2-toggle-underline": false,
  "blue-topaz-theme@@print-h3-color@@dark": "#61D1C1",
  "blue-topaz-theme@@h1-toggle-underline": false,
  "blue-topaz-theme@@fancy-hr": "fancy-hr-icon",
  "blue-topaz-theme@@list-style-change-options": "rainbow-lines-reading",
  "blue-topaz-theme@@file-bg-shape-option": "file-bg-pill",
  "blue-topaz-theme@@light-background-color-files": false,
  "blue-topaz-theme@@remove-file-icons": false,
  "blue-topaz-theme@@folder-icons": false,
  "blue-topaz-theme@@folder-style-change-options-colorful": "folder-style-change-options-colorful",
  "blue-topaz-theme@@folder-style-change-options-colorful-subfolder": "folder-colorful-two",
  "blue-topaz-theme@@blockquote-style-change-options": "blockquote-style-quotation-mark",
  "blue-topaz-theme@@adjustable-embed-content-height": true,
  "blue-topaz-theme@@embed-hover": true,
  "blue-topaz-theme@@code-box-style-option": "codebox-frosted-glass",
  "blue-topaz-theme@@text-color-code@@dark": "#FE8DB9",
  "blue-topaz-theme@@link-click": false,
  "blue-topaz-theme@@setting-etc-pane-style": "translucent-setting-panel",
  "blue-topaz-theme@@simple-titlebar": false,
  "blue-topaz-theme@@toggle-bg-file-page": false,
  "blue-topaz-theme@@layout-style-options": "asymmetric-split-left",
  "blue-topaz-theme@@titlebar-close-button": "default-titlebar",
  "blue-topaz-theme@@hide-titlebar-text": true,
  "blue-topaz-theme@@hide-vault-name": true,
  "blue-topaz-theme@@search-bar-style-option": "default-search-bar",
  "blue-topaz-theme@@bt-status-off": false,
  "blue-topaz-theme@@scrollbar-style-option": "hover-scrollbars",
  "blue-topaz-theme@@text-normal@@light": "#2E3248",
  "blue-topaz-theme@@background-primary-bg-4-bt@@light": "#F5F2E2",
  "blue-topaz-theme@@background-primary-alt-bg-4-bt@@light": "#F5F2E2",
  "blue-topaz-theme@@background-secondary-bg-4-bt@@light": "#F5F2E2",
  "blue-topaz-theme@@background-secondary-alt-bg-4-bt@@light": "#F5F2E2",
  "blue-topaz-theme@@background-modifier-border@@light": "#F5F2E2",
  "blue-topaz-theme@@custom-titlebar-bg@@light": "#F5F2E2",
  "blue-topaz-theme@@accent-strong@@light": "#2E3248",
  "blue-topaz-theme@@accent-em@@light": "#BEB5D4",
  "blue-topaz-theme@@mjx-inline-math-color@@light": "#2E3248",
  "blue-topaz-theme@@print-h1-color@@light": "#8F729C",
  "blue-topaz-theme@@h1-text-align-settings": "h1-text-align-start",
  "blue-topaz-theme@@print-h2-color@@light": "#95CAFA",
  "blue-topaz-theme@@print-h3-color@@light": "#E968A0",
  "blue-topaz-theme@@print-h4-color@@light": "#FDC2BF",
  "blue-topaz-theme@@toggle-calendar-shadow": true,
  "blue-topaz-theme@@toggle-calendar-transparent": true,
  "blue-topaz-theme@@style-options-for-calendar-plugin": "style-options-for-calendar-plugin-style-two",
  "blue-topaz-theme@@file-name-style-option": "file-name-animation"
}
```