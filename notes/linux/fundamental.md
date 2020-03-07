linux fundamental
-----------------
```bash
lsusb   lspci   lshw
lsmod    rmmod(remove)   modprobe(add)  #kernel module
/etc/modules-load.d/modules.conf #add module.
dmesg   #kernel log

runlevel    #show runlevel
telinit     #change runlevel
shutdown    #os reboot/ shutdown

systemctl enable abc.service    #systemd service manager
systemctl start abc.service
systemctl status abc.service

/etc/apt/sources.list   #package repository config
apt-get install|remove|autoremove jcal
dpkg-reconfigure jcal
dpkg -L jcal #list of directories
aptitude install|remove|search|show jcal

command-1 metaCharacter command-2
;   #always run both
&&  #command-2 only run when command-1 was normal exit
||  #command-2 only run when command-1 was error exit

uname -a #print system information

history, history 20
!!      #run again the last command
!351
ctrl+R  #search inside of history, hit again show next result

man -f copy     #search only in titles
man -k copy     #full search, equal to apropos copy

(ls) = bash; ls; exit

/etc/passwd #all users setting
sudo su -   #root login in interactive bash
```