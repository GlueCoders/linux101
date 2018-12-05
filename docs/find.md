[Home](/index.html)  

# Find  

The `find` command is used to search for files in given one or more directories. We can specify several criteria to match required files, these come under tests and operators. We can also perform actions on the found files, appropriately named as actions.  

For eg :  
```bash
$ find ~ -type d
> Desktop 
> Documents
....
```  
In above command `find` is given `home` directory to search from and it only searches for files which are of directory type as defined by `-type d`. Following are some common tests that can be used:  

| Test | Description |
|------|-------------|
| -cmin n | Match files or directories whose content or attributes were modified exactly n minutes ago. To specify less than n minutes ago, use -n and to denote more than n minutes, use +n |
| -cnewer file | Match files or directories whose content or attributes were modified last recently than the given file |
| -ctime n | Match files or directories whose content or attributes were last modified n\*24 hours ago |
| -empty | Match empty files and directories |
| -group name | Match files or directories which belong to given group |
| -iname pattern | Like the -name but case insensitive |
| -inum n | Match files which inode number n, used to find hard links to a particular node |
| -mmin n | Match files or directories whose contents were modified exactly n minutes ago |
| -mtime n | Match files or directories whose contents were modified n\*24 hours ago |
| -name pattern | Match files or directories with the specified wildcard pattern |
| -newer file | Match files or directories whose contents were modified most recently than the given file |
| -nouser | Match files or directories which do not belong to a valid user | 
| -nogroup | Match files or directories which do not match to any valid group |
| -perm mode | Match files or directories that have permissions set to a certain mode, mode can be octal or symbolic expression |
| -samefile name | 	Similar to -inum test, matches the files which share the same inode number as given file |
| -size n | Matches the file of size n |
| -type c | Matches files of type c |
| -user name | Matches the files or directories belonging to given user |  

### Operators

Operators are used to combine several tests and actions together. The operators are basically `and` , `not` and `or`. Parantheses can be added around the tests to group the tests into a larger expression. Example:  

```bash
$ find ~ \(-type f -not -perm 0600 \) -or \( -type d -not -perm 0700 \)
```  







