---
layout: lab
num: lab05
ready: true
desc: "Binary <-> Decimal Conversions"
assigned: 2018-05-02 08:00:00.00-7
due: 2018-05-07 12:00:00.00-7
---

<div markdown="1">

<h1>CS16: Programming Assignment 05</h1>
<h2>Introduction</h2>
The assignment for this week will utilize loops, conditionals, and functions, in the context of doing number conversions between binary and decimal (and vice-versa). You will have to utilize strings and string manipulation to some degree.

It is HIGHLY RECOMMENDED that you go through these 3 exercises in the order in which they are described to you here. Also, it is equally HIGHLY RECOMMENDED that you develop the algorithms for each program FIRST and THEN develop the C++ code for it.

<h2>Pair programming is <b>REQUIRED</b> for this lab!!!</h2>
You **must** choose a partner for this lab before you begin! Partners **must** be in the **same** lab section. Please consult with your lab TA if you cannot find a partner. No changes will be allowed to your paired grouping once established.

Again, you MUST pair with someone IN THE SAME LAB AS YOU. Both students will submit the same files and get the same grade. Ask your T.A. for help if you need it. In the case where there is an odd number of students in the lab, the T.A. will choose who the un-paired student will be (ONLY ONE student per lab is allowed this).

To learn more about pair programming, watch the following video (it takes less than 10 minutes, but watch it BEFORE you get to the lab to make the best out of your time in there):

[http://bit.ly/pair-programming-video](http://bit.ly/pair-programming-video){: target="_blank"}_

Choose who will be the first "driver" and who will start as "navigator", and then remember to switch (at least once) during the lab. But you should probably know the long-term goal too: each partner should participate in both roles in approximately equal parts over the course of the assignment. 

DO NOT share passwords. Instead, use scp or email to share files with each other at the end of each work session.

**PLEASE MAKE SURE YOU TRADE CONTACT INFORMATION WITH YOUR LAB PARTNER! This means emails, phone numbers, online chat handles, or whatever is necessary to continue working together when you are working remotely.**

Share your work with each other at the end of EVERY work session. That way, if your pair partner gets hit by a bus (or a rusty Ferrari, or a flying fish, or wins the lottery and quits UCSB, or ... you get the idea) you can continue working without him/her. :)

All lab exercises will be graded for styling as well as any requirements spelled-out below.

<h2>Step 1: Getting Ready</h2>
Open a terminal window and log into the correct machine.
Change into your CS 16 directory, create a lab05 directory and change into it.
Remember that at any time, you can check what directory you are currently in with the command <b>pwd</b>.

<h2>Step 2: Create and Edit Your C++ Files</h2>
This week, you will need to create <b>3 files called 8binConv.cpp, binGen.cpp, and 8binTest.cpp</b>:
Each corresponds to one of the problems listed below, which make up this lab.
Each should be solved in its own file and must be submitted for full assignment credit. 

*IMPORTANT NOTE:* This lab will be also graded for use of comments and style. See below for details. In addition, we will take points OFF if you use C++ instructions/libraries/code that either (a) was not covered in class, or (b) was found to be copied from outside sources (or each other) without proper citation.

---
<h3>8binConv.cpp</h3>

This program will take 1 command-line input in the form of an 8-bit number. It always has to be an 8-bit number.
It will convert that 8-bit BINARY number into a DECIMAL number.
For example, if the user runs the program with a command-line argument of 00000101, the result is the decimal number 5.

If the user enters no command-line inputs, then the program will print out an error message.
If the user enters more than 1 command-line input, the program will print out that same error message.
If the user enters an input that is NOT comprised of an 8-bit binary number, the program will print out that same error message (the program only needs to check the length of that input, not whether the user actually put in a proper binary number).

See example print out (note that the first 2 entries are purposeful mistakes and generate the error message):

```
$ ./8binConv
Usage: 8binConv <8-bit binary number>
$ ./8binConv 0000000
Usage: 8binConv <8-bit binary number>
$ ./8binConv 00000000
That's 0 in decimal.
$ ./8binConv 00000001
That's 1 in decimal.
$ ./8binConv 01010001
That's 81 in decimal.
$ ./8binConv 11111111
That's 255 in decimal.
```
You can include <b>cstdlib</b>, <b>cstring</b>, <b>string</b>, and <b>cmath</b> (in addition to <b>iostream</b>, of course) libraries.

