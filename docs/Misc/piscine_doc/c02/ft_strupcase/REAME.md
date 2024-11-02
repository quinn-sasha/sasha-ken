- A function that transforms every letter to uppercase

- ASCII code:
	- A = 65
	- a = 97
	- a - A = 32

```c
char *ft_strupcase(char *str)
{
    while (*str != '\0') {
        if ('a' <= *str && *str <= 'z')
            // A <- a - 32
            str = str - 32;
        str++;
    }
    return str;
}
```
