- Print all different combinations of three different digits in ascending order

Main idea
```txt
for a = o to 7
	for b = a + 1 to 8
		for c = b + 1 to 9
			print abc
```

```c
#include <unistd.h>

void ft_print_comb(void)
{
    char a, b, c;
    // (ASCII) 0: 48, 7: 55, 9:57
    for (a = '0'; a <= '7'; ++a) {
        for (b = a + 1; b <= '8'; ++b) {
            for (c = b + 1; c <= '9'; ++c) {
                write(1, &a, 1);
                write(1, &b, 1);
                write(1, &c, 1);
                write(1, &", ", 2); // 2: it needs two bytes (2 chars)
            }
        }
    }
}

/*
int main(void) {
    ft_print_comb();
    return 0;
}
*/

```
