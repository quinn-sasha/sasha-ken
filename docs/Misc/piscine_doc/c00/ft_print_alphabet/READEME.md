- Function that prints alphabets from 'a' to 'z' one by one on a single line.
- Alphabets in ASCII:
	- 'a' to 'z': 97 to 122

```c
#include <unistd.h>

void ft_print_alphabet(void)
{
    // a ~ z = 97 to 122 in ascii
    for (char c = 97; c <= 122; ++c) {
        write(1, &c, 1);
    }
}

/*
int main(void) {
    ft_print_alphabet();
    return (0);
}
*/
```


