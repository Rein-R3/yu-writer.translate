# C05 便携式运行模式

Yu Writer 可以以便携模式（Portable Mode）来运行，便携模式也就是 U 盘运行模式，即程序产生的所有文档、数据及配置皆放在 U 盘的指定的文件夹之内，程序不会对运行它的系统作任何改动、不会写入任何数据。

## 使用场合

便携模式一般用于没有固定计算机可使用的场合，比如有些学生只能在公共机房使用计算机，或者经常需要在几台计算机之间切换，那么可以把 Yu Writer 装进 U 盘里，并且让它运行于便携模式，这样 Yu Writer 的所有设置、文档都可以随身携带了。

## 配置方法

配置便携模式的方法是进入 Yu Writer 应用程序文件夹，用文本编辑器（比如记事本）打开里面的 “bootstrap.config”
文件（对于 Yu Writer macOS 版，这个文件位于 “Yu Writer/Contents/Resources” 之内），把其中的

    "portableMode": false

更改为

    "portableMode": true

完成后可以把 Yu Writer 应用程序文件夹复制到 U 盘，然后再从 U 盘启动 Yu Wrtier 即以便携模式运行。