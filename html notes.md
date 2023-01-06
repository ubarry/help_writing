# 在 Markdown 中使用 html 标签
Markdown 支持几乎全部的的 html 标签

## 2022-09-01
simple tags:

**居中标签**

<center\></center\>

示例:
```html
<center>  
居中  
</center>
```

效果：

> <center>
> 居中
> </center>

**换行标签**

<br\>  
不需要加</br\>标签，单个<br\>即可实现换行效果

示例：
```html
这里换行→<br>blah, blah, blah
```

效果:

> 这里换行→<br>blah, blah, blah

## 2022-10-10

**倾斜标签**

有 <i\></i\> 和 <em\></em\> 两种，其中 <em\></em\> 除了文本倾斜作用外，还而且可以加强语气，告诉搜索引擎这里是重要的。从便利性的角度考虑，我们应当谨慎使用该标签，让内容保持“干净”

示例:
```html
<i>Actions speaks louder than words</i>

<em>Why did Slobodan Praljak commited suicide?</em>
```
效果:

> <i>Actions speaks louder than words</i>
> 
> <em>Why did Slobodan Praljak commited suicide?</em>
> 
## 2022-12-22

**下标记号**

示例：
```html
Al<sub>2</sub>O<sub>3</sub>
```
效果：

> Al<sub>2</sub>O<sub>3</sub>


## 2023-01-04

Markdown 自带的标记和 HTML 标签之间具有一定的互换性。事实上，Github 在展示 Markdown 格式的 README 文件的时候，就是将 Markdown 的标记替换为 HTML 标签，再通过一定的方式渲染得到最终效果的。

例如，在行末输入两个及以上的空格后，单次回车并在新的一行输入内容，可以实现换行，效果相当于在两行之间插入换行标签<br\>。 这种换行效果不同于键入两次回车 ——— Markdown 编辑器会将两段空白行之间的内容视为段落，并加上<p\>标签。一般而言，段落分隔的行距要大于普通换行。

一个众所周知的事实是，如果文字之间出现空格，那么无论空格有多少，那么 HTML 编辑器一般都只会在渲染效果中将之呈现为一个空格。这一点对于 Markdown 来说同样成立。Markdown 不推荐使用空格、制表等来实现格式控制，如果有额外的需求，应当考虑使用 css 文件来实现格式控制。

尽管 Markdown 脱胎于 HTML，但是它们之间依然存在显著的区别。HTML 侧重于渲染的效果，具有复杂且多样的标签和繁复的框架结构，而 Markdown 则更加关注文本内容，标记少而简单，内容以文本为主。显然，HTML 学习和编辑的难度更大，但是能获得更多样，更统一，更加标准化的渲染效果，适合表达复杂的多媒体内容；Markdown 学习和编辑的难度更小，源文件更简洁直观，但是能实现的功能也更加单一，难以处理复杂的层次结构。Markdown 在标准化方面的表现也不尽人意，渲染效果依赖 css 格式控制，甚至不同 Markdown 编辑器支持的标记也存在差别。因此 Markdown 更加适合比较简单的富文本内容。

另外，虽然 Markdown 编辑器基本都支持在内容中插入 HTML 标签，但是在 HTML 段落中，Markdown 标记的效果可能被屏蔽。例如：

```html
*Actions speaks louder than words.*

**Actions speaks louder than words.**

<html>
Actions speaks louder than words.<br><big>Actions speaks louder than words.</big><br>**Actions speaks louder than words.**
</html>
```
渲染效果：

> *Actions speaks louder than words.*
> 
> **Actions speaks louder than words.**
> 
> <html>
> Actions speaks louder than words.<br><big>Actions speaks louder than words.</big><br>**Actions speaks louder than words.**
> </html>

<br>

因此，在编辑 Markdown 内容时，要注意：尽量减少 HTML 标签的使用；即使不得不使用 HTML 标签，也要注意“统一格式”，避免出现 Markdown 标记和 HTML 标签混搭的段落。

## 2023-01-06

在 Markdown 内容的书写时，有时会遇到文本内容和 Markdown 标记或是 HTML 标签撞车的情况，在这时，可以使用转义符号 \ 来替代一部分内容，并实现破坏原本标签或标记的效果。例如，原本想要呈现**或是<br\>之类的内容，假如直接输入以下内容

```
* aa

* zz

**bb**

下面来介绍一下<br>标签的用法
```

并不能得到与源文件内容中一模一样的结果，而会得到：

> * aa
>
> * zz
>
> **bb**
>
> 下面来介绍一下<br>标签的用法


但假如引入转义字符，就可以规避这种现象：
```
\* aa

\* zz

\*\*bb\*\*

下面来介绍一下<br\>标签的用法
```
效果：

> \* aa
> 
> \* zz
>
> \*\*bb\*\*
>
> 下面来介绍一下<br\>标签的用法
