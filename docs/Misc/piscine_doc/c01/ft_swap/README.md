- A function that takes 2 integers whose addresses are entered as parameters and  swaps the values of them.
- Idea: Use indirect operation (`*`) to change values of parameters

```c
void ft_swap(int *a, int *b)
{
    int temp = *a;
    *a = *b;
    *b = temp;
}
```