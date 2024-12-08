## ch_4 Program Structure

- 外部変数の宣言はタイプを決める。定義はその変数のためにストレージを割り当てる。外部変数は関連する全てのソースファイルの中で、**一度だけ定義**される。"Static variable or function" can be only seen in the file where they are declared. Runtimeの待ち時間(overhead)を避けるためにmacro変数を関数の代わりに使用することがある。ソースファイルを実行する前に、実行するか否かを条件式で決定することができる。大規模プログラムでのヘッダーファイルの存在意義を知った。

## ch-5 Pointers

- 関数に渡された引数の値を変化させるためには、ポインターとして関数に渡す必要がある。多次元配列は、実際一つの配列の各要素が配列になっていることで実現されている。ポインタ配列が多次元配列より優れている点は、多次元配列の行の長さを指定する必要がないこと。
- Storage allocatorの基本的な役割は、サイズに合ったストレージを割り当てることと、割り当てられたストレージを解放すること。スタックを使うことで簡単に実装できる。
- Declarationは通常左から右に適用される。しかし`()`を使うことで適用順番を操作することができる。`void`へのポインターは、どんなタイプのデータを指すことができるから汎用性がある。

## ch-6 Structure

- Struct宣言のみでは新たにストレージを割り当てられることはない。`typedef struct { .. } elem;`と`struct elem { .. };`の違いは、前者では`elem`が変数になったのに対して、後者はstructureのテンプレを宣言しただけということ。また他のファイルに`#include`される場合も前者を使えば、何度も`struct`宣言をしなくて済んで便利。