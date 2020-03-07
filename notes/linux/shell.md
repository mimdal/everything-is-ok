SHell, bash
-----------
```bash
#! /bin/bash
#! /usr/bin/env bash

login vs non login (interactive)
ssh   --    gui shell

login shels:
1-  global shell run
/etc/profile

if [ -d /etc/profile.d ]; then
  for i in /etc/profile.d/*.sh; do #execute all shell scripts
    if [ -r $i ]; then
      . $i
    fi
  done
  unset i
fi

2- user profile run
only one of these run:
    /etc/USER/.bash_profile
    /etc/USER/.bash_login
    /etc/USER/.profile
    
3- always to set aliases
    /home/USERNAME/.bashrc
    
4- ~/.bash_logout

=========================================

non login
1- /etc/bash.bashrc
2- /home/mim/.bashrc

==========================================

. abc.sh = source abc.sh    #parent could use child export env
./abc.sh                    #env var not send to parent shell

function() {            #call: function "param 1" param2
    echo $1
}

```
