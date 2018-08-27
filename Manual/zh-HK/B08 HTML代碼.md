---
enable html: true
---

# B08 HTML 代碼

Yu Writer 允許在 Markdown 文檔裏嵌入 HTML 代碼，以實現某些 Markdown 暫時實現不了的功能，比如為文本設置不同顏色或者字體大小等。

## 啟用 HTML 標籤解析功能

默認情況下 Yu Writer 是沒有啟用 HTML 標籤解析功能的，因為對於寫一般文檔或者記事來説，目前的 Markdown 格式基本上滿足需要。當如果你是寫技術文檔、或者寫靜態博客，則可能希望能解析和渲染 HTML 標籤。

你可以在軟件的設置裏啟用 HTML 解析功能，也可以在文檔庫的屬性裏，或者文件夾的屬性裏（此兩項功能 0.5.x 尚未完成）設置，甚至可以通過 Front Matter 只設置某篇文檔，比如當前這篇文檔。只需添加 `enable html: true` 字段即可。

## 支持的 HTML 標籤

為安全起見，並不是所有 HTML 標籤都支持的，比如 `<script>...</script>` 這種，另外即使是支持的 HTML 標籤，也並不是所有屬性都支持的。

下面是支持的 HTML 標籤：

    ["div", "p", "br", "span", "input", "textarea", "label", "select", "option", "img", "video", "audio", "source"]

一般標籤都允許 `class` 和 `style` 兩個屬性，下面是完整的支持屬性列表：

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

## 應用示例

### 設置字體的顏色和大小

這是普通的一行文字
<p style="color: red;">這是一行紅色的文字</p>
<p style="font-size: 1.5em">設置放大的一行文字</p>

### 插入視頻

<video src="$appres/images/example.mp4"></video>

 注：相對路徑尚未支持。

## 自定義標籤和屬性

可以在應用程序配置文件目錄裏（[點擊這裏打開]($command:reveal?${runtime.paths.config})）找到應用程序的配置文件 `globalkeybinding.json`，打開編輯並在裏面寫上你需要的標籤以及屬性，比如：

```json
[{
  "allowedHtmlTags": ["em"]
  "allowedHtmlAttributes": {
    "em": ["class", "style"]
  }
}]
```

保存並重新運行 Yu Writer 即生效。
