# lambda-view

大型项目的 JavaScript 代码很难阅读？试试 lambda-view，它能解析指定的 JavaScript 源代码文件，转换为适合阅读和分析的形式助你度过难关。

## 安装 & 用法

执行下面的命令便能将 lambda-view 安装到你的系统中（执行前请确保您已经安装了[node.js](https://nodejs.org/)）：

```
npm install -g lambda-view
```

然后你就可以执行 lv 命令来分析任何的 JavaScript 文件了：

```
lv /path/somewhere/xyz.js
```

就这么简单！

## 主要优势

lambda-view 的主要目标是用于“阅读代码”，它和你使用的 Sublime Text 或者 Atom 等编辑器不同，lambda-view 没有编辑功能。但它具备如下优势：

* 能够将 JavaScript 源代码的“结构”展现出来，而不仅仅是文本
* 表达式计算顺序通过括号原样呈现出来，能够很容易的看清楚而不会弄错
* 基于 Grammar 的高亮，准确无歧义
* 随心所欲的折叠，不仅是函数块，非常方便
* 转换为单个 Html 文件，无外部依赖，可以在移动端（特别是 ipad 上）方便的阅读代码

## 已知缺陷

lambda-view 还存在下述问题有待修复：

* 对部分 JavaScript 语法的支持还不完整，例如函数默认参数、生成器等
* 对于万行级别 JavaScript 代码文件，转换后的 Html 页面消耗的资源较高，以 jQuery3 slime 为例，在 Chrome 中大致需要消耗超过 150MB 的内存，而微软的 Edge 浏览器则需要超过 400MB 的内存

不过不用担心，我首先会补完对 JavaScript 语法的支持，大概需要两周时间，2016-09-15 日前完成。主要是需要收集一些测试用例（来自 esprima 和 Tachyon 等），并结合 ECMA-262 2016 进行校对。

性能方面，我在设计时已经有所考虑。实际上有一些办法可以大大降低资源消耗。但我会把这项工作推迟一些。因为虽然内存消耗看起来有些吓人，我在实际使用中并未遇到任何问题（使用 Chrome 浏览器）。

## 历史回顾 & 未来计划

我从 2014 年中开始萌生开发 lambda-view 的想法，目的是解决 JavaScript 代码难以阅读的问题，主要是无处不在的嵌套函数让人眩晕。后来我花了一周多写出了第一个粗糙的原型，在这里可以了解我当时的情况：[阅读大型 JavaScript 源码时有什么好用的工具？](https://www.zhihu.com/question/25490540/answer/30883710)

由于工作繁忙，不久后，我就停止继续开发了。我关闭了服务器上的相关页面，只是在自己的计算机上安装了本地版本继续使用。在这两年时间里，早期那个粗糙的 lambda-view 一次又一次帮助我理解了一些复杂项目内部的工作机制。我对它的价值有了新的认识。所以我又萌生出了继续开发的念头。于是这个项目又复活了。

在新的 lambda-view 中我的计划是实现以下目标：

* 利用复杂的布局更充分的展现出 JavaScript 源代码的结构，跳出传统编辑器思维方式
* 能够针对语句、表达式作注解（如 Markdown 格式），把对代码的理解和疑惑与代码结构直接衔接起来，为持续性的研究提供支持
* 对代码本身进行尽可能多的辅助分析，例如变量作用域分析、变量生命周期分析、（有限程度的）类型推导、结构相似性分析等
* 提供一些常用的代码重新工具，例如规范化重写、常量折叠重写、加密变换重写、解密变换重写等
* 必须对移动端提供良好的支持（我非常喜欢在 ipad 上看资料，包括代码）

## 一点思辨

很多程序员是不读代码的。我早先也不喜欢读，主要是读不懂，但是慢慢的越来越喜欢读代码，这已经成了我的一种乐趣。我感觉常常阅读代码的好处很多，但最重要的是有两个：

1. 能够了解到各种不同级别程序员的设计思路，发现别人超越自己的闪光点，让自己保持谦虚的心态
2. 消除对所谓“大型”项目的恐惧心理，让自己不被复杂性吓倒，充满勇气

我是希望大家也能喜欢读代码的。对于那些不读代码，又声称读代码无意义的人，我是反对的。这一点永远也不会变。毕竟不断的学习是我们能取得进步的关键，而阅读代码正是一种非常深入的学习方式，如果只是停留在读文档、读论文、自己埋头写代码而从不读别人的代码的话，我是很怀疑这样的学习方法的。

当然传统上阅读代码确实体验也不佳，所以我很希望 lambda-view 能让大家感觉阅读代码也可以是一件舒服的事情，有更多的人愿意去尝试。那么我会非常开心。

by 林建入 2016年8月29日