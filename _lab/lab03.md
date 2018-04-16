---
layout: lab
num: lab03
ready: false
desc: "Functions and Command Line Arguments"
assigned: 2018-04-18 08:00:00.00-7
due: 2018-04-23 12:00:00.00-7
---

<div markdown="1">
<h1>THIS LAB DESCRIPTION IS NOT IN FINAL FORM!!! DO NOT USE!!!</h1>

<h1>CS16: Programming Assignment 03</h1>
<h2>Introduction</h2>
The assignment for this week will utilize concepts of void functions, function calls-by-reference, and command line arguments. 
This is material that is covered in lectures 4 and 5 in class.

<h2>Step 1: Getting Ready</h2>
This week we are <strong>NOT USING SUBMIT.CS</strong>, but rather another auto-grading system, so please <strong>read these instructions very carefully</strong>.

First, open a terminal window and log into the correct machine.
Change into your CS 16 directory, create a lab03 directory and change into it.
Remember that at any time, you can check what directory you are currently in with the command <b>pwd</b>.

<h2>Step 2: Create and Edit Your C++ Files</h2>
This week, you will need to create <b>2 files called change.cpp, and calculate.cpp</b>:
Each corresponds to one of the problems listed below, which make up this lab.
Each is worth 50 points and should be solved in its own file and both must be submitted for full assignment credit. 

*IMPORTANT NOTE:* This lab will be also graded for use of comments and style. See below for details. In addition, we will take *major* points OFF if you use C++ instructions/libraries/code that either (a) was not covered in class, or (b) was found to be copied from outside sources (or each other) without proper citation.

<h3>CHANGE.CPP</h3>
Write a program that tells what coins to give out for any amount of change from 1 cent to 99 cents. For example, if the amount is 86 cents, the output would be something like the following:

`86 cents can be given as 3 quarters, 1 dime, 1 penny.`

Use coin denominations of 25 cents (quarters), 10 cents (dimes), and 1 cent (pennies). Do not use nickel and half-dollar coins. 

Your program should use the following function (it doesn't have to be the only function, but you HAVE to use this one). Please note the use of call-by-reference parameters.

```cpp
void compute_coins(int coin_value, int& num, int& amount_left);
// Precondition: 0 < coin_value < 100; 0 <= amount_left < 100.
// Postcondition: num has been set equal to the maximum number
// of coins of denomination coin_value cents that can be obtained
// from amount_left. Additionally, amount_left has been decreased
// by the value of the coins, that is, decreased by num * coin_value.
```

For example, suppose the value of the variable `amount_left` is 86. Then, after the following call: 

`compute_coins(25, number, amount_left);`

the value of `number` will be 3 and the value of `amount_left` will be 11 (because if you take 3 quarters from 86 cents, that leaves 11 cents).

Include a loop that lets the user repeat this computation for new input values until the user says he or she wants to end the program by inputting a zero (see example below).

Your program <i><b>must use</b></i> the `compute_coins` function declaration shown above. A program which does not will be awarded a score of zero, even if all tests pass.

A session should look <b><i>exactly</i></b> like the following example (including whitespace and formatting - note that there is no whitespace at the end of each of these lines and each printed line has a newline at the end), with all manners of different numbers for inputs and the output:

<img src="change.png" width="700" alt="change program example" />

Also note that the words have to match the numbers (so singulars for quarter, dime, and penny are expected as appropriate for the case). This can be trickier than it looks.

<h3>CALCULATE.CPP</h3>
You will write a program that mimicks a simple calculator that can do adding, multiplication, or modulo of 2 integers.

The program takes 3 arguments at the command line: an integer, a character, and another integer. All of these arguments must be separated by a space character. The middle character can be one of only 3 types: '+', 'x', or '%'. The program then returns either the sum, the product, or the modulo of the 2 integers.

For example, if you ran the program as (by typing the following on the Linux command line): `./calculate 1 + 2`, then you should get `3` as the answer.

The program should be able to verify that:

1) the user has exactly 3 arguments.   
2) the operator used is one of the 3 allowed operators and nothing else.   
3) when using modulo, the second integer is not zero (otherwise, you would divide by zero).   

For each of these conditions, the program should print out a specific error message (called USAGE messages) and exit. For each condition, the error message should be:

1) Number of arguments is incorrect.   
2) Bad operation choice.   
3) Cannot divide by zero.   

<b>Hint:</b> you have to use <b>cerr</b> instead of <b>cout</b> to output the usage messages. Do not use <b>cerr</b> for any other outputs the program makes. While <b>cerr</b> and <b>cout</b> are alike in that they direct values to standard output, we usually use <b>cout</b> for the standard output, but use <b>cerr</b> to show or report errors to the user and the system. 

You may use the <b>exit(1)</b> statement when exiting from giving some of the error messages. The instructor will demonstrate the proper use of <b>exit(1)</b> and <b>cerr</b> in class on Tuesday (lecture 5).

