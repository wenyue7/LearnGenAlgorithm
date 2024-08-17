# markdown 公式语法

## 基本语法

1. 行内公式
* 语法：使用`$...$`包裹公式内容，表示公式将嵌入到文本行中。
* 示例：$\sum_{i=1}^{n}a_i$

2. 行间公式
* 语法：使用`$$...$$`或`\[...\]`（部分Markdown环境支持）包裹公式内容，表示公式将单独成行并居中显示。
* 示例：
$$
\int_{a}^{b}f(x)dx
$$

$$
\int_{0}^{\infty} e^{-x^2} \, dx = \frac{\sqrt{\pi}}{2}
$$


## 常用数学符号

1. 希腊字母
* 小写希腊字母如`\alpha`、`\beta`、`\gamma`等，大写则首字母大写，如`\Alpha`、`\Beta`。
* 示例：$\alpha$，$\Gamma$

| 符号 | LaTex命令 |
|--|--|
| α | \alpha      |
| β | \beta       |
| γ | \gamma      |
| δ | \delta      |
| ϵ | \epsilon    |
| ε | \varepsilon |
| ζ | \zeta       |
| η | \eta        |
| θ | \theta      |
| ϑ | \vartheta   |
| ι | \iota       |
| κ | \kappa      |
| λ | \lambda     |
| μ | \mu         |
| ν | \nu         |
| ξ | \xi         |
| π | \pi         |
| ρ | \rho        |
| ϱ | \varrho     |
| σ | \sigma      |
| τ | \tau        |
| υ | \upsilon    |
| ϕ | \phi        |
| φ | \varphi     |
| χ | \chi        |
| ψ | \psi        |
| ω | \omega      |


2. 上下标
* 上标使用`^`，下标使用`_`。
* 示例：$a^2_b$

3. 分数
* 使用`\frac{分子}{分母}`
* 示例：$\frac{1}{2}$

4. 根号
* 使用`\sqrt[开方数]{被开方数}`，省略开方数则为平方根。
* 示例：$\sqrt{x}$

5. 积分与求和
* 积分使用`\int`，求和使用`\sum`，均可通过上标下标指定范围。
* 示例：$\int_{a}^{b}f(x)dx$

## 复杂公式

1. 矩阵
* 使用`\begin{matrix}...\end{matrix}`，元素间用`&`分隔，行末用`\\`换行。
* 边框类型可通过替换matrix为pmatrix、bmatrix、Bmatrix等实现。
* 示例：
$$
\begin{pmatrix}
  a & b \\
  c & d \\
\end{pmatrix}
$$

2. 方程组
使用`\begin{cases}...\end{cases}`，每个方程用`\\`换行。
示例：
$$
\begin{cases}
  a_1x + b_1y = c_1 \\
  a_2x + b_2y = c_2 \\
\end{cases}
$$

## 其他常用符号

* 加减乘除：$+$、$-$、$\times$、$\div$。
* 比较运算符：$\geq$、$\leq$、$\neq$。
* 箭头：$\rightarrow$、$\leftarrow$、$\uparrow、\longrightarrow$等。
* 集合运算：$\in$、$\notin$、$\subset$、$\supset$等。
* 在箭头上下写字：$A \overset{a}{\longrightarrow} B \quad \text{和} \quad A \underset{b}{\longrightarrow} B$
  或者也可以用如下方法：$0 \stackrel{a}{\longrightarrow} 1$


## 注意事项

* Markdown编辑数学公式时，通常需要MathJax等库的支持。
* 不同的Markdown编辑器或平台可能对LaTeX语法的支持程度有所不同，使用时请参考具体环境的文档。

# LaTex 语法

LaTeX是一种高质量排版系统，尤其擅长于科技文档的排版，如学术论文、书籍、报告等。
它提供了丰富的控制命令和宏包，使得用户可以精细地控制文档的布局、字体、样式等。
在markdown中，需要以`$...$`包围公式语法，下面简要介绍LaTeX的一些基本语法：

## 文档结构

LaTeX文档的基本结构通常包括以下几个部分：
* 导言区：位于`\documentclass{}`和`\begin{document}`之间的部分，用于设置文档的类型
  （如article、book、report等）、加载宏包（如\usepackage{}）、定义全局命令等。
  > 举例：$\documentclass{}导言\begin{document}$
* 正文区：位于`\begin{document}`和`\end{document}`之间的部分，包含文档的实际内容。
  > 举例：$\begin{document}正文\end{document}$

## 常用命令

* 文档类型：$\documentclass{article}$ 指定文档类型为文章。
* 文档开始与结束：`\begin{document}` 和 `\end{document}` 分别标记文档内容的开始和结束。
* 章节标题：$\section{}$、$\subsection{}$、$\subsubsection{}$ 分别用于生成节、
            小节、小小节标题。
* 段落：LaTeX通过空行来区分段落。
* 换行：在LaTeX中，通常不需要手动换行，但可以使用\\命令强制换行。
* 注释：LaTeX中的注释以%开始，直到行末。

## 字体与样式

