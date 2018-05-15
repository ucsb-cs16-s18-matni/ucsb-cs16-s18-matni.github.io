---
layout: lab
num: lab06
ready: true
desc: "Using File I/O Data Streams & String Manipulation"
assigned: 2018-05-09 08:00:00.00-7
due: 2018-05-14 12:00:00.00-7
---
<div markdown="1">

<h1>CS16: Programming Assignment 06</h1>
<h2>Introduction -- Important: Read this!</h2>
The assignment for this week will utilize concepts of file I/O data streams and string manipulation. 

Again, the TAs and I will be looking for (and grading) programming stylizations, such as proper use of comments, tab indentation, good variable names, and overall block and function designs. So, it is not enough for your lab to pass the auto-grader! Please read the instructions herein <b>carefully</b>.

BE AWARE that we will run anti-plagiarism software on this lab. If you are caught cheating by copying code from another student (lab partners excepted) or from a source on the internet, you WILL GET A ZERO ON THIS LAB and maybe a ZERO ON THIS COURSE.

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
Change into your CS 16 directory, create a lab06 directory and change into it.
Remember that at any time, you can check what directory you are currently in with the command <b>pwd</b>.

<h2>Step 2: Create and Edit Your C++ Files</h2>
This week, you will need to create <b>2 files called stddev.cpp and rhymes.cpp</b>:
Each corresponds to one of the problems listed below, which make up this lab.

Each of the 2 problems is worth 50% of the Gradescope portion of the grade. Each problem should be solved in its own file and each must be submitted for full assignment credit. Note: All these submissions will be checked by the automatic system on submit.cs AND by the instructor and TAs for further evaluation of coding style and meeting requirements. Details below.

---

<h3>STDDEV.CPP</h3>
This program takes its inputs from a file that contains numbers. The program reads them in as type double. The program outputs to the screen the <i>standard deviation</i> of the numbers in the file. The file contains nothing but numbers of type double separated by blanks and/or line breaks. The standard deviation of a list of numbers x1, x2, x3, and so forth is defined as the <b><i>square root</i></b> of:

((x1 – a)<sup>2</sup> + (x2 – a)<sup>2</sup> + (x3 – a)<sup>2</sup> + ...) / (n - 1)

Where the number a is the average of the numbers x1, x2, x3, and so forth and the number n is the count of how many numbers there are.  The answers should be given with 3 decimal points precision.  

The program has to ask the user for the file name and has to check to see if the file exists (use the string "Enter file name:\n" for the question). If it does not exist, the program must output (via cerr) an error message: "Input file opening failed." and then exit with code 1.

Your program should define <b>at least one function</b>. If your program does NOT have at least one function, you will not get credit for this part of the assignment, even if your program passes submit.cs grading. And remember that you can ONLY use programming techniques and instructions that we have covered in class so far.

A session should look <b><i>exactly</i></b> like the following example (including whitespace and formatting - note that there is no whitespace at the end of each of these lines and each printed line has a newline at the end), with all manners of different numbers for inputs and the output:

```
Enter filename:
nums.txt
The standard deviation is 1.581
```
The accompanying input file in this example, could look like this (note the separation by one or more spaces):

```
6 7 8    9			10
```

or like this (note the separation by either spaces or newline characters):

```
6 7
8
9
10
```

MAJOR REQUIREMENT: At least ONE function.

---

<h3>RHYMES.CPP</h3>
Write a program that finds rhyming words in a poem. Specifically, the program reads an input file, line by line, and extracts the last word in each line. It then compares this last word with the last word from the line after it. If it finds that the 2 words "rhyme" (which is simply defined as the 2 words that are being compared share the same 2 last letters), then it prints out these two words to standard output (i.e. the display). But FIRST, the words must be cleaned up of any
non-alphabetical characters (usually this means puncuation, since many poems have their last lines often end with a comma, a semicolon, a question-mark, etc...) So if the last word on a line has punctuation marks on it, e.g. "hello?!", it becomes "hello". Or if the last word is "don't", it becomes "dont".

Finally, the program has to state how many rhyming pairs it found, or if it did not find any at all.

The program has to ask the user for the file name and has to check to see if the file exists (use the string "Enter file name: " for the question). If it does not exist, the program must output (via cerr) an error message: "Input file opening failed." and then exit with code 1.

Your program should define <b>at least one function</b>. If your program does NOT have at least one function, you will not get credit for this part of the assignment, even if your program passes submit.cs grading. And remember that you can ONLY use programming techniques and instructions that we have covered in class so far.

