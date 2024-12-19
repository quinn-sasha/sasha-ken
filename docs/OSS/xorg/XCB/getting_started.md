## [tutorial](https://xcb.freedesktop.org/tutorial/)

- The XCB library gives a low level access to X server
- Lighter than Xlib

| Clinet                   | Server                                            |
| ------------------------ | ------------------------------------------------- |
| Serverに何をするべきかの指示を送信する   | Actually process inputs and client's instructions |
| programだから異なるマシンにいることもある |                                                   |
|                          |                                                   |
- GUI programming model: asynchronous (相手との足並みを揃えないこと) or called event-driven programming 
- XCBのエッセンス (主にXlibとの対比で説明される):
	1. X connection: X serverとのconnection (送受信するメッセージのつらなり)に対するポインターをXCBが提供する
	2. Request/reply: Xlibを介してX serverとやりとりをすると、1つのプロセスが完全に完了するまで次が待つ必要がありとても遅くなる。しかしXCBを使えば、大量のリクエストを連続して送って、その後好きな時にcookie(識別子)を使用して、repleyを受け取れる
	3. Event: XCB recieves event from X server and return a pointer to a `event`'s structure
	4. Graphical context: 

| Xlib                                                                | XCB                                                                                 |
| ------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| Keep a full structure of GC and modify request for the optimization | Minimalist.<br>GC are just simple IDs.<br>Each request is directly sent to X server |
|                                                                     |                                                                                     |



