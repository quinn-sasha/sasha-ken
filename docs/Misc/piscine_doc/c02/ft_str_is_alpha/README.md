- A function that returns 1 if the string given as a parameter contains only alphabetical characters
- 0 if it contains any other character

- Idea:
	- All alphabets are from A to z: 65 to 122 in ASCII
	- Check if the each character is alphabet or not

```c
int ft_str_is_alpha(char *str)
{
    while (*str++ != '\0') {
        if (*str < 'A' || *str > 'z') {
            return 0;
        }
    }
    return 1;
}
```