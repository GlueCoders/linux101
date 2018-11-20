[Home](/index.html "Home")

# Expansions

### Brace Expressions { }  

This expression supports range in the braces and can take preamble (text that appears before brace expression) and postscript (text that appears after brace expression. It can take number and letters range.   
Syntax: preamble-{range}-postscript    
```bash
$ echo this-{1,2,3}-nice  
> this-1-nice this-2-nice this-3-nice  
```  
Preamble and postscript can itself be a brace expression as :  
```bash
$ echo {1,2}-{3,4}  
> 1-3 1-4 2-3 2-4  
```  

With letters :  
```bash
$ echo z-{a,b,c}-z
> z-a-z z-b-z z-c-z  
```  

Range can also given in form of {a..z} or {1..10} i.e. two dots between bounds(inclusive).  


### Tilde expansion  

This just points to the home directory of the user.  
```bash
$ echo ~  
> /home/ubuntu
```  
In my case ubuntu is the current user.

### Arithmetic expansion  

Syntax: $((expression))  
```bash  
$ echo  $((2+2))
> 4
```  

### Parameter expansion  

Syntax: $PARAMTERNAME  

```bash
$ echo $USER
> ubuntu
```  

### Command substitution  

Syntax: command $(command)  

```bash
$ echo $(ls)
> Desktop Documents Downloads Music Pictures Public Templates Videos
```
Though same output would have come for `ls` also, the point is that you can pass the output of a command to other command using Command substituion.  


### Quoting  

When single quotes are used expansion is not used, the statement is used as it is in the output.  
```bash
$ echo '$USER wont expand'
> $USER wont expand  
```  

When double quotes are used word-splitting, pathname expansion, tilde expansion, and brace expansion are suppressed, but parameter expansion, arithmetic expansion, and command substitution are still carried out.

```bash
$ echo this is a        test
> this is a test
$ echo "this is a       test"
> this is a test
$ echo "$USER will expand"
> ubuntu will expand
```

### Escaping

"\\" can be used to escape expansions in double quotes as shown below:  

```bash
$ echo "The balance for user $USER is : $5.00"
> The balance for ubuntu is .00
```
In above output you can see that `$5` evaluates to nothing and hence only `.00` is printed. Using escape characters this can be fixed.  

```bash
$ echo "The balance for user $USER is : \$5.00"
> The balance for ubuntu is $5.00
```  

