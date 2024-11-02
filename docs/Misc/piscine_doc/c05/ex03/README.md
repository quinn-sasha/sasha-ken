- A recursive function that returns the value of a power applied to a number

```c
int ft_recursive_power(int nb, int power)
{
    int res;
    if (power < 0)
        return (0);
    if (power == 0)
        return (1);
    if (power > 1) {
        res = nb * ft_recursive_power(nb, power - 1);
    }
    return (res);
}
```

- The value of `nb` remains unchanged on recursive step
