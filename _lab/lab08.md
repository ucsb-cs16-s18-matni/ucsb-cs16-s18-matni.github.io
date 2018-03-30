---
layout: lab
num: lab08
ready: true
desc: "Arrays, Vectors and Strings"
assigned: 2017-11-20 08:00:00.00-8
due: 2017-11-29 12:00:00.00-8
---
<div markdown="1">

<h1>CS16: Programming Assignment 08</h1>
<h2>Introduction -- Important: Read this!</h2>
This lab will have you do programming exercises with arrays, strings and vectors.

The TAs and I will be looking for (and grading) programming stylizations, as per the styling guide discussed in class. The lab exercises also have specific requirements. So, it is not enough for your lab to pass submit.cs! Please read the instructions herein **CAREFULLY!!!**.

<h3>Pair programming is <b>OPTIONAL BUT RECOMMENDED</b> for this lab!!!</h3>

Choose who will be the first driver and who will start as navigator, and then remember to switch (at least once) during the lab. But you should probably know the long-term goal too: each partner should participate in both roles in approximately equal parts over the course of the assignment. 

DO NOT share passwords. Instead, use scp or email to share files with each other at the end of each work session.

**PLEASE MAKE SURE YOU TRADE CONTACT INFORMATION WITH YOUR LAB PARTNER! This means emails, phone numbers, online chat handles, or whatever is necessary to continue working together when you are working remotely (like, say, if one of you goes home for the holiday weekend).**

<h2>Step 1: Getting Ready</h2>
1. Go to submit.cs, navigate to this lab page and create a team for you and your pair partner. Do this by clicking on the blue "Join Groups" button, then follow directions.

2. Decide on initial navigator and driver.

3. Driver, log on to your CSIL account.

4. Open a terminal window and log into the correct machine.

5. Change into your CS 16 directory, create a lab08 directory and change into it.

<h2>Step 2: Writing the Programs</h2>
This lab will have you create 3 programs: anagram.cpp, histogram.cpp, and split.cpp. You must follow the instructions carefully. It is not enough to pass the submit.cs check as the instructor and the TAs *will* be checking your submitted program files.

NOTE: IF AN ASSIGNMENT BELOW ASKS YOU TO IMPLEMENT A CERTAIN APPROACH, YOU **MUST** FOLLOW THOSE INSTRUCTIONS VERY CAREFULLY!!!

Each corresponds to one of the problems listed below, which make up this lab. Each of the programs is worth 40 points on submit.cs. (the total score will be normalized from 120 to 100 points when the grade is calculated). Each should be solved in its own file and each must be submitted for full assignment credit. 

Note: All these submissions will be checked by the automatic system on submit.cs AND by the instructor and TAs for further evaluation. Details below.

---
<h3>ANAGRAM.CPP</h3>
Write a function that determines if two strings are anagrams. An anagram is a word or phrase formed by rearranging the letters of a different word or phrase, for example, the letters in the word "listen" can be re-arranged to spell "silent".

The function should not be case sensitive and should disregard any punctuation or spaces. Two strings are anagrams if the letters can be rearranged to form each other. For example, “Eleven plus two” is an anagram of “Twelve plus one”. Each string contains one “v”, three “e’s”, two “l’s”, etc. You may use C++ strings, arrays, or vectors to solve this problem. You may **not** use built-in C++ functions that we have NOT discussed in lecture.

Write a program that inputs two strings and calls your function to determine whether or not the strings are anagrams and prints the result.

Beware of copying solutions from other students or from the Internet. We will be checking on this and if you are caught doing this, you will get a ZERO grade on this lab (at least), possibly a ZERO grade in this CS16 class, and be reported to the department and the university for academic dishonesty and plagiarism.

A session should look like one of the following examples (including whitespace and formatting), with possibly different numbers and numbers of asterisks in the output:

```
Enter first string:
Eleven plus two
Enter second string:
Twelve plus three
The strings are not anagrams.
```

OR

```
Enter first string:
Rats and Mice
Enter second string:
in cat's dream
The strings are anagrams.
```

The strings printed by the program should include a newline at the end, but no other trailing whitespace (whitespace at the end of the line).'

REQUIREMENT: At least one function.

---
<h3>HISTOGRAM.CPP</h3>
Write a program that outputs a histogram of student grades for an assignment. First, the program will input the number of grades from the user; this can be any positive number. Then, the program should input the grade of each student as an integer and store the grade appropriately. You can do this with either dynamic arrays or vectors. You cannot use techniques and functions that we have not discussed in class. 

The program should then compute and generate the histogram. In computing the histogram, the minimum value of a grade is 0 but your program should determine the maximum value entered by the user. Output the histogram to the console.

