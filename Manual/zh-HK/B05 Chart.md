---
flag: blue
---
# 圖表

Yu Writer 支持把表格數據以圖表的方式來顯示，目前支持柱型圖、條形圖、折線圖、面積圖、餅型圖、圓環圖等類型。

要把表格以圖表方式顯示，只需在表格上方添加一個 `@chart` 指令即可。

## 柱型圖和條形圖

下面是一個典型的表格，然後在上面空出一行，再在上面輸入 `@chart`。

@chart

| Category   | Series 1 | Series 2 | Series 3 |
| ---------  | -------- | -------- | -------- |
| Category 1 |      4.3 |      2.4 |        2 |
| Category 2 |      2.5 |      4.4 |        2 |
| Category 3 |      3.5 |      1.8 |        3 |
| Category 4 |      4.5 |      2.8 |        5 |

在右側的即時預覽面板或者預覽窗口應該能看到表格以柱型圖的形式顯示。

### 指令參數

Yu Writer 指令允許添加參數，方法是在指令下方使用 `key: value` 的形式添加，比如：

```markdown
@chart
type: column
size: auto
```

也可以把所有參數連接成一行，然後寫在指令後面的括號內（此功能尚未完成），比如：

```markdown
@chart(type=column, size=auto)
```

### chart 指令的通用參數

chart 指令有兩個通用參數，分別是：

#### type

用於指定顯示的圖表類型。

| 值     | 作用               |
| ------ | ----------------- |
| column | 顯示為柱型圖（默認值）|
| line   | 顯示為折線圖        |
| pie    | 顯示為餅型圖        |
| donut  | 顯示為圓環圖        |
| bar    | 顯示為條形圖        |
| area   | 顯示為面積圖        |

#### size

指定圖表顯示的大小。

| 值      | 作用                            |
| ------- | ------------------------------ |
| auto    | 根據顯示區域自動調整圖表大小（默認值）|
| x-large | 顯示為特大圖，約 720 像素          |
| large   | 顯示為大圖，約 600 像素            |
| medium  | 顯示為中等圖，約 480 像素          |
| small   | 顯示為小圖，約 360 像素            |
| x-small | 顯示為特小圖，約 240 像素          |

### 柱型圖和條形圖支持的參數

#### stack

指定是否以堆棧方式來顯示圖表，可選值為 true 和 false，默認值是 false。

#### space

指定柱子之間的間距，值為一個正整數，單位是像素，默認值為 30（柱型圖） 或者 15（條形圖）。如果 stack 參數值為 true，則會忽略此參數。

### 使用指令參數調整柱型圖的外觀的例子

@chart
size: large
space: 20

| Category   | Series 1 | Series 2 | Series 3 |
| ---------  | -------- | -------- | -------- |
| Category 1 |      4.3 |      2.4 |        2 |
| Category 2 |      2.5 |      4.4 |        2 |
| Category 3 |      3.5 |      1.8 |        3 |
| Category 4 |      4.5 |      2.8 |        5 |


### 使用指令參數調整條形圖的外觀的例子

@chart
type: bar
stack: true
size: small

| Category   | Series 1 | Series 2 | Series 3 |
| ---------  | -------- | -------- | -------- |
| Category 1 |      4.3 |      2.4 |        2 |
| Category 2 |      2.5 |      4.4 |        2 |
| Category 3 |      3.5 |      1.8 |        3 |
| Category 4 |      4.5 |      2.8 |        5 |

## 餅型圖和圓環圖

下面是餅型圖的例子：

@chart
type: pie

| Qtr     | Sales |
| ------- | ----- |
| 1st Qtr |   8.2 |
| 2nd Qtr |   3.2 |
| 3rd Qtr |   1.4 |
| 4th Qtr |   1.2 |


下面是圓環圖的例子

@chart
type: donut

| Qtr     | Sales |
| ------- | ----- |
| 1st Qtr |   8.2 |
| 2nd Qtr |   3.2 |
| 3rd Qtr |   1.4 |
| 4th Qtr |   1.2 |

## 折線圖和麪積圖

下面是折線圖的例子：

@chart
type: line

|        | Series 1 | Series 2 |
| ------ | -------- | -------- |
| 1/5/02 |       32 |       12 |
| 1/6/02 |       32 |       12 |
| 1/7/02 |       28 |       12 |
| 1/8/02 |       12 |       21 |
| 1/9/02 |       15 |       28 |

### 折線圖和麪積圖支持的參數

#### point

指定是否顯示拐點，可選值有 true 和 false，默認是 false。

#### smooth: true

指定是否圓滑線條，可選值有 true 和 false，默認值是 false。

### 下面是面積圖的例子

@chart
type: area
point: true
smooth: true

|        | Series 1 | Series 2 |
| ------ | -------- | -------- |
| 1/5/02 |       32 |       12 |
| 1/6/02 |       32 |       12 |
| 1/7/02 |       28 |       12 |
| 1/8/02 |       12 |       21 |
| 1/9/02 |       15 |       28 |

