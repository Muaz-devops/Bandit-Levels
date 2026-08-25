# Bandit-Levels
My solutions for OTW Bandit documented.

Over The Wire Bandit Levels 1-10 Solutions 

Level 0 - Pretty simple, just logging on

Level 1 - Opening a readme file where the name was a dash. First i tried with quotations (' ') but that didnt make any difference as there were no spaces in the name and cat still took the - as a flag and not a filenane. 

![Image Alt](https://github.com/Muaz-devops/Bandit-Levels/blob/main/bandit1.JPG?raw=true)

Level 2 - This file name starts with dashes and has spaces, so to solve the spaces problem i used ' ' again but when that didnt work i tried by giving linux the absolute path, remebering from lesson 1. 
![Image Alt](https://github.com/Muaz-devops/Bandit-Levels/blob/main/bandit2.JPG?raw=true)

Level 3 - Practice navigating the command line to find hidden files, the file containing the password was hidden so used the ls -la command to access. 


Level 4 - Navigating the file system to find a human readbale text file, to do this I used the wildcard * to find what the files contained. 


Level 5 - Objective was to find a file that was a certain size, so i used the find -size 1033c command to filter by size. 


Level 6 - Goal is to find a file somewhere on the device that has certain characteristics, so i used these specific details to find the file. This time a key difference was since i didnt know where on the system to look I began my search at the root, so i used find / -user bandti7 -group bandit6 -size 33c 2>/dev/null (I specified where to start and what sort of file to look for then the 2>/dev/null tells linux to redirect any error msgs away from the terminal)


Level 7 - The objective was to find a line of text that was next to the word millionth, I used the simplest method i know of, the grep command. They maybe a more comprehensive method, if so, do tell. 


Level 8 - For this level you need to find a line of text that is not duplicateed (unique) for this there is a command 
