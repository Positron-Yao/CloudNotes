# LaTeX 学习

[TOC]

##  编写文档

###  文档类型

- 英文为: book, article, beamer；
- 中文为: ctexbook, ctexart[^1], ctexbeamer；

### 基本参数

在documentclass处写。

```latex
\documentclass[12pt, a4paper, oneside]{ctexart}
```

### 宏包

与数学公式与定理环境相关的宏包为`amsmath`、`amsthm`、`amssymb`，用于插入图片的宏包为`graphicx`。

```latex
\usepackage{amsmath, amsthm, amssymb, graphicx}
```

### 标题部分

在document环境外写标题等信息，用\maketitle加载。

```latex
\title{Title}
\author{Author}
\date{114514}

...

\begin{document}

\maketitle

...
```

### 空格

| 符号     | 距离             |
| :------- | :--------------- |
| \qquad   | 2em              |
| \quad    | 1em              |
| \ (空格) | $\frac{1}{3}$em  |
| \;       | $\frac{2}{7}$em  |
| \,       | $\frac{1}{6}$em  |
| \\!      | $-\frac{1}{6}$em |

其他：

- \hspace{}: 水平距离，{}中填_em等;

- \vspace{}: 竖直距离，如`\vspace{1em}`等价于空一行;

- \hfill: 等距排列，如

  1\hfill 1\hfill 4\hfill 5\hfill 1\hfill 4


### 正文

两段之间要空行。

多个空格：`\;`

另起一页：`\newpage`

特殊字体：

| 字体     | 命令                       |
| -------- | -------------------------- |
| 直立     | \textup{up}  $\textup{up}$ |
| 意大利   | \textit{it}  $\textit{it}$ |
| 倾斜     | \textsl{sl}  --            |
| 小型大写 | \textsc{sc}  --            |
| 加宽加粗 | \textbf{bf}  $\textbf{bf}$ |

#### 章节

```latex
\section{一级标题}

\subsection{二级标题}

adadadad

\subsection{二级标题 2}

asasasas
```

#### 目录

`\tableofcontents`

#### 图片

```latex
\begin{figure}[htbp]
    \centering
    \includegraphics[width=8cm]{图片.jpg}
    \caption{图片标题}
\end{figure}
```

其中，`[htbp]`的作用是自动选择插入图片的最优位置，`\centering`设置让图片居中，`[width=8cm]`设置了图片的宽度为8cm，`\caption{}`用于设置图片的标题。

#### 表格

直接拿网站插入罢。

[Create LaTeX tables online](https://www.tablesgenerator.com/#)

将表格居中：\centering

固定表格位置(防止浮动错位): [htbp]:灵活一点点  [H]:完全固定

#### 分栏排版

minipage环境:

```latex
\begin{figure}[H]
  \centering
  % 左侧表格（占页面宽度的 48%）
  \begin{minipage}{0.48\textwidth}
    \centering
    \begin{tabular}{|cc|cc|c|}
        ...
    \end{tabular}
    \captionof{table}{年龄$\times$就业状态交叉表} % 为表格添加独立标题
  \end{minipage}
  \hfill % 填充水平间距
  % 右侧图片（占页面宽度的 48%）
  \begin{minipage}{0.48\textwidth}
    \centering
    \includegraphics[width=\linewidth]{年龄x就业.png} % 图片宽度自适应 minipage
    \captionof{figure}{年龄$\times$就业状态} % 为图片添加独立标题
  \end{minipage}
  \label{fig:table_and_figure}
\end{figure}
```

#### 列表

有三种：itemize(无序), enumerate(有序), description(描述).

```latex
\begin{enumerate}
    \item 这是第一点; 
    \item 这是第二点;
    \item 这是第三点. 
\end{enumerate}
```

另外，也可以自定义`\item`的样式：

```latex
\begin{enumerate}
    \item[(1)] 这是第一点; 
    \item[(2)] 这是第二点;
    \item[(3)] 这是第三点. 
\end{enumerate}
```

#### 定理环境

(好像就是为了这个自动计数)

定理环境需要使用`amsthm`宏包，首先在导言区加入：

```latex
\newtheorem{theorem}{定理}[section]
```

其中`{theorem}`是环境的名称，`{定理}`设置了该环境显示的名称是“定理”，`[section]`的作用是让`theorem`环境在每个section中单独编号。在正文中，用如下方式来加入一条定理：

```latex
\begin{theorem}[定理名称]
    这里是定理的内容. 
\end{theorem}
```

其中`[定理名称]`不是必须的。另外，我们还可以建立新的环境，如果要让新的环境和`theorem`环境一起计数的话，可以用如下方式：

```latex
\newtheorem{theorem}{定理}[section]
\newtheorem{definition}[theorem]{定义}
\newtheorem{lemma}[theorem]{引理}
\newtheorem{corollary}[theorem]{推论}
\newtheorem{example}[theorem]{例}
\newtheorem{proposition}[theorem]{命题}
```

另外，定理的证明可以直接用`proof`环境。

#### 调整页面部分

geometry包。

```latex
\usepackage{geometry}
\geometry{left=2.54cm, right=2.54cm, top=3.18cm, bottom=3.18cm} % 页边距
\linespread{1.5} % 行距
```

#### 页码

\pagenumbering{}: `aiph`表示小写字母，`Aiph`表示大写字母，`Roman`表示大写罗马数字，`arabic`表示默认的阿拉伯数字。

设置页码从0开始：

```tex
\setcounter{page}{0}
```

#### 数学公式部分

与Markdown差不多。

#### pandoc

类似这样的命令:

```bash
pandoc ./2024-11-04.md -s -o 1.pdf --pdf-engine=xelatex -V mainfont='Noto Sans CJK HK'
```

指定个字体就行了





[^1]: 无脑选这个（）