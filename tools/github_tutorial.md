
# Table of Contents

1.  [Setup](#orgd996388)
    1.  [Git bash cli](#org2baeb43)
        1.  [Windows](#orgb057b6e)
        2.  [Mac](#org1626deb)
        3.  [Terminal commands](#orgf9e2a00)
2.  [Repositories](#orgacf8136)
    1.  [Initializing a local git repository](#org33f03ee)
    2.  [Status](#orgb96df27)
    3.  [Adding a file](#orgd18e140)
    4.  [Commiting](#org867c7c3)
    5.  [Edit-add-commit cycle](#orgad644a8)
    6.  [Remotes](#orgfc9548f)
        1.  [Setting up remote authentication](#orge562f1a)
        2.  [mac](#org118a77c)
        3.  [Push a local to a new remote](#org005d9ac)
        4.  [Fork](#org4f3ea0a)
        5.  [Cloning](#orgd6cb3e4)



<a id="orgd996388"></a>

# Setup


<a id="org2baeb43"></a>

## Git bash cli

We will rely on the command line interface (CLI) to work with git. While this may
seem arcane at first, relative to a more famililar point-and-click interface,
using the command line will have major payoffs for the initial investment. The
key benefits of the cli over a graphical client are:

-   efficiency
-   flexibility
-   portability

We are going to use git-bash as our CLI client on Windows. We then will setup a cli
for Mac after configuring Windows. 


<a id="orgb057b6e"></a>

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


<a id="org1626deb"></a>

### Mac

1.  Configuration


<a id="orgf9e2a00"></a>

### Terminal commands

Once we have the command line client setup, we are at a bash prompt on either
Windows or Mac, and the commands will all be the same (with the exception of
the editor if we are using one to create the git commit messages-more below).

Some common bash commands to become familiar with include:

1.  finding out current directory: `pwd`

        serge@DESKTOP-FA80SDI MINGW64 ~
        $ pwd
        /c/Users/serge/
        
        serge@DESKTOP-FA80SDI MINGW64 ~

2.  listing contents of current director: `ls`

        serge@DESKTOP-FA80SDI MINGW64 ~
        $ ls
        '3D Objects'/
         Anaconda3/
         AppData/
        'Application Data'@
         Contacts/
         Cookies@
         Desktop/
         Documents/
         Downloads/
         Dropbox/
         Favorites/
         Links/
        'Local Settings'@
         MicrosoftEdgeBackups/
         Music/
        'My Documents'@
         NetHood@

3.  moving to a directory: `cd`

        serge@DESKTOP-FA80SDI MINGW64 ~
        $ cd Documents/
        
        serge@DESKTOP-FA80SDI MINGW64 /c/Users/serge/Documents
        $ pwd
        /c/Users/serge/Documents
        
        serge@DESKTOP-FA80SDI MINGW64 /c/Users/serge/Documents
    
    Note that `cd` without an argument will take you back to your home directory.
    
    Also note that `clear` will clear the terminal.

4.  making a directory: `mkdir`

    We will create a directory for our course work.
    
        serge@DESKTOP-FA80SDI MINGW64 /c/Users/serge/Documents
        $ mkdir courses
        
        serge@DESKTOP-FA80SDI MINGW64 /c/Users/serge/Documents
        $ ls
         ArcGIS/                                       courses/       'My Videos'@
        'ArcGIS 10.5.1'/                               desktop.ini     p/
        'ArcGIS Pro 2.2'/                             'My Music'@
         ArcGISDesktopAdvanced_SingleUse_690779.prvc  'My Pictures'@
        
        serge@DESKTOP-FA80SDI MINGW64 /c/Users/serge/Documents
        $ cd courses
        
        serge@DESKTOP-FA80SDI MINGW64 /c/Users/serge/Documents/courses
        $ pwd
        /c/Users/serge/Documents/courses
        
        serge@DESKTOP-FA80SDI MINGW64 /c/Users/serge/Documents/courses
        $ mkdir pbpl204w19
        
        serge@DESKTOP-FA80SDI MINGW64 /c/Users/serge/Documents/courses
        $ ls
        pbpl204w19/
        
        serge@DESKTOP-FA80SDI MINGW64 /c/Users/serge/Documents/courses
        $

5.  Shell tips

    There are a number of handy features in the shell that can save us time.
    
    1.  History
    
        Using the up arrow key, we can recall the history of things we have done to
        recall a command we want to repeat (or edit). Each time we up-arrow we go back
        in the history one step. If you are on the command you want, you can hit
        `Enter` to execute that command. If you overshoot with the up arrow key, use
        the down arrow key to go in the other direction.
        
        You can also use the `history` command to get a listing of what you have done:
        
             242  cd git_tutorial/
              243  ls
              244  git status
              245  git remote -v
              246  git pull origin master
              247  ssh -v snuc
              248  emacs -nw
              249  exit
              250  pwd
              251  ls
              252  clear
              253  ls
              254  cd Documents/
              255  pwd
              256  ls
              257  cd courses/
              258  ls
              259  rmdir -f pbpl204s19/
              260  rm -f pbpl204s19/
              261  rm -fr pbpl204s19/
              262  ls
              263  clear
              264  cd ..
              265  clear
              266  rm -rf courses
              267  clear
              268  ls
              269  mkdir courses/pbpl204s19
              270  clear
              271  mkdir courses
              272  ls
              273  cd courses
              274  pwd
              275  mkdir pbpl204w19
              276  ls
              277  history
            
            serge@DESKTOP-FA80SDI MINGW64 /c/Users/serge/Documents/courses
            $
        
        So `history` was the last thing I did. If I want to use `pwd`, for example, I
        can use `!274` and `Enter` to repeat the command:
        
              274  pwd
              275  mkdir pbpl204w19
              276  ls
              277  history
            
            serge@DESKTOP-FA80SDI MINGW64 /c/Users/serge/Documents/courses
            $ !274
            pwd
            /c/Users/serge/Documents/courses
            
            serge@DESKTOP-FA80SDI MINGW64 /c/Users/serge/Documents/courses
            $
    
    2.  Tab completion
    
        We can also make use of the `Tab` key to save us some typing. We have
        previously created the directory `pbpl204w19` but haven't yet changed into it
        as we are currently in its parent folder. We could get into that directory
        using `cd pbpl204w19` but that is too much typing. Instead use `cd pb<TAB>`
        where `<TAB>` means use the tab key to complete the typing:
        
            serge@DESKTOP-FA80SDI MINGW64 /c/Users/serge/Documents/courses
            $ cd pbpl204w19/
        
        Then `Enter`:
        
            $ cd pbpl204w19/
            
            serge@DESKTOP-FA80SDI MINGW64 /c/Users/serge/Documents/courses/pbpl204w19
            $ pwd
            /c/Users/serge/Documents/courses/pbpl204w19
            
            serge@DESKTOP-FA80SDI MINGW64 /c/Users/serge/Documents/courses/pbpl204w19
            $


<a id="orgacf8136"></a>

# Repositories

Next we will set up a git repository in our new directory. Repositories are
where the files for our project will reside, and where git keeps track of the
history of all files in the project.

Let us create a new directory for our project (good practice is to have one git
repository for each project, rather than one repository to hold many projects).

    serge@DESKTOP-FA80SDI MINGW64 /c/Users/serge/Documents/courses/pbpl204w19
    $ mkdir gittutorial
    
    serge@DESKTOP-FA80SDI MINGW64 /c/Users/serge/Documents/courses/pbpl204w19
    $ cd gittutorial/
    
    serge@DESKTOP-FA80SDI MINGW64 /c/Users/serge/Documents/courses/pbpl204w19/gittutorial


<a id="org33f03ee"></a>

## Initializing a local git repository

So far we have a new directory, but not a respository. We will initialize the
repository with `git init`

    serge@DESKTOP-FA80SDI MINGW64 /c/Users/serge/Documents/courses/pbpl204w19/gittutorial
    $ git init
    Initialized empty Git repository in C:/Users/serge/Documents/courses/pbpl204w19/gittutorial/.git/

The directory `.git` is where all the bookkeeping is done by git. We need not
go in there, but it is good to know what it is.


<a id="orgb96df27"></a>

## Status

Anytime we want to see what the status of our repository is we use `git status`:

    $ git status
    On branch master
    
    No commits yet
    
    nothing to commit (create/copy files and use "git add" to track)

This tells us we are on the `branch` called `master`. More on branches later,
but for now, you can think of a branch as a version of the project repository.

The other output from the `status` command is that we have nothing to commit so
we may want to add files to our project.


<a id="orgd18e140"></a>

## Adding a file

First we need to create a file, then add it to the repository.

Open up `spyder` and create a file *in this directory* called `README.md`.

![img](figures/spydereditreadme.png)

Then edit the file to have the first line be:

    # Git and github tutorial
    
    Notes on using git and github for PBPL204

so that your editor should look something like:

![img](figures/spyderreadme.png)

Now that file is a simple text file that uses [Markdown](<https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet>) syntax that is
rendered on github nicely (and used to build webpages everywhere).

If we check the status of our repository now:

    $ git status
    On branch master
    
    No commits yet
    
    Untracked files:
      (use "git add <file>..." to include in what will be committed)
    
            README.md
    
    nothing added to commit but untracked files present (use "git add" to track)

we see that the new file `README.md` shows up under *Untracked files*. This
means it is not tracked by the repository, but rather is in the folder where
the other files in our repository reside. 

We can add the file to our repository with `git add`:

    serge@DESKTOP-FA80SDI MINGW64 /c/Users/serge/Documents/courses/pbpl204w19/gittutorial (master)
    $ git add README.md
    
    serge@DESKTOP-FA80SDI MINGW64 /c/Users/serge/Documents/courses/pbpl204w19/gittutorial (master)

Now check the status again:

    $ git status
    On branch master
    
    No commits yet
    
    Changes to be committed:
      (use "git rm --cached <file>..." to unstage)
    
            new file:   README.md
    
    
    serge@DESKTOP-FA80SDI MINGW64 /c/Users/serge/Documents/courses/pbpl204w19/gittutorial (master)

and we see the file `README.md` has changes that can be committed. This means
the file is now being tracked by git (since we just added it).
Technically speaking, the file has been *stagged* and is ready for *commiting*.
The stagging area holds changes we have made to a file in the respository, but
those changes have not yet been commited to the repository.
The stage allows us to make a bunch of changes to a file before we do a commit.


<a id="org867c7c3"></a>

## Commiting

We now are in a position to commit our changes in the file to the respository.
We use `git commit` for this:

    serge@DESKTOP-FA80SDI MINGW64 /c/Users/serge/Documents/courses/pbpl204w19/gittutorial (master)
    $ git commit

which should bring up Notepadd++ that we configured above to edit our commit
message. Below the lines beginning with `#` add a commit message so your editor
looks like:

![img](figures/commitmessage.png)

Save the file (`<CTRL-s>`) and quit notepad++ and you should see:

    serge@DESKTOP-FA80SDI MINGW64 /c/Users/serge/Documents/courses/pbpl204w19/gittutorial (master)
    $ git commit
    [master (root-commit) 9440660] My first commit.
     1 file changed, 3 insertions(+)
     create mode 100644 README.md
    
    serge@DESKTOP-FA80SDI MINGW64 /c/Users/serge/Documents/courses/pbpl204w19/gittutorial (master)
    $

Recheck the status of the repository:

    serge@DESKTOP-FA80SDI MINGW64 /c/Users/serge/Documents/courses/pbpl204w19/gittutorial (master)
    $ git status
    On branch master
    nothing to commit, working tree clean
    
    serge@DESKTOP-FA80SDI MINGW64 /c/Users/serge/Documents/courses/pbpl204w19/gittutorial (master)
    $

So we have nothing to commit, and our working tree is clean. All good.

We can get a look at what git knows about our respository using `git log`:

    $ git log
    commit 94406606f5b2f20a0abf290a0b916308aa4ac0e2 (HEAD -> master)
    Author: Serge Rey <sjsrey@gmail.com>
    Date:   Tue Apr 23 10:14:29 2019 -0700
    
        My first commit.
    
    serge@DESKTOP-FA80SDI MINGW64 /c/Users/serge/Documents/courses/pbpl204w19/gittutorial (master)
    $

Note that our commit message `My first commit` shows up in the log. So it is
good practice to write meaningful commit messages as they can help you remember
the purpose of the changes you made at that point in the project.


<a id="orgad644a8"></a>

## Edit-add-commit cycle

Now that we have the file `README.md` under version control we can continue on
working on the project and getting use to the general workflow.

Continue to edit the file in `spyder`, adding the two additional lines:

![img](figures/spyderedits.png)
and save. Then check the status of our repository:

    serge@DESKTOP-FA80SDI MINGW64 /c/Users/serge/Documents/courses/pbpl204w19/gittutorial (master)
    $ git status
    On branch master
    Changes not staged for commit:
      (use "git add <file>..." to update what will be committed)
      (use "git checkout -- <file>..." to discard changes in working directory)
    
            modified:   README.md
    
    no changes added to commit (use "git add" and/or "git commit -a")
    
    serge@DESKTOP-FA80SDI MINGW64 /c/Users/serge/Documents/courses/pbpl204w19/gittutorial (master)

Our file has been modified by the edits we just made. These changes have not
yet been stagged or committed to the repository. This is ok as we might want to
continue making changes, we don't have to immediately stage all changes - we
can accumulate a bunch related to one task/section and then add.

For now let's stage these with `git add`:

    serge@DESKTOP-FA80SDI MINGW64 /c/Users/serge/Documents/courses/pbpl204w19/gittutorial (master)
    $ git add README.md
    
    serge@DESKTOP-FA80SDI MINGW64 /c/Users/serge/Documents/courses/pbpl204w19/gittutorial (master)

and check the status

    $ git status
    On branch master
    Changes to be committed:
      (use "git reset HEAD <file>..." to unstage)
    
            modified:   README.md
    
    
    serge@DESKTOP-FA80SDI MINGW64 /c/Users/serge/Documents/courses/pbpl204w19/gittutorial (master)
    $

so now the file is stagged, but not committed. 

We can now commit the changes, but we will do so in a way that shorcuts adding
the commit message without having to use Notepad++. We do this with:

    $ git commit -m 'More edits to README.md'
    [master 27388d9] More edits to README.md
     1 file changed, 3 insertions(+)
    
    serge@DESKTOP-FA80SDI MINGW64 /c/Users/serge/Documents/courses/pbpl204w19/gittutorial (master)
    $

The `-m` flag tells git what follows between the single pair of `` ` `` characters
is our commit message. So no need for firing up an editor to get the commit
message added.

And, we can always check the log to see our history:

    $ git log
    commit 27388d99e35ab4188794ec18cc3ea59f5c0d3fd7 (HEAD -> master)
    Author: Serge Rey <sjsrey@gmail.com>
    Date:   Tue Apr 23 10:58:21 2019 -0700
    
        More edits to README.md
    
    commit 94406606f5b2f20a0abf290a0b916308aa4ac0e2
    Author: Serge Rey <sjsrey@gmail.com>
    Date:   Tue Apr 23 10:14:29 2019 -0700
    
        My first commit.


<a id="orgfc9548f"></a>

## Remotes


<a id="orge562f1a"></a>

### Setting up remote authentication

[ssh keys](https://git-scm.com/book/en/v2/Git-on-the-Server-Generating-Your-SSH-Public-Key#_generate_ssh_key)

[auto launching agent on git bash](https://help.github.com/en/articles/working-with-ssh-key-passphrases#auto-launching-ssh-agent-on-git-for-windows)


<a id="org118a77c"></a>

### mac

[agent](https://help.github.com/en/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#adding-your-ssh-key-to-the-ssh-agent)


<a id="org005d9ac"></a>

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


<a id="org4f3ea0a"></a>

### Fork


<a id="orgd6cb3e4"></a>

### Cloning

