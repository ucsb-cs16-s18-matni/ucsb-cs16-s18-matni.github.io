---
layout: lab
num: lab07
ready: true
desc: "Arrays"
assigned: 2018-05-16 08:00:00.00-8
due: 2018-05-21 08:00:00.00-8
---
<div markdown="1">
<h1>CS16: Programming Assignment 07</h1>
<h2>Introduction -- Important: Read this!</h2>
<h2>This assignment is due on Monday, May 21st at Noon.</h2>
The assignment for this week will utilize concepts of arrays. Once again, the TAs and I will be looking for (and grading) programming stylizations and other requirements.So, it is not enough for your lab to pass Gradescope! Please read the instructions herein <b>carefully</b>. 

<h3>Pair programming is <b>OPTIONAL</b> for this lab. If you choose a lab partner, they MUST be registered in the SAME lab as you.</h3>

If working in a pair: Choose who will be the first driver and who will start as navigator, and then remember to switch (at least once) during the lab. But you should probably know the long-term goal too: each partner should participate in both roles in approximately equal parts over the course of the assignment. 
We realize it is not possible to equally split time in every lab perfectly, but it is worth trying, and it is possible to make up for unequal splits in future labs. We trust you will try to meet this goal. Thanks!

<h2>Step 1: Getting Ready</h2>
1. Decide if you are working alone, or working in a pair.

2. If you are working as a pair, register as such on Gradescope AND put your partner's name in all your submitted files (as a comment at the top of the file).

3. Decide on initial navigator and driver.

4. Driver, log on to your CSIL account.

5. Open a terminal window and log into the correct machine.

6. Change into your CS 16 directory, create a lab07 directory and change into it.
Remember that at any time, you can check what directory you are currently in with the command <b>pwd</b>.

<h2>Step 2: Create and Edit Your C++ Files</h2>
This week, you will need to create <b>2 files called matrix.cpp, and climb.cpp</b>:
Each corresponds to one of the problems listed below, which make up this lab.

This assignment consists of 2 problems, each of which is described below. Each is worth 50 points. Each should be solved in its own file and each must be submitted for full assignment credit. 

Note: All these submissions will be checked by the automatic system on Gradescope AND by the instructor and TAs for further evaluation. Details below.

---

<h3>CLIMB.CPP</h3>
DO NOT USE ANY PROGRAMMING INSTRUCTIONS/TECHNIQUES NOT COVERED IN CLASS. YOU WILL GET A ZERO GRADE IF YOU DO SO!

This program will utilize concepts of geometry and trigonometry.  
Write a program which determines how steep the climb is to the top of a mountain. The program will take user input which looks like the following:

```
1 2 3
2 2 2
```

This represents a two-dimensional rectangle of integers. We are looking at a mountain (or mountains) from above (think of flying over a Minecraft landscape), and the area has a rectangular base. Each value is the height of the terrain at that specific point in the rectangle (in increments of 1 on both axes). Each horizontal row will be on a new line, and the end of the entire input will be noted with an empty line with no integers.

In this example, the top left corner is the lowest point with a height/elevation of 1 and the top right corner is the peak of the mountain at height 3.

The horizontal distance between each point is the standard 2-dimensional distance. In this example, the distance between the top left and top right corners is 2, and the distance between the top left and bottom right corners is sqrt(5) -- because of the Pythogrean Rule.

<b>Your program should find lowest and highest heights in the input</b>. It should then <b>compute the angle</b> between a line between the terrain at those two points and the horizontal plane (i.e. the angle you would be climbing if you went in a straight line from the lowest to highest point). The angle should then be printed in radians.

Using the example above, you can visualize the lowest and highest points (they happen to be on the same horizontal) and the angle made in the diagram below:

<img src="climb_visual.png" width="150" alt="climb visual image" />

With the heights given above, the horizontal distance between the lowest and highest points is 2 and the change in height is also 2 (lowest at 1 to highest at 3). Therefore the angle of the line between them (from the horizontal) is 45 degrees or 0.785 radians.

Hint: remember that the distance between two points, (x<sub>1</sub>, y<sub>1</sub>) and (x<sub>2</sub>, y<sub>2</sub>), is the square root of ( (x<sub>1</sub> - x<sub>2</sub>)<sup>2</sup> + (y<sub>1</sub> - y<sub>2</sub>)<sup>2</sup> ).

Hint: the <cmath> library contains the arctangent function, with the name <b>atan()</b>.

Note: Assume that the lowest and the highest points are unique. This may not be true for other points.

REQUIRED: 
The input should be stored in a multidimensional integer array. The rectangle of heights will have a size less than or equal to 10 by 10. The program must utilize functions in the design. You are required to have at least one function that passes an array.

The program should print a string of text to the terminal before getting each line of input from the user. A session should look like one of the following examples (including whitespace and formatting), with a possibly numbers and letters in the output:

