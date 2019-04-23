
# Table of Contents

1.  [Setup](#org7f1fd28)
    1.  [Git cli](#orgbdc8755)
        1.  [Windows](#org8e4dd0c)
        2.  [Mac](#org0bbc50b)
        3.  [Terminal commands](#org24dcc01)
2.  [Repositories](#orgda91ab3)
    1.  [Local](#org9bb03c7)
    2.  [Remotes](#org0566ad5)
        1.  [Setting up remote authentication](#orgad3f557)
        2.  [mac](#orgbd62610)
        3.  [Push a local to a new remote](#orgd23ef3a)
        4.  [Fork](#orgc128ced)
        5.  [Cloning](#org8221807)



<a id="org7f1fd28"></a>

# Setup


<a id="orgbdc8755"></a>

## Git cli


<a id="org8e4dd0c"></a>

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


<a id="org0bbc50b"></a>

### Mac


<a id="org24dcc01"></a>

### Terminal commands

1.  cd

2.  ls

3.  mkdir


<a id="orgda91ab3"></a>

# Repositories


<a id="org9bb03c7"></a>

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


<a id="org0566ad5"></a>

## Remotes


<a id="orgad3f557"></a>

### Setting up remote authentication

[ssh keys](https://git-scm.com/book/en/v2/Git-on-the-Server-Generating-Your-SSH-Public-Key#_generate_ssh_key)

[auto launching agent on git bash](https://help.github.com/en/articles/working-with-ssh-key-passphrases#auto-launching-ssh-agent-on-git-for-windows)


<a id="orgbd62610"></a>

### mac

[agent](https://help.github.com/en/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#adding-your-ssh-key-to-the-ssh-agent)


<a id="orgd23ef3a"></a>

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


<a id="orgc128ced"></a>

### Fork


<a id="org8221807"></a>

### Cloning

