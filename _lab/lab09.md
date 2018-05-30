---
layout: lab
num: lab09
ready: true
desc: "Linked Lists"
assigned: 2018-05-30 08:00:00.00-8
due: 2018-06-04 12:00:00.00-8
---
<div markdown="1">

<h1>CS16: Programming Assignment 09</h1>
<h2>Introduction -- Important: Read this!</h2>
This lab will have you do programming exercises with linked lists.

The TAs and I will be looking for (and grading) programming stylizations, as per the styling guide discussed in class. The lab exercises also have specific requirements. So, it is not enough for your lab to pass Gradescope! Please read the instructions herein **CAREFULLY!!!**.

<h3>Pair programming is <b>OPTIONAL BUT RECOMMENDED</b> for this lab!!! It is a long one!!</h3>

Choose who will be the first driver and who will start as navigator, and then remember to switch (at least once) during the lab. But you should probably know the long-term goal too: each partner should participate in both roles in approximately equal parts over the course of the assignment. 

DO NOT share passwords. Instead, use scp or email to share files with each other at the end of each work session.

**PLEASE MAKE SURE YOU TRADE CONTACT INFORMATION WITH YOUR LAB PARTNER! This means emails, phone numbers, online chat handles, or whatever is necessary to continue working together when you are working remotely**

<h2>Step 1: Getting Ready</h2>
1. Go to Gradescope, navigate to this lab page and create a team for you and your pair partner. Do this by clicking on the blue "Join Groups" button, then follow directions.

2. Decide on initial navigator and driver.

3. Driver, log on to your CSIL account.

4. Open a terminal window and log into the correct machine.

5. Change into your CS 16 directory, create a lab09 directory and change into it.

<h2>Step 2: Writing the Programs</h2>
This lab will have you create 1 program with 7 functions. You must follow the instructions carefully. It is not enough to pass the Gradescope check as the instructor and the TAs *will* be checking your submitted program files.

NOTE: IF AN ASSIGNMENT BELOW ASKS YOU TO IMPLEMENT A CERTAIN APPROACH, YOU **MUST** FOLLOW THOSE INSTRUCTIONS VERY CAREFULLY!!!

AS ALWAYS: DO NOT USE TECHNIQUES/INSTRUCTIONS THAT I HAVE NOT COVERED IN CLASS (or risk a zero grade).

Each corresponds to one of the problems listed below, which make up this lab. Each should be solved in its own file and each must be submitted for full assignment credit. 

Note: All these submissions will be checked by the automatic system on Gradescope AND by the instructor and TAs for further evaluation. Details below.

---
Your program will create and manipulate a linked list of nodes of type LinkNode (already defined for you) that contains 2 pieces of data: a name, and an integer number.

Your **FIRST STEP** should be to go an get copies of the following files found in our shared area:
http://cs.ucsb.edu/~zmatni/cs16s18/lab09/lab09.cpp

http://cs.ucsb.edu/~zmatni/cs16s18/lab09/lab09_functions.cpp

http://cs.ucsb.edu/~zmatni/cs16s18/lab09/lab09_headers.h

http://cs.ucsb.edu/~zmatni/cs16s18/lab09/Makefile

The **lab09.cpp** file is the one with the main() function. Take a look at this file first to get a rough idea of what you need to design (and then see the glorious details below!)
You will NOT be editing this file.

The **lab09_headers.h** file contains the program headers: the structure definition and the declaration of all the functions that are used in the program. You will NOT to be edited either; the same goes for the Makefile. Take a look at these files before beginning as well.

You WILL be editing the **lab09_functions.cpp file only.**

<h3>DESCRIPTION OF THE PROGRAM</h3>
As I mentioned, your program will create and manipulate a linked list of nodes of type LinkNode (already defined for you) that contains 2 pieces of data: a name, and an integer number.

The node structure is given to you as:

```cpp
struct LinkNode
{
    string name;
    int number;
    LinkNode *link;
};
```

You can see this definition in the lab09_header.h file.

Your program will do the following (and in the following order, as seen in the lab09.cpp file provided for you):
1. create a linked list of variable length (for example, nodes A->B->C).
2. print that linked list.
3. reverse that linked list (so that A->B->C becomes C->B->A, for example).
4. print that linked list again.
5. insert a node in that list based on an insertion point position in the list (so that A->B->C becomes A->B->X->C, for example, if you chose the insertion point to be after the 2nd node).
6. print that linked list again.
7. find the largest value in your linked list (i.e. a maximum).
8. find the smallest value in your linked list (i.e. a minimum).

