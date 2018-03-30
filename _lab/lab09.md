---
layout: lab
num: lab09
ready: true
desc: "Multiple Compilations"
assigned: 2017-11-27 08:00:00.00-7
due: 2017-12-06 12:00:00.00-7
---
<div markdown="1">

<h1>CS16: Programming Assignment 09</h1>
<h2>Introduction -- Important: Read this!</h2>

THIS IS A CHALLENGING LAB AND I AM GIVING YOU THE OPTION TO PAIR UP WITH SOMEONE ELSE IN YOUR LAB (because two heads are - often - better than one).

The TAs and I will be looking for (and grading) programming stylizations, such as proper use of comments, tab indentation, good variable names, and overall block and function designs. So, it is not enough for your lab to pass submit.cs! Please read the instructions herein <b>carefully</b>. 

<h3>Pair programming is <b>OPTIONAL</b> for this lab.</h3>

If working in a pair: Choose who will be the first driver and who will start as navigator, and then remember to switch (at least once) during the lab. But you should probably know the long-term goal too: each partner should participate in both roles in approximately equal parts over the course of the assignment. 
We realize it is not possible to equally split time in every lab perfectly, but it is worth trying, and it is possible to make up for unequal splits in future labs. We trust you will try to meet this goal. Thanks!

Also: DO NOT share passwords. Instead, use scp or email to share files with each other at the end of each work session.
If you are not sure how to use scp (remote file copy), ask your lab TA.

**PLEASE MAKE SURE YOU TRADE CONTACT INFORMATION WITH YOUR LAB PARTNER! This means emails, phone numbers, online chat handles, or whatever is necessary to continue working together when you are working remotely (like, say, if one of you goes home for the weekend).** Share your work with each other at the end of EVERY work session. 

<h2>Step 1: Getting Ready</h2>
1. Decide if you are working alone, or working in a pair.

2. If you are working as a pair, go to submit.cs, navigate to this lab page and create a team for you and your pair partner. Do this by clicking on the blue "Join Groups" button, then follow directions.

3. Decide on initial navigator and driver.

4. Driver, log on to your CSIL account.

5. Open a terminal window and log into the correct machine.

6. Change into your CS 16 directory, create a lab09 directory and change into it.

<h2>Step 2: Copying Files from my Directory</h2>
Visit the following web link — you may want to use "right click" (or "control-click" on Mac) to bring up a window where you can open this in a new window or tab:

<http://www.cs.ucsb.edu/~zmatni/cs16f17/lab09/code>

You should see a listing of several C++ programs. We are going to copy those into your ~/cs16/lab09 directory on CSIL all at once with the following command:

`cp ~zmatni/public_html/cs16f17/lab09/code/* ~/cs16/lab09`

Note: If you get the error message:
`cp: target /cs/student/youruserid/cs16/lab09 is not a directory`

then it probably means you did not create a ~/cs16/lab09 directory in step 1, so go back to step 1 and do that first.
The * symbol in this command is a "wildcard" — it means that we want <b>all</b> of the files from the source directory copy be copied into the destination directory namely ~/cs16/lab09.

After doing this command, if you cd into ~/cs16/lab09 and use the ls command, you should see several files in your ~/cs16/lab09 directory—the same ones that you see if you visit the link http://www.cs.ucsb.edu/~zmatni/cs16f17/lab09/code

If so, you are ready to move on to the next step.

If you do not see those files, work with your pair partner to go back through the instructions and make sure you did not miss a step. If you still have trouble, ask your TA for assistance.

<h2>Step 3: Reviewing Separate Compilation</h2>
The files in your directory this week use separate compilation, that is each program is not necessarily taking all of its code from a single .cpp source file.

In Lecture, we have introduced the idea of separate compilations, where your C++ program may be divided among multiple source files.

The following web page explains more about separate compilation, dividing your program up among multiple C++ and .h files, and using a Makefile.

I strongly encourage you to read over it briefly before you go on to review the information there, as well as your notes from the separate compilation lecture, if you took any. I also *very* strongly encourage you to open the Makefile provided and look it over while reading the information at:

