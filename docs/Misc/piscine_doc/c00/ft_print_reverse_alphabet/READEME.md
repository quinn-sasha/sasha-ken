- Reverse version of `ft_print_alphabet`
- Just print from z to a.

```c
#include <unistd.h>

void ft_print_reverse_alphabet(void)
{
    // z ~ z = 122 7 to 97 in ascii
    for (char c = 122; c >= 97; --c) {
        write(1, &c, 1);
    }
}

/*
int main(void) {
    ft_print_reverse_alphabet();
    return (0);
}
*/
```