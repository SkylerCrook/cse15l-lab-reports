# Lab Report 4
By Skyler Crook

---

# find Command

The find command is an extrmely useful command that is commonly used to sort through and find specific files.
There are many options which can be used to narrow the search of the find command, and these are 4 that are useful to know.

**Command Line Options to Go Over**
* -name
* -exec
* -inum
* -links

Soruces:
Information about these commands all come from [geeksforgeeks](https://www.geeksforgeeks.org/find-command-in-linux-with-examples/)


# -name

The -name command will narrow the results of the find command and look for files that include the key passed by -name

**Examples:**

```
find ./written_2 -name WhereToFrance.txt
```
<img width="633" alt="Screen Shot 2023-02-13 at 12 22 11 PM" src="https://user-images.githubusercontent.com/105748004/218566501-40d42c6d-bb64-43c9-b253-3c4305561aab.png">

This command searches through the /written_2 directory and looks for a file named WhereToFrance.txt
Since this file exists, the terminal returns the path to the file passed by the command.


```
find ./written_2 -name HistoryJ*.*
```
<img width="577" alt="Screen Shot 2023-02-13 at 12 27 07 PM" src="https://user-images.githubusercontent.com/105748004/218567369-9520e49b-18e4-427a-a0b4-47f37a0c280b.png">

This command using the * symbol to look for patterns in the -name search. It searches through the /written_2 directory and looks for a file named HistoryJ* which will look for any file that starts with HistoryJ and the * will allow any text after to be returned. The .* means that a file of any type will be found by the command. The paths of all the files that match the command are then returned.


# -exec

the exec command is used to take the output of the find command and apply another command to it.

**Examples:**

```
find ./written_2 -name "WhereTo*.txt" -exec wc {} \;
```
<img width="703" alt="Screen Shot 2023-02-13 at 12 54 57 PM" src="https://user-images.githubusercontent.com/105748004/218572477-184d1132-4ab9-4344-9c04-dacac9308169.png">

This command uses the find command with -name to narrow the searches to all the txt files that start with "WhereTo". It then uses the -exec option and applies the command wc to all the files returned by the find command. This then prints the line, word, and character count of each of the files.


```
find ./written_2 -name "Hand*.txt" -exec grep 'help' {} \;
```
<img width="750" alt="Screen Shot 2023-02-13 at 12 46 55 PM" src="https://user-images.githubusercontent.com/105748004/218571058-60d60db9-dbcc-4871-9fd6-28b5bb30c841.png">

This command uses the find command with -name to narrow the searches to all txt files that start with the word "Hand". It then uses the -exec option with the grep command to find all lines that include the word "help". All the lines from the txt files that have this word in them are then printed out.


# -inum

The inum command is used to search for files by their specific inode number.

**Examples:**

```
find ./written_2/ -inum 204847731
```
<img width="569" alt="Screen Shot 2023-02-13 at 1 45 28 PM" src="https://user-images.githubusercontent.com/105748004/218581631-d3da7099-f6cd-4cdd-ae8e-36bcd5f94f20.png">

This command searches through the written_2 directory for a file with the inode 204847731. Because this file exists and is present in the parent directory, the path to the file is returned.


```
find ./written_2/ -inum 204847634 -o -inum 204847633 -o -inum 204847632
```
<img width="832" alt="Screen Shot 2023-02-13 at 1 51 39 PM" src="https://user-images.githubusercontent.com/105748004/218582778-be2cc651-9eaf-41d5-8dc5-0185091cc1fb.png">

This command searches through the written_2 directory for a file with the inodes 204847634, 204847633, 204847632. Note one of the inodes is for a directory, not a file. Because these files/directories exists and are present in the parent directory, the paths are returned.


# -links

The links command is used to search for files/directories based on the amount of hard links that reference a file or directory.

**Examples:**

```
find ./written_2/ -name "WhereTo*.txt"  -links 1 
```
<img width="675" alt="Screen Shot 2023-02-13 at 2 03 15 PM" src="https://user-images.githubusercontent.com/105748004/218584778-ded1698f-d455-4580-b20e-21538c971ecc.png">

This command uses the find command with -name to narrow the searches to all the txt files that start with "WhereTo". It then uses the links option to show all of the files out of those specified by -name which have exactly 1 hard link which references that inode.


```
find ./written_2/ -links 4
```
<img width="518" alt="Screen Shot 2023-02-13 at 2 06 05 PM" src="https://user-images.githubusercontent.com/105748004/218585221-a591f998-dced-4632-8949-9932ef999457.png">

This command uses the find command to search through all files and directories within the written_2 directory. It then uses the links option to show which of these files or directories have exactly 4 hard links which reference that inode, which are the 2 directories returned.


# Thank You!
