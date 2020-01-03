---
layout: default
---
## KIK-LG219 : Command Line Tools for Linguists

Command line tools for linguists KIK-LG219 is an introduction course to Linux and Unix environments, directed at linguists. The course offers basic information on Linux and is fit for students who have never used Linux before. Students learn how to create and navigate between directories in a Linux environment, how to execute commands and write scripts, and how to install and use programs. The course also introduces students to basic methods of and handy tools for corpus linguistics in a Linux environment, such as creating frequency lists from plain text.


### Week 1: Introduction to Command Line Environments

Introduces commands such as: **cat, mv, mkdir, cd, wget, man, echo, touch, emacs**

The first week focuses on how to create and navigate between directories on Linux. Basic terminology and information on what a command line is exactly is introduced. The week’s most useful commands from a linguistic perspective were **wget**, which retrieves material such as text files from the Internet, and **emacs**, which is a text editor that can be used to examine text files. With just these two commands, it is already possible to do some corpus linguistics. However, command line can be used for much more than just examining corpora. One command that will be quite useful later on is **echo**. This command simply prints the string written after it. So, the command

    `$ echo “Hi!”`

simply prints the output:

       `Hi!`

What makes echo useful is that it can be used for testing RegEx commands, for example. This, however, is not a part the first week’s material!

This was my first time working with Linux. It took some time to grasp the basic commands, but once I learnt how to use them, navigating the command line became easy and honestly quite fun. While I’m interested in understanding just how the command line works, I mostly tried to think about how I could use it in my future work as a linguist.

### Week 2: Navigating the Unix System

Introduces commands such as: **ls, cp, ln, chmod, sort, killall, ssh, scp, gzip, tar**

This week students learn how to copy, move and remove entire directories. Student also learn about processes, process management, and standard system files, all of which are fundamental in understanding how Linux works, as well as remote servers. The week also includes information on privacy and permissions.
For this week’s example I have chosen the command **chmod**. It is used to modify users’ permissions to read (r), write (w) and execute (w) files and directories. Users here mean the owner of the file (u), group the file belongs to (g), and others (o). For example, the following command grants writing permission for all users:

    `$ chmod a+w file.txt`


### Week 3: Basic Corpus Processing

Introduces commands such as: **head, tail, tr, egrep, wc, cut, sort, uniq** and regular expressions.

Week 3 focuses on methods of basic corpus processing. This includes searching text files for specific strings and creating word lists from plain text. This week also includes an introduction to simple regular expressions (Regex for short). Regular expressions are strings that form search patterns, and they’re very useful in corpus linguistics. With Regex, it is possible to easily examine e.g. a certain prefix even in unannotated text corpora. In Linux together with the command `grep`, Regex can be used in just these kinds of ways. This is also where the aforementioned command `echo` becomes very handy! It can be used to check whether or not the RegEx command does what it’s supposed to. In the following example, I’ve used `echo`, `grep` and regular expressions together to test if my command designed to match all lowercase letters in a text works.

 ![An example of a grep command](https://i.imgur.com/37QV7Xx.png)

Lowercase letters are highlighted in red, while uppercase letters and punctuation are not. This means that the command matches what it’s supposed to. After this test, I can safely use this string for some text file, knowing that I’m getting correct results.

I found this week’s material along with week 4 the most useful for me personally, as corpus linguistics is something I’m already somewhat familiar with and I think it’s something I’m going to be working with in the future, too. Knowing how to process corpora in Linux is absolutely a helpful skill, as it makes processing unannotated text quite easy.


### Week 4: Advanced Corpus Processing

Introduces commands such as: **sed, diff**

Week 4 expands on things introduced in week 3. Last week included creating word lists from plain text, and one of this week’s themes is creating frequency lists, which are word lists that include all of the word types’ frequency counts.

`sed` (short for stream editor) is a command used to find and replace strings in a text file. It can also be used to insert or delete strings altogether. Regular expressions are used to specify `sed`’s search patterns. To replace strings, the following kind of command is used:

      `$ echo “I like dogs!” | sed s/dogs/cats`

Here “dogs” is a Regex search pattern, meaning that the command finds all instances of the word “dogs” in the text (or in this case, the echo command’s output), while “cats” is the replacement string. In other words, all instances of the word “dogs” will be replaced with the word “cats” if this command is executed. The output would be “I like cats!”. This is also an example of piping commands, another theme of this week; it simply means that commands are combined in a way in which the first command’s output is the input for the next ones. As seen in the example, this is done by writing the commands in correct order after one another and using `|` to separate them.

As with week 3, I found this week’s material interesting and useful. However, this week’s material felt quite a bit more challenging and I think I’m going to need more practice with `sed` in the future.


### Week 5: Scripting and Configuration Files

Week 5 focuses on scripts, more specifically bash scripts. These scripts are text files with several commands written into them. When the script is executed, just like a singular command would be, it executed all of the commands it includes. This makes for example creating frequency lists very easy. With a ready script including all necessary commands needed for creating frequency lists, the process is far quicker and far easier as only one script needs to be executed instead all of the necessary commands one by one with attention paid to the right order. Here is a simple example of a script that

This week’s material also includes configuration files. For example, bash configuration files can be used to:
  * customize your prompt
  * change the hostname for your computer
  * change the length of your command history
  * switch your preferred editor
  * change your timezone

Here’s an example of a very basic script.

```
#!/bin/bash/
# Miska's super simple script
# Just echoes the words “Hi, I’m a script!” because the author lacks further imagination

echo "Hi, I'm a script!"
```

Week 5 was definitely the hardest one for me. I didn’t have time to properly study any of the material, so I only managed to grasp very basic concepts. Scripts are definitely something I’ll have to come back to in the future…


### Week 6: Installing and Running Programs

Introduces commands such as: **sudo, apt-get, pip, make**

This week’s themes include executing commands as the root user (the `sudo` command), and installing programs using the commands `pip` (for python packages), `apt-get` and `make`. These commands make installing programs very simple and easy. Makefiles, which are necessary for the `make` command, are also explained.
They are similar to scripts in that they also include several commands. The difference is that makefiles are meant to compile and install programs, whereas bash scripts execute commands.

Here’s a very useful example command with both `sudo` and `apt-get` that is used to update packages in your system: 

       `sudo apt-get update`

Like with scripts, I find makefiles a bit difficult to understand; while I get the basics, I’m lost on how they’re actually written. Otherwise, I feel like this week’s material was easy to grasp.


### Week 7: Version control

Introduces commands such as: **git clone, git status, git add, git commit, git push**

This week’s topic is version control. Version control means a system where the changes made to a file or a project are saved as separate versions. This makes making changes safe, since even if a change you make messes the whole thing up, you can return to an earlier version of your project, and nothing is lost. Version control is especially helpful in bigger projects, such as creating websites or software. Version control allows the user to work not only in versions, but in branches. Branches are like different piles of versions, developed in separate directions. These branches can optionally be merged for the final version. On this course, version control is learnt through making websites through Git and Github. There are many Git commands, but here’s some of them:

| Command        | Function                                              |
| ---------      | -------                                               |
| `git push`     | Pushes new changes to Github                          |
| `git pull`     | Pulls changes from Github to local                    |
| `git branch`   | Shows all current branches and which one you’re using |
| `git checkout` | Switches branch                                       |
| `git merge`    | Merges branches                                       |
| `git clone`    | Clones a repository from Github to local              |

Personally, I found this week the most fun. While the weeks related to corpora will like be the most useful ones for me in the future, working with Git and Github was easy and enjoyable.
