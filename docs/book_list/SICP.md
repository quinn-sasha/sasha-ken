# SICP 


# project

 - To understand how program works,
 - So be versatile to any programming language

By 9/1


# 1.1 Elements of programming language

### Key Ideas

```mermaid
flowchart LR
A[simple idea] --> B[complex idea]
C[simple idea] --> B
D[simple idea] --> B  
```

 1. primitive expressions
 2. means of combination
 3. means of abstraction

The most basic elements of programming language is 'data' and 'procedure'.

```mermaid
flowchart LR
A[procedures] --- B[primitive such as +]
A --- C[compound procedures]
```

### Combination
combination = procedure 
How interpreter evaluates combination?

 - evaluate subexpressions of combination
 - apply operators to the arguments that are resulting values of subexpressions

次に各数値などのprimitive expressionを評価する。
実はoperatorも変数の特殊系みたいなものだと言える。
### Variable
Variable is one of abstraction ways.
It enables us to write more complex programs.
変数を使うために、memoryのどこかに記録しておく。
その場所を'global environment'という。

```scheme
(define size 2)
```
```mermaid
flowchart LR
environment-- determines -->meaning-of-symbol
```
つまり複雑な問題も分解すれば、簡単になる。

### Procedure definitions
手順の複合体に名前をつけること。関数的なイメージ。

```scheme
(define (<name> <parameter>) (<body>))
```

### Applicative-order evaluaion and Normal-order evaluation

How interpreter recognizes your program?

| applicative | normal |
| --- | --- |
| the arguments to procedure must be evaluated before the procedure is applied| the arguments to a procedure aren't evaluated until the values needed|


### Conditional
```scheme
(cond (<p1> <e1>)
	  (<p2> <e2>)
	  ...
	  (<pn> <en>))
```
p: predicate. (T or F)
e: subsequent expression

 - and, or = non procedures. なぜなら式の評価途中で処理が中止され、全ての引数が見られることがないかもしれないから。
 -  not = procedures

> if vs cond

In applicative-order evaluation, cond evaluates all arguments before the procedure. 
However, If firstly checks predicate and only evaluate the one side resulting expression (argument).

### mathematical functions vs computer procedures

| math-function | procedure |
|--|--|
| 物事の特性 | 物事の実行方法 |
| 宣言的知識 | 命令的知識 |
| what is  | how to    |

### procedures as black-box

procedureを構成するサブ手続きをblack boxとして扱うことができる。そのためには各サブ問題のパラメータ名が局所的で他の同じ名前と関係ない状態にあるべき。

限定されている変数をbound variableという。
限定されている範囲をscopeという。
freeはboundと反対の意味を持つ。例えば'+'はfree'。

```mermaid
graph LR
A[procedure] -- independent --> B[bound variable]
A -- dependent --> C[free variable]
```

sqrtを1つにブラックボックス化することで、サブ問題を自由な状態から、限定的な状態にすることができる。block structureという。

Before block structure
```mermaid
flowchart TD
A[sqrt] <-- バラバラ --> B[sqrt-iter]
B <--> C[good-enough?]
C <--> D[improve]
```

After block structure
```
define sqrt
	define improve
	define good-enough?
	define sqrt-iter
```
sqrtの中に閉じ込められることで、サブ問題が局所化した。
またsqrtの引数xは内部範囲内でfree variable化しているので、サブ問題で引数としてxを明示する必要はなくなった。

# 1.2 Procedures and the Processes They Generate

### Linear Recursion vs Iteration

階乗をプログラムで表現する。
$n! = {n(n-1)(n-2)...3 *2*1}$
または
$n! = n * (n-1)!$


Linear recursion process
```scheme
(define (factorial n)  
	(if (= n 1)  
	1  
	(* n (factorial (- n 1)))))
```

linear iterative process
```scheme
(define (factorial n)
  (fact-iter 1 1 n))

(define (fact-iter product counter max-count)
  (if (> counter max-count)
      product
      (fact-iter (* counter product)
                 (+ counter 1)
                 max-count)))
```

| Linear recursion process | linear iterative process |
|--|--|
| nが1増えるにつれて記録しなければならない情報量が1増える。図にしてみると右に出張った2次関数みたいになる。 | nが1増えるにつれてループ中の処理が1つ増える。しかしnの大きさに関係なく、必要とする変数は一定。 |

>iterative processは3つの要素で構成されている。
>固定ルール、固定された数の変数、ループ終了条件。



## バグの見つけ方
手順

 1. オリジナルのプログラムをチェックする
 2. ツールを使い、プログラムの流れを追う
 3. プログラムにチェックポイントを入れる

### デバッグの方針

プログラムを解釈するinterpreterがどのようにプログラムをチェックしていくかを知る必要がある。ここまで、先に部分式を求めるapplicatvie-orderと必要になるまで部分式を求めないnormal-orderを学んだ。
両方の方法に共通しているのが、プログラムが「分解」されていく過程である。

デバッグツールでは、プログラムの流れを掴む助けをしてくれる。
ある式を評価している時点をレベル0として、過去に遡っていくにつれてレベルが1づつ上がるようにする。subproblem levelという。