Your program must call upon 8 functions that you will have to define for this lab.

I have given you a main program to use (lab09.cpp). You have to edit the functions file (lab09_functions.cpp) that contains the definitions of all the functions used in this lab and, in the end, compile the files together. You can compile all these together using the Makefile that I've provided for you (see section on compilation below for more details).

Your functions are declared as follows (see the lab09_headers.h file):

```cpp
typedef LinkNode* LinkNodePtr;

void h_insert(LinkNodePtr& head, string nom, int num);
void createLL(LinkNodePtr& h);
void reverseLL(LinkNodePtr& h);
void insertNodeAfter(LinkNodePtr h);
void findMax(LinkNodePtr h);
void findMin(LinkNodePtr h);
void printLL(LinkNodePtr h);
```

Here are description of each of what these functions must do. Remember that all linked lists (LL) start with a header link that points to the start of the LL:

<strong>a) createLL and h_insert:</strong>
createLL() is the main one of these 2 (i.e. it calls h_insert). It takes the head link (which is, at first, a NULL pointer) and starts adding nodes to it using another function called h_insert(). h_insert() is actually all defined for you and you do not need to edit it further. The program asks the user to: "Enter name, then a number. To quit, enter 0 for the name AND 0 for the number:"

The user then enters two inputs via cin - a name (string) and an integer number. These two variables, along with the header link, get passed on to h_insert(). This happens in a loop until 0 0 are entered.

<strong>b) reverseLL:</strong>
Takes the head link and proceeds to reverse the links of the LL created by createLL(). Think carefully about how to implement this. HINT: Define links that are about the current node you're looking at, as well as what the next node is and what the previous node is.

<strong>c) findMax and findMin:</strong>
These functions go thru the LL and respectively print out the largest and smallest integers in the "number" field that they find.

<strong>d) insertNodeAfter:</strong>
Takes the head link as input. It asks the user for a node position to insert a new node after that position, by asking: "Enter node position to insert new node after (enter negative number to exit): ". Node positions START with the number 0. The function should then:

1. Quit (return) if a negative position is given.

Otherwise, it should:

2. Determine how many positions (i.e. how many nodes) exist in the LL.
3. If the position given by the user is too big, then the function should say: "Position entered is illegal. Nothing inserted." (with a newline) and quit (return).

Otherwise, it should:

4. Ask the user for the data (i.e. name and number) for the new node by asking: "Enter data (name, then number): "
5. Create a new node with this data and (the trickiest part) insert it in the LL.

<strong>e) printLL:</strong>
Takes the head link and prints out all the nodes' data as follows:

```
Printing the list:
Node #0: <name data>, <number data>
Node #1: <name data>, <number data>
Node #2: ...etc... 
```

See the sample test runs shown below.

<h3>SAMPLE RUNS</h3>

**Sample Run 1**: We enter data for 4 nodes, print them, reverse them, and print them again.
We then ask the user to insert, but we exit from that process by entering a -1.
The list is then printed (one more time) and the maximum and minimum values of the numbers in the LL are given.

```
Enter name, then a number. To quit, enter 0 for the name AND 0 for the number:
Amy
42
Enter name, then a number. To quit, enter 0 for the name AND 0 for the number:
Jim
12
Enter name, then a number. To quit, enter 0 for the name AND 0 for the number:
Marty 
-21
Enter name, then a number. To quit, enter 0 for the name AND 0 for the number:
Jojo
11
Enter name, then a number. To quit, enter 0 for the name AND 0 for the number:
0
0
Printing the list:
Node #0: Jojo, 11
Node #1: Marty, -21
Node #2: Jim, 12
Node #3: Amy, 42
--------
Reversing the list...
Printing the list:
Node #0: Amy, 42
Node #1: Jim, 12
Node #2: Marty, -21
Node #3: Jojo, 11
--------
Enter node position to insert new node after (enter negative number to exit): -1
Printing the list:
Node #0: Amy, 42
Node #1: Jim, 12
Node #2: Marty, -21
Node #3: Jojo, 11
--------
Largest number in the list is: 42
Smallest number in the list is: -21
```

**Sample Run 2**: We enter data for 4 nodes (same as for Run 1), print them, reverse them, and print them again.
We then ask the user to insert, and we chose position 2 (i.e. insert **after** the data point (Jim, 12)). We give that new node data as (Mr.X, 99).
The list is then printed (one more time) and the maximum and minimum values of the numbers in the LL are given.

