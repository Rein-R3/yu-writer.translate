---
enable html: true
---

# B08 HTML 程式碼

Yu Writer 允許在 Markdown 文件裡嵌入 HTML 程式碼，以實現某些 Markdown 暫時實現不了的功能，比如為文字設定不同顏色或者字型大小等。

## 啟用 HTML 標籤解析功能

預設情況下 Yu Writer 是沒有啟用 HTML 標籤解析功能的，因為對於寫一般文件或者記事來說，目前的 Markdown 格式基本上滿足需要。當如果你是寫技術文件、或者寫靜態部落格，則可能希望能解析和渲染 HTML 標籤。

你可以在軟體的設定裡啟用 HTML 解析功能，也可以在文件庫的屬性裡，或者資料夾的屬性裡（此兩項功能 0.5.x 尚未完成）設定，甚至可以通過 Front Matter 只設置某篇文件，比如當前這篇文件。只需新增 `enable html: true` 欄位即可。

## 支援的 HTML 標籤

為安全起見，並不是所有 HTML 標籤都支援的，比如 `<script>...</script>` 這種，另外即使是支援的 HTML 標籤，也並不是所有屬性都支援的。

下面是支援的 HTML 標籤：

    ["div", "p", "br", "span", "input", "textarea", "label", "select", "option", "img", "video", "audio", "source"]

一般標籤都允許 `class` 和 `style` 兩個屬性，下面是完整的支援屬性列表：

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

### 設定字型的顏色和大小

這是普通的一行文字
<p style="color: red;">這是一行紅色的文字</p>
<p style="font-size: 1.5em">設定放大的一行文字</p>

### 插入視訊

<video src="$appres/images/example.mp4"></video>

 注：相對路徑尚未支援。

## 自定義標籤和屬性

可以在應用程式配置檔案目錄裡（[點選這裡開啟]($command:reveal?${runtime.paths.config})）找到應用程式的配置檔案 `globalkeybinding.json`，開啟編輯並在裡面寫上你需要的標籤以及屬性，比如：

```json
[{
  "allowedHtmlTags": ["em"]
  "allowedHtmlAttributes": {
    "em": ["class", "style"]
  }
}]
```

儲存並重新執行 Yu Writer 即生效。