Some clues that will likely come in handy:

* Recall that argv[x] are strings of characters, more commonly known as <b>C-strings</b>. If you have a C-string variable, cst, the command <b>strlen(cst)</b> returns the LENGTH of that C-string. <b>strlen</b> is a built-in function found in <cstring>.

* To examine a character in a C-string, say in cst, you can use indexing of the C-string, for example, if str="Hello", then str[0]='h', str[1]='e', and so on. Indexing in C/C++ always starts at zero.

* To convert a binary number into decimal, you can use the "positional notation" algorithm as illustrated by the example here:

```
1011 (in binary) = 1 x (2^3) + 0 x (2^2) + 1 x (2^1) + 1 x (2^0) = 8 + 2 + 1 = 11 (in decimal)
```

---
<h3>binGen.cpp</h3>

This program will ask the user the number of bits needed (let us say that value goes into the variable "N").
The program will then generate ALL POSSIBLE "N"-bit BINARIES.
For example, if the user enters 3 at the input prompt, the program would then generate:

```
000
001
010
011
100
101
110
111
```

Those are all 8 possibilities using 3 bits. Note that (and this will be a challenge) when the numbers are printed out, they are ALWAYS in forms of "N" bits (in this case N = 3), that is, you will need to PAD your printed numbers with enough "0"s on the left to always maintain "N" bits.

See example print out:

```
$ ./binGen 
How many bits to generate? 2
The decimal number 0 is 00
The decimal number 1 is 01
The decimal number 2 is 10
The decimal number 3 is 11
$ ./binGen 
How many bits to generate? 3
The decimal number 0 is 000
The decimal number 1 is 001
The decimal number 2 is 010
The decimal number 3 is 011
The decimal number 4 is 100
The decimal number 5 is 101
The decimal number 6 is 110
The decimal number 7 is 111
$ ./binGen 
How many bits to generate? 4
The decimal number 0 is 0000
The decimal number 1 is 0001
The decimal number 2 is 0010
The decimal number 3 is 0011
The decimal number 4 is 0100
The decimal number 5 is 0101
The decimal number 6 is 0110
The decimal number 7 is 0111
The decimal number 8 is 1000
The decimal number 9 is 1001
The decimal number 10 is 1010
The decimal number 11 is 1011
The decimal number 12 is 1100
The decimal number 13 is 1101
The decimal number 14 is 1110
The decimal number 15 is 1111
```

You will need to include <b>string</b> and <b>cmath</b> (in addition to <b>iostream</b>, of course) libraries.

Some clues that will come in handy:

* Here, we are going to be using <b>strings</b>, not C-strings. The difference is subtle between the two types, but they are essentially both strings of characters (I explained some of the differences in lecture). As such, if you want to find out the length of a string (called, say, MyStr), you would NOT use strlen(MyStr), but rather <b>MyStr.size()</b>.

* To examine a character in a string, say MyStr, you can use indexing of the string, for example, if MyStr="Hello", then MyStr[0]='h', MyStr[1]='e', and so on. Indexing in C/C++ always starts at zero.

* To convert a decimal number into binary, you can use the "Division/Remainder" algorithm, which I covered in lecture on Thursday. You can see from the example below:

```
EXAMPLE: Convert the decimal number 22 into a binary representation.
Algorithm: Divide by 2, put aside the remainder and "collect" it, and re-divide the quotient by 2. Repeat until quotient is zero.
All the remainders (either 1 or 0) you put aside and collected now make up the binary number (note the order: the LAST remainder collected is the Most-Significant Bit).

22 / 2 = 11 R 0
11 / 2 = 5  R 1 
5  / 2 = 2  R 1
2  / 2 = 1  R 0
1  / 2 = 0  R 1

answer = 10110
```

---
<h3>8binTest.cpp</h3>

This program will test out a <b>function</b>, "binConv()", that converts an 8-bit BINARY number into a DECIMAL number. The function MUST therefore be based on the <b>8binConv.cpp</b> program that you developed earlier.

