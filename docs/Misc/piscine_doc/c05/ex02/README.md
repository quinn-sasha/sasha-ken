- An iterated function that returns the value of a power applied to a number

```c
int ft_iterative_power(int nb, int power)
{
    int i, acc;
    if (power < 0)
        return (0);
    if (nb == 0)
        return (1);

    acc = 1;
    for (i = 0; i < power; ++i)
        acc *= nb;
    return acc;
}
```

- You shouldn't do `nb = nb * nb` because it will be $nb^2, nb^4, nb^8...$
