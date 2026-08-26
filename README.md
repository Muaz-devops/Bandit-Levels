# Bandit-Levels
My solutions for OTW Bandit documented. 

#This is not a walkthrough or guide, this is how I solved the levels, I do plan to write up a full guide explaining the objective of each lesson, possible commands, their uses and examples. NOT ANSWERS AS THEN THERE'S NO CHALLENGE 
Over The Wire Bandit Levels 1-10 Solutions 

Level 0 - Pretty simple, just logging on

Level 1 - Opening a readme file where the name was a dash. First I tried with quotations (' ') but that didnt make any difference as there were no spaces in the name and cat still took the - as a flag and not a filenane. 

![Image Alt](https://github.com/Muaz-devops/Bandit-Levels/blob/main/bandit1.JPG?raw=true)

Level 2 - This file name starts with dashes and has spaces, so to solve the spaces problem I used ' ' again but when that didnt work I tried by giving linux the absolute path, remembering from lesson 1. 

![Image Alt](https://github.com/Muaz-devops/Bandit-Levels/blob/main/bandit2.JPG?raw=true)

Level 3 - Practice navigating the command line to find hidden files, the file containing the password was hidden so used the ls -la command to access. 

![Image Alt](https://github.com/Muaz-devops/Bandit-Levels/blob/main/bandit3.JPG?raw=true)

Level 4 - Navigating the file system to find a human readable text file, to do this I used the wildcard * to find what the files contained. 

![Image Alt](https://github.com/Muaz-devops/Bandit-Levels/blob/main/bandit4.JPG?raw=true)

Level 5 - Objective was to find a file that was a certain size, so I used the find -size 1033c command to filter by size. 

![Image Alt](https://github.com/Muaz-devops/Bandit-Levels/blob/main/bandit5.JPG?raw=true)

Level 6 - Goal is to find a file somewhere on the device that has certain characteristics, so I used these specific details to find the file. This time a key difference was since i didnt know where on the system to look I began my search at the root, so I used find / -user bandti7 -group bandit6 -size 33c 2>/dev/null (I specified where to start and what sort of file to look for then the 2>/dev/null tells linux to redirect any error msgs away from the terminal)

![Image Alt](https://github.com/Muaz-devops/Bandit-Levels/blob/main/bandit6.JPG?raw=true)

Level 7 - The objective was to find a line of text that was next to the word millionth, I used the simplest method I know of, the grep command. They maybe a more comprehensive method, if so, do tell. 

![Image Alt](https://github.com/Muaz-devops/Bandit-Levels/blob/main/bandit7.JPG?raw=true)

Level 8 - For this level you need to find a line of text that is not duplicated (unique) for this there is a command uniq, it prints lines that have no duplicates, this is used together with the sort command (which sort and places duplicate lines together) 

![Image Alt](https://github.com/Muaz-devops/Bandit-Levels/blob/main/bandit8.JPG?raw=true)

Level 9 - For this level you have to extract readable text from binary files, this involved learning a new command (strings, which i had not previously used) and to filter my search to look for a file which had many ==== in the name. 
I used strings command (this scans the binary file and only prints the sequence of printable characters) I then piped (combined) this with grep to search for lines where there were multiple '=', I used-E to use grep with + (without -E grep would take my command as look for the =+ symbol in the text whereas I wanted to tell it to use the + to mean plus, my mistake was to only inlcude one = in my command so the output was for all those lines that had one or more = symbols on the line, had i done grep -E '==+' it would have ignore a few more lines.)

![Image Alt](https://github.com/Muaz-devops/Bandit-Levels/blob/main/bandit9_-E-isthere-so+works_as_add.JPG?raw=true) 

Level 10 - The objective here is to decode base64 content. This was my first time coming across base64 and Linuxhint came in handy, very good resource, I also used them on a few other commands. I learnt how to use the simple base64 command to encode and decode data. 
The solution for this level was pretty simple once I learnt how to use base64 command. simply tell linux to decode using the -d flag and content is readable.

![Image Alt](https://github.com/Muaz-devops/Bandit-Levels/blob/main/bandit10-usebase64_-d-istodecode.JPG?raw=true)