Here is a skeleton program to help you get started:
```cpp
// Calculate.cpp
// By: <Your Name Here>
// Created on: <Date Here>
#include <iostream>
#include <cstdlib>
using namespace std;

// Usage: ./calculate int char int
// char can be one of 3 things: + x or %
int main( int argc, char *argv[] ) {

    // MISSING CODE: Check to see if the number of arguments is correct (hint: use argc)

    // MISSING CODE: Check for illegal operations

    // MISSING CODE: Do the appropriate calculations, outputs to std. output, etc...

    // Other missing code? You decide... :)

    return 0;
}
```

This program does not loop back to take inputs again. See the sample runs examples below.

```
$ ./calculate 4
Number of arguments is incorrect.

$ ./calculate 1 + 2
$ 3

$ ./calculate 6 + -19
$ -13

$ ./calculate 7 x -5
$ -35

$ ./calculate 8 % 3
$ 2

$ ./calculate 4 3 2 + 0
Number of arguments is incorrect.

$ ./calculate 5 - 4
Bad operation choice.

$ ./calculate 8 % 0
Cannot divide by zero.
```

<h2>Step 3: Create a makefile and Compile the Codes with the make Command</h2>
In order to learn another way to manage our source codes and their compilations, we will first create a makefile and put in the usual g++ commands in it. Afterwards, whenever we want to compile our programs, the Linux command is a lot shorter. The use of makefiles will reveal itself to be very useful the more complex our programs and CS projects become. We will discuss make and makefile in class soon!

Using your text editor, create a new file called makefile and enter the following into it:

<div markdown="1">
```
all: change calculate

change:
	g++ change.cpp -o change

calculate:
	g++ calculate.cpp -o calculate
```
</div>

Then from the Linux prompt, you can do one of two things: either issue separate compile commands for each project, like so:

`$ make change`

Or, you can issue one command that will compile all the projects mentioned in the makefile, like so:

`$ make`

If the compilation is successful, you will not see any output from the compiler. You can then run your programs, for example:

`$ ./change`

<b>If you encounter an error, use the compiler hints and examine the line in question. If the compiler messsage is not sufficient to identify the error, you can search online to see when the error occurs in general.</b>

Remember to re-compile the relevant files after you make any changes to the C++ code.

<h2>Step 4: Submit using GRADESCOPE</h2>

*BEFORE YOU SUBMIT YOUR FILES:* Make sure that you have COMMENTS in your program that would help explain what your program is doing to another person reading your program code. Also make sure that you STYLIZE your program appropriately with correct indendation and so on (see the handout on Piazza re: this) to additionally make it easier on others reading your code. These 2 aspect (having appropriate comments and style) will be graded for an *extra 20 points* beyond the automatic grade you get from the submission system (called Gradescope). Please remember that you must submit the programs to obtain any credit for the assignment; just completing the programs is not enough.

You may submit this lab multiple times. You should submit only after local compilation does not produce any errors and runs as expected. The score of the last submission uploaded before the deadline will be used as your assignment grade.

<strong>We will use Gradescope to grade all your lab/programming assignments from here on. You should have received an email notification with instructions about logging into Gradescope.</strong>

Log into <a href="https://www.gradescope.com" _target="blank">https://www.gradescope.com</a> and find our class site: <strong>CS16, Spring 2018, Matni</strong>. Then navigate to the lab assignment (lab03) and select this assignment. You should see a "Submit Programming Assignment" window pop up. Make sure you have selected "Upload" as Submission Method (not "Github" or "Bitbucket"). Go ahead and submit all of your .cpp files for this assignment and click the green "Upload" button.

<img src="Gradescope_Upload.png" alt="pic of gradescope submit" width="450" />

When you submit *BOTH* your change.cpp and calculate.cpp C++ program files, wait for the results (these might take a minute or two).
You then will see feedback from Gradescope's Autograder - both about what passed and what failed, like in the picture here:

<img src="Gradescope_PassFail.png" alt="pic of gradescope pass and fail tests" width="800" />

You can re-submit your programs (you have to re-submit ALL of them, even if you're only making changes in one of them) before the deadline. Do this by clicking on the “Resubmit” button on the bottom right corner to make a submission. 

<img src="Gradescope_Buttons.png" alt="pic of gradescope buttons" width="600" />

When you are done (after submitting), you will be able to see your lab score.

<h2>Step 5: Done!</h2>

Once your submission receives a score of 100/100, you are done with this assignment. REMEMBER that there are 20 additional points that will be scored according to your proper use of comments and styling. The total will then be normalized to 100 points again (i.e. 120 score will be 100%, 111 score is 92.5%, etc...) to grade this lab.

If you are in the Phelps lab or in CSIL, make sure to log out of the machine before you leave. Also, make sure to close all open programs before you log out. Some programs will not work next time if they are not closed. Remember to save all your open files before you close your text editor.

If you are logged in remotely, you can log out using the exit command:

`$ exit`

</div>
