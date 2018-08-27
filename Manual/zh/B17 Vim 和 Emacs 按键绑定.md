# B17 Vim 和 Emacs 按键绑定

Yu Writer 支持绑定 Vim 和 Emacs 的部分基本按键，对于熟悉 Vim 和 Emacs 的用户可以在 Yu Writer 里继续沿用自己的编辑习惯。

默认情况下应用程序没有启用 Vim 和 Emacs 按键绑定功能，如果需要这项功能，需到应用程序的设置里勾选 ‘Enable base Emacs/Vim key bindings’。

启用这项功能后编辑框并不会立即进入按键绑定状态，因为 Vim 和 Emacs 按键跟 Yu Writer 本身的部分快捷键有冲突，所以 Yu Writer 设定仅当你有需要时再使用快捷键进入绑定状态。

在编辑框里按下：

* `Esc`：用于进入或退出 Vim 按键绑定状态，或者退出 Vim 绑定状态下的插入模式；
* `Ctrl+Esc`：用于进入或退出 Emacs 按键绑定状态。

进入按键绑定状态后，状态栏里会显示绑定的类型（是 Vim 还是 Emacs）以及被按下的按键。

## Emacs 按键绑定

### 移动光标

* `Ctrl + A` 移动到行的开头；
* `Ctrl + E` 移动到行的末尾；
* `Ctrl + B` 往后移动，同左箭头；
* `Ctrl + F` 往前移动，同右箭头；
* `Ctrl + N` 往下移动，同下箭头；
* `Ctrl + P` 往上移动，同上箭头；
* `Alt+F` （暂时使用 `Ctrl + Alt + F` 代替）往前移动一个词，同 `Alt+右箭头`；
* `Alt+B` （暂时使用 `Ctrl + Alt + B` 代替）往后移动一个词，同 `Alt+左箭头`；
* `Ctrl + V` 往下翻一页。

### 删除字符

* `Ctrl + D` 删除光标所在位置的字符；
* `Ctrl + K` 删除一行文字光标之后的字符；
* `Ctrl + T` 交换光标当前位置以及光标之后的一个字符；
* `Ctrl + Y` 粘贴上面删除掉的字符。

## Vim 按键绑定

TODO