LaTeX提供了多种字体样式和大小的控制命令，如：
* 加粗：$\textbf{文本}$
* 斜体：$\textit{文本}$
* 数学斜体：$\mit{文本}$（在某些上下文中使用，不是所有LaTeX发行版都支持）
* 字号：`\Huge`、`\huge`、`\LARGE`、`\Large`、`\large`、`\normalsize`（默认）、
        `\small`、`\footnotesize`、`\scriptsize`、`\tiny`

## 数学公式

LaTeX在数学排版方面尤为强大，提供了多种数学模式和命令：
* 行内公式：使用`$...$`或`\(...\)`将公式嵌入到文本行中。
* 独立公式：使用`\[...\]`或`\begin{equation}...\end{equation}`将公式单独成行，
  并自动编号（后者需要加载amsmath宏包）。
* 数学环境：LaTeX提供了多种数学环境，如align、gather、split等，用于复杂公式的排版。
* 特殊数学符号：LaTeX通过特定的命令来输入数学符号，如`\sum`、`\int`、`\frac{分子}{分母}`等。

### 基本元素

* 上标和下标：使用^和_分别表示上标和下标，如果上标或下标包含多个字符，则需要将它们放在大括号{}中。
  > 举例：$x^2$  $a_{ij}$
* 分数：使用`\frac{分子}{分母}`来表示分数。
  > 举例：$\frac{1}{2}$
* 根号：使用`\sqrt[根指数]{被开方数}`来表示根号，省略根指数则为平方根。
  > 举例：$\sqrt{x}$  $\sqrt[3]{x}$
* `\quad`和`\,`都是LaTeX中用于控制水平间距的命令。
    * `\quad`插入的空格宽度较大，大约相当于一个汉字的宽度，适用于需要较大间距分隔的场合。
    * `\,`插入的空格宽度较小，适用于需要微调间距的场合，特别是在数学表达式中。


### 运算符

* 求和与积分：使用`\sum`和`\int`分别表示求和与积分，并通过上标和下标指定范围和变量。
  > 举例：$\sum_{i=1}^{n} a_i$  $\int_{a}^{b} f(x) \, dx$  从a到b的f(x)积分，
          注意`\,`用于添加少量空间
* 极限：使用`\lim_{变量 \to 表达式}`来表示极限。
> 举例：$\lim_{x \to \infty} \frac{1}{x} = 0$  x趋向于无穷大时，1/x的极限为0
* 正负号：$\pm1$

### 符号与函数

* 希腊字母：使用`\alpha`、`\beta`、`\gamma`等来表示小写希腊字母，大写则首字母大写
           （如\Gamma）。
  > 举例：$\alpha$ $\Gamma$
* 三角函数：直接使用`\sin`、`\cos`、`\tan`等来表示三角函数。
  > 举例：$\sin(x)$
* 对数函数：使用`\log`、`\ln`等来表示对数函数。注意，`\log`默认以10为底，`\ln`
            表示自然对数。
  > 举例：$\log_{10}x$  $\ln x$

### 矩阵与方程组

* 矩阵：使用`\begin{matrix}...\end{matrix}`环境，元素间用`&`分隔列，用`\\`分隔行。
  > 举例：
$$
\begin{matrix}
  a & b \\
  c & d \\
\end{matrix}
$$
* 方程组：使用`\begin{cases}...\end{cases}`环境，每个方程用`\\`分隔。
> 举例：
$$
\begin{cases}
  a_1x + b_1y = c_1 \\
  a_2x + b_2y = c_2 \\
\end{cases}
$$

### 注意事项

* 在Markdown文件中编写LaTeX公式时，请确保Markdown渲染器支持LaTeX数学公式的渲染。
* 对于Markdown文件中的LaTeX公式，有时需要转义一些特殊字符（如\、_、*等），但在
  LaTeX公式内部，这些字符通常有其特定的数学意义，不需要额外转义（除非它们在公式中
  有特殊用途且你希望按字面意义显示它们）。
* 空格和缩进在LaTeX公式中通常不重要，但在Markdown文件中编写时，为了保持代码的可读
  性，适当使用空格和缩进是个好习惯。然而，在LaTeX公式内部，空格通常会被忽略，除非
  使用特定的命令（如`\,`、\quad等）来添加空间。



## 列表与表格

* 列表：LaTeX支持有序列表（`\begin{enumerate}...\end{enumerate}`）和无序列表
       （`\begin{itemize}...\end{itemize}`）。
* 表格：使用`\begin{tabular}{列格式}...\end{tabular}`环境来创建表格，其中列格式指定了
        每列的对齐方式（如l左对齐、c居中对齐、r右对齐）。

## 引用与交叉引用

LaTeX支持文献引用和文档内的交叉引用。对于交叉引用，首先需要为需要引用的对象（如图表、
公式等）添加`\label{}`命令，然后在文档中通过`\ref{}`或`\pageref{}`命令引用。

## 宏包与自定义命令

LaTeX通过宏包来扩展其功能，用户可以通过`\usepackage{}`命令加载所需的宏包。此外，用户
还可以定义自己的命令和环境，以便在文档中重复使用。

## 编译与查看

LaTeX文档需要编译才能生成最终的PDF文件。编译过程可能涉及多次编译（特别是当文档中
包含交叉引用时），以确保所有引用都正确解析。编译完成后，可以使用PDF阅读器查看生成
的文档。
