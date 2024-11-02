- An iterated function that returns a computation of factorial operation on the given number

```c
int ft_iterative_factorial(int nb)
{
    int i, acc;
    if (nb < 0)
        return 0;
    if (nb == 0)
        return 1;
    acc = 1;
    for (i = 0; i <= nb; ++i)
            acc *= i;
    return acc;
}
```