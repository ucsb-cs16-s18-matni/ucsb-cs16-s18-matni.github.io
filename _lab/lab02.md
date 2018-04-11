---
layout: lab
num: lab02
ready: true
desc: "Simple Flow Control"
assigned: 2018-04-11 08:00:00.00-7
due: 2018-04-16 12:00:00.00-7
---

<div markdown="1">

<h1>CS16: Programming Assignment 02</h1>
<h2>Introduction</h2>
The assignment for this week will utilize concepts of input and output and simple control flow (Chapter 2 in the book).

<h2>Step 1: Getting Ready</h2>
If you have not gotten a CoE account yet, please do so as soon as possible!
Open a terminal window and log into the correct machine - refer to the instructions in Lab #1, if you forgot how to do that.

Start by changing into your CS 16 directory:

`$ cd cs16`

And then create and change into the lab02 directory:

`$ mkdir lab02`

`$ cd lab02`

Remember that at any time, you can check what directory you are currently in with the command <b>pwd</b>.

<h2>Step 2: Create and Edit Your C++ Files</h2>
For a reminder on how to open and use a text editor to create and edit new source files, refer back to Lab #1.

This assignment consists of 3 problems, each of which is described below. The first two are worth 30 points each, and the last is worth 40 points. Each should be solved in its own file and all three must be submitted for full assignment credit. These exercises are inspied by ones from the textbook (in Ch. 2) - but they are NOT the same, so follow the instructions on THIS sheet carefully.

IMPORTANT NOTE: DO NOT PLAGIARIZE. WE WILL BE ABLE TO TELL! 

ANOTHER VERY IMPORTANT NOTE: YOU MUST FOLLOW THE DIRECTIONS CAREFULLY BELOW OR YOU MAY LOSE POINTS: for example, the 1st program described has a requirement to use nested if-else statements. You can probably make the program run with different approaches: but I want you to create it with nested if-else statements.

ADDITIONALLY, YOU ARE NOT ALLOWED TO USE C++ CODE THAT HAS NOT BEEN COVERED IN CLASS. For example, we have not discussed functions or arrays as of yet in class, and you are not allowed to use those (and other not-covered topics) in this lab!

<h3>DESCEND.CPP</h3>
Write a program that takes 3 integer inputs from a user and prints them back in descending order. YOUR PROGRAM MUST HAVE NESTED IF-ELSE STATEMENTS!

A session should look <b><i>exactly</i></b> like the following example (including whitespace and formatting - although note that there is no whitespace at the end of each of these lines), with all manners of different numbers for inputs and the output:

```
-2 8 4
8 4 -2
```

OR:

```
22 -41 22
22 22 -41
```

Each string printed by the program should include a newline at the end, but no other trailing whitespace (i.e. NO extra space characters at the end of the line). If you DO have extra spaces at the end, then the submit.cs system will flag it as INCORRECT!!

<h3>BLOCK.CPP</h3>
Write a program that takes input from a user for number of rows and number of columns and prints out a block of characters that is based on these 2 parameters. The program should keep asking the user for input, and printing out the result, until the user enters zero for each of the input parameters.

A session should look <b><i>exactly</i></b> like the following example (including whitespace and formatting - although note that there is no whitespace at the end of each of these lines), with all manners of different numbers for inputs and the output:

<img src="block.png" width="700" alt="block program example" />

Each string printed by the program should include a newline at the end, but no other trailing whitespace (i.e. extra space characters at the end of the line).

<h3>PI.CPP</h3>
Write a C++ program that approximates the value of the constant π, based on both the Leibniz formula for estimating π. The formula is shown in the images below:

<img src="pi_formula_l.png" alt="pi Leibniz formula" width="500" />

The formula works well for high values of n.

The program takes an input from the user for the value of n, which determines the number of terms in the approximation of the value of pi. The program then outputs that calculation for the formula. You must also include a loop that allows the user to repeat this calculation for new values n until the user says she or he wants to end the program by issuing an input of 0. Finally, the results must be shown to the 5th decimal place.

The number of terms is assumed to NOT include the added 1 in the formula.
In other words, if the variable terms = 1, then pivalue = 4*[ 1 - (1/3) ], and if terms = 2, then pivalue = 4*[ 1 - (1/3) + (1/5) ], etc...

