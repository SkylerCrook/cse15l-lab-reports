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

**Exampels:**

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

This command using the * symbol to look for patterns in the -name search. It searches through the /written_2 directory and looks for a file named HistoryJ* which will look for any file that starts with HistoryJ and the * will allow any text after to be returned. The .* means that a file of any type will be returned by the command.



