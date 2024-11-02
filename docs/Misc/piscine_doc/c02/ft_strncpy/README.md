- A function copy at most `n` characters from `src` into `dest`.  
- If src is less than `n` characters long, the remainder of `dest` is filled with `\0` characters. 
- Otherwise, `dest` is not terminated.
- Return dest

- Idea:
	- Pretty much similar to ft_strcpy
	- Just handle the case which  length of `src` < `n`

```c
char *ft_strncpy(char *dest, const char *src, unsigned int n)
{
    unsigned int i;
    for (i = 0; src[i] != '\0' && i < n; ++i) {
        dest[i] = src[i];
    }
    for (; i < n; ++i) {
        dest[i] = '\0';
    }
    return dest;
}
```
