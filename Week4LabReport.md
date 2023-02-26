# Lab Report 4
By Skyler Crook

---

# Competition

1. Setup Delete any existing forks of the repository you have on your account
2. Setup Fork the repository
3. The real deal Start the timer!
4. Log into ieng6
5. Clone your fork of the repository from your Github account
6. Run the tests, demonstrating that they fail
7. Edit the code file to fix the failing test
8. Run the tests, demonstrating that they now succeed
9. Commit and push the resulting change to your Github account (you can pick any commit message!)



# Step 4
**Log into ieng6**

```
ssh cs15lwi23anl@ieng6.ucsd.edu
```

I used the ssh command to login into the ieng6 server

<img width="459" alt="Screen Shot 2023-02-26 at 1 00 00 PM" src="https://user-images.githubusercontent.com/105748004/221436994-901ba25c-3ca7-418e-8c82-1f6b0f5c76f0.png">



# Step 5
**Clone your fork of the repository from your Github account**

```
git clone git@github.com:SkylerCrook/lab7.git
```

I used git clone with the ssh key to the fork of the repository on GitHub to clone it into my account

<img width="552" alt="Screen Shot 2023-02-26 at 1 04 50 PM" src="https://user-images.githubusercontent.com/105748004/221437216-a32de8d1-4424-401f-9dc9-b25983e0d5e3.png">



# Step 6
**Run the tests, demonstrating that they fail**

```
cd lab7/
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests
```

I used the cd command to change lab7 to my working directory
Next I compiled the files using javac and the junit jar files
Finally I ran the ListExamplesTests file with JUnit to produce the output of the tests

<img width="905" alt="Screen Shot 2023-02-26 at 1 21 12 PM" src="https://user-images.githubusercontent.com/105748004/221437984-346d6e99-8400-4964-a014-57bc9b7bdbb5.png">



# Step 7
**Edit the code file to fix the failing test**

```
nano ListExamples.java
<down arrow>(x42)
<right arrow>(x12)
<delete>
2
^O
<enter>
^X
```

I used the nano command to go into ListExamples.java
Then I moved down to line 43 and changed "index1" to "index2"
Next I saved and then exited nano

<img width="974" alt="Screen Shot 2023-02-26 at 1 13 18 PM" src="https://user-images.githubusercontent.com/105748004/221437664-f0e30f64-c45c-44f1-9087-e7c5c8ab88dd.png">



# Step 8
**Run the tests, demonstrating that they now succeed**

```
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples
```

<img width="923" alt="Screen Shot 2023-02-26 at 1 22 29 PM" src="https://user-images.githubusercontent.com/105748004/221438050-e13b106c-da14-4e1c-9fb9-3d205fb1c923.png">




# Step 9
**Commit and push the resulting change to your Github account (you can pick any commit message!)**

```
git add ListExamples.java
git commit -m  "Fixed ListExamples"
git push
```

First I added the changed file to the files I will commit next through git
Then I commited the file with the message "Fixed ListExamples"
Finally I pushed the commits

<img width="546" alt="Screen Shot 2023-02-26 at 1 24 44 PM" src="https://user-images.githubusercontent.com/105748004/221438152-ea8ac8b2-75a4-49b3-b236-5fb2f8be8de3.png">



# Thank You
