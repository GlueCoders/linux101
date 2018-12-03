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

Whenever lost in `vi`, press `ESC` twice and you will find yourself in ex command mode. To exit enter `:q`, semicolon is part of the command. To force exit use `:q!`.

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
| Ctrl - b or Page Up | Up one page | 
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

## Cut Copy Paste using single file  
## Search and Replace  
## Open multiple files  
## Cut Copy Paste using multiple files
