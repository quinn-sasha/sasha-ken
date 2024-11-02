- a function that converts the initial portion of the string pointed by `str` to its int representation
- Determine the if integer is negative or positive from number of `-` signs
- Return integer representation after characters turn into non-digit

```c
int ft_atoi(char *str)
{
    while (*str == ' ')
        str++;
    int sign = 1;
    while (*str == '+' || *str == '-') {
        if (*str == '-') {
            sign = -sign;
        }
        str++;
    }

    int res = 0;
    while (*str >= '0' && *str <= '9') {
        res = res * 10 + (*str - '0');
        str++;
    }

    return sign * res;
}
```