[Separate Compilation and Makefiles](https://foo.cs.ucsb.edu/16wiki/index.php/C%2B%2B:_Separate_Compilation_and_Makefiles)

<h2>Step 4: Writing isOdd(), isEven() and isPrime()</h2>

Your first step is very simple to describe, but somewhat challenging. The challenge here is mostly C++ coding — we will not get into the details of the separate compilation until a bit later.

To get started, do the following steps:

<b>Step 4a: make clean</b>
In your ~/cs16/lab09 directory, type <b>ls</b> and make note of the different files therein: some are .cpp types, some are .o (short for "object file"), some are .h (short for "header file"), and others do not have extensions (they are binary executables). Now, type <b>make clean</b>. This command cleans out any .o files and executables from your directory

That should look like this:

```
-bash-4.2$ make clean
/bin/rm -f arrayToStringTest arrayBoundsDemo countEvensTest minOfArrayTest minOfArrayErrorTest 
countPrimesTest maxOfArrayTest maxOfArrayErrorTest sumOddsTest sumOfArrayTest utilityTest *.o

-bash-4.2$ 
```

Take a look at the <b>Makefile</b> file to understand why this happened. Be prepared, however, for a more complex version of a Makefile than the one introduced in class (part of the challenge is trying to understand what is happening in this Makefile).

<b>Step 4b: make utilityTest</b>

Next type: `make utilityTest`

This command makes the executable for a main program, defined in `utilityTest.cpp`, that tests the functions defined in `utility.cpp`. 
Recall that for functions defined in a file such as `utility.cpp` that has no <b>main()</b>, the function prototypes are defined in the file `utility.h`
Look at the source code for both `utility.cpp` and `utility.h` to see what they contain.
Recall that a "stub" is place-holder code that allows an incomplete function to compile. It is designed to fail all the tests, though for a boolean function, since there are only two possible values (true and false), any stub value you choose is going to pass at least some of the tests.

That should look like this:

```
-bash-4.2$ make utilityTest
g++ -Wall -Wno-uninitialized   -c -o utilityTest.o utilityTest.cpp
g++ -Wall -Wno-uninitialized   -c -o tddFuncs.o tddFuncs.cpp
g++ -Wall -Wno-uninitialized   -c -o utility.o utility.cpp
g++ -Wall -Wno-uninitialized  utilityTest.o tddFuncs.o utility.o -o utilityTest

-bash-4.2$ 
```

<b>Step 4c: Run ./utilityTest</b>

Next, type `./utilityTest` 

This runs the `utilityTest` program that tests the three functions isOdd, isEven and isPrime. As we noted above, some of the tests will pass, even though the implementation of the three functions is totally bogus (hard coded to return false always).

Here is what that looks like (some output truncated)

```
-bash-4.2$ ./utilityTest
	FAILED: isEven(2)
		Expected: 1 Actual: 0
	PASSED: isEven(3)
	FAILED: isEven(4)
		Expected: 1 Actual: 0
	PASSED: isEven(55)

[...      Some output omitted here... ]

PASSED: isPrime(64507)
	FAILED: isPrime(69997)
		Expected: 1 Actual: 0
PASSED: isPrime(-55)
PASSED: isPrime(-80)
PASSED: isPrime(0)
PASSED: isPrime(1)

-bash-4.2$ 
```

<b>Step 4d: Repeat: edit, compile, run ,until all tests pass</b>
Now do these steps, repeatedly, until all tests pass:

edit utility.cpp (e.g. emacs utility.cpp, or vim utility.cpp)
make utilityTest
run utilityTest (e.g. ./utilityTest)

This is the starting point, because for other files you will be editing later, you will NEED functions isOdd, isEven and isPrime. Once you get them working, you will be able to call them in other files and KNOW that they work properly. You will not have to repeat the function definition.

When all the tests for `utlityTest` pass, move on to the next step.

<h2>Step 5: Reviewing the rest of the files and what your tasks are</h2>

Now, let us look at the files you actually have in your directory, and what you need to do with them.
You have the following .cpp files. This table indicates what you must do with each one to get full credit on this lab.


|Filename|Your task|Details
|--- |---|---
|arrayBoundsDemo.cpp|NOTHING TO CHANGE OR SUBMIT.|This is here as example code only. You are encouraged to run it, study it, and learn about how array bounds work in C++
|arrayToString.cpp|	NOTHING TO CHANGE OR SUBMIT.|This code is part of your solution, but you do not have to submit it - we will use our own version, which matches the one in your sample directory. This file just has utiltiy funcitons for printing arrays as strings.
|arrayToStringTest.cpp|NOTHING TO CHANGE OR SUBMIT.|This code is part of your solution, but you do not have to submit it - we will use our own version, which matches the one in your sample directory. This file is an example of how to test cases to determine whether the output of `arrayToString` works correctly.
|countEvens.cpp|REPLACE STUB WITH CORRECT CODE.|You must replace the code in this file with correct code that returns the number of even integers in each array passed in.
|countEvensTest.cpp|NO MODIFICATIONS NEEDED|This tests the changes you made in *countEvens.cpp*.
|countPrimes.cpp|REPLACE STUB WITH CORRECT CODE.|You must replace the code in this file with correct code that returns the number of prime integers in each array passed in. Treat negative numbers, 0 and 1 as "not prime". You may want to add a definition of `isPrime()` to the *utility.cpp* file and a function prototype to *utility.h* so that you can call function `isPrime` in your solution.
|countPrimesTest.cpp|NO MODIFICATIONS NEEDED|This tests the changes you made in *countEvens.cpp*.
|maxOfArray.cpp|REPLACE STUB WITH CORRECT CODE.|You can look at *minOfArray.cpp* for hints. This one should be easy.
|maxOfArrayErrorTest.cpp|REPLACE EMPTY MAIN WITH TESTS.|Insert code to call maxOfArray with zero length array. Use *minOfArrayErrorTest.cpp* as a model.
|maxOfArrayTest.cpp|REPLACE EMPTY MAIN WITH TESTS.|Insert code to call `assertEqual` exactly seven times testing whether `maxOfArray` returns correct values. Use *minOfArrayTest.cpp* as a model. It must be exactly "seven" calls to `assertEquals` to pass the submit.cs tests. You should call your arrays the same things that they are called in `minOfArrayTests`, and the lengths should be the same. So the messages you get out for passed tests should match the messages from `minOfArrayTests` except that the name of the function is `maxOfArray` instead of `minOfArray`. You MAY change the values in the arrays themselves, though, to make the tests better tests, if you need to. **(Note that just hard coding a program that prints "PASSED" seven times with the apprpriate messages is not sufficient to get credit--you need to really have actual tests. Any attempt to "game the system", i.e. to get submit.cs tests to pass without a bona-fide attempt to actually solve the problem will get zero credit.)**
|minOfArray.cpp|NOTHING TO CHANGE.|This is a model of correct code that can serve as a hint for how to write *maxOfArray.cpp*
|minOfArrayErrorTest.cpp|NOTHING TO CHANGE.|This is an model of correct code for how to test whether a function behaves as expected when given input that should print a message to cerr and exit the progrm.
|minOfArrayTest.cpp|NOTHING TO CHANGE.|This is a model of how to do unit testing on a function that returns an integer.
|sumOdds.cpp|REPLACE STUB WITH CORRECT CODE.|You must replace the code in this file with correct code that returns the number of sum of the odd integers in each array passed in. Negative odd integers count as odd integers.
|sumOddsTest.cpp|REPLACE EMPTY MAIN WITH TESTS|Insert code to call `assertEqual` exactly seven times testing whether `sumOdds` returns correct values. Use *sumOfArrayTest.cpp* as a model. It must be exactly "seven" calls to `assertEquals` to pass the submit.cs tests. You should call your arrays the same things that they are called in `sumOfArrayTests`, and the lengths should be the same. So the messages you get out for passed tests should match the messages from `sumOfArrayTests` except that the name of the function tested is `sumOdds` instead of `sumOfArray`. You MAY change the values in the arrays themselves, though, to make the tests better tests, if you need to. **(Note that just hard coding a program that prints "PASSED" seven times with the apprpriate messages is not sufficient to get credit--you need to really have actual tests. Any attempt to "game the system", i.e. to get submit.cs tests to pass without a bona-fide attempt to actually solve the problem will get zero credit.)**
|sumOfArray.cpp|INCORRECT CODE FOR YOU TO FIX.|The sum is not initialized properly. So the tests should fail. Your job is to see that the tests fail, then fix the sum initialization so the tests pass. Should be easy.
|sumOfArrayTest.cpp|NOTHING TO CHANGE.|This is a set of tests to verify whether `sumOfArray()` works correctly.
|tddFuncs.cpp|NOTHING TO CHANGE.|These are two functions that can be used to test functions that return either int or string values.
|utility.cpp|ADD FUNCTIONS HERE AS NEEDED.|If you need to write your own helper functions, e.g. `isPrime`, `isOdd`, `isEven`, to use in other files, here is where you can put those definitions.


<h2>Step 6: Actually Getting Started</h2>
I suggest you start by typing: `make`.

You should see a lot of activity as programs are compiled. You then will have a lot of executables you can run. Here is a list. Try running each one and see what happens.

Note these are the programs listed under BINARIES in the Makefile.

|file|Anything to do?|explanation
|--- |---|---
|arrayToStringTest|no|Run this and all tests should pass. Nothing to do here.
|arrayBoundsDemo|no|Run this, and look at the code. This is an opportunity to learn something about how we pass arrays to functions in C++, but there is nothing you have to turn in from this program for the lab. It is just here as an example for you to learn from.
|countEvensTest|<b>*YES*</b>|Run this, and you will see all the tests fail. YOU NEED TO FIX THE `countEvens` function and then get all these tests to pass.
|minOfArrayTest|no|Just run this and see the tests pass. You can use the .cpp file *minOfArrayTest.cpp* as a model for writing *maxOfArrayTest.cpp*
|minOfArrayErrorTest|no|Just run this and see the output. It should be `ERROR: minOfArray called with size < 1` printed on cerr (the standard error output stream). The submit.cs system will check this as one of the acceptance tests for this lab, and it will also check that `maxOfArrayErrorTest` does the same thing. You can use the .cpp file *minOfArrayErrorTest.cpp* as a model for writing *maxOfArrayErrorTest.cpp*
|countPrimesTest|<b>*YES*</b>|Run this, and you will see all the tests fail. YOU NEED TO FIX THE `countPrimes` function and then get all these tests to pass.
|maxOfArrayTest|<b>*YES*</b>|Run this, and you will see that initially there is no output. That is because the main is empty. YOU NEED TO REPLACE THIS MAIN with code that tests `maxOfArray`. Use `minOfArrayTest` as a model. Initially, just put in the tests, and keep `maxOfArray` returning the stub vaue -42. See all the tests fail. Then get `maxOfArray` to return the right values and see all the tests pass.
|maxOfArrayErrorTest|<b>*YES*</b>|Run this, and you will see that initially there is no output. That is because the main() is empty. YOU NEED TO REPLACE THIS MAIN with code that tests `maxOfArray`. Use `minOfArrayTest` as a model. Initially, just put in the tests, and keep `maxOfArray` returning the stub vaue -42. See all the tests fail. Then get `maxOfArray` to return the right values and see all the tests pass.
|sumOddsTest|<b>*YES*</b>|Run this, and you will see that initially there is no output. That is because the main() is empty. YOU NEED TO REPLACE THIS MAIN with code that tests `sumOdds`. Use `minOfArrayTest` as a model. Initially, just put in the tests, and keep `sumOdds` returning the stub vaue -42. See all the tests fail. Then get `sumOdds` to return the right values and see all the tests pass.
|sumOfArrayTest|<b>*YES*</b>|Run `sumOfArrayTest` and you will see that all the tests fail. Getting them to pass is probably the easiest step in this lab. Just look at the `sumOfArray` function, which is almost correct - it just needs you to initialize sum correctly. Note that in C/C++ variables are NOT automatically initialized, and failing to initialize them does not always result in an error message or warning unless you specifically ask the compiler to tell you about those. For this lab, the Makefile deliberarly turns that warning OFF so that we have to catch that ourselves.

So, if you go through that list, and do all the things indicated, you are finished with the lab and ready to submit.

<h2>Step 7: Checking your work before submitting</h2>

When you are finished, you should be able to type `make tests` and see the following output:

```
-bash-4.2$ make tests
./arrayToStringTest
PASSED: arrayToString(fiveThrees,5)
PASSED: arrayToString(zeros,3)
PASSED: arrayToString(empty,0)
PASSED: arrayToString(primes,10)
PASSED: arrayToString(meaning,1)
PASSED: arrayToString(mix,10)
./countEvensTest
PASSED: countEvens(fiveThrees,5)
PASSED: countEvens(zeros,3)
PASSED: countEvens(fiveInts,5)
PASSED: countEvens(empty,0)
PASSED: countEvens(primes,10)
PASSED: countEvens(meaning,1)
PASSED: countEvens(mix,10)
./countPrimesTest
PASSED: countPrimes(fiveThrees,5)
PASSED: countPrimes(zeros,3)
PASSED: countPrimes(fiveInts,5)
PASSED: countPrimes(empty,0)
PASSED: countPrimes(primes,10)
PASSED: countPrimes(meaning,1)
PASSED: countPrimes(mix,10)
./maxOfArrayTest
PASSED: maxOfArray(fiveThrees,5)
PASSED: maxOfArray(zeros,3)
PASSED: maxOfArray(fiveInts,5)
PASSED: maxOfArray(fiveInts,2)
PASSED: maxOfArray(fiveInts,3)
PASSED: maxOfArray(meaning,1)
PASSED: maxOfArray(mix,10)
./minOfArrayTest
PASSED: minOfArray(fiveThrees,5)
PASSED: minOfArray(zeros,3)
PASSED: minOfArray(fiveInts,5)
PASSED: minOfArray(fiveInts,2)
PASSED: minOfArray(fiveInts,3)
PASSED: minOfArray(meaning,1)
PASSED: minOfArray(mix,10)
./sumOddsTest
PASSED: sumOdds(fiveThrees,5)
PASSED: sumOdds(zeros,3)
PASSED: sumOdds(fiveInts,5)
PASSED: sumOdds(fiveInts,3)
PASSED: sumOdds(fiveInts,2)
PASSED: sumOdds(meaning,1)
PASSED: sumOdds(mix,10)
./sumOfArrayTest
PASSED: sumOfArray(fiveThrees,5)
PASSED: sumOfArray(zeros,3)
PASSED: sumOfArray(fiveInts,5)
PASSED: sumOfArray(fiveInts,3)
PASSED: sumOfArray(fiveInts,2)
PASSED: sumOfArray(meaning,1)
PASSED: sumOfArray(mix,10)
./utilityTest
PASSED: isEven(2)
PASSED: isEven(3)
PASSED: isEven(4)
PASSED: isEven(55)
PASSED: isEven(-55)
PASSED: isEven(-80)
PASSED: isOdd(2)
PASSED: isOdd(3)
PASSED: isOdd(4)
PASSED: isOdd(55)
PASSED: isOdd(-55)
PASSED: isOdd(-80)
PASSED: isPrime(2)
PASSED: isPrime(3)
PASSED: isPrime(4)
PASSED: isPrime(55)
PASSED: isPrime(859)
PASSED: isPrime(861)
PASSED: isPrime(863)
PASSED: isPrime(1337)
PASSED: isPrime(1373)
PASSED: isPrime(64507)
PASSED: isPrime(69997)
PASSED: isPrime(-55)
PASSED: isPrime(-80)
PASSED: isPrime(0)
PASSED: isPrime(1)

-bash-4.2$ 
```
And, you should be able to type `make errorTests` and see the following output:

```
-bash-4.2$ make errorTests
./minOfArrayErrorTest
ERROR: minOfArray called with size < 1
make: [errorTests] Error 1 (ignored)
./maxOfArrayErrorTest
ERROR: maxOfArray called with size < 1
make: [errorTests] Error 1 (ignored)

-bash-4.2$ 
```
At that point, you are ready to try submitting on the submit.cs system.

<h2>Step 8: Submit</h2>

For this lab, since there are a lot of files to upload to submit.cs, your best course is to type the following from the Linux/UNIX prompt, that is, from the command line (terminal) on any CS machine, including from your computer when you are remotely logged into a CS machine (via ssh):

`$ ~submit/submit -p 869 *.cpp *.h`

You can then copy the URL shown in the output of the above and paste into a web browser to reach the submission result page.

PLEASE NOTE THAT THIS IS A NON-TYPICAL LARGE SUBMISSION TO THE SYSTEM. Be patient if the system takes a bit longer to respond to your submission.

<h2>Grading Rubric</h2>
Points from automated submit.cs system tests

<b>Passed Tests</b>

|Test Group|Test Name|Value
|--- |---|---
|countEvens|countEvensTest|30 pts
|countPrimes|countPrimesTest|30 pts
|maxOfArray|maxOfArrayTest|30 pts
|maxOfArrayErrorTest|maxOfArrayErrorTest |30 pts
|sumOdds|sumOddsTest|30 pts
|sumOfArray|sumOfArrayTest|30 pts
|utilityTest|utilityTest|50 pts

<b>Points assigned by TAs manually</b>

(40 pts) Style:
Good choice of variable names, code indented in ways that are consistent, and in line with good C++ practice. Where applicable, common code is factored out into functions (added to utility.h and utility.cpp as needed). 

This last point may or may not arise, but if it does, utility.h and utility.cpp is a place where functions needed in multiple files can be put—prototypes in utility.h and function definitions in utility.cpp.

(30 pts) Following instructions and submitting on time.

You will note that the submit.cs score is worth 230 points tal points for this lab equal to 300. The grade will ultimately normalized to be out of 100 points. This lab is worth exactly the same as all the other labs done so far (i.e. the 230 points here are equivalent to 100 points in other labs).

<h2>Step 9: Done!</h2>

Once your submission receives a score of 230/230, you are done with this assignment. Remember that we will check your code for appropriate comments, formatting, and the use of required code, as stated earlier.

If you are in the Phelps lab or in CSIL, make sure to log out of the machine before you leave. Also, make sure to close all open programs before you log out. Some programs will not work next time if they are not closed. Remember to save all your open files before you close your text editor.

If you are logged in remotely, you can log out using the exit command:

`$ exit`

</div>
