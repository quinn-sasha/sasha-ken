(1)
```c
f        = A[f + 2];
B[g - 2] = (A[f + 4] + A[f + 2]) * 8;
```

(2)
```c
g = 2 * (&A[2]) - 12;
```

(3)

(a)
```assembly
		addi x6, x0, 15
FOR:    blt  x6, x0, DONE
		addi x6, x6, -1
		slli x28, x6, 2
		add  x29, x10, x28
		lw   x5, 0(x29)
		add  x30, x11, x28
		lw   x31, 0(x30)
		sw   x31, 0(x29)
		sw   x5, 0(x30)
		j FOR
DONE:
```

(b)
```assembly
		addi x28, x11, 60
		addi x29, x10, 60
FOR:    blt  x29, x10, DONE
		addi x29, x29, -4
		lw   x5, 0(x29)
		lw   x30, 0(x28)
		sw   x30, 0(x29)
		sw   x5, 0(x28)
		addi x28, x28, -4
		j    FOR
DONE:
```

(c)

- If CPI are same, then the performance depends on instruction counts.

|   | Outside of loop | Inside of loop | counts |
|---|-----------------|----------------|--------|
| a | 1               | 10 * 16 = 160  | 161    |
| b | 2               | 8 * 16 = 128   | 130    |

- Performance(b) / performance(a) = 161 / 130 = 1.24
- Performance of b is improved by 24 % compared to performance a

(4)

(a)
- 0x3ED

(b)
```c
i = 0;
j = 200;
while (i >= 0) {
	j -= 1;
	i += 5;
}
```

(5)

(a)
- number of blocks are 4
```txt
BB1: 0x0080 - 0x0090
BB2: 0x0094 - 0x009C
BB3: 0x00A0 ~ 0x00A4
BB4: 0x00A8 ~ 0x00BC
```

(b)
```txt
0xFFF0 -> 0xFFE8 -> 0xFFE0 -> 0xFFD8 -> 0xFFE0 -> 0xFFE8 -> 0xFF0
```

(c)
```txt
0x0040 (initial) → 0x00A8 (by 0x00A4) → 0x00A8 (by 0x00A4) → 0x00A8 (by 0x00A4) → 0x00A8 (by 0x00B0) → 0x00A8 (by 0x00B0) → 0x0040 (by 0x00B0)
```

(d)
1. `bge x5, x0, 16`
2. jal x1, -36

(6)

(a) 
The new design reduces total cycles from 3.80e9 to 3.78e9. 
Performance improvement = (3.80e9 / 3.78e9) = 1.0053 This means the new design improves performance by 0.53% compared to the original design. 

(b)
Speedup = 3.80e9 / 3.40e9 = 1.12 Performance of the improved system is improved by 12.00% compared to the original system. Improving arithmetic instruction performance by 10 times:
Speedup = 3.80e9 / 3.08e9 = 1.23 Performance of the improved system is improved by 23.00% compared to the original system.
`
(7)
```assembly
addi x7, x0, 0
LOOPI: bge x7, x5, ENDI
addi x29, x0, 0
addi x30, x7, 0
LOOPJ: bge x29, x6, ENDJ
add x31, x30, x29
sw x31, 0(x10)
addi x29, x29, 2
addi x10, x10, 8
jal x0, LOOPJ
ENDJ: addi x7, x7, 1
jal x1, LOOPI
ENDI:
```