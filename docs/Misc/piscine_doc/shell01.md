## EX01

- 問題文がわかりづらいので言い換えてみる
> Write a command line that will display the list of groups for which the current user is in. The information is contained in the environment variable FT_USER. Format should be separated by commas without spaces.

- Environment variables: variables that are set up in your shell when you log in
- `groups` == `id -nG` : list names of groups which current user are in
- FT_USER is like $USER
- `tr` command: translate characters
	- `tr str1 str2`: translate str1 to str2

```shell
groups $FT_USER | tr ' ' ','
```

## EX02


- `basename, dirname` – return filename or directory portion of pathname

```shell
basename NAME suffix
```

```shell
find [path] [arguments] -exec [command] {} \;
```

```shell
find . -type f -name "*.sh" -exec basename {} .sh \;
```

## EX03

- Find files and directories recursively and count lines of them

## EX04

- What is a mac address?

> MAC addresses are always a 12 digit hexadecimal number, with the numbers separated every two digits by a colon or hyphen


- ifconfig – configure network interface parameters

```shell
ifconfig [-a] [-v] [-s] <interface> [[<AF>] <address>]
```

## EX05

- Tricky problem because the file name contains special characters
- Putting a backslash in front of a special-effect character makes it normal text

```shell
echo -n "42" > \"\\\?\$\*\'MaRViN\'\*\$\?\\\"
```

## EX06

- `ls -l --ignore=pattern` was incorrect
- `nl`: line number filtering
- `sed -i 's/SEARCH_REGEX/REPLACEMENT/g' [INPUTFILE]`
- `sed -n -e '1,2p' -e '5,6p'`: -e enables multiple selections
- `sed -n '1~2p'`: 
	- -n: suppress default printing
	- `1~2` means "start at line 1, then step by 2"

```shell
ls -l | nl | sed -n '1~2p' # works on GNU sed(linux), but not BSD sed(mac os)
ls -l | awk 'NR % 2 == 1' # works on both
```

# EX07

- Problem statement
	- `cat /etc/passwd`
	- removing comments
	- Take every line starting from the second line
	- reverse each login
	- sort in reverse alphabetical order
	- keep only logins between FT_LINE1 and FT_LINE2
	- they must separated by ", "
	- output must end with a "."

**"every other line starting from the second line"**?

- i.e.) Even number
```txt
Line 1 # skip
Line 2 # take
Line 3 # skip
Line 4 # take
...
```

- Structure of each line of `etc/passwd` 
```txt
mark:x:1001:1001:mark,,,:/home/mark:/bin/bash
[--] - [--] [--] [-----] [--------] [--------]
|    |   |    |     |         |        |
|    |   |    |     |         |        +-> 7. Login shell
|    |   |    |     |         +----------> 6. Home directory
|    |   |    |     +--------------------> 5. GECOS
|    |   |    +--------------------------> 4. GID
|    |   +-------------------------------> 3. UID
|    +-----------------------------------> 2. Password
+----------------------------------------> 1. Username
```
- "Reversing each login": login means username in this context.

- FT_LINE1 and FT_LINE2 are environmental variable


