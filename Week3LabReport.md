# Week 3 Lab Report
By Skyler Crook

---

# find Command

The find command is an extrmely useful command that is commonly used to sort through and find specific files.
There are many options which can be used to narrow the search of the find command, and these are 4 that are useful to know.

**Command Line Options**
* -name
* -exec
* -user
* -perm


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







