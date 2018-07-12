---
flag: blue
---
# A10 收件箱

为方便用户在浏览网页、阅读电子书时收集感兴趣的内容，Yu Writer 自带了一个资料收集工具。

首先在其他应用程序里把感兴趣的内容（可以是文字、图片、表格等）选中并复制到剪贴板，然后按下 Yu Writer 资料收集工具的系统级快捷键，剪贴板里面的内容会被自动保存在 `Inbox（收件箱）` 文档库里，并且会自动转换为 Markdown 格式。

## 全局快捷键

默认的资料收集快捷键是 `Ctrl+Command+V`（在 Windows/Linux 里是 `Ctrl+Alt+V`），这是一个系统级别的全局快捷键，也就是说你可以在任何时候按下它，比如在浏览网页时，在用 Word 编辑文档时、在阅读电子书时等均可按下。

除了使用全局快捷键，你也可以通过点击屏幕右上角状态栏的 Yu Writer 小图标（在 Windows 系统里小图标在屏幕右下角的托盘区里），然后选择 `保存剪贴板内容到收件箱` 来实现相同的操作。

### 修改全局快捷键

可以在应用程序配置文件目录里（[点击这里打开]($command:reveal?${runtime.paths.config})）新建一个名为 `globalkeybinding.json` 的文件，在里面写上你喜欢的快捷键组合，比如：

```json
[{
  "key": "Ctrl+Command+A",
  "command": "save-clipboard-content-to-inbox"
}]
```

保存并重新运行 Yu Writer 即生效。