Additionally, this <b>8binTest.cpp</b> program is based on the <b>binGen.cpp</b> program you developed earlier, 
in that it will generate all possible combinations of binary numbers made up of <b>8-bits</b> and feed them, one by one, into the <b>"binConv()"</b> function.

The function <b>binConv()</b> must take a string input parameter (representing an 8-bit binary number) and returns an integer conversion. For example, binConv("00000111") returns the integer 7.

Your program will look something like this:

```cpp
int binConv(string n) 
{
// Copy in the code you made for 8binConv.cpp here,
// but take out the parts that are related to argc, argv, etc...
// and tailor it to taking in strings instead (simple change)
}

int main() 
{
// The first part of this will be just like binGen.cpp, 
// except that you will be fixing the number of bits to generate to 8
// and the cout statement at the end will look differently.
}
```

When you run the program, you should see it roll through all possible 8-bit numbers (there are 256 possible 8-bit numbers)
and present the decimal number next to it, as per this print out (of course, I am only showing the first 6 and the last 3 output lines...)

```
$ ./8binTest 
Binary number 00000000 is decimal number 0
Binary number 00000001 is decimal number 1
Binary number 00000010 is decimal number 2
Binary number 00000011 is decimal number 3
Binary number 00000100 is decimal number 4
Binary number 00000101 is decimal number 5

... 

Binary number 11111101 is decimal number 253
Binary number 11111110 is decimal number 254
Binary number 11111111 is decimal number 255
```

In order to learn another way to manage our source codes and their compilations, we will first create a makefile and put in the usual g++ commands in it. Afterwards, whenever we want to compile our programs, the Linux command is a lot shorter. The use of makefiles will reveal itself to be very useful the more complex our programs and CS projects become.

Using your text editor, create a new file called makefile and enter the following into it (note that the lines that have the g++ commands actually begin with a TAB character):

```
all: 8binConv binGen 8binTest

8binConv: 8binConv.cpp
	g++ -Wall -std=c++11 -o 8binConv 8binConv.cpp

binGen: binGen.cpp
	g++ -Wall -std=c++11 -o binGen binGen.cpp

8binTest: 8binTest.cpp
	g++ -Wall -std=c++11 -o 8binTest 8binTest.cpp

```

Then from the Linux prompt, you can do one of two things: either issue separate compile commands for each project, like so:

`$ make 8binConv`

Or, you can issue one command that will compile all the projects mentioned in the makefile, like so:

`$ make`

If the compilation is successful, you will not see any output from the compiler. You can then run your programs, for example:

`$ ./8binConv 10010110`

<b>If you encounter an error, use the compiler hints and examine the line in question. If the compiler messsage is not sufficient to identify the error, you can search online to see when the error occurs in general.</b>

Remember to re-compile the relevant files after you make any changes to the C++ code.

<h2>Step 3: Submit using GRADESCOPE</h2>

*BEFORE YOU SUBMIT YOUR FILES:* Make sure that you have COMMENTS in your program that would help explain what your program is doing to another person reading your program code. Also make sure that you STYLIZE your program appropriately with correct indendation and so on (see the handout on Piazza re: this) to additionally make it easier on others reading your code. These 2 aspect (having appropriate comments and style) will be graded for an *extra 20 points* beyond the automatic grade you get from the submission system (called Gradescope). Please remember that you must submit the programs to obtain any credit for the assignment; just completing the programs is not enough.

You may submit this lab multiple times. You should submit only after local compilation does not produce any errors and runs as expected. The score of the last submission uploaded before the deadline will be used as your assignment grade.

<strong>We will use Gradescope to grade all your lab/programming assignments from here on. You should have received an email notification with instructions about logging into Gradescope.</strong>

Log into <a href="https://www.gradescope.com" _target="blank">https://www.gradescope.com</a> and find our class site: <strong>CS16, Spring 2018, Matni</strong>. Then navigate to the lab assignment (lab05) and select this assignment. You should see a "Submit Programming Assignment" window pop up. Make sure you have selected "Upload" as Submission Method (not "Github" or "Bitbucket"). Go ahead and submit all of your .cpp files for this assignment and click the green "Upload" button.

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
