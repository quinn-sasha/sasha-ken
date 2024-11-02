- A function that displays a string of characters on the standard output.
- What I learned:

```c
char *p = str++; 
char *q = ++str;
```
- `str++`: p gets the original value of str, then str is incremented 
- `++str`: str is incremented first, then q gets the new value of str

```c
#include <unistd.h>

void ft_putstr(char *str)
{
    while (*str != '\0') { // str[n] == *(str + n)
        write(1, str, 1);
        str++;
    }
}
/*
int main()
{
    char *str;
    str = "Shibuya";
    ft_putstr(str);
}
*/
```