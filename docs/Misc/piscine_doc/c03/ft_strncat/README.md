- The strncat() function appends not more than n characters from `src`, and then adds a terminating ‘\0’.

```c
#include <stdio.h>

char *ft_strcat(char *dest, const char *src, unsigned int nb)
{
    char *ptr = dest;

    while (*ptr != '\0')
        ptr++;

    while (*src != '\0' && nb > 0) {
        *ptr++ = *src++;
        --nb;
    }

    *ptr = '\0';

    return dest;
}
```