input: a character as parameter
output: None (print the character)

- Allowed functions: write

```c
void ft_putchar(char c)
```

- `write` function : used to write a data to a file descriptor
- file descriptor:
	- integer represents opened file uniquely
	- Used to identify the file instead of the file name
- Unix input/output: done by reading and writing files

- write function syntax
	- `fd`: file descriptor
	- `*buf`: A pointer to the buffer (character array) containing the data to write
	- `n`: number of bytes to transfer
```c
int n_write = (int fd, char *buf, int n)
```

```c
write(1, &c, 1);
```
- Meaning: write 1 character (1 byte) directly to console using file descriptor 1