As an example, assume there is a text file called "MyPoem.txt", which contains this:

<div markdown="1">
```
"I cannot go to school today,"
Said little Peggy Ann McKay.
"I cannot go to school and play!
I have the measles and the mumps,
A gash, a rash and purple bumps.
My mouth is wet, my throat is dry,
I’m going blind in my right eye.
My tonsils are as big as rocks,
I’ve counted sixteen chicken pox"
```
</div>

(slightly modified from the poem "Sick" by Shel Silverstein)

The program would run as follows:

<div markdown="1">
```
Enter file name: MyPoem.txt
today and McKay
McKay and play
mumps and bumps
There are 3 pairs of rhyming words.
```
</div>

Note that "dry" and "eye" were not shown, nor were "rocks" and "pox". This is because they do not meet the program's criteria of a "rhyme"'. Also note the last line says how many pairs of rhyming words there are. **Please make the word "pair" singular if only 1 pair of rhyming words is found and use the plural "pairs" if you found more than 1 rhyming pairs.**

Consider another example file called "No.txt":

<div markdown="1">
```
No means no, it always means no
If I say it once it means 
A thousand times no!
```
</div>

(slightly modified from the song "No!" by They Might Be Giants)

The program would run as follows:

<div markdown="1">
```
Enter file name: No.txt
No rhymes found.
```
</div>

Note that no rhymes were found because the program only looks at adjacent lines.

You can assume that the text file containing the poem has at least 2 words per line, that the rhyme comparison is case-sensitive, and that the last words in the line contain at least 2 characters.

You will need to use multiple <string> member functions to manipulate strings in this program. In addition, you will have to use the getline() function in the <string> library in order to read an entire line by ifstream. 

MAJOR REQUIREMENT: At least ONE function.

---

<h2>Step 3: Create a makefile and Compile the Codes with the make Command</h2>
In order to learn another way to manage our source codes and their compilations, we will first create a makefile and put in the usual g++ commands in it. Afterwards, whenever we want to compile our programs, the Linux command is a lot shorter. The use of makefiles will reveal itself to be very useful the more complex our programs and CS projects become.

Using your text editor, create a new file called makefile and enter the following into it:

<div markdown="1">
```
all: stddev rhymes

stddev:
	g++ -std=c++11 -Wall stddev.cpp -o stddev

rhymes:
	g++ -std=c++11 -Wall rhymes.cpp -o rhymes

```
</div>

Then from the Linux prompt, you can do one of two things: either issue separate compile commands for each project, like so:

`$ make stddev`

Or, you can issue one command that will compile all the projects mentioned in the makefile, like so:

`$ make`

If the compilation is successful, you will not see any output from the compiler. You can then run your programs, for example:

`$ ./stddev`

<b>If you encounter an error, use the compiler hints and examine the line in question. If the compiler messsage is not sufficient to identify the error, you can search online to see when the error occurs in general.</b>

Remember to re-compile the relevant files after you make any changes to the C++ code.

<h2>Step 4: Submit using Gradescope</h2>
*BEFORE YOU SUBMIT YOUR FILES:* Make sure that you have COMMENTS in your program that would help explain what your program is doing to another person reading your program code. Also make sure that you STYLIZE your program appropriately with correct indendation and so on (see the handout on Piazza re: this) to additionally make it easier on others reading your code. These 2 aspect (having appropriate comments and style) will be graded for an *extra 20 points* beyond the automatic grade you get from the submission system (called Gradescope). Please remember that you must submit the programs to obtain any credit for the assignment; just completing the programs is not enough.

You may submit this lab multiple times. You should submit only after local compilation does not produce any errors and runs as expected. The score of the last submission uploaded before the deadline will be used as your assignment grade.

<strong>We will use Gradescope to grade all your lab/programming assignments from here on. You should have received an email notification with instructions about logging into Gradescope.</strong>

Log into <a href="https://www.gradescope.com" _target="blank">https://www.gradescope.com</a> and find our class site: <strong>CS16, Spring 2018, Matni</strong>. Then navigate to the lab assignment (lab06) and select this assignment. You should see a "Submit Programming Assignment" window pop up. Make sure you have selected "Upload" as Submission Method (not "Github" or "Bitbucket"). Go ahead and submit all of your .cpp files for this assignment and click the green "Upload" button.

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
