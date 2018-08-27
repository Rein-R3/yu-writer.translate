# B11 Front Matter

Yu Writer 允许为每个文档设置特有的属性，用于改变文档的渲染外观、设置标签等。把这些属性值以 YAML 格式[^1]或者 TOML 格式[^2]写在文档的开头，这段信息则称为 Front Matter。或者简单来说，Front Matter 就是文档的属性设置。

## 什么时候用到 Front Matter？

实际上为文档设置置顶、标签（Tag）、标识（Flag)、内容摘要、截稿日期、创建时间等信息都是储存在 Front Matter 的，另外为文档选择的文档样式、幻灯片样式也会储存在 Front Matter 里。

## Front Matter 语法

Yu Writer 支持 YAML 和 TOML 两种格式的 Front Matter，为简化起见，这里只介绍 YAML 格式的。

首先 Front Matter 必须在文档的第一行开始写，由一行 `---` 开始，由同样内容的一行 `---` 结束。在中间以 `name: value` 这样的格式记录着属性值，下面是一个 Front Matter 的实例：

```yaml
---
pin: true
tags:
  - Foo
  - Bar
flag: yellow
note: 这是内容简介
due: 2018-07-19
date: 2018-07-12
style: summer
slide style: red
---
```

### 属性值的数据类型

属性值可以是布尔型、字符串型、日期时间型以及数组型。当属性值为字符串类型时，并不需要加单引号或者双引号。

### 数组类型的属性值

上例中的 `tags` 属性值即为数组型，数组的每个元素以相同数量空格和一条横线表示开始。YAML 规定数组元素也可以写成一行，比如上例中的 `tags` 可以写成 `tags: [Foo, Bar]`。为简化起见，Yu Writer 还允许把 `tags` 的值直接写成用逗号分隔的一行字符串，比如 `tags: Foo, Bar`。

### 属性值的名称

属性值的名称可以是空格分开的单词，也可以写成 “驼峰风格” 的字符串，比如 `slide style` 可以写成 `slideStyle`，在 Yu Writer 里他们是等效的，甚至可以把空格换成横线或者下划线，比如 `slide-style` 和 `slide_style`，他们都会被视为相同的属性名称。

## 文档的默认属性值

Yu Writer 的每篇文档都有一些默认的属性值

| 属性名称           | 作用 | 默认值 | 可能的值 |
| ----------------- | ---- | ------ | ------- |
| style             | 设置文档的渲染样式 | default | ocean，summer... |
| slide style       | 设置文档幻灯片播放时的样式 | default | black, red... |
| page orientation  | 设置导出为 PDF 格式文档时初始的页面方向 | portrait | landscape |
| page size         | 设置导出为 PDF 格式文档时初始的页面尺寸 | A4 | A3, A5, Legal, Letter, Tabloid |

## 属性值的继承

属性值具有继承特性，文档的最终属性 = 应用程序属性 + 文档库的属性 + 文档所在的文件夹的属性。其中由继承而得而且会影响到文档渲染结果的属性有：

| 属性名称                       | 作用 | 默认值 |
| ----------------------------- | ---- | ----- | ------- |
| enable ins                    | 允许下划线格式             | true  |
| enable mark                   | 允许高亮格式               | true  |
| enable footnote               | 允许脚注                  | true  |
| enable task list              | 允许任务列表               | true  |
| enable toc                    | 允许生成目录               | true  |
| toc level                     | 设置目录中标题的层级范围     | 1-3  |
| enable chart                  | 允许图表                   | true  |
| enable equation               | 允许数学公式                | true |
| enable single dollar equation | 允许使用单美元符号的数学公式 | true  |

需注意的是，继承链末端设置的属性值会覆盖前端的属性值，比如在应用程序、文档库、文档三个地方都设置了 `enable chart` 属性，则文档最后的 `chart` 属性值将会是文档本身设置的值，因为它处于继承链的最末端。

[^1]: YAML https://en.wikipedia.org/wiki/YAML
[^2]: TOML https://en.wikipedia.org/wiki/TOML