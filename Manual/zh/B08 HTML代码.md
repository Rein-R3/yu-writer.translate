---
enable html: true
---

# B08 HTML 代码

Yu Writer 允许在 Markdown 文档里嵌入 HTML 代码，以实现某些 Markdown 暂时实现不了的功能，比如为文本设置不同颜色或者字体大小等。

## 启用 HTML 标签解析功能

默认情况下 Yu Writer 是没有启用 HTML 标签解析功能的，因为对于写一般文档或者记事来说，目前的 Markdown 格式基本上满足需要。当如果你是写技术文档、或者写静态博客，则可能希望能解析和渲染 HTML 标签。

你可以在软件的设置里启用 HTML 解析功能，也可以在文档库的属性里，或者文件夹的属性里（此两项功能 0.5.x 尚未完成）设置，甚至可以通过 Front Matter 只设置某篇文档，比如当前这篇文档。只需添加 `enable html: true` 字段即可。

## 支持的 HTML 标签

为安全起见，并不是所有 HTML 标签都支持的，比如 `<script>...</script>` 这种，另外即使是支持的 HTML 标签，也并不是所有属性都支持的。

下面是支持的 HTML 标签：

    ["div", "p", "br", "span", "input", "textarea", "label", "select", "option", "img", "video", "audio", "source"]

一般标签都允许 `class` 和 `style` 两个属性，下面是完整的支持属性列表：

| Tag      | Attributes |
| -------- | ---------- |
| div      |  ["class", "style"] |
| p        |  ["class", "style"] |
| span     |  ["class", "style"] |
| input    |  ["class", "style", "type", "name", "value", "checked"] |
| textarea |  ["class", "style"] |
| select   |  ["class", "style", "name"] |
| option   |  ["class", "style", "value", "selected"] |
| img      |  ["class","style","src","width","height","alt"] |
| video    |  ["class", "style", "width", "height", "src", "poster", "autoplay", "loop", "controls"] |
| audio    |  ["class", "style", "src", "autoplay", "loop", "controls"] |
| source   |  ["src", "type"] |

## 应用示例

### 设置字体的颜色和大小

这是普通的一行文字
<p style="color: red;">这是一行红色的文字</p>
<p style="font-size: 1.5em">设置放大的一行文字</p>

### 插入视频

<video src="$appres/images/example.mp4"></video>

 注：相对路径尚未支持。

## 自定义标签和属性

可以在应用程序配置文件目录里（[点击这里打开]($command:reveal?${runtime.paths.config})）找到应用程序的配置文件 `globalkeybinding.json`，打开编辑并在里面写上你需要的标签以及属性，比如：

```json
[{
  "allowedHtmlTags": ["em"]
  "allowedHtmlAttributes": {
    "em": ["class", "style"]
  }
}]
```

保存并重新运行 Yu Writer 即生效。
