---
layout: lab
num: lab04
ready: true
desc: "Functions; Passing Arguments into C++ Programs"
assigned: 2018-04-25 08:00:00.00-7
due: 2018-04-30 12:00:00.00-7
---

<div markdown="1">

<h1>CS16: Programming Assignment 04</h1>
<h2>Introduction</h2>
The assignment for this week will utilize concepts of passing arguments from the command line and basic function use in C++. PLEASE READ THESE INSTRUCTIONS CAREFULLY: DETAILS MATTER!!!

<h2>Step 1: Getting Ready</h2>
This week we are <strong>NOT USING SUBMIT.CS</strong>, but rather another auto-grading system, so please <strong>read these instructions very carefully</strong>.

First, open a terminal window and log into the correct machine.
Change into your CS 16 directory, create a lab04 directory and change into it.
Remember that at any time, you can check what directory you are currently in with the command <b>pwd</b>.

<h2>Step 2: Create and Edit Your C++ Files</h2>
This week, you will need to create <b>2 files called inflation.cpp and reverseArgs.cpp</b>:
Each corresponds to one of the problems listed below, which make up this lab.
Each is worth 50 points and should be solved in its own file and both must be submitted for full assignment credit. 

*IMPORTANT NOTE:* This lab will be also graded for use of comments and style. See below for details. In addition, we will take *major* points OFF if you use C++ instructions/libraries/code that either (a) was not covered in class, or (b) was found to be copied from outside sources (or each other) without proper citation.

<h3>INFLATION.CPP</h3>
Write a program that gauges the rate of inflation over the past year. The program asks for the price of an item (such as a hot dog or a 1-carat diamond) both from one year ago and today. It estimates the inflation rate as the difference in price divided by the year-ago price. Your program should allow the user to repeat this calculation as often as the user wishes. Define a function to compute the rate of inflation. The inflation rate should be a value of type double giving the rate as a percent, for example 5.32 for 5.32 percent. The inflation rate must be displayed to exactly two digits after the decimal point.

REQUIREMENT: Your program must use a function to compute the rate of inflation. A program which does not use a function will be awarded a score of zero, even if all tests pass. You are only permitted to use the <strong>iostream</strong> library. These requirements will be checked by the instructor and the TAs.  

STYLING: You must follow the styling conventions that we have been discussing in class. I have posted a list of these conventions on Piazza. Additionally, the program must make good use of comments in the code, per the discussions we have been having in class. Again, proper styling and the presence of comments (and thier good use) will be checked by the instructor and the TAs.

A session should look <b><i>exactly</i></b> like the following example (including whitespace and formatting - note that there is no whitespace at the end of each of these lines and each printed line has a newline at the end), with all manners of different numbers for inputs and the output:

<img src="inflation.png" width="500" alt="inflation program example" />

<h3>REVERSEARGS.CPP</h3>
Write the program reverseArgs.cpp that takes command line input arguments and prints them back in reverse order.
For example, if you ran the program as `./reverseArgs first_arg second_arg`, you would get an output back of `second_arg first_arg`.

If you ran the program as `./reverseArgs I love gorgonzola cheese, but I hate toothpaste`, you would get an output back of `toothpaste hate I but cheese, gorgonzola love I`. This is why I (lovingly) refer to this exercise as "the Yoda program"...

If you ran the program with double quotes, then the words within should act as one unit. For example: `./reverseArgs I would rather be at "UC Santa Barbara"` would output: `UC Santa Barbara at be rather would I`.

REQUIREMENTS: You are only permitted to use the <strong>iostream</strong> and (optionally) the <strong>cstdlib</strong> libraries.

STYLING: You must follow the styling conventions that we have been discussing in class. I have posted a list of these conventions on Piazza. Additionally, the program must make good use of comments in the code, per the discussions we have been having in class. Again, proper styling and the presence of comments (and thier good use) will be checked by the instructor and the TAs.

A session should look <b><i>exactly</i></b> like the following example (including whitespace and formatting - note that there is no whitespace at the end of each of these lines and each printed line has a newline at the end), with all manners of different numbers for inputs and the output:

<img src="reverseArgs.png" width="700" alt="reverse program example" />

<h2>Step 3: Create a makefile and Compile the Codes with the make Command</h2>
In order to learn another way to manage our source codes and their compilations, we will first create a makefile and put in the usual g++ commands in it. Afterwards, whenever we want to compile our programs, the Linux command is a lot shorter. The use of makefiles will reveal itself to be very useful the more complex our programs and CS projects become.

Using your text editor, create a new file called makefile and enter the following into it:

<div markdown="1">
```
all: inflation reverseArgs 

inflation: inflation.cpp
   g++ -Wall -o inflation inflation.cpp

reverseArgs: reverseArgs.cpp
   g++ -Wall -o reverseArgs reverseArgs.cpp
```
</div>

Then from the Linux prompt, you can do one of two things: either issue separate compile commands for each project, like so:

`$ make inflation`

etc...

Or, you can issue one command that will compile all the projects mentioned in the makefile, like so:

`$ make`

If the compilation is successful, you will not  see any output from the compiler. You can then use the following commands to run your programs:

`$ ./inflation`

`$ ./reverseArgs (with different line command inputs)`

<b>If you encounter an error, use the compiler hints and examine the line in question. If the compiler messsage is not sufficient to identify the error, you can search online to see when the error occurs in general.</b>

Remember to re-compile the relevant files after you make any changes to the C++ code.

<h2>Step 4: Submit using GRADESCOPE</h2>

*BEFORE YOU SUBMIT YOUR FILES:* Make sure that you have COMMENTS in your program that would help explain what your program is doing to another person reading your program code. Also make sure that you STYLIZE your program appropriately with correct indendation and so on (see the handout on Piazza re: this) to additionally make it easier on others reading your code. These 2 aspect (having appropriate comments and style) will be graded for an *extra 20 points* beyond the automatic grade you get from the submission system (called Gradescope). Please remember that you must submit the programs to obtain any credit for the assignment; just completing the programs is not enough.

You may submit this lab multiple times. You should submit only after local compilation does not produce any errors and runs as expected. The score of the last submission uploaded before the deadline will be used as your assignment grade.

<strong>We will use Gradescope to grade all your lab/programming assignments from here on. You should have received an email notification with instructions about logging into Gradescope.</strong>

Log into <a href="https://www.gradescope.com" _target="blank">https://www.gradescope.com</a> and find our class site: <strong>CS16, Spring 2018, Matni</strong>. Then navigate to the lab assignment (lab04) and select this assignment. You should see a "Submit Programming Assignment" window pop up. Make sure you have selected "Upload" as Submission Method (not "Github" or "Bitbucket"). Go ahead and submit all of your .cpp files for this assignment and click the green "Upload" button.

<img src="Gradescope_Upload.png" alt="pic of gradescope submit" width="450" />

When you submit *BOTH* your .cpp C++ program files, wait for the results (these might take a minute or two).
You then will see feedback from Gradescope's Autograder - both about what passed and what failed, like in the picture here:

<img src="Gradescope_PassFail.png" alt="pic of gradescope pass and fail tests" width="800" />

You can re-submit your programs (you have to re-submit ALL of them, even if you're only making changes in one of them) before the deadline. Do this by clicking on the “Resubmit” button on the bottom right corner to make a submission. 

<img src="Gradescope_Buttons.png" alt="pic of gradescope buttons" width="600" />

When you are done (after submitting), you will be able to see your lab score.

<h2>Step 5: Done!</h2>

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
