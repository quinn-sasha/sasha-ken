## 1
<https://mypy.readthedocs.io/en/latest/getting_started.html>

>This behavior is actually a fundamental aspect of the PEP 484 type system: when we annotate some variable with a type `T`, we are actually telling mypy that variable can be assigned an instance of `T`, or an instance of a _subtype_ of `T`. That is, `list[str]` is a subtype of `Iterable[str]`.

Tがある任意のタイプを指しているなら、タイプXとした方がその役割に適していると思う。なぜならalgebraでは慣習的にXを利用しており、読者にもわかりやすく伝えられると思う。

## 2
