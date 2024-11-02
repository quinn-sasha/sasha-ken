- function that takes a pointer to pointer to pointer to pointer to pointer to pointer to pointer to pointer to pointer to int as a parameter and sets the value "42" to that int

- idea: Apply * operations many times to pointer to change value of the int

```c
void ft_ft(int *********nbr)
{
    *********nbr = 42;
}
```