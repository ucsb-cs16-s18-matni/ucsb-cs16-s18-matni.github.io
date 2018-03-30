---
layout: lab
num: lab03
ready: true
desc: "Basic Functions; Passing Arguments into C++ Programs"
assigned: 2017-10-16 08:00:00.00-7
due: 2017-10-23 12:00:00.00-7
---

<div markdown="1">

<h1>CS16: Programming Assignment 03</h1>
<h2>Introduction</h2>
The assignment for this week will utilize concepts of passing arguments from the command line and basic function use in C++. PLEASE READ THESE INSTRUCTIONS CAREFULLY: DETAILS MATTER!!!

<strong>Because of Midterm Exam #1 falling on Thursday, 10/19, Lab #3 is due to be turned in on Monday, 10/23. PLEASE NOTE THAT LAB #4 WILL BE GIVEN OUT NEXT WEEK AND WILL BE DUE ON THE REGULAR DATE!</strong>

<h2>Step 1: Getting Ready</h2>
If you have not gotten a CoE account yet, please do so as soon as possible!
Open a terminal window and log into the correct machine - refer to the instructions in Lab #1, if you forgot how to do that.

Start by changing into your CS 16 directory:

`$ cd cs16`

And then create and change into the lab03 directory:

`$ mkdir lab03`

`$ cd lab03`

Remember that at any time, you can check what directory you are currently in with the command <b>pwd</b>.

<h2>Step 2: Create and Edit Your C++ Files</h2>
This week, you will need to create <b>4 files called inflation.cpp, mortgage.cpp, reverseArgs.cpp and gonzo.cpp</b>:
Each corresponds to one of the problems listed below, which make up this lab. The first 2 problems are worth 30 points each and the last 2 problems are worth 20 points each. In addition, we will be grading you on program text style and readability AS WELL AS on following directions correctly.

For a reminder on how to open and use a text editor to create and edit new source files, refer back to Lab #1.

<h3>INFLATION.CPP</h3>
Write a program that gauges the rate of inflation over the past year. The program asks for the price of an item (such as a hot dog or a 1-carat diamond) both from one year ago and today. It estimates the inflation rate as the difference in price divided by the year-ago price. Your program should allow the user to repeat this calculation as often as the user wishes. Define a function to compute the rate of inflation. The inflation rate should be a value of type double giving the rate as a percent, for example 5.32 for 5.32 percent. The inflation rate must be displayed to exactly two digits after the decimal point.

REQUIREMENT: Your program must use a function to compute the rate of inflation. A program which does not use a function will be awarded a score of zero, even if all tests pass. You are only permitted to use the <strong>iostream</strong> library. These requirements will be checked by the instructor and the TAs.  

STYLING: You must follow the styling conventions that we have been discussing in class. I have posted a list of these conventions on Piazza. Additionally, the program must make good use of comments in the code, per the discussions we have been having in class. Again, proper styling and the presence of comments (and thier good use) will be checked by the instructor and the TAs.

A session should look <b><i>exactly</i></b> like the following example (including whitespace and formatting - note that there is no whitespace at the end of each of these lines and each printed line has a newline at the end), with all manners of different numbers for inputs and the output:

<img src="inflation.png" width="500" alt="inflation program example" />


<h3>MORTGAGE.CPP</h3>
Write a program that calculates the <i>annual after-tax cost</i> of a new house for the first year of ownership. The user inputs the price of the house and the downpayment made on it. The program thus knows what the loan amount is: the difference between the house price and the downpayment. The program also knows at least three constants: the loan interest rate (6%), the loan reduction cost rate (3%), and your income tax rate (35%).

Home loans are subjected to an interest rate - that is one cost to home-owners. Additionally, they are paying off their loan at a certain rate (the loan reduction rate) - that is another cost. Thus the total annual mortgage costs for home-ownership is defined. However, home-owners get a bit of a break on their total costs because they can deduct part of their interest payments when they pay their taxes. These tax savings amount to the interest payment amount multiplied by their income tax rate.

So, the real annual cost to a home-owner - the annual after-tax cost - is computed as the total annual mortgage cost minus the tax savings.

Should inputs should be of type double or int? 

REQUIREMENT: Your program should use at least TWO function definitions (other than main function) and should allow the user to repeat this calculation as often as the user wishes. A program which does not use at least 2 functions will be awarded a score of zero, even if all tests pass. You are only permitted to use the <strong>iostream</strong> library. These requirements will be checked by the instructor and the TAs.

STYLING: You must follow the styling conventions that we have been discussing in class. I have posted a list of these conventions on Piazza. Additionally, the program must make good use of comments in the code, per the discussions we have been having in class. Again, proper styling and the presence of comments (and thier good use) will be checked by the instructor and the TAs.

A session should look <b><i>exactly</i></b> like the following example (including whitespace and formatting - note that there is no whitespace at the end of each of these lines and each printed line has a newline at the end), with all manners of different numbers for inputs and the output:

<img src="mortgage.png" width="700" alt="mortgage program example" />

<h3>REVERSEARGS.CPP</h3>
Write the program reverseArgs.cpp that takes command line input arguments and prints them back in reverse order.
For example, if you ran the program as `./reverseArgs first_arg second_arg`, you would get an output back of `second_arg first_arg`.

