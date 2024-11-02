- A function that returns the square root of a number

```c
int ft_sqrt(int nb)
{
    int i;

    if (nb == 0)
        return (0);
    if (nb == 1)
        return (1);

    i = 1;
    while ((i * i) <= nb && i < 10000)
    {
        if ((i * i) == nb)
            return i;
        ++i;
    }
    return (0);
}
```

- Square root of number is expected to be positive integer
- Compute square root of number by incrementing 1 by 1
- Ends loop if guess powered by 2 exceeds the target number or the guess becomes too large