Here is a "skeleton" program to help you get started:

```cpp
#include <iostream>
#include <cmath> 
using namespace std;

int main()
{
    int terms(1);
    double pivalue(0); 

    // You need to do something about the formatting requirement here!
    // You also need to do a loop here that keeps asking for number of terms and then calculates pi!
    // HINT: You can use cmath for its pow() function, which calculates x raised to the power y when used like: pow(x,y)
    
    return 0;
}
```

The program should print a string of text to the terminal before getting each piece of input from the user. A session should look like the following example (including whitespace and formatting), with various and different inputs and numbers in the output:

```
Enter the number of terms to approximate (or zero to quit):
5
The approximation for Leibniz's Formula is 2.97605 using 5 terms.
Enter the number of terms to approximate (or zero to quit):
50
The approximation for Leibniz's Formula is 3.16120 using 50 terms.
Enter the number of terms to approximate (or zero to quit):
1000
The approximation for Leibniz's Formula is 3.14259 using 1000 terms.
Enter the number of terms to approximate (or zero to quit):
0
```

Note that each string printed by the program should include a newline at the end, but no other trailing whitespace (whitespace at the end of the line). Note that when the program exits, when a user enters 0, there is no approximation given - the program just ends there.

<h2>Step 3: Compile the Codes</h2>

To compile our codes, we will use the same g++ command as we described in previous labs. The following three commands will compile the three source files (in the same order as listed above):

`$ g++ -o descend descend.cpp`

`$ g++ -o block block.cpp`

`$ g++ -o pi pi.cpp`

If the compilation is successful, you will not  see any output from the compiler. You can then use the following commands to run your programs:

`$ ./descend`

`$ ./block`

`$ ./pi`

<b>If you encounter an error, use the compiler hints and examine the line in question. If the compiler messsage is not sufficient to identify the error, you can search online to see when the error occurs in general.</b>

Remember to re-compile the relevant files after you make any changes to the C++ code.

<h2>Step 4: Submit</h2>

Once you are satisfied that your programs are correct, it is time to submit them. Login at [https://submit.cs.ucsb.edu](https://submit.cs.ucsb.edu), then navigate to “CS16_s18_matni” and click on “lab02”. Then click “Make Submission”, and make your submission the same way as last week. Remember to submit all three .cpp files.

Please remember that you must submit the programs to obtain any credit for the assignment; just completing the programs is not enough.

Once you submit, you should see a page detailing your submission. The system will automatically grade your program and will show you the results on this page after a 1 minute delay.

You can alternatively submit your code from the command line (terminal) on any CS machine, including the Phelps lab machines or the CSIL server. You can use this method when logged in remotely. To submit the the three source files to this assignment by running the command:

`$ ~submit/submit -p 980 block.cpp descend.cpp pi.cpp`

You can copy the URL shown in the output of the above and paste into a web browser to reach the submission result page.

<h2>Step 5: Check Submission Results</h2>

After the 1 minute delay, the submit system will show your score and give you feedback on your submission. Refresh the webpage after a minute to see this information.

You may submit this lab multiple times. You should submit only after local compilation does not produce any errors and runs as expected. The score of the last submission uploaded before the deadline will be used as your assignment grade.

<h2>Step 6: Almost Done!</h2>

Once your submission receives a score of 100/100, you are done with this assignment. HOWEVER, PLEASE NOTE THAT YOUR ASSIGNMENT WILL ALSO BE GRADED FOR FOLLOWING DIRECTIONS (see the "IMPORTANT NOTE" at the top of this document) AND MAKING YOUR CODE "READABLE" (that is, use comments and tabbed spaces appropriately)! 

If you are in the Phelps lab or in CSIL, make sure to log out of the machine before you leave. Also, make sure to close all open programs before you log out. Some programs will not work next time if they are not closed. Remember to save all your open files before you close your text editor.

If you are logged in remotely, you can log out using the exit command:

`$ exit`

<hr>
<p><font size="1">
Copyright 2018, Ziad Matni, CS Dept, UC Santa Barbara. Permission to copy for non-commercial, non-profit, educational purposes granted, provided appropriate credit is given; all other rights reserved.
</font></p>

</div>
