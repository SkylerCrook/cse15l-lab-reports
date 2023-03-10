# Week 2 Lab Report
By Skyler Crook

---

# Part 1: Servers

For this assignment, I created a local web server called StringServer that contains a single string which gets lines added to it by the user inputing requests through the URL.

**Code**

Here is my code for the assignment

<img width="800" alt="StringServerCodeSS" src="https://user-images.githubusercontent.com/105748004/214973511-ae0a2b8a-8bca-455e-ac69-24d88d2ecda1.png">

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

<img width="800" alt="LocalHostInput1SS" src="https://user-images.githubusercontent.com/105748004/214971367-dfdd20e2-6524-43c5-be85-1c699d004580.png">

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

<img width="800" alt="LocalHostInput2SS" src="https://user-images.githubusercontent.com/105748004/214971380-8fd35566-ddb8-4da6-94a7-07fb95e56c87.png">

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

```
@Test
public void testReverseInPlace() {
	int[] input1 = {0, 1, 2, 3, 4};
	ArrayExamples.reverseInPlace(input1);
	assertArrayEquals(new int[]{4, 3, 2, 1, 0}, input1);
}
```

**Non-Failure Inducing Input**
```
@Test 
public void testReverseInPlace() {
	int[] input2 = {0, 1, 2, 1, 0};
	ArrayExamples.reverseInPlace(input2);
	assertArrayEquals(new int[]{0, 1, 2, 1, 0}, input2);	
}
```

**JUnit Tests / Symptom**

<img width="800" alt="JUnitTestsSS" src="https://user-images.githubusercontent.com/105748004/214991955-1fa7b022-4f7a-4a09-8166-0a6db94e5797.png">

**The Bug**


Buggy Code

```
static void reverseInPlace(int[] arr) {
	for(int i = 0; i < arr.length; i += 1) {
		arr[i] = arr[arr.length - i - 1];
	}	
}
```




Fixed Code

```
static void reverseInPlace(int[] arr) {
	int temp = 0;	
	for(int i = 0; i < arr.length/2; i += 1) {
		temp = arr[i];
		arr[i] = arr[arr.length - i - 1];
		arr[arr.length-i-1] = temp;
	}
}
```

Explanation:
In the buggy method, the loop iterated through the entire array, changing every element to the element on the opposite side of the array. However, this meant that once the first half of the array is changed to equal the second half of the array, the second half of the array is changed to the same values that it already is (creating a mirrored array).
The Fixed method only iterates through half of the array, and switches the values on both ends of the array. This chcanges the first half of the array to equal the back half, and vice versa.

**Passed JUnit Tests**

<img width="800" alt="JUnitTestsPassSS" src="https://user-images.githubusercontent.com/105748004/214994031-a03b5877-d85f-4119-b93c-f3e2e7f4535a.png">


---

# Part 3: What I Learned

Something that I learned in labs 2 and 3 is how to use JUnit tests. Before lab 2 I had never used JUnit and didn't know what it was, much less how to use it for testing code. However, after getting lots of experience during lab hours, I have become very comfortable using JUnit and its assorted methods, such as assertEquals(), assertArrayEquals, and AssertTrue(). JUnit is a valuable resource that I will definitely use as I continue to code in Java.



# Thanks For Reading
