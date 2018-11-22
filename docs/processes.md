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

