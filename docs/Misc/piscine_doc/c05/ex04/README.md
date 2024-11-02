- A function returns the n-th element of the Fibonacci sequence

```c
int ft_fibonacci(int index)
{
    int fb_num;
    if (index < 0)
        return (-1);
    if (index == 0)
        return (0);
    if (index == 1)
        return (1);
    else {
        fb_num = ft_fibonacci(index - 2) + ft_fibonacci(index - 1);
    }
    return (fb_num);
}
```
