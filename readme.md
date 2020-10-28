# NUDT硕士/博士论文Latex模版

本项目提供 NUDT 硕士博士论文Latex模板。

# 更新日志
- 2020.10.28 修复双面打印版(twoside)空页无页码、页眉的问题；修复\url字体与正文不统一的问题；个人成果部分增加注释提示。（更新thesis.tex，resume.tex）
- 2020.03.04 删除会议论文集论文(inproceedings)参考文献中多余的单词"In" （更新bstutf8.bst）
- 2019.10.21 去掉交叉引用的颜色（更新mynudt.sty）
- 2019.10.17 修正英文字体渲染效果与Word不一致的问题（主tex文件去掉lmodern宏包）；将英文摘要从“ABSTRACT”改为“Abstract”；修正a3cover的字体设置；模版默认使用ttf字体。
- 2019.10.12 更新原创性声明的格式；提供ttf和otf两种字体，ttf字体可以解决macOS上TexStudio内置pdf阅读器不显示中文的问题。
- 2019.03.31 修正参考文献缩进格式；修正英文封面格式 （之前版本仅替换nudtpaper.cls和data/resume.tex）
- 2018.04.27 更新为二〇一八年三月版本格式



# 编译环境
推荐的编译环境如下：

+ 编译器：Texlive 2015。`台式机上，Texlive2015从头编译100页的大论文仅需8秒，增量编译仅需3秒。但是Texlive2019的编译时间在10秒以上。其他版本未做测试。`
+ 编辑器：Texstudio。项目主页：[https://sourceforge.net/projects/texstudio](https://sourceforge.net/projects/texstudio)。Ubuntu可以直接通过命令在线安装：`sudo apt-get install texstudio`。其他操作系统需要从项目主页下载程序。

## Texlive 的安装方法

- Texlive 官网：<https://www.tug.org/texlive/acquire-netinstall.html>
- Windows 安装程序（在线）：<http://mirror.ctan.org/systems/texlive/tlnet/install-tl-windows.exe>
- Ubuntu 可以直接通过命令在线安装：`sudo apt-get install texlive-full`
- macOS 安装方法：<http://www.tug.org/mactex/>


# 依赖的字体

使用此模板需要下载安装配套字体：

+ [ttf字体下载(Windows字体，与Word一致)](https://github.com/TomHeaven/nudt_thesis/releases/download/v1.1/ttf.zip)
使用ttf需要修改入口thesis.tex / thesis_blind.tex，确保documentclass的字体参数为

```
\documentclass[doctor,ttf]{nudtpaper}   % ttf字体
```
注意Windows 10系统安装字体`不要双击字体安装`，这样只会为当前用户安装字体，latex可能还是无法找到字体。要右击字体文件，选`为所有用户安装字体`。


# 用法

+ 用texstudio打开 thesis.tex，设置封面相关个人信息，编译生成论文明评版。thesis.tex包含data目录下的chap0X.tex文件为论文的各个章节。ref/refs.bib是参考文献。注意documentclass的第一个参数为`doctor`是博士论文，而为`master`则是硕士论文：

```
\documentclass[doctor,ttf]{nudtpaper} % 第一个参数表示博士论文，第二个参数表示ttf字体
```
注意：学位办要求评阅版论文（包括明评和盲评）“个人成果”部分隐去，并替换为一段文字：
> 该论文作者在学期间取得的阶段性成果(学术论文等)已满足我校博士学位评 阅相关要求。为避免阶段性成果信息对专家评价学位论文本身造成干扰，特将论文作者的阶段性成果信息隐去。

这需要手动修改resume.tex文件。

+ 设置封面信息时，\title中可以用双斜杠来控制封面页标题的换行位置，使得封面更加美观。\displaytitle中只填写标题纯文本，不要添加换行，否则会影响“独创性声明”页面的显示。例如：

```
\title{基于先验模型与深度学习的图像去噪\\方法研究}
\displaytitle{基于先验模型与深度学习的图像去噪方法研究}
```
+  在thesis.tex / thesis_blind.tex 顶部的doucumentclass传入参数twoside可以生成打印版。该版本将插入必要的空白页，使得每一章的首页在奇数页面，支持直接双面打印。

```
\documentclass[doctor,ttf,twoside]{nudtpaper} 
```

+ 复制已经填好封面信息的thesis.tex文件为thesis\_blind.tex文件，用texstudio打开 thesis\_blind.tex，在documentclass处添加参数anon：

```
\documentclass[doctor,ttf,twoside,anon]{nudtpaper} 
```
编译生成论文盲评版thesis_blind.pdf

+ 用texstudio打开 a3cover目录下的 spine.tex，，设置封面相关个人信息，编译；再打开a3cover.tex，编译，可以得到A3纸论文封面。
+ word文件夹下有官方word模版，如果发现Latex模版有任何问题可以江湖救急。


# 参考文献类别
refs.bib中可用的参考文献类别有：
+ article: Article from a magazine or journal 【学术文章】
+ book: A published book   【书】
+ inbook: A part of a book (section, chapter and so on)  【书的一部分，无单独标题】
+ incollection: A part of a book having its own title        【书的一部分，有单独标题】
+ booklet: A work that is printed but have no publisher or sponsoring institution 【未出版的书】
+ conference: An article in a conference proceedings    【会议论文】
+ inproceedings: An article in a conference proceedings【会议论文集中的论文】
+ manual: Technical documentation                             【手册】
+ masterthesis: A Master’s thesis                                【硕士论文】
+ phdthesis: A PhD thesis                                           【博士论文】
+ proceedings: The same as conference                       【会议论文】
+ techreport: Report published by an institution             【技术报告】
+ unpublished: Document not formally published, with author and title  【未发表的文献】
+ misc: Something that doesn’t fit in any other type       【其他类别】

# 致谢

本模版修改自这些前辈们的工作：

+ LiuBenYuan <liubenyuan@gmail.com>：Github项目[https://github.com/liubenyuan/nudtpaper](https://github.com/liubenyuan/nudtpaper)
+ Ruini <xueruini@gmail.com> 
+ sofoot

在此表示感谢！

# 免责声明

本模板免费提供于同学们使用或修改，但 is provided "As IS"。使用本模板产生的任何问题作者不承担任何直接或者间接责任。但作者会尽力帮助有需要的同学解决问题。

