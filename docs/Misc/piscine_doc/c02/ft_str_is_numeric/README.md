-  A function that returns 1 if the string (given as a parameter) contains only
digits, Otherwise 0.

- Idea: Pretty much similar to ft_str_is_alpha function

```c
int ft_str_is_numeric(char *str)
{
    while (*str++ != '\0') {
        if (*str < '0' || *str > '9') {
            return 0;
        }
    }
    return 1;
}
```