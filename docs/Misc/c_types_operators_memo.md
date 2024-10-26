- const (type) (name): variable's value won't change
```c
const char[] // array won't be changed
```

- Type conversions
- Automatic conversions:
	- convert a `narrower` operand into a `wider` one without losing information(e.g int -> float)
- `+`, `*` for 2 different types:  lower type is promoted to the higher' type before operation

- Comparison of signed and unsigned integer
```c
-1L < 1U // 1U promoted to signed long
-1L > 1UL // 1L promoted to unsigned long(positive number)
```

- Char to integer conversion
	- Char can be sign or unsigned
	- If char is signed, sight extension might occur
- Integer to char conversion
	- When an integer is assigned to a char, only the least significant byte (8 bits) of the integer is kept

| ++x                                   | x++                                        |
|---------------------------------------|--------------------------------------------|
| Increments n before its value is used | increments n after its value has been used |
- Shift operation
	- Unsigned: after shifting (right and left), the rest is filled with 0
	- Signed: filled with 1 because of 2's complement