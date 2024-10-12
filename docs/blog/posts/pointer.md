---
date: 2024-10-05
categories:
  - C
  - pointers
---

# Pointers

- Pointer: group of cells that hold

```c
p = &c // & gives address of an object (=c)
```

- `*object`: indirection (dereferencing) operator
  - access the object which pointer points to

```c
int x = 1, y = 10;
int *p; // p is a pointer to int

p = &x // p points to x (=1)
y = *p // x = y = 1
```

- **Every pointer points to a particular object**

```c
int x = 1
int *p; // declaration

p = &x;
*p = *p + 10; // x = x + 10
```

## Pointers-functions

- Using pointers as arguments, you can modify parameters even if c follows call by value rule

```c
f(&a[2]) == f(a + 2)

f(int array[]) == f(int *arr)
```

## Pointers-arrays

- Pointer is almost equal to array except one difference.
- The difference is that pointer is variable so it can be passed as arguments.
- Example

```c
int *pa;
pa = &a[0] // == (pa = a)

&a[i] == a + i
a[i] == *(a + i)

*(pa + i) == a + i
*(pa + i) == pa[i]
```

- String: arrays which contain character

```c
char s[] == char *s
```

```c
cahr message[] // array
char *pmessage // pointer

pmessage = "I am your father" // not a string assignement
// pmessage points to a first element of the char array
// pmessage = &("I am your father"[0])
// char *str  = "hello";
```

reference: C programming language 2d edition
