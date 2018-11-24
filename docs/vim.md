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
## Save / Undo  
## Cut Copy Paste using single file  
## Open multiple files  
## Cut Copy Paste using multiple files
