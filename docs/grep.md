[Home](/index.html "Home")  

# Grep

Syntax : `grep [options] regex [file...]`


### Options  

|Option|Meaning|
|------|-------|
|-i| Case insensitive match|
|-v| Invert match, prints lines which do not match|
|-c| Count of matches|
|-l| Prints files which have matches|
|-L| Prints files which does not have matches|
|-n| Prefix each matching line with line number from file|
|-h| Multi-file searches, surpresses the output of filenames|
|-E| To use extended regular expressions|


### Metacharacters  

|Metacharacter|Meaning|
|-------------|-------|
| \^ | Anchor, matches regex if it occurs at start. If present in brackets then it means negation |
| $ | Anchor, matches regex if it occurs at end |
| \[] | To give a set of characters to match from, also makes metacharacters to be treated as literals |
| \{} | To express minimum and maximum  number of matches required {n,m} |
| \. | Match any character |
| \\ | To escape a character with special meaning|
| \| | Alternation, gives options of patterns to match from|
| \- | If present in brackets then it defines range|
| \? | Quantifier, match zero or one time|
| \* | Quantifier, match zero or more times|
| \+ | Quantifier, match one or more times|  

### Character classes  

|Character class|Description|
|---------------|-----------|
|\[:alnum:]|The alphanumeric character, \[A-Za-z0-9]|
|\[:word:]|The same as \[:alnum:] with addition of underscore _ character|
|\[:alpha:]|The alphabetic characters, \[A-Za-z]|
|\[:blank:]|Space and tab characters|
|\[:cntrl:]| ASCII control codes 0 to 31 and 127|
|\[:digit:]|The numbers zero to nine|
|\[:graph:]| The visible characters, ASCII 33 to 126|
|\[:lower:]| The lowercase letters|
|\[:punct:]| The punctuation letters|
|\[:print:]| The printable characters, i.e. \[:graph:] plus space character|
|\[:space:]| The whitespace characters including space, tab, carriage return, newline, vertical tab, and form feed|
|\[:upper:]|The uppercase letters|
|\[:xdigit:]|Hexadecimal characters, \[0-9A-Fa-f]|