```
Enter heights:
5 5 6 5
5 6 7 6
5 5 6 6
3 4 4 5
2 3 3 3
2 2 2 2
1 2 2 2

The angle of the climb is 0.839 radians.
```

or

```
Enter heights:
1 2 3

The angle of the climb is 0.785 radians.
```

The string printed by the program should include a newline at the end, but no other trailing whitespace (whitespace at the end of the line).

The angle, in radians, should be printed to three places after the decimal.

---

<h3>MATRIX.CPP</h3>
DO NOT USE ANY PROGRAMMING INSTRUCTIONS/TECHNIQUES NOT COVERED IN CLASS. YOU WILL GET A ZERO GRADE IF YOU DO SO!

This program will utilize concepts regarding matrix algebra. 
Write a program which multiplies two matrices. The matrices may be any size, contain integers, and will come as input from the user. 
Each matrix will be input with the columns separated by spaces and the rows each on a new line. The end of each matrix will be specified by an empty line with no integers. Your program should print the resulting matrix with each column separated by a space, and each row on a new line.

Remember that the matrix product is defined as:

(AB)<sub>ij</sub> = sum of (A<sub>ik</sub> * B<sub>kj</sub>) for k = 1 to m (where m is the number of columns in A and the number of rows in B).

Your program should output an error if the dimensions of the input matrices are incompatible (the number of columns in the first matrix is not equal to the number of rows in the second matrix).

REQUIRED: 
Each input matrix should be stored in a multidimensional integer array. The result matrix will also be stored in a multidimensional array. All three matrices have sizes less than or equal to 10 by 10. 

The program should print a string of text to the terminal before getting input from the user. A session should look like one of the following examples (including whitespace and formatting), with a matrix (or error message) in the output:

```
Enter first matrix:
1 2 3
4 5 6

Enter second matrix:
7 8
9 0
1 2

The product is:
28 14
79 44
```

or

```
Enter first matrix:
1 2 3

Enter second matrix:
4 5 6

The two matrices have incompatible dimensions.
```
	
Each string printed by the program should include a newline at the end, but no other trailing whitespace (whitespace at the end of the line).

---

<h2>Step 3: Create a makefile and Compile the Codes with the make Command</h2>
In order to learn another way to manage our source codes and their compilations, we will first create a makefile and put in the usual g++ commands in it. Afterwards, whenever we want to compile our programs, the Linux command is a lot shorter. The use of makefiles will reveal itself to be very useful the more complex our programs and CS projects become.

Using your text editor, create a new file called makefile and enter the following into it:

<div markdown="1">
```
all: climb matrix

climb:
	g++ -std=c++11 -Wall climb.cpp -o climb

matrix:
	g++ -std=c++11 -Wall matrix.cpp -o matrix

clean:
	rm climb matrix

```
</div>

The new option -Wall is short for "warn all" in g++. This allows the compiler to throw out a maximum number of warnings or errors at you when compiling, which might be useful in your test and debug phases.

The new "clean:" make allows you to remove the executable files that you have previously created when re-launching a new compliling session (that should create new files for you in any case). This is an option to use, but I find it useful to "clean house" once in a while. You can add any number of other Linux/Unix commands in make files.

To run the makefile, see the previous 2 labs for examples.

<b>If you encounter an error, use the compiler hints and examine the line in question. If the compiler messsage is not sufficient to identify the error, you can search online to see when the error occurs in general.</b>

Remember to re-compile the relevant files after you make any changes to the C++ code.

<h2>Step 4: Submit using GRADESCOPE</h2>

*BEFORE YOU SUBMIT YOUR FILES:* Make sure that you have COMMENTS in your program that would help explain what your program is doing to another person reading your program code. Also make sure that you STYLIZE your program appropriately with correct indendation and so on (see the handout on Piazza re: this) to additionally make it easier on others reading your code. These 2 aspect (having appropriate comments and style) will be graded for an *extra 20 points* beyond the automatic grade you get from the submission system (called Gradescope). Please remember that you must submit the programs to obtain any credit for the assignment; just completing the programs is not enough.

You may submit this lab multiple times. You should submit only after local compilation does not produce any errors and runs as expected. The score of the last submission uploaded before the deadline will be used as your assignment grade.

<strong>We will use Gradescope to grade all your lab/programming assignments from here on. You should have received an email notification with instructions about logging into Gradescope.</strong>

Log into <a href="https://www.gradescope.com" _target="blank">https://www.gradescope.com</a> and find our class site: <strong>CS16, Spring 2018, Matni</strong>. Then navigate to the lab assignment (lab07) and select this assignment. You should see a "Submit Programming Assignment" window pop up. Make sure you have selected "Upload" as Submission Method (not "Github" or "Bitbucket"). Go ahead and submit all of your .cpp files for this assignment and click the green "Upload" button.

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