```
Enter name, then a number. To quit, enter 0 for the name AND 0 for the number:
Amy
42
Enter name, then a number. To quit, enter 0 for the name AND 0 for the number:
Jim
12
Enter name, then a number. To quit, enter 0 for the name AND 0 for the number:
Marty
-21
Enter name, then a number. To quit, enter 0 for the name AND 0 for the number:
Jojo
11
Enter name, then a number. To quit, enter 0 for the name AND 0 for the number:
0
0
Printing the list:
Node #0: Jojo, 11
Node #1: Marty, -21
Node #2: Jim, 12
Node #3: Amy, 42
--------
Reversing the list...
Printing the list:
Node #0: Amy, 42
Node #1: Jim, 12
Node #2: Marty, -21
Node #3: Jojo, 11
--------
Enter node position to insert new node after (enter negative number to exit): 2
Enter data (name, then number): Mr.X 99
Printing the list:
Node #0: Amy, 42
Node #1: Jim, 12
Node #2: Marty, -21
Node #3: Mr.X, 99
Node #4: Jojo, 11
--------
Largest number in the list is: 99
Smallest number in the list is: -21
```

**Sample Run 3**: We enter data for 2 nodes, print them, reverse them, and print them again.
We then ask the user to insert, and we chose position 3 (i.e an "illegal" value since there are only 2 nodes in the LL).
The program senses this illegal request and prints out a message that says: "Position entered is illegal. Nothing inserted."
The list is then printed (one more time) and the maximum and minimum values of the numbers in the LL are given.

```
Enter name, then a number. To quit, enter 0 for the name AND 0 for the number:
Amy
42
Enter name, then a number. To quit, enter 0 for the name AND 0 for the number:
Bob
9
Enter name, then a number. To quit, enter 0 for the name AND 0 for the number:
0
0
Printing the list:
Node #0: Bob, 9
Node #1: Amy, 42
--------
Reversing the list...
Printing the list:
Node #0: Amy, 42
Node #1: Bob, 9
--------
Enter node position to insert new node after (enter negative number to exit): 3
Position entered is illegal. Nothing inserted.
Printing the list:
Node #0: Amy, 42
Node #1: Bob, 9
--------
Largest number in the list is: 42
Smallest number in the list is: 9
```

**Sample Run 4**: We enter data for NO nodes, print them, reverse them, and print them again. This only results in printing "The list is empty."
When the insertion function is called, it senses that there are no nodes present and so it issues a printout that says "Cannot insert in a non-existing link."
Finally, when the re-printing and the findMax() and findMin() functions are called, the program prints "The list is empty" every time (i.e. 3 times).

```
Enter name, then a number. To quit, enter 0 for the name AND 0 for the number:
0
0
This list is empty.
Reversing the list...
This list is empty.
Cannot insert in a non-existing link.
This list is empty.
This list is empty.
This list is empty.
```

To compile the programs, make use of the provided Makefile and run it like this:

$ make

---

<h2>Step 3: Submit using GRADESCOPE</h2>

*BEFORE YOU SUBMIT YOUR FILES:* Make sure that you have COMMENTS in your program that would help explain what your program is doing to another person reading your program code. Also make sure that you STYLIZE your program appropriately with correct indendation and so on (see the handout on Piazza re: this) to additionally make it easier on others reading your code. These 2 aspect (having appropriate comments and style) will be graded for an *extra 20 points* beyond the automatic grade you get from the submission system (called Gradescope). Please remember that you must submit the programs to obtain any credit for the assignment; just completing the programs is not enough.

You may submit this lab multiple times. You should submit only after local compilation does not produce any errors and runs as expected. The score of the last submission uploaded before the deadline will be used as your assignment grade.

<strong>We will use Gradescope to grade all your lab/programming assignments from here on. You should have received an email notification with instructions about logging into Gradescope.</strong>

Log into <a href="https://www.gradescope.com" _target="blank">https://www.gradescope.com</a> and find our class site: <strong>CS16, Spring 2018, Matni</strong>. Then navigate to the lab assignment (lab09) and select this assignment. You should see a "Submit Programming Assignment" window pop up. Make sure you have selected "Upload" as Submission Method (not "Github" or "Bitbucket"). Go ahead and submit all of your .cpp files for this assignment and click the green "Upload" button.

<img src="Gradescope_Upload.png" alt="pic of gradescope submit" width="450" />

**IMPORTANT**
**You will submit 3 files: lab09.cpp, lab09_functions.cpp, and lab09_headers.h. You do not need to submit the Makefile.**

When you submit your C++ program files, wait for the results (these might take a minute or two).
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
