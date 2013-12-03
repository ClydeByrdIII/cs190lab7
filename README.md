cs190 Lab 7 - Using Vim and Regular Expressions
=========

The purpose of this lab is for you to learn how to use vim as a text editor and to familiarize the student
with Regular Expressions.

Before starting the lab, please navigate to [the lecture material](https://docs.google.com/presentation/d/1mm5oDlTgyXVmkHaTHhWeHtDz9cT-MoGLzLolqzNGFEs/edit?usp=sharing) and make sure you have a basic understanding of Vim and regular expression. You can also look at [this website](http://www.fprintf.net/vimCheatSheet.html) because for a detailed cheatsheet for Vim.

## Setup ##

Depending on your working environment, perform the appropriate action:

| Environment   | Action        |
| ------------- | ------------- |
| Linux Lab Machine            | Open a terminal window        |
| Windows or Personal Computer | SSH into `data.cs.purdue.edu`*  |

----

\* You must have X11 forwarding enabled. If you are on the Windows Lab Computer, follow the instructions below:

1. Search for 'Xming' in the start menu and run it.
2. Open PuTTy
3. Expand the 'SSH' tab from the 'Category' list
4. Choose 'X11' from 'SSH' list
5. Check 'Enable X11 Forwarding'
6. Connect like normal to `data.cs.purdue.edu` within PuTTy.

## Required Vim Setup ##

You need to download a sample .vimrc to make using Vim a little easier.

```bash
# NOTE: Don't do this if you already have a .vimrc customized to your liking!!!

wget https://raw.github.com/ClydeByrdIII/cs190lab7/master/.vimrc ~/.vimrc
```

----

## Downloading and Opening the cs190lab7 Directory ##

1. Copy the Clone URL under the `HTTPS clone URL` label (right side of page).
2. In your home directory, type the terminal command

    ```bash
    git clone https://github.com/ClydeByrdIII/cs190lab7.git ~/cs190lab7
    ```

3. A directory named `cs190lab7` appeared in your home directory (if that was your working directory).
    

## Part 1 - Editing a file with vim ##

```bash
# cd into the lab repository
cd ~/cs190lab7
```

Inside ~/cs190lab7 there should be three files a README.md, toEdit.txt, and a .vimrc.

For part one we will edit toEdit.txt with Vim in order to familiarize ourself with the editor.

Here are some useful commands for this lab
![navigation in vim](http://i.imgur.com/oZTcHDE.png)

![editing in vim](http://i.imgur.com/noTuncZ.png)

*You can do a command multiple times by inserting the number of times you want to execute it followed by the command.*
`Ex: to delete 10 words, you would use 10dw`
`Ex: to Copy 10 lines, you would use 10yy`

1. Open toEdit.txt with Vim
    ```bash
    vim toEdit.txt
    ```
    ![The file should look like so:](http://i.imgur.com/GC7qccO.png)

    As you can see there are multiple errors in this text file.

2. Navigate to the line 3.
    Here we see three lines of the same text,
    Delete two using one command in vim and 
    write it command down in a separate document.
    *Hint the command will begin with 2d*

    ![The file should now look like:](http://i.imgur.com/jdzhq5s.png)

3. Now navigate to line 5. Here we see three of the same word.
   Delete two of them using one command and
   write it down the document with the other command.
   *Hint the command will begin with 2d*

   ![The file should now look like:](http://i.imgur.com/Jcoke7v.png)

4. Now navigate to line 6 and 7. Here we see a spelling mistakes on both line.
   Delete the extra I in II and delete the s in Its
   write the command in the document with the other commands.
   ![The file should now look like:](http://i.imgur.com/Hhb4lw0.png)

## Part Two - Editing the .vimrc ##

