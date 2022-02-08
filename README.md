# 一个用于快速创建 `Sphinx` 文档的模板

![GitHub issues](https://img.shields.io/github/issues-raw/Eugene-Forest/A-Sphinx-Book-Template)
![GitHub issues closed](https://img.shields.io/github/issues-closed-raw/Eugene-Forest/A-Sphinx-Book-Template)
![GitHub repo size](https://img.shields.io/github/repo-size/Eugene-Forest/A-Sphinx-Book-Template)
![GitHub last commit (branch)](https://img.shields.io/github/last-commit/Eugene-Forest/A-Sphinx-Book-Template/main)
![GitHub](https://img.shields.io/github/license/Eugene-Forest/A-Sphinx-Book-Template)
[![Documentation Status](https://readthedocs.org/projects/a-sphinx-book-template/badge/?version=latest)](https://a-sphinx-book-template.readthedocs.io/zh/latest/?badge=latest)

## `MyST Markdown`

推荐使用 MyST Markdown 作为编写文档的语言。

### 为什么使用 `MyST Markdown`

虽然 Markdown 无处不在，但它的功能还不足以编写现代的、功能齐全的文档。为此需要一些 Markdown 支持功能，但没有围绕这些功能的各种语法选择的社区标准。

而 Sphinx 是一个用 Python 编写的文档生成框架。它大量使用了 reStructuredText 语法，这是另一种用于编写文档的标记语言。特别是，Sphinx 定义了两个非常有用的扩展点： 内联角色和块级指令。

MyST 试图将 Markdown 的简单性和可读性与 reStructuredText 和 Sphinx 平台的强大功能和灵活性相结合。它以 CommonMark 降价规范为基础，并有选择地添加了一些额外的语法片段以利用 reStructuredText 最强大的部分。

### `MyST Markdown` 、 `reStructuredText` 和 `Sphinx` 之间的关系

MyST Markdown 提供了与 reStructuredText 语法等效的 Markdown，这意味着您可以在 MyST 中做任何可以用 reStructuredText 做的事情。

Sphinx 文档引擎支持多种不同的输入类型。默认情况下，Sphinx 读取reStructuredText ( .rst) 文件。Sphinx 使用解析器将输入文件解析为它自己的内部文档模型（由核心 Python 项目 docutils 提供）。

MyST 解析器是用于 MyST 降价语言的 Sphinx 解析器。当您使用它时，Sphinx 将知道如何解析包含 MyST Markdown 的内容文件（默认情况下，Sphinx 会假设任何以 结尾的文件.md都是用 MyST Markdown 编写的）。一旦文档被解析为 Sphinx，无论它是用 rST 还是 MyST Markdown 编写的，它的行为都是一样的。

```
myst markdown (.md) ------> myst parser ---+
                                           |
                                           +-->Sphinx document (docutils)
                                           |
reStructuredText (.rst) --> rst parser ----+
```

## 本地运行环境推荐配置

[`Sphinx`](https://www.sphinx-doc.org/zh_CN/master/index.html) 项目需要 `Python` 环境来支持,在此不对如何安装 `Python` 进行说明。 有需要的可以通过 [Python官网](https://www.python.org/) 单独下载。

### 本机安装 `Sphinx` 和其他必要的包

本机要运行需要向 `Python` 环境中添加一些必要的包，以及提高编写效率的插件包如：`sphinx-autobuild` 。

```powershell
pip install sphinx
pip install myst-parser
pip install sphinx-rtd-theme
pip install sphinx-design
pip install sphinx-autobuild
pip install sphinx-copybutton
```

### 在 `VS Code` 中安装推荐插件

笔者使用 VS Code 编写此项目的，因为 VS Code 提供了我们所需的语法高亮和提示功能。

* `MyST-Markdown VS Code` ： `MyST` 扩展语法高亮
* `reStructuredText` ： 这个扩展为 `Visual Studio Code` 提供了丰富的 `reStructuredText` 语言支持。现在，您可以使用 `VS Code` 提供的优秀的 IDE-like 接口编写 `reStructuredText` 脚本。
* `reStructuredText Syntax highlighting` ：这个扩展为 `reStructuredText` 提供了丰富的语法高亮显示和非侵入式节导航。
* `Markdown All in One` ：`Visual Studio Code` 的 `Markdown` 支持

### 运行和预览

在配置完本地的项目运行环境后，我们就可以运行此项目。由于现有的 `VS Code` 中没有支持 `MyST Markdown` 的预览插件，所以我们选需要通过 `Python` 环境安装 `sphinx-copybutton` 包来支持 `Sphinx` 文档工具的热部署功能。

> 需要注意的是，`sphinx-copybutton` 插件对文档索引的更新没办法做到动态更新，所以如果在对项目文档的目录修改后，会出现不同页面的左侧边栏目录不同的情况。

### 通过 `bash` 终端执行自动构建工具

我们可以通过命令行来执行 autobuild.sh 文件，打开 bash 终端然后直到此项目的根目录( `source` 目录的父目录)，然后执行命令 `$ ./autobuild.sh`。

### 通过 `powershell` 终端执行自动构建工具

我们可以通过命令行来执行 autobuild.bat 文件，打开 bash 终端然后直到此项目的根目录( `source` 目录的父目录)，然后执行命令 `> .\autobuild.sh`。

> 需要优化，即在运行前判断 source 文件夹下是否存在 _build 文件夹，若存在则删除自动构建或预览产生的html等文件


## `Read The Docs` 运行环境推荐配置

我们对 Read The Docs 的配置全部在 `.readthedocs.yaml` 和 `requirements/requirements.txt` 文件中，这些文件的配置会覆盖 Read The Docs 平台中的项目的配置。

## 样板主目录文件 `source/index.md` 和语法运行结果示例文件夹 `source/syntax/..`

参考样板目录文件 `source/index.md` ，我们可以新建一个自定义的目录文件，然后参考示例文件夹编写笔记；当然，也可以使用自己的方式来编写。至于此模板的语法，可以参考示例文件有选择地适用。


