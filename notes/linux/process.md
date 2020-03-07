process
--------
```shell

ctrl+C              #exit, kill current ps  
ctrl+Z              #stopped    
command &           #run and send to background, end if bash exit 
nohup command &     #run and send to background, always run
jobs    #show ps that starts in current terminal    
ps      #show all ps     

fg %jobId, bg   #send to background/ forground

kill -num PID   #-9 force exit, -15 default

top         #dynamic real-time view of a running ps
c           #show command
k           #kill ps
shift+M     #sort by memory usage
q           #exit

nice -n 12         #ps priority, بداخلاق -20 < nice < 19  خوش اخلاق
renice -n 12 PID

uptime      #how long the system has been running.

```