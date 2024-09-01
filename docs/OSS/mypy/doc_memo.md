# Memo for mypy document

- cheat sheet
  - not need annotate just variables because my can infer data-type from value
  - basic usage: 'type-name'[ 'type-name' ]
  - use | when type could be one of few types
   - e.g) ```x: list[int | str] = [3, 5, 'fun']```
- function
  - ```x: callable[[int, float], float] = f```
  - e.g.) ```def plus(x: int, y: float) -> float: ...```
- yield of int equals to iterator of int:
 	- Iterator[int]
