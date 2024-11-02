- A recursive function that returns the factorial of the given number

```c
int ft_iterative_factorial(int nb)
{
    if (nb < 0)
        return 0;
    else {
        if (nb == 0)
            return 1;
        else
            return nb * ft_iterative_factorial(nb - 1);
    }
}
```