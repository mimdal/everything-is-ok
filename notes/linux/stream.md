Streams
-------
```bash
echo $?     #show the return code of last command, 0 for ok

streams:            stdin       stdout      stderr
file description:   0           1           2

stream redirect:
n>      #for override, n=1 is defalt, 1> eq > 
n>>     #for append
&> eq 1> + 2>
2>&1    #redirect 2 to where 1 was redirect
/dev/null   #to mute a stream
0< eq <

here docs: tr ':' '=' <<tamam

command-1 | command-2       #output of one command serves as input to the next

xargs
find . -name "a*" -type f | xargs rm    #delete all files that names start by a

tee #redirect output and always show in console
ls | tee -a file1 file2     #-a for append
```

