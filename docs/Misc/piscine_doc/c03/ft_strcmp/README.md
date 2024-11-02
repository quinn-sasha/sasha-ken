- Compares two null-terminated byte strings lexicographically (in alphabetical order)
	- (i.e) It compares two strings character by character
- Input: pointers to the null-terminated byte strings to compare (s1 and s2)
- Output: 
	- Returns 0 if the strings are identical.
	- Returns a positive value if the first different character in s1 is greater than in s2.
	- Returns a negative value if the first different character in s1 is less than in s2.

(Lexicographic ordering: The first difference determines the overall order. Once a difference is found, the rest of the characters don't matter for determining which string comes first.) 
(e.g cat vs category => `\0` vs `e` => cat is shorter)

```c
int ft_strcmp(char *str1, char *str2)
{
    while (*str1 && *str2 && *str1 == *str2) {
        ++str1;
        ++str2;
    }
    return (*(unsigned char *)str1 - *(unsigned char *)str2);
}
```

1. Skip until `*str1` and `*str2` are equal or both of them has next characters.
2. When it encounters difference characters, return the difference of two characters.