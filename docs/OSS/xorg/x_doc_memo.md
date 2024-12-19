
[List of docs](https://www.x.org/wiki/Development/)

# [Building the X Window System from Source](https://wiki.x.org/wiki/Building_the_X_Window_System/#introduction)
- X Window System Concepts
	- X serverはコンピュータのハードウェア(keyboard, display etc.)をサービスとして、複数のプログラム(client)に提供する
	- X can work across a network, so it enables programs on the other computer (client) to display things to your computer (server)
	- XがInputとoutputを実際どのように処理しているかに説明されている。inputの方が実はより複雑で難しい
-  [Building the X Window System from Source](https://wiki.x.org/wiki/Building_the_X_Window_System/#introduction)

# [Xplain: Explaining X11 for the rest of us](http://magcius.github.io/xplain/article/)
- x clientsがx serverにrequestを送り、何かが達成されたらserverからclientにeventが送信される
- 各windowのpixel memoryが存在する必要はない
- 全体のスクリーンに一つの巨大なpixel buffer ("front buffer")を用意し、そのスペースをwindowに貸し出す
- X serverはwindow上のpixelの位置を常に追跡し、各アプリにいつpixelを再描画するかを`Expose` eventを送信して知らせている
- "clip list": 画面に表示されている部分は、一つの画像（長方形）としてではなく、より軽量な長方形のリストとして保存されている
- windowはX serverの"front buffer"上からpixelを借りる長方形でしかない
- windowに何かを表示する方法にはおおまかに2つの方法がある。`background-pixmap` は、表示内容が固定的で変化しない場合に使う。`Expose` eventをappに送って再描画させる方法は、動的で時間と共に変わりやすい場合に使う。
- Front buffer is a also "backing pixmap" but called as "root pixmap". 違いは"front buffer"の場合スクリーンに表示さること。
- As if very redirected window had its own "front buffer" to borrow pixels from
	- 透明な映像を表示するのは、x window systemではなくthird partyの"composing manager"が"backing pixmap"を利用して可能にしてるq

| Normal drawing                                                                         | Redirected drawing                                                                                                                                      |
| -------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Drawing a window directly to the screen by borrowing pixels from parent's windows.<br> | Firstly all drawing operations are sent to a separately created space (backing pixmap). Then drawing a window by borrowing pixels from parent's windows |

まだ読んでない部分：[Regional Geometry](https://magcius.github.io/xplain/article/regions.html)

# 
