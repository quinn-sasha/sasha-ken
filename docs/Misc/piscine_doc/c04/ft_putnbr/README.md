- Function that displays the number entered as a parameter
- Display all possible values within an int type variable.

- Idea:
	- use recursive call to split digit
	- and make its type char (small int) from int
	- convert a integer digit to corresponding ascii code

```c
#include <unistd.h>

void ft_putnbr(int nb)
{
    if (nb < 0) {
        write(1, &"-", 1);
        ft_putnbr(-nb);
    } else if (nb > 9) {
        ft_putnbr(nb / 10);
        ft_putnbr(nb % 10);
    } else { // if one digit
        char digit = nb + '0';
        write(1, &digit, 1);
    }
}
```

- Base case: one digit such as 0 to 9.
- Split digit by using `/` `%` operation
- Convert into ascii code by adding `'0'`(48)
- 