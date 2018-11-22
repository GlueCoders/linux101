[Home](/index.html "Home")

# All about processes

### Process state 

The `STAT` output in `ps x` command shows the current state of the process.  

```bash 
$ ps x
> PID  TTY   STAT TIME COMMAND	
> 2936 pts/0 R+   0:00 ps x
```  

| State | Meaning|
|-------|--------|
|R|Runing|
|S|Sleeping, waiting for some event like keystroke event or network packet|
|D|Uninterruptible sleep. Waiting for I/O such as a disk drive|
|T|Stopped|
|Z|Zombie process, orphan child process not cleaned up by parent process|
|<|High priority process|
|N|Low priority process|  


### Moving process from backround to foreground and vice-versa

`&` keyword if appended after the command/job, it will start in background.  

```bash
$ xlogo &
> [1] 2943
```  
In output first part is the `jobspec` (jobid) and second part is the `PID`(process id).  To make a foreground job to background following can be done:  

```bash
$ bg %<jobspec>
```  

Running jobs can be viewed using `jobs` command.  

```bash
$ jobs
> [1]+ Running xlogo
```  

`fg` command can be used to move background job to foreground.  

```bash
$ xlogo &
> [1] 2974
$ jobs
> [1]+ Running xlogo
$ fg %1
> xlogo
```

The terminal will wait for signal and until that will not accept any other command. To terminate a foreground job `Ctrl+C` or to stop it `Ctrl+Z` is required.

 

