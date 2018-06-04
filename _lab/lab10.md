---
layout: lab
num: lab10
ready: true
desc: "Recursive Functions"
assigned: 2018-06-06 08:00:00.00-8
due: 2018-06-08 12:00:00.00-8
---
<div markdown="1">

<h1>CS16: Programming Assignment 10</h1>
<h2>Introduction -- Important: Read this!</h2>
This lab will have you do a programming exercise with recursion in C++.

The TAs and I will be looking for (and grading) programming stylizations, as per the styling guide discussed in class. The lab exercises also have specific requirements. So, it is not enough for your lab to pass Gradescope! Please read the instructions herein **CAREFULLY!!!**.

<h3>Pair programming is <b>OPTIONAL</b> for this lab!</h3>

Choose who will be the first driver and who will start as navigator, and then remember to switch (at least once) during the lab. But you should probably know the long-term goal too: each partner should participate in both roles in approximately equal parts over the course of the assignment. 

DO NOT share passwords. Instead, use scp or email to share files with each other at the end of each work session.

**PLEASE MAKE SURE YOU TRADE CONTACT INFORMATION WITH YOUR LAB PARTNER! This means emails, phone numbers, online chat handles, or whatever is necessary to continue working together when you are working remotely**

<h2>Step 1: Getting Ready</h2>
1. Go to Gradescope, navigate to this lab page and create a team for you and your pair partner. Do this by clicking on the blue "Join Groups" button, then follow directions.

2. Decide on initial navigator and driver.

3. Driver, log on to your CSIL account.

4. Open a terminal window and log into the correct machine.

5. Change into your CS 16 directory, create a lab10 directory and change into it.

<h2>Step 2: Writing the Programs</h2>
This lab will have you create 1 program with 2 functions. You must follow the instructions carefully. It is not enough to pass the Gradescope check as the instructor and the TAs *will* be checking your submitted program files. The process will be *very* similar to what you did in lab09.

NOTE: IF AN ASSIGNMENT BELOW ASKS YOU TO IMPLEMENT A CERTAIN APPROACH, YOU **MUST** FOLLOW THOSE INSTRUCTIONS VERY CAREFULLY!!!

AS ALWAYS: DO NOT USE TECHNIQUES/INSTRUCTIONS THAT I HAVE NOT COVERED IN CLASS (or risk a zero grade).

Each corresponds to one of the problems listed below, which make up this lab. Each should be solved in its own file and each must be submitted for full assignment credit. 

Note: All these submissions will be checked by the automatic system on Gradescope AND by the instructor and TAs for further evaluation. Details below.

---
Your **FIRST STEP** should be to go an get copies of the following files found in our shared area:
http://cs.ucsb.edu/~zmatni/cs16s18/lab10/lab10.cpp

http://cs.ucsb.edu/~zmatni/cs16s18/lab10/lab10_functions.cpp

http://cs.ucsb.edu/~zmatni/cs16s18/lab10/lab10_headers.h

http://cs.ucsb.edu/~zmatni/cs16s18/lab10/Makefile

The **lab10.cpp** file is the one with the main() function. Take a look at this file first to get a rough idea of what you need to design (and then see the glorious details below!)
You will NOT be editing this file.

The **lab10_headers.h** file contains the program headers: the structure definition and the declaration of all the functions that are used in the program. You will NOT to be edited either; the same goes for the Makefile. Take a look at these files before beginning as well.

You WILL be editing the **lab10_functions.cpp file only.**

<h3>DESCRIPTION OF THE PROGRAM</h3>
A *palindrome* is a word or phrase whose meaning may be interpreted the same way in either forward or reverse direction. Famous examples include "Amore, Roma", "A man, a plan, a canal: Panama" and "No 'x' in 'Nixon'".

Write a recursive function that returns a Boolean value of true if an input string is a palindrome and false if it is not. You can do this by checking if the first character equals the last character, and if so, make a recursive call with the input string minus the first and last characters. You will have to define a suitable stopping condition.

Important: the string may contain ANY character, like whitespaces, hash-tags, numbers, etc... You should only be checking if the alphabet characters constitute a palindrome (ignore the character case).

Look at the lab10.cpp program provided and the main() function therein. It takes in a string as user input, then calls 2 functions (cleanUp() and isPalindrome()) and, on the basis of the answer it sees, it outputs the result.

Here are a few sample runs:

The program should print a string of text to the terminal before getting the inputs from the user. A session should look like one of the following examples (including whitespace and formatting):

