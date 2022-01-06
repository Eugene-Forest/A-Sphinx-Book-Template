# Recommend for Sphinx Book Template

> **文档构建时间: {sub-ref}`today`**

本文章推荐使用 MyST Markdown 作为编写文档的语言。

## 为什么使用 MyST Markdown

虽然 Markdown 无处不在，但它的功能还不足以编写现代的、功能齐全的文档。为此需要一些 Markdown 支持功能，但没有围绕这些功能的各种语法选择的社区标准。

而 Sphinx 是一个用 Python 编写的文档生成框架。它大量使用了 reStructuredText 语法，这是另一种用于编写文档的标记语言。特别是，Sphinx 定义了两个非常有用的扩展点： 内联角色和块级指令。

MyST 试图将 Markdown 的简单性和可读性与 reStructuredText 和 Sphinx 平台的强大功能和灵活性相结合。它以 CommonMark 降价规范为基础，并有选择地添加了一些额外的语法片段以利用 reStructuredText 最强大的部分。

## MyST Markdown、reStructuredText 和 Sphinx 之间的关系

MyST Markdown 提供了与 reStructuredText 语法等效的 Markdown，这意味着您可以在 MyST 中做任何可以用 reStructuredText 做的事情。

Sphinx 文档引擎支持多种不同的输入类型。默认情况下，Sphinx 读取reStructuredText ( .rst) 文件。Sphinx 使用解析器将输入文件解析为它自己的内部文档模型（由核心 Python 项目 docutils 提供）。

MyST 解析器是用于 MyST 降价语言的 Sphinx 解析器。当您使用它时，Sphinx 将知道如何解析包含 MyST Markdown 的内容文件（默认情况下，Sphinx 会假设任何以 结尾的文件.md都是用 MyST Markdown 编写的）。一旦文档被解析为 Sphinx，无论它是用 rST 还是 MyST Markdown 编写的，它的行为都是一样的。

:::
myst markdown (.md) ------> myst parser ---+
                                           |
                                           +-->Sphinx document (docutils)
                                           |
reStructuredText (.rst) --> rst parser ----+
:::
