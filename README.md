CS190 Lab 7 - Vim and Regular Expressions
=========

The purpose of this lab is for you to learn how to use vim as a text editor and to familiarize yourself with Regular Expressions. 

Before starting the lab, please navigate to [the lecture material](https://docs.google.com/presentation/d/1mm5oDlTgyXVmkHaTHhWeHtDz9cT-MoGLzLolqzNGFEs/edit?usp=sharing) and make sure you have a basic understanding of Vim and regular expression. 

You should also open up the [Vim Cheatsheet](https://raw.github.com/ClydeByrdIII/cs190lab7/master/cheatsheet.md) we created for quick reference.

## Setup ##

Depending on your working environment, perform the appropriate action:

| Environment   | Action        |
| ------------- | ------------- |
| Linux Lab Machine            | Open a terminal window        |
| Windows or Personal Computer | SSH into `data.cs.purdue.edu`  (No X11 Forwarding)|

----

## Required Vim Setup ##

You need to download a sample .vimrc to make using Vim a little easier.

```bash
# NOTE: Don't do this if you already have a .vimrc customized to your liking!!!

wget https://raw.github.com/ClydeByrdIII/cs190lab7/master/vimrc ~/.vimrc
```

----

## Downloading and Opening the cs190lab7 Directory ##

1. Copy the Clone URL under the `HTTPS clone URL` label (right side of page).
2. In your home directory, type the terminal command

    ```bash
    git clone https://github.com/ClydeByrdIII/cs190lab7.git ~/cs190lab7
    ```

3. A directory named `cs190lab7` appeared in your home directory.
    

## Part 1 - Editing example files with vim ##

The first file we need to edit is `errors.txt`. It contains duplicate lines, mispellings, and other things that need to be fixed. 

> This is the time you should probably open up the [Vim Cheatsheet](https://raw.github.com/ClydeByrdIII/cs190lab7/master/cheatsheet.md) mentioned in the beginning of the lab.

1. Open errors.txt with Vim
    ```bash
    vim errors.txt
    ```
    ![Original File](http://i.imgur.com/qQeNKfY.png)

    The file orignally looks like **Image 1**. As you can see there are multiple errors in this text file, such as lines 3-6 being duplicated and lines 8 having a mispelled 'I'.

2.  **Remove duplicate lines**
    ```
    Goal:       Remove duplicated lines appearing on lines 4 and 5. 
    Commands:   delete current line, delete n lines.
    ```

    ![After removing duplicated lines](http://i.imgur.com/4B8EFn2.png)

3.  **Remove duplicate words**
    ```
    Goal:       Remove duplicated words appearing on line 5
    Commands:   delete word, delete n words
    ```

    ![After deleting duplicated words](http://i.imgur.com/lDA7Xpu.png)

4.  **Fix mispellings**
    ```
    Goal:       Remove characters causing mispellings on lines 6 and 7.
    Commands:   Remove character
    ```
    
    ![After fixing simple mispellings](http://i.imgur.com/gXR1KCt.png)

## Part Two - Editing the .vimrc ##

### What is the .vimrc? ###
`The vimrc file contains optional runtime configuration settings to initialize Vim when it starts.` 

This means that what ever settings you have in this file, they will be executed when vim is started.

For part two we will add a couple of settings to your .vimrc that maybe useful.

1. Open ~/.vimrc with Vim
    ```bash
    vim .vimrc
    ```
![If you downloaded the .vimrc during setup it should look like this:](http://i.imgur.com/0O6bRKg.png)

2. Create a new line at the end of the file and input the following on that line (remember to press i for insert mode):
    ```
    " Always display the current cursor position in the lower right corner of the Vim window.
    set ruler
    " Press space to clear search highlighting and any message already displayed.
    nnoremap <silent> <Space> :silent noh<Bar>echo<CR>
    ```
3. Now save the file and quit
    ```
    :wq!
    ```
4. Now open the file again in vim and you should see the current cursor position in the lower right of the window.

![It should look similiar to this](http://i.imgur.com/ENnvQXA.png)

    
