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

After doing changes in file, press `ESC` and then write `:w`. This will save the file. Note if a filename is given after then it works as save as command though the file opened in the editor would still be the original file that opened.  
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
To paste below the current line, small P : `p`  
To paste above the current line, capital P : `P`  
`y` command just like `d` can be suffixed with cursor movement characters.  

## Joining lines  

To join lines captial j is used : `J`.  

## Search and Replace  

To search a character in the current line `f` command is used. To search for let's say `a` in the current line type `fa`. The cursor will move to next occurrence of a in the line. To continue searching type `;` (semicolon). Note `f` works only for current line and not whole file.  

To search for a word or phrase in whole file `\` is used. After typing `\` type the phrase to be searched. The phrase could also be a regex pattern. The cursor will move to the next occurrence of the found pattern, type `n` to move the next occurrence.  

To search and replace globally, use `:%s/searchtext/replacetext/g`. Lets breakdown this command:  

|Item|Meaning|
|----|-------|
| : | Starts ex command|
| % | Specifies the range of lines for the operation. % denotes whole file.Alternatively the range can be specified as 1,5 or 1,$. If no range is given then operations takes place on current line|
| /searchtext| The phrase to be searched|
| /replacetext| The phrase which will replace search candidates|
| g | global indicator, indicating that operation should take place on every instance of search found. If `g` is not given then only first instance is changed|  

For confirmation on every replacement operation `gc` can be given at the end. It prompts following values:  

|Key|Action|
|---|------|
| y | Perform the substitution|
| n | Skip this instance|
| a | Perform substitution on this instance and on all the next instances|
| q or Esc| Quit substitution|
|  l | Perform this substituion and then exit|
| Ctrl-e, Ctrl-y| Scroll up and down respectively|  


## Open multiple files  

To open multiple files, just give filenames to the vi command as `vi file1.txt file2.txt`. Vi will open all the files given, the list of the files can be confirmed using `:buffers` command. To switch between files `:bufferNumber` command can be used, where `Number` is the position of file in buffers output like `buffer2`. Alternatively `n` can be used to go to next file and `N` to the previous file, `!` can be appeneded to force switch between the files. Note that if the files are added to vi afte vi was already openend then `:n` and `:N` command will not work, only `:buffer` command will work.  
To add file to existing vi session type `:e filename` and that file will be available for editing in vi.  


## Cut Copy Paste using multiple files  

To cut copy paste between multiple files same `y`, `d` and `p` commands can be used. Only after copying text from one file the buffer should be switched to next file using `:buffer` command. To insert whole file in another file `:r` command is used.  