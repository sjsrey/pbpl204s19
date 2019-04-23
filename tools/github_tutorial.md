
# Table of Contents

1.  [Setup](#org760e622)
    1.  [Git bash cli](#orgd5835d1)
        1.  [Windows](#org7ff368a)
        2.  [Mac](#org13afe48)
        3.  [Terminal commands](#orgddaf9f7)
2.  [Repositories](#orgd5d4694)
    1.  [Local](#org76ea439)
    2.  [Remotes](#org2fbecad)
        1.  [Setting up remote authentication](#orgd504536)
        2.  [mac](#org2aa9b0e)
        3.  [Push a local to a new remote](#org5848845)
        4.  [Fork](#org2af7dd4)
        5.  [Cloning](#org6a843fc)



<a id="org760e622"></a>

# Setup


<a id="orgd5835d1"></a>

## Git bash cli

We will rely on the command line client (CLI) to work with git. While this may
seem arcane at first, relative to a more famililar point-and-click interface,
using the command line will have major payoffs for the initial investment. The
key benefits of the cli over a graphical client are:

-   efficiency
-   flexibility
-   portability

We are going to use git-bash as our client on Windows and Mac. 


<a id="org7ff368a"></a>

### Windows

1.  Configuration

    We follow instructions from the
    [Git book](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup)
    
    1.  Start git bash
    
        ![img](figures/gitbashstart.png)
        
        This should open up the console with a git bash shell:
        
        ![img](figures/gitbashterminal.png)
    
    2.  git user config file is:
    
        `C:\Users\$USER\.gitconfig`
        
        where `$USER` is the user name (i.e., serge)
    
    3.  In git bash:
    
            serge@DESKTOP-FA80SDI MINGW64 ~
            $ cat .gitconfig
            [user]
                    name = Serge Rey
                    email = sjsrey@gmail.com
        
        This was after I setup my config with:
        
            $ git config --global user.name "Serge Rey"
            $ git config --global user.email sjsrey@gmail.com
    
    4.  Editor: Notepad ++
    
        [download and install 32-bit version](https://notepad-plus-plus.org/)
        used only for git commit messages
        
        Setup for git commit messages:
        
            git config --global core.editor "'C:/Program Files (x86)/Notepad++/notepad++.exe' -multiInst -nosession"
        
        After this check, check your settings:
        
            $ pwd
            /c/Users/serge/
            
            serge@DESKTOP-FA80SDI MINGW64 ~
            $ cat .gitconfig
            [user]
                    name = Serge Rey
                    email = sjsrey@gmail.com
            [core]
                    editor = 'C:/Program Files (x86)/Notepad++/notepad++.exe' -multiInst -nosession
            
            serge@DESKTOP-FA80SDI MINGW64 ~
        
        Or use git itself to check specific settings:
        
            serge@DESKTOP-FA80SDI MINGW64 ~
            $ git config user.name
            Serge Rey
            
            serge@DESKTOP-FA80SDI MINGW64 ~
            $ git config user.email
            sjsrey@gmail.com


<a id="org13afe48"></a>

### Mac


<a id="orgddaf9f7"></a>

### Terminal commands

1.  cd

2.  ls

3.  mkdir


<a id="orgd5d4694"></a>

# Repositories


<a id="org76ea439"></a>

## Local

-   create a local repository
-   git init
-   edit a file README.md
-   git status
-   demonstrate git add
-   demonstrate git commit
-   using the editor
-   git status
-   

-   fire up spyder
-   create a file saving to the same directory as the repository
-   git status
-   edit in spyder to develop
-   git bash for interfacing with git


<a id="org2fbecad"></a>

## Remotes


<a id="orgd504536"></a>

### Setting up remote authentication

[ssh keys](https://git-scm.com/book/en/v2/Git-on-the-Server-Generating-Your-SSH-Public-Key#_generate_ssh_key)

[auto launching agent on git bash](https://help.github.com/en/articles/working-with-ssh-key-passphrases#auto-launching-ssh-agent-on-git-for-windows)


<a id="org2aa9b0e"></a>

### mac

[agent](https://help.github.com/en/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#adding-your-ssh-key-to-the-ssh-agent)


<a id="org5848845"></a>

### Push a local to a new remote

-   create a remote on github
-   see instructions about pushing a local repositor
-   cut and paste instructions
-   git remote -v
-   git push -u origin master
-   checkout remote repos
-   


-   make a change on the web site
-   git status


<a id="org2af7dd4"></a>

### Fork


<a id="org6a843fc"></a>

### Cloning

