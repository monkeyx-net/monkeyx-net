# Git notes for those new to git!

For some reason I struggled to get my head around git. So I am sharing these notes to help others.

### Have you got a github account?

Starting with the obvious. You need a github account and git hub personal access tokens to able to push content

You also need to install the git tools (gh-cli is a separate install for linux)


### Create a fork of the Portmaster-New repository

Clone the fork from website via this link https://github.com/PortsMaster/PortMaster-New/fork


Clone you fork to your local machine if forked via the web interface

```git clone https://github.com/PortsMaster/PortMaster-New.git```

From the command line fork and clone

```gh repo fork https://github.com/PortsMaster/PortMaster-New.git --clone```

### After forking the repo

After forking the repo, go into the settings for the fork and disable github actions for your fork. 

Actions can be found on the github page under Settings for your forked repo.


### After cloning the repo


First we always do

```git pull``` 

and make sure you're up to date in your repo

### Create a branch for you port

Then we're going to make seperate workspace (branch) for each port

```git checkout -b portname```

After this you are now in a seperate space (branch) . The -b tells it to create a new one. If you want to continue an existing PR do not use the -b
Add your port files to roms/ports/<your port name>

### Check the added port files 

After you finished adding the files do:-

```python3 tools/build_release.py --do-check```

This check will tell you if youre files are in order.
So correctly named, in the wrong folder etc. If this comes up with sucess.
cd into your current ports folder

### The git commit process

cd into the folder ports/your port

```git add .```

This marks the changed files into adding to github.

Next

```git commit```

Before you enter a message, check the file list that is generated in the textfile for anything out of order. Like a 2nd port or something.
After you are confident nothing is wrong. Add your commit message like : New Port: Portname

```git commit -m "New Port Portname"```

Next

```git push```

It'll tell you to push to the branch origin just copy the command it'll tell you.

Well done you made your first push and can now create the Pull Request

NOW IMPORTANT:
If you want to work on a 2nd PR You have to switch back to main or into another branch. 

```git checkout main``` 

to get back to the main repo

Any changes made in the branches will automatically get added to the correspondigng PRs once you push.

So always check in what branch you are. You can also use git status