## Data structure
- Priority queueはsortingよりも特定の優先順位でelementを取り出すことに向いている。
- Selection sortにとって適切なデータ構造はheap。Heap内のitemは優先順位が高いほどrootに近い。
- nodeは最後（右下のnode）を除いて存在しなければならない。
- arrayによる実装では、binary searchはできないので、特定のキーを探すのにO(n)かかる
- Heapにitemを挿入した場合、再帰的に親と優先順位を比べる。もし子の方が優先度が高い場合、2つのノードを入れ替える。
- Heap作成にかかる時間：各挿入は最悪treeのheightを通ることになるから、O(log n)。よってn個のノード挿入はO(n log n)。
-  Heapによるselection sort: Min elementsを抜き出すだけならO(1)。しかしHeapの性質を保つためにO(log n)。よって全てn個の要素を取り出すのにO(n log n)かかる。
- より効果的なheap作成法は、とりあえず全ての要素をぶち込んで、treeのleafから親と子を比べること。Leafはすでに正しいmini heapなので、n / 2個のノードは何もしなくて済む。
- 
## Graph traversal
- 各グラフアルゴリズムよりも、グラフに関する問題に親しむことがより本質的
- Implicit vs explicit: グラフがすでに作られたものである。もしくはtraverseするにつれて構築されるものであるか。
- Adjacency listsが大体の場合、グラフの表現に適切なデータ構造
- Graphにbfsを実行すると、あるtreeができるが、元のグラフのedgeいくつかはtreeに含まれない。
- bfsによって