If you ran the program as `./reverseArgs I love gorgonzola cheese, but I hate toothpaste`, you would get an output back of `toothpaste hate I but cheese, gorgonzola love I`. This is why I (lovingly) refer to this exercise as "the Yoda program"...

If you ran the program with double quotes, then the words within should act as one unit. For example: `./reverseArgs I would rather be at "UC Santa Barbara"` would output: `UC Santa Barbara at be rather would I`.

REQUIREMENTS: You are only permitted to use the <strong>iostream</strong> library.

STYLING: You must follow the styling conventions that we have been discussing in class. I have posted a list of these conventions on Piazza. Additionally, the program must make good use of comments in the code, per the discussions we have been having in class. Again, proper styling and the presence of comments (and thier good use) will be checked by the instructor and the TAs.

A session should look <b><i>exactly</i></b> like the following example (including whitespace and formatting - note that there is no whitespace at the end of each of these lines and each printed line has a newline at the end), with all manners of different numbers for inputs and the output:

<img src="reverseArgs.png" width="700" alt="reverse program example" />

<h3>GONZO.CPP</h3>
Write a program gonzo.cpp that takes 2 command line input arguments: a number (N) and a name. The program then does 2 things: it prints out what the remainder of N divided by 10 is and, on the next line, prints out the name N times separated by a comma and space character with a period at the end of the sentence.

REQUIREMENTS: You are only permitted to use the <strong>iostream</strong> library and you must use a <strong>switch</strong> statement at least once in this program.

STYLING: You must follow the styling conventions that we have been discussing in class. I have posted a list of these conventions on Piazza. Additionally, the program must make good use of comments in the code, per the discussions we have been having in class. Again, proper styling and the presence of comments (and thier good use) will be checked by the instructor and the TAs.

A session should look <b><i>exactly</i></b> like the following example (including whitespace and formatting - note that there is no whitespace at the end of each of these lines and each printed line has a newline at the end), with all manners of different numbers for inputs and the output:

<img src="gonzo.png" width="900" alt="gonzo program example" />

<h2>Step 3: Create a makefile and Compile the Codes with the make Command</h2>
In order to learn another way to manage our source codes and their compilations, we will first create a makefile and put in the usual g++ commands in it. Afterwards, whenever we want to compile our programs, the Linux command is a lot shorter. The use of makefiles will reveal itself to be very useful the more complex our programs and CS projects become.

Using your text editor, create a new file called makefile and enter the following into it:

<div markdown="1">
```
all: inflation mortgage reverseArgs gonzo

inflation: inflation.cpp
   g++ -std=c++11 -o inflation inflation.cpp

mortgage: mortgage.cpp
   g++ -std=c++11 -o mortgage mortgage.cpp

reverseArgs: reverseArgs.cpp
   g++ -std=c++11 -o reverseArgs reverseArgs.cpp

gonzo: gonzo.cpp
   g++ -std=c++11 -o gonzo gonzo.cpp
```
</div>

Then from the Linux prompt, you can do one of two things: either issue separate compile commands for each project, like so:

`$ make inflation`

`$ make mortgage`

etc...

Or, you can issue one command that will compile all the projects mentioned in the makefile, like so:

`$ make`

If the compilation is successful, you will not  see any output from the compiler. You can then use the following commands to run your programs:

`$ ./inflation`

`$ ./mortgage`

`$ ./reverseArgs`

`$ ./gonzo`

<b>If you encounter an error, use the compiler hints and examine the line in question. If the compiler messsage is not sufficient to identify the error, you can search online to see when the error occurs in general.</b>

Remember to re-compile the relevant files after you make any changes to the C++ code.


<h2>Step 4: Submit</h2>

Once you are satisfied that your programs are correct, it is time to submit them. Login at [https://submit.cs.ucsb.edu](https://submit.cs.ucsb.edu), then navigate to “CS16_f17” and click on “lab03”. Then click “Make Submission”, and make your submission the same way as last week. Remember to submit all three .cpp files.

Please remember that you must submit the programs to obtain any credit for the assignment; just completing the programs is not enough.

Once you submit, you should see a page detailing your submission. The system will automatically grade your program and will show you the results on this page after a 1 minute delay.

You can alternatively submit your code from the command line (terminal) on any CS machine, including the Phelps lab machines or the CSIL server. You can use this method when logged in remotely. To submit the the three source files to this assignment by running the command:

`$ ~submit/submit -p 851 gonzo.cpp inflation.cpp mortgage.cpp reverseArgs.cpp`

You can copy the URL shown in the output of the above and paste into a web browser to reach the submission result page.

<h2>Step 5: Check Submission Results</h2>

After the 1 minute delay, the submit system will show your score and give you feedback on your submission. Refresh the webpage after a minute to see this information.

You may submit this lab multiple times. You should submit only after local compilation does not produce any errors and runs as expected. The score of the last submission uploaded before the deadline will be used as your assignment grade.

<h2>Step 6: Done!</h2>

Once your submission receives a score of 100/100, you are done with this assignment. HOWEVER, PLEASE NOTE THAT YOUR ASSIGNMENT WILL ALSO BE GRADED FOR FOLLOWING DIRECTIONS AND STYLING!

If you are in the Phelps lab or in CSIL, make sure to log out of the machine before you leave. Also, make sure to close all open programs before you log out. Some programs will not work next time if they are not closed. Remember to save all your open files before you close your text editor.

If you are logged in remotely, you can log out using the exit command:

`$ exit`

</div>
