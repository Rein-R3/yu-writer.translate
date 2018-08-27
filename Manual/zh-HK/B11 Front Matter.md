# B11 Front Matter

Yu Writer 允許為每個文檔設置特有的屬性，用於改變文檔的渲染外觀、設置標籤等。把這些屬性值以 YAML 格式[^1]或者 TOML 格式[^2]寫在文檔的開頭，這段信息則稱為 Front Matter。或者簡單來説，Front Matter 就是文檔的屬性設置。

## 什麼時候用到 Front Matter？

實際上為文檔設置置頂、標籤（Tag）、標識（Flag)、內容摘要、截稿日期、創建時間等信息都是儲存在 Front Matter 的，另外為文檔選擇的文檔樣式、幻燈片樣式也會儲存在 Front Matter 裏。

## Front Matter 語法

Yu Writer 支持 YAML 和 TOML 兩種格式的 Front Matter，為簡化起見，這裏只介紹 YAML 格式的。

首先 Front Matter 必須在文檔的第一行開始寫，由一行 `---` 開始，由同樣內容的一行 `---` 結束。在中間以 `name: value` 這樣的格式記錄着屬性值，下面是一個 Front Matter 的實例：

```yaml
---
pin: true
tags:
  - Foo
  - Bar
flag: yellow
note: 這是內容簡介
due: 2018-07-19
date: 2018-07-12
style: summer
slide style: red
---
```

### 屬性值的數據類型

屬性值可以是布爾型、字符串型、日期時間型以及數組型。當屬性值為字符串類型時，並不需要加單引號或者雙引號。

### 數組類型的屬性值

上例中的 `tags` 屬性值即為數組型，數組的每個元素以相同數量空格和一條橫線表示開始。YAML 規定數組元素也可以寫成一行，比如上例中的 `tags` 可以寫成 `tags: [Foo, Bar]`。為簡化起見，Yu Writer 還允許把 `tags` 的值直接寫成用逗號分隔的一行字符串，比如 `tags: Foo, Bar`。

### 屬性值的名稱

屬性值的名稱可以是空格分開的單詞，也可以寫成 “駝峯風格” 的字符串，比如 `slide style` 可以寫成 `slideStyle`，在 Yu Writer 裏他們是等效的，甚至可以把空格換成橫線或者下劃線，比如 `slide-style` 和 `slide_style`，他們都會被視為相同的屬性名稱。

## 文檔的默認屬性值

Yu Writer 的每篇文檔都有一些默認的屬性值

| 屬性名稱           | 作用 | 默認值 | 可能的值 |
| ----------------- | ---- | ------ | ------- |
| style             | 設置文檔的渲染樣式 | default | ocean，summer... |
| slide style       | 設置文檔幻燈片播放時的樣式 | default | black, red... |
| page orientation  | 設置導出為 PDF 格式文檔時初始的頁面方向 | portrait | landscape |
| page size         | 設置導出為 PDF 格式文檔時初始的頁面尺寸 | A4 | A3, A5, Legal, Letter, Tabloid |

## 屬性值的繼承

屬性值具有繼承特性，文檔的最終屬性 = 應用程序屬性 + 文檔庫的屬性 + 文檔所在的文件夾的屬性。其中由繼承而得而且會影響到文檔渲染結果的屬性有：

| 屬性名稱                       | 作用 | 默認值 |
| ----------------------------- | ---- | ----- | ------- |
| enable ins                    | 允許下劃線格式             | true  |
| enable mark                   | 允許高亮格式               | true  |
| enable footnote               | 允許腳註                  | true  |
| enable task list              | 允許任務列表               | true  |
| enable toc                    | 允許生成目錄               | true  |
| toc level                     | 設置目錄中標題的層級範圍     | 1-3  |
| enable chart                  | 允許圖表                   | true  |
| enable equation               | 允許數學公式                | true |
| enable single dollar equation | 允許使用單美元符號的數學公式 | true  |

需注意的是，繼承鏈末端設置的屬性值會覆蓋前端的屬性值，比如在應用程序、文檔庫、文檔三個地方都設置了 `enable chart` 屬性，則文檔最後的 `chart` 屬性值將會是文檔本身設置的值，因為它處於繼承鏈的最末端。

[^1]: YAML https://en.wikipedia.org/wiki/YAML
[^2]: TOML https://en.wikipedia.org/wiki/TOML