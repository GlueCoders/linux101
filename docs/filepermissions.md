[Home](/index.html "Home")

If you do `ls -l <filename>` you will see expanded output which tells about the permissions and other attributes of the file.  

```bash
$ ls -l 
> drwxr-xr-x 2 ubuntu ubuntu 4096 Nov 17 14:22 Desktop
```  

The first part in the output `drwxr-xr-x` represents what is the file type and what permissions it has.  

The first attribute is the file type. Rest 9 attributes are permissions for the owner, group and world(other users) giving three attributes to each permission group.  

### File types  

| Attribute | File type     |
| --------- | ------------- |
|    -      | Regular file  |
|    d      | Directory     |
|    l      | Symbolic Link |
|    c      | Character special file|
|    b      | Block special file|  

### Permission attributes  

|Attribute|     On file   | On directory |
| ------- | ------------- | ------------ | 
|    r    |  Read only    | Directory items can be seen |
|    w    |  Writeable    | Files within a directory can be created, deleted, and renamed if the execute attribute is also set|
|    x    |  Executable   | Allows a directory to beentered, e.g., cd directory |  



### Octal Representations of the permissions to be used with chmod command  


|Octal Digit|Permission|  
| --------- | -------- |  
|    0      |    ---   |
|    1      |    --x   |
|    2      |    -w-   |
|    3      |    -wx   |
|    4      |    r--   |
|    5      |    r-x   |
|    6      |    rw-   |
|    7      |    rwx   |  