```
$ ./lab10
Enter sentence:
hello
It is not a palindrome.
$ ./lab10
Enter sentence:
Madam, I'm Adam
It is a palindrome.
$ ./lab10
Enter sentence:
MADAM!! I'M a d  am!?
It is a palindrome.
$ ./lab10
Enter sentence:
Madam I'm ada
It is not a palindrome.
```

Other example runs:

```
$ ./lab10
Enter sentence:
A Santa dog lived as a devil God at NASA
It is a palindrome.
$ ./lab10
Enter sentence:
...Maps, DNA, and spam...
It is a palindrome.
$ ./lab10
Enter sentence:
As I pee, sir, I see Pisa!
It is a palindrome.
$ ./lab10
Enter sentence:
Just as I suspected...
It is not a palindrome.
```

*You MUST use a recursive function to build this program and you may not use built-in C++ functions or any other techniques that we have NOT discussed in lecture.*

---

<h2>Step 3: Submit using GRADESCOPE</h2>

*BEFORE YOU SUBMIT YOUR FILE:* Make sure that you have COMMENTS in your program that would help explain what your program is doing to another person reading your program code. Also make sure that you STYLIZE your program appropriately with correct indendation and so on (see the handout on Piazza re: this) to additionally make it easier on others reading your code. These 2 aspect (having appropriate comments and style) will be graded for an *extra 20 points* beyond the automatic grade you get from the submission system (called Gradescope). Please remember that you must submit the programs to obtain any credit for the assignment; just completing the programs is not enough.

You may submit this lab multiple times. You should submit only after local compilation does not produce any errors and runs as expected. The score of the last submission uploaded before the deadline will be used as your assignment grade.

<strong>We will use Gradescope to grade all your lab/programming assignments from here on. You should have received an email notification with instructions about logging into Gradescope.</strong>

Log into <a href="https://www.gradescope.com" _target="blank">https://www.gradescope.com</a> and find our class site: <strong>CS16, Spring 2018, Matni</strong>. Then navigate to the lab assignment (lab10) and select this assignment. You should see a "Submit Programming Assignment" window pop up. Make sure you have selected "Upload" as Submission Method (not "Github" or "Bitbucket"). Go ahead and submit all of your .cpp files for this assignment and click the green "Upload" button.

<img src="Gradescope_Upload.png" alt="pic of gradescope submit" width="450" />

**IMPORTANT**
**You will submit just ONE file: *lab10_functions.cpp*. You do not need to submit any of the other files.**

When you submit your C++ program file, wait for the results (these might take a minute or two).
You then will see feedback from Gradescope's Autograder - both about what passed and what failed, like in the picture here:

<img src="Gradescope_PassFail.png" alt="pic of gradescope pass and fail tests" width="800" />

You can re-submit your programs (you have to re-submit ALL of them, even if you're only making changes in one of them) before the deadline. Do this by clicking on the “Resubmit” button on the bottom right corner to make a submission. 

<img src="Gradescope_Buttons.png" alt="pic of gradescope buttons" width="600" />

When you are done (after submitting), you will be able to see your lab score.

<h2>Step 4: Done!</h2>

Once your submission receives a score of 100/100, you are done with this assignment. REMEMBER that there are 20 additional points that will be scored according to your proper use of comments and styling. The total will then be normalized to 100 points again (i.e. 120 score will be 100%, 111 score is 92.5%, etc...) to grade this lab.

*WE WILL BE CHECKING FOR PLAGIARISM -- DO NOT COPY FROM OTHER STUDENTS OR FROM SOURCES ONLINE! USE PROPER CITATION OF CODE THAT YOU DID NOT WRITE! THE CONSEQUENCES WILL - AT MINIMUM - BE A ZERO ON THIS LAB AND POSSIBLY A ZERO IN THIS COURSE AND YOU WILL BE REPORTED TO THE UNIVERSITY.*

If you are in the Phelps lab or in CSIL, make sure to log out of the machine before you leave. Also, make sure to close all open programs before you log out. Some programs will not work next time if they are not closed. Remember to save all your open files before you close your text editor.

If you are logged in remotely, you can log out using the exit command:

`$ exit`

<hr>
<p><font size="1">
Copyright 2018, Ziad Matni, CS Dept, UC Santa Barbara. Permission to copy for non-commercial, non-profit, educational purposes granted, provided appropriate credit is given; all other rights reserved.
</font></p>

</div>
