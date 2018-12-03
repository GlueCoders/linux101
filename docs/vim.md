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
`u` command is using for undo operation.  

## Cut Copy Paste using single file  
## Search and Replace  
## Open multiple files  
## Cut Copy Paste using multiple files
