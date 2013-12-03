# CS190 Lab 7 - Vim and Regular Expressions #


The purpose of this lab is for you to learn how to use vim as a text editor and to familiarize yourself with Regular Expressions. 

Before starting the lab, please navigate to [the lecture material](https://docs.google.com/presentation/d/1mm5oDlTgyXVmkHaTHhWeHtDz9cT-MoGLzLolqzNGFEs/edit?usp=sharing) and make sure you have a basic understanding of Vim and regular expression. 

You should also open up the [Vim Cheat-sheet](https://github.com/ClydeByrdIII/cs190lab7/blob/master/cheatsheet.md) we created for quick reference.

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

**NOTE: IN ALL OF PART 1, DO NOT USE INSERT MODE. USE THE COMMANDS LISTED TO FIX THE ERRORS.** 

----

### errors.txt ###

This file contains duplicate lines, words, and misspellings that need to be fixed. You need to edit this file using Vim and fix the errors. 

You can find the commands and their keyboard shortcut in the Vim Cheat-sheet.

> This is the time you should probably open up the [Vim Cheat-sheet](https://github.com/ClydeByrdIII/cs190lab7/blob/master/cheatsheet.md) mentioned in the beginning of the lab :)

1.  Open `errors.txt` in Vim
    ```bash
    vim errors.txt
    ```
    ![Original File](http://i.imgur.com/qQeNKfY.png)

    The file originally looks like the above text. As you can see there are multiple errors in this text file, such as lines 3-6 being duplicated and lines 8 having a mispelled 'I'.

2.  **Remove duplicate lines**
    ```
    GOAL:       Remove duplicated lines appearing on lines 4 and 5. 
    COMMANDS:   delete current line, delete n lines.
    ```

    ![After removing duplicated lines](http://i.imgur.com/4B8EFn2.png)

3.  **Remove duplicate words**
    ```
    GOAL:       Remove duplicated words appearing on line 5
    COMMANDS:   delete word, delete n words
    ```

    ![After deleting duplicated words](http://i.imgur.com/lDA7Xpu.png)

4.  **Fix misspellings**
    ```
    GOAL:       Remove characters causing misspellings on lines 6 and 7.
    COMMANDS:   Remove character
    ```
    
    ![After fixing simple misspellings](http://i.imgur.com/gXR1KCt.png)

5.  **Save the file and quit**
    ```
    :wq
    ```
----

### annoying.txt ###

This file contains more than 1000 lines and sometimes more than 1000 words on a single line. The labs asks us to edit it in annoying ways. It would be really annoying to make these edits with `gedit`. Vim will save the day.

1.  Open `annoying.txt` in Vim. 

    This file has lines containing `'Please Keep This LineX'` and `'delete this lineX'`. You need to delete the lines that ask you to delete themselves.

2.  **Remove 3 lines**
    ```
    GOAL:       Delete lines 6-8 (3 lines)
    COMMANDS:   delete current line
    ```

3.  **Remove 20 lines**
    ```
    GOAL:       Delete lines 14-33 (20 lines)
    COMMANDS:   delete n lines
    ```

4.  **Remove 1000 lines**
    ```
    GOAL:       Delete lines 39-1038 (1000 lines)
    COMMANDS:   delete n lines
    ```

5.  **Remove 3 words**

    Just as you can remove 1000 lines, you can also remove ***n*** words. 

    ```
    GOAL:       Remove the BADWORD words from the last line of the file
    COMMANDS:   delete n words
    ```

6.  **Save the file and quit**
    ````
    GOAL:       Save the file annoying.txt
    COMMANDS:   Save and quit Vim 
    ```
----

### jump_around.txt ###

This is a really long file...actually a book called The Young Engineers. There are little messages interleaved in the middle. 

1.  Open `jump_around.txt` in Vim.
2.  Press `Shift + G` to go the very end of the file
3.  Type `gg` to go to the beginning of the file
4.  Type `:50` to go to line 50.
5.  Type `:457` to go to line 457.
6.  Type `$` to go to the end of line 457.
7.  Type `^` to go to the beginning of line 457.
8.  Get comfortable with what you just did. Do it over if you have to.
9.  Type the letter `i` on the keyboard.
10. Insert some text. 
11. Quit Vim without saving. 

## Part Two - Editing the .vimrc ##

### What is the .vimrc? ###
The vimrc file contains optional runtime configuration settings that get loaded each time Vim is run. This means that what ever the settings you have in this file, they will be executed when Vim is started.

For part two we will add a couple of settings to your .vimrc that maybe useful.

1. Open `~/.vimrc` with Vim
    ```bash
    vim ~/.vimrc
    ```
![If you downloaded the .vimrc during setup it should look like this:](http://i.imgur.com/0O6bRKg.png)

2. Jump to the bottom of the file using `Shift + G`.

3. Jump to the end of the line by typing `$`.

4. Press `i` to enter *Insert Mode*.

5. Insert a new line at the bottom of the file, and paste the code below on that line. 

    > If you try and paste code without being in *Insert Mode*, each character that is part of the
    > pasted string will act as input to Vim. 
    > 
    > e.g., if you paste the word `insert` while still in *Command Mode*, `i` will trigger *Insert Mode* and then `nsert` will be pasted.

    ```
    " Always display the current cursor position in the lower right corner of the Vim window.
    set ruler
    " Press space to clear search highlighting and any message already displayed.
    nnoremap <silent> <Space> :silent noh<Bar>echo<CR>
    ```

3. Now save the file and quit
    ```
    <ESC>
    :wq
    ```
4. Now open the file again in vim and you should see the current cursor position in the lower right of the window.

![It should look similar to this](http://i.imgur.com/ENnvQXA.png)

    


