Assignment1:

Create a script to generate a mearge conflict.
Command – vi conflict.sh
Added below script in that file and run it
#!/bin/bash
touch /home/vagrant/gittest/my_code.sh
git add my_code.sh
echo "echo Hello" > /home/vagrant/gittest/my_code.sh
git commit -am 'initial'
git checkout -b new_branch
echo "echo \"Hello World\"" > /home/vagrant/gittest/my_code.sh
git commit -am 'first commit on new_branch'
git checkout master
echo "echo \"Hello World!\"" > /home/vagrant/gittest/my_code.sh
git commit -am 'second commit on master'
git merge new_branch

Checked git conflict merge by checking that created file (my_code.sh) as output received as:
<<<<<<< HEAD
echo "Hello World!"
=======
echo "Hello World"
>>>>>>> new_branch

 

Create multiple branches and push changes for each branch into remote repo.
Command -  git branch new_branch1
                       git branch new_branch2
                       git branch new_branch3
                       git checkout new_branch1
                       git commit -am “changes to branch1”
                      git checkout new_branch2
                      git commit -am “changes to branch2”
                      git checkout new_branch2
                      git commit -am “changes to branch3”


Create a script to clone remote repo and check out all existing remote branch.
Command – vi clone.sh
Added below script in that file and run it
#!/bin/bash
git clone https://github.com/Amit-Kumar945/git-bootcamp.git
git checkout test
git checkout new_branch
git checkout master

 

Clone a particular folder from a remote repo.
git config core.sparsecheckout true
moved to .git directory and list the files
created sparse-checkout file and Inserted the name of the folder/file which need to clone.
Then ran the command - git clone “path of folder(https://github.com/Amit-Kumar945/git-bootcamp.git)”



Assignment2:
Use both https and SSH protocol to clone your remote repo.
By Https – git clone https://github.com/Amit-Kumar945/git-bootcamp.git
By SSH – first you need to create SSH Key: SSH-keygen -t rsa
                 Add that public key into your github account
                Then copy the SSH URL from your repo and use that URL for cloning.
               Git clone git@github.com:Amit-Kumar945/SSHClone.git
Change your working copy into a cloneable remote repo
Command – git init –bare
                      Vi .git/config
                      Keep “bare = true” instead of false 
Use file system protocol in both local and remote mode (clone from another machine using file protocol) to clone your repo.
Command – git remote add origin /home/vagrant/.git
                       git remote -v 
                       git clone file:///home/vagrant/.git
Ignore backup, swp and pyc file from being committed.
Command – vim /home/vagrant/gittest/.gitignore
                       Put path of swp, pyc and backup file there

Assignment3:

Add remote name parent for ot-training/Jenkins to your own repo.
Command – git remote add origin1 https://github.com/Amit-Kumar945/jenkins.git
                       Git remote rename origin1 parent

                       
Check and verify two remotes.
Command – git remote -v
Git fetch changes from parent repo.
Command – git fetch parent master
Git merge changes into your branch.
Command – git merge parent master
Git pull changes from parent repo.
Command – git pull parent master

Assignment4:
Rename remote name from parent to main
Command – git remote rename parent main
Remove main remote.
Command – git remote remove main 

