# Week 2 Lab Report
By Skyler Crook

---

# Part 1: Servers

For this assignment, I created a local web server called StringServer that contains a single string which gets lines added by inputing requests through the URL.

**Code**

Here is my code for the assignment

<img width="600" alt="StringServerCodeSS" src="https://user-images.githubusercontent.com/105748004/214973511-ae0a2b8a-8bca-455e-ac69-24d88d2ecda1.png">

* The code contains 2 methods and 1 instance variable
* Class variable
  * myPage is the only class variable
  * it is a string which contains all of the strings passed by the user through the url
* The handleRequest method
  * this method takes in the url passed by ther user
  * if the url contains the correct syntax of ( /add-message?s=" ), then anything after the equal sign will get added to the string
  * If the url is not recognized, the website will print "404 Not Found" and nothing will be added to the myPage string
* The main method
  * this method runs the code and creates the local host for the web server

**Running the Web Server**

Here is a screenshot of the page after the first input
<img width="600" alt="LocalHostInput1SS" src="https://user-images.githubusercontent.com/105748004/214971367-dfdd20e2-6524-43c5-be85-1c699d004580.png">

* Methods
  * This calls the handleRequest method and passes it the URI "/add-message?s=Hello There"
* Arguments
  * The url is passed as an argument to the handleRequest method, which dissects it to make sure it contains
  * /add-message : the first part of the path
  * ? : the query
  * = : to split the rest of the path into different parameters
  * s : to be the first paremeter (before the =)
* Values
  * the myPage String is then assigned to "Hello There", the path after the equal sign, as it was previosuly empty


Here is a screenshot of my page after the second input
<img width="600" alt="LocalHostInput2SS" src="https://user-images.githubusercontent.com/105748004/214971380-8fd35566-ddb8-4da6-94a7-07fb95e56c87.png">

* Methods
  * This calls the handleRequest method and passes it the URI "/add-message?s=This is Skylers StringServer!"
* Arguments
  * The url is passed as an argument to the handleRequest method, which dissects it to make sure it contains
  * /add-message : the first part of the path
  * ? : the query
  * = : to split the rest of the path into different parameters
  * s : to be the first paremeter (before the =)
* Values
  * the myPage String then gets the string "\nThis is Skylers StringServer!" appended, as it was not empty before so the if statement does not run

---

# Part 2: Bugs

One of the bugs from lab 3 was the reverseInPlace method in ArrayExamples.java

**Failure Inducing Input**

`
@Test

public void testReverseInPlace() {

	int[] input = {0, 1, 2, 3, 4};
	
	ArrayExamples.reverseInPlace(input);
	
	assertArrayEquals(new int[]{4, 3, 2, 1, 0}, input);
	
}
`






