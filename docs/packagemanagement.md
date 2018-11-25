[Home](/index.html "Home")  

# Package Management  

There are main two flavors of package management  
1. Debian(.deb) - apt, dpkg  
2. Red Hat(.rpm) - yum, rpm  

### Install a Package  

```bash
$ apt-get update
$ apt-get install package_name
```

```bash
$ yum install package_name
```  

To install from a local package file:  

```bash
$ dpkg --install package_file
```  

```bash
$ rpm -i package_file
```  

### Search for a package  

```bash
$ apt-get update
$ apt-cache search package_name
```

```bash
$ yum search package_name
```  

### Update a package  

```bash
$ apt-get update
$ apt-get upgrade
```  

```bash
$ yum update
```  

If upgrading from local package file:  

```bash
$ dpkg --install package_file
```  

```bash
$ yum update package_file
```  

### Remove a package  

```bash
$ apt-get remove package_name
```  

```bash
$ yum erase package_name
```  

### Check status of package  

```bash
$ dpkg --status package_name
$ apt-cache show package_name
$ dpkg --search file_name
```  

```bash
$ rpm -q package_name
$ yum info package_name
$ rpm -qf file_name
```  

### Listing all installed packages  

```bash
$ dpkg --list
```  

```bash
$ rpm -qa
```  
