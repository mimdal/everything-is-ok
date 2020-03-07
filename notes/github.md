Set up SSH access to GitHub
---------------------------
```bash
ssh-keygen -t rsa -b 4096 -C "email@gmail.com"   
eval "$(ssh-agent -s)"  #Start the ssh-agent in the background  
ssh-add ~/.ssh/id_rsa   #Add SSH private key to the ssh-agent
```

git tutorial
-----------
```bash
git init    
git add README.md   
git commit -m "first commit"    
git remote add origin git@github.com:user/repo-name.git 
git push -u origin master
```