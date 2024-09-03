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
- class
  - `__init__` returns None
  - omit type for `self`
  - To keep class attributes dynamic, override ```__setattr__``` or `__getattr__`
    - above implementation allow assignment to any Class.x if type of value is compatible
- Others
  - reveal_type(`type`) will specify type
  - Use `any` if you want to keep it dynamic
  - `# type: ignore` comment to suppress confusing errors
  - cast:
    - let you override inferred data type of an expression
    - `cast(data_type, expression)`
    - mypy can infer positional-only and keyword-only argument
      - positional-only: `x: int, /`
      - keyword-only: `*, y: int`
- duck types
  - e.g.) iterable, sequence
  - use Io[str] or Io[bytes] for function that uses objects coming from an open() call
- What is decorator function?
  - input: another function
  - output: new function
  - `@decorator_name` above function to apply decorator function

```py
from typing import TypeVar, Callable, Any

# F will be used to represent decorator function
F = TypeVar('F', bound=Callable[..., Any])
```
