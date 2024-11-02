- The `strncmp()` function compares not more than n characters 

- Idea: add the above condition into `strcmp`

```c
int ft_strncmp(char *s1, char *s2, unsigned int n)
{
    while (n > 0) {
        if (*s1 != *s2) {
            return (*(unsigned char *)s1 - *(unsigned char *)s2);
        }
        if (*s1 == '\0') {
            return 0;  // No difference between s1 and s2
        }
        ++s1;
        ++s2;
        --n;
    }
    return 0;
}
```

- If there is difference between `s1` and `s2` , return it immediately
- After end of loop, return 0 (=both are same) because it doesn't compare characters after n