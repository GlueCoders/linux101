[Home](/index.html "Home")  

# Vi(m) editor  

Vim can be accessed by `vi` command.

## Open a file  

```bash  
$ ls
> foo.txt
$ vi foo.txt
```  
Typing `vi <filename>` opens the editor in terminal.  

## Exit Vi  

Whenever lost in `vi`, press `ESC` twice and you will find yourself in ex command mode. To exit enter `:q`, semicolon is part of the command. To force exit use `:q!`, this can be useful when you have to exit without saving any recent changes made to the file.  

## Cursor Movement  

|Command| Moves the cursor|
|-------|----------------|
| l or Right arrow | Right one character |
| h or Left arrow | Left one character |
| j or Down arrow | Down one line |
| k or Up arrow | Up one line |
| 0 (zero) | To the beginning of the current line |
| ^ | To the first non-whitespace character of the current line |
| $ | To the end of the line |
| w | To the beginning of next word or punctuation character |
| W | To the beginning of next word ignoring punctuation character |
| b | To the beginning of previous word or punctuation characater |
| B | To the beginning of previous word ignoring punctuation character | 
| Ctrl -f or Page down | Down one page | 
| Ctrl -b or Page Up | Up one page | 
| numberG | To line number, as in 2G will take to 2nd line |
| G | To the last line of file|  

## Make a new file  

If vi is opened with a non-existent file, then vi will create that file upon saving.

```bash
$ ls
> 
$ vi foo.txt
```
If foo.txt is saved from vi then it will created.  

## Edit a file  

|Command|Effect|
|-------|------|
| i | Vi enters insert mode, you can start typing at the cursor position |
| a | Vi enters append mode, by which you can start typing at the end of the line. Cursor first should be replaced at the end of line.  `i` does not allow typing at the end of the line |
| A | Vi enters append mode and also the cursor is automatically moved to end of line |
| o | Vi makes a new line below the current line |
| O | Vi makes a new line above the current line |  

## Save / Undo  

After doing changes in file, press `ESC` and then write `:w`. This will save the file.  
`u` command is using for undo operation. Traditional `vi` supports only one undo operation whereas `vim` support multiple undo operations.  

## Deleting  

There are two keywords which are used for deletion in vim: `x` and `d`. `x` deletes one character at a time, and can be preceeded with a number to denote how many characters should be deleted for eg `3x`, `2x`. Pressing `x` multiple times also work. `d` is more general purpose deletion command, also acts like `cut` operation hat keeps text in buffer. `dd` deletes a single line, and it can be preceeded with a number to denote how many lines should be deleted like `3dd` will delete the current and next two lines. `d` can also be suffixed with cursor movement characters (listed in table under Cursor movement heading) to delete a chunk of file. Following are some examples:  

| Command | Deletes |
|---------|---------|
| x | The current character |
| xx | The current and next character |
| 3x | The current and next two characters |
| dd | The current line |
| 5dd | The current and next 4 lines |
| dW | From the current cursor position to the beginning of the next work |
| d$ | From the current cursor position to the end of the line |
| d0 | From the current cursor position to the start of the line |
| d^ | From the current cursor position to the first non whitespace character in the line |
| dG | From the current line to the end of the file |
| d20G | From the current line to the 20th line of the file |  

## Cut Copy Paste using single file  

To cut : `dd`  
To copy : `yy`  
To paste below the current line : `p`  
To paste above the current line : `P`  
`y` command just like `d` can be suffixed with cursor movement characters.  

## Joining lines  

To join lines captial j is used : `J`.  

## Search and Replace  
## Open multiple files  
## Cut Copy Paste using multiple files