The scores should be right-justified with width 3 (there should be two spaces before a one-digit number, and one space before a two-digit number). So you can assume that the "grades" inputted will not be composed of more than 3 digits. The histogram should utilize the asterix symbol ("*") to indicate the histogram count.

Beware of copying solutions from other students or from the Internet. We will be checking on this and if you are caught doing this, you will get a ZERO grade on this lab (at least), possibly a ZERO grade in this CS16 class, and be reported to the department and the university for academic dishonesty and plagiarism.

The program should print a string of text to the terminal before getting each line of input from the user. A session should look like one of the following examples (including whitespace and formatting), with possibly different numbers and numbers of asterisks in the output:

```
Enter number of grades:
8
Enter grades (each on a new line):
20
30
4
20
30
30
120
20
Histogram:
  4 *
 20 ***
 30 ***
120 *
```

OR

```
Enter number of grades:
7
Enter grades (each on a new line):
1
1
100
100
100
99
50
Histogram:
  1 **
 50 *
 99 *
100 ***
```

REQUIRED: At least one function.

---
<h3>SPLIT.CPP</h3>
This should look familiar - it is also a homework question!

Given the following function header:

`vector<string> split(string target, string delimiter);`

implement the function *split* so that it returns a vector of the strings in target that are separated by the string delimiter.

For example: **split("10,20,30", ",")** should return a vector with the strings "10", "20", and "30". Similarly, **split("do re mi fa so la ti do", " ")** should return a vector with the strings "do", "re", "mi", "fa", "so", "la", "ti", and "do".

Write a program that inputs two strings and calls your function to split the first target string by the second delimiter string and prints the resulting vector all on line line with elements separated by commas. If one of the sub-strings is an empty string, then it must not be printed.

REQUIRED: You MUST use **vectors** to write this program. You may **not** use any C++ functions that we have NOT discussed in lecture. The strings printed by the program should include a newline at the end.

Beware of copying solutions from other students or from the Internet. We will be checking on this and if you are caught doing this, you will get a ZERO grade on this lab (at least), possibly a ZERO grade in this CS16 class, and be reported to the department and the university for academic dishonesty and plagiarism.

The program should print a string of text to the terminal before getting each line of input from the user. A session should look like one of the following examples (including whitespace and formatting), with possibly different numbers in the output:

```
Enter string to split:
10,20,30
Enter delimiter string:
,
The substrings are: "10", "20", "30"
```

OR

```
Enter string to split:
do re mi fa so la ti do
Enter delimiter string:
 
The substrings are: "do", "re", "mi", "fa", "so", "la", "ti", "do"
```

Note: the fourth line in the second example has a single space character (it is not an empty line).

REQUIRED: At least one function (called split).

---

<h2>Step 3: Create a File for "make" & Compile the Codes with the make Command</h2>

Copy the file provided to you at this URL. This file contains an almost finished file that helps you run "make":
<http://www.cs.ucsb.edu/~zmatni/cs16f17/lab08/IncompleteFile>

Using your text editor, fill in the missing parts of the file (you will also have to rename it appropriately - we will discuss "make" in class, but feel free to research on your own as well).

<h2>Step 4: Submit</h2>

Once you are satisfied that your programs are correct, it is time to submit them. Login at [https://submit.cs.ucsb.edu](https://submit.cs.ucsb.edu), then navigate to “CS16_f17” and click on “lab08”. Then click “Make Submission”, and make your submission the same way as last week. Remember to submit all of the .cpp files.

Once you submit, you should see a page detailing your submission. The system will automatically grade your program and will show you the results on this page after a 1 minute delay.

You can alternatively submit your code from the command line (terminal) on any CS machine, including the Phelps lab machines or the CSIL server. You can use this method when logged in remotely. To submit the the source files (make sure they are the only 3 .cpp files)  to this assignment by running the command:

`~submit/submit -p 902 anagram.cpp histogram.cpp split.cpp`

You can copy the URL shown in the output of the above and paste into a web browser to reach the submission result page.

<h2>Step 5: Check Submission Results</h2>

After the 1 minute delay, the submit system will show your score and give you feedback on your submission. Refresh the webpage after a minute to see this information.

You may submit this lab multiple times. You should submit only after local compilation does not produce any errors and runs as expected. The score of the last submission uploaded before the deadline will be used as your assignment grade.

<h2>Step 6: Done!</h2>
Remember that we will check your code for appropriate comments, formatting, and the use of required code, as stated earlier.

If you are in the Phelps lab or in CSIL, make sure to log out of the machine before you leave. Also, make sure to close all open programs before you log out. Some programs will not work next time if they are not closed. Remember to save all your open files before you close your text editor.

If you are logged in remotely, you can log out using the exit command:

`$ exit`

</div>
