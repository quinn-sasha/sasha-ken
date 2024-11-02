# Requirement

- Write a function that displays the character passed as a parameter.
- Use only write function

```c
#include <unistd.h>

void ft_putchar(char c)
{
    write(1, &c, 1);
}
```

## Main point: write function

- Unix input/output: done by reading and writing files

- `write` function : used to write a data to a file descriptor
- file descriptor:
	- integer represents opened file uniquely
	- Used to identify the file instead of the file name

### Syntax of write function

```c
int n_write = (int fd, char *buf, int n)
```
- `fd`: file descriptor
- `*buf`: A pointer to the buffer (character array) containing the data to write
- `n`: number of bytes to transfer

### Meaning of the code

```c
write(1, &c, 1);
```
- File descriptor is 1: write directly to console
- What to write: pointer to a target character
- Transfer 1 byte (1 character)