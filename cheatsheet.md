# Vim and Regular Expression Cheatsheet #

----

## Vim

### Opening and closing files ###

To open a file in vim, just type 

```bash
vim <filename>
```

To save and exit files, you must be in command mode (click esc). You must type the `:` before each of the lettered commands.

- **:q** &nbsp;&nbsp;&nbsp;exit editor
- **:w** &nbsp;&nbsp;&nbsp;save changes
- **:wq** &nbsp;save changes and exit editor
- **:q!** &nbsp;&nbsp;&nbsp;force quit editor without saving changes


### Moving through the text ###

- **h** &nbsp;&nbsp;move the cursor to the left
- **l** &nbsp;&nbsp;&nbsp;move it to the right
- **k** &nbsp;&nbsp;move up
- **j** &nbsp;&nbsp;&nbsp;move down
- or use the arrow keys
<br>
- **^** &nbsp;&nbsp;&nbsp;move the cursor to the begnning of the line
- **$** &nbsp;&nbsp;&nbsp;move the cursor to the end of the line
- **gg** &nbsp;move the cursor to the beginning of file
- **G** &nbsp;&nbsp;&nbsp;move the cursor to the end of the file

### Get into Insert Mode ###

- This will allow you to type and make changes just like you would in gedit or similar
- **i** &nbsp;&nbsp;insert mode 

> To exit editing mode, press `ESC` key.

### Editing Text in Command Mode (The Basics) ###

- **dd** &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;will delete current line
- ***n* dd** &nbsp;&nbsp;will delete ***n*** lines including and below current line
- **dw** &nbsp;&nbsp;will delete the word to the right of the cursor
- ***n* dw** &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;will delete ***n*** words to the right of the cursor
- **x** &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;will delete letter highlighted by the cursor 
- **:*n*** &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;go to the ***n***th line in the file.

----

## Regular Expressions

`[abc]` - matches the single characters a,b,c
`[a-z]` - matches the letters in range a-z
`[A-Za-z]` - matches the letters in range a-z or A-Z
`[A-Za-z0-9]` - matches any letter or number

`.` - any single character

`[abc]*` - zero or more of a,b,c (any combination)
`[abc]+` - one or more of a,b,c (any combination)
`(a|b|c)` - a, b, or c

### Examples ###

Ensure a domain ends with .com or .org
```perl
[A-Za-z0-9]+\.(com|org)

[A-Za-z0-9]+ - one or more letters or numbers
\. - the symbol '.'. Must escape it since in regex it has an alternative meaning
(com|org) - domain must end in com or org
```


Validate Java Function Name
```perl
Regex:  [A-Za-z][A-Za-z0-9_]*

[A-Za-z] - first character of function MUST be a letter
[A-Za-z0-9_]* - the characters after the first (if they exist) can be a letter, number, or underscore.
```
