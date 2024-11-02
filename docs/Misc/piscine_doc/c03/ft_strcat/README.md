- Function appends a copy of string `src` to the end of the string `dest`
- Then add a terminating ‘\0’ 
- The string `dest` must have sufficient space to hold the result
- Output: the pointer `dest`

```c
#include <stdio.h>

char *ft_strcat(char *dest, const char *src)
{
    char *ptr = dest;

    while (*ptr != '\0')
        ptr++;

    while (*src != '\0') {
        *ptr++ = *src++;
    }

    *ptr = '\0';

    return dest;
}

```

