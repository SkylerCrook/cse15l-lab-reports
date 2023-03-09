# Lab Report 5
By Skyler Crook

---

# Favorite Lab

My favorite lab from this class was from week 7. In this lab we competed to correct a file as fast as possible, and though I was not the fastest in my class I made it to the top 3. Even after the lab ended, I continued trying to find better ways to improve my time and make the commands as fast as possible.


# Steps Reminder

To attempt the challenge these where the rules we had to follow:

1. Setup Delete any existing forks of the repository you have on your account
2. Setup Fork the repository
3. The real deal Start the timer!
4. Log into ieng6
5. Clone your fork of the repository from your Github account
6. Run the tests, demonstrating that they fail
7. Edit the code file to fix the failing test
8. Run the tests, demonstrating that they now succeed
9. Commit and push the resulting change to your Github account (you can pick any commit message!)


# My Original Attempts

Originally I ran all of the tests using individual commands and nano to edit the file

Commands I used:

```
ssh cs15lwi23anl@ieng6.ucsd.edu
git clone git@github.com:SkylerCrook/lab7.git
cd lab7/
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests
nano ListExamples.java
```
After using nano I manually changed the file in the nano editor:
```
<down arrow>(x42)
<right arrow>(x12)
<delete>
2
^O
<enter>
^X
```
And then ran the tests and commited/pushed to GitHub:
```
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples
git add ListExamples.java
git commit -m  "Fixed ListExamples"
git push
```

Using these commands I was able to achieve a relatively fast time by using my past commands insetad of typing all of this in. I then started to string the commands together using `;` but the biggest thing slowing my time down was nano.


# Improving

To improve my commands and make the process as fast as possible, I knew that I needed to do more then string all of the commands together. To accomplish this I used the sed command, whioch allowed me to change the file directly from the command line.

Added line
```
sed -i '43 s/index1/index2/' ListExamples.java

```

Full command
```
ssh cs15lwi23anl@ieng6.ucsd.edu
git clone git@github.com:SkylerCrook/lab7.git ; cd lab7/ ; javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java ;
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests ;
sed -i '43 s/index1/index2/' ListExamples.java ; javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java ;
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests ;
git add ListExamples.java ; git commit -m  "Fixed ListExamples" ; git push
```
This uses the same commands as before, but replaces the `nano` command with the `sed` command. This command changes "index1" to "index2" on line 43, and uses the -i modifier to directly change the file.


# Results

Using this new command, I got my time down to 8 seconds, as I did not have to spend any time typing, looking for commands, or using nano to changhe the document. Instead the time is just based on how fast the computer can run the commands.


# Thank You
