# Vim 和 Emacs 按鍵繫結

Yu Writer 支援繫結 Vim 和 Emacs 的部分基本按鍵，對於熟悉 Vim 和 Emacs 的使用者可以在 Yu Writer 裡繼續沿用自己的編輯習慣。

預設情況下應用程式沒有啟用 Vim 和 Emacs 按鍵繫結功能，如果需要這項功能，需到應用程式的設定裡勾選 ‘Enable base Emacs/Vim key bindings’。

啟用這項功能後編輯框並不會立即進入按鍵繫結狀態，因為 Vim 和 Emacs 按鍵跟 Yu Writer 本身的部分快捷鍵有衝突，所以 Yu Writer 設定僅當你有需要時再使用快捷鍵進入繫結狀態。

在編輯框裡按下：

* `Esc`：用於進入或退出 Vim 按鍵繫結狀態，或者退出 Vim 繫結狀態下的插入模式；
* `Ctrl+Esc`：用於進入或退出 Emacs 按鍵繫結狀態。

進入按鍵繫結狀態後，狀態列裡會顯示繫結的型別（是 Vim 還是 Emacs）以及被按下的按鍵。

## Emacs 按鍵繫結

### 移動游標

* `Ctrl + A` 移動到行的開頭；
* `Ctrl + E` 移動到行的末尾；
* `Ctrl + B` 往後移動，同左箭頭；
* `Ctrl + F` 往前移動，同右箭頭；
* `Ctrl + N` 往下移動，同下箭頭；
* `Ctrl + P` 往上移動，同上箭頭；
* `Alt+F` （暫時使用 `Ctrl + Alt + F` 代替）往前移動一個詞，同 `Alt+右箭頭`；
* `Alt+B` （暫時使用 `Ctrl + Alt + B` 代替）往後移動一個詞，同 `Alt+左箭頭`；
* `Ctrl + V` 往下翻一頁。

### 刪除字元

* `Ctrl + D` 刪除游標所在位置的字元；
* `Ctrl + K` 刪除一行文字游標之後的字元；
* `Ctrl + T` 交換游標當前位置以及游標之後的一個字元；
* `Ctrl + Y` 貼上上面刪除掉的字元。

## Vim 按鍵繫結

TODO