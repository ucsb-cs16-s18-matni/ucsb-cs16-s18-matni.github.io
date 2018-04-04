---
layout: lab
num: lab01
ready: true
desc: "Getting started with C++"
assigned: 2018-04-04 08:00:00.00-7
due: 2018-04-09 12:00:00.00-7
---
<h2>Introduction</h2>

<p>Your first lab for this week is an introduction to programming on CSIL and in the Computer Science lab. You will write your first 2 C++ programs.</p>

<p><b>THE DEADLINE TO SUBMIT THIS LAB IS MONDAY, 2/9 BY NOON</b>. Details on how to submit are further down in this document.</p>
<hr>

<p>For this first lab, you will do the following:</p>
<ol>
<li>Create a College of Engineering online computer account, if you do not have one already.</li>
<li>Learn how to open a terminal on a lab or personal computer.</li>
<li>Learn how to edit a text file used for writing programming code.</li>
<li>Write actual programs in C++.</li>
<li>Compile your programs and see if they run.</li>
<li>Learn how to submit your programs for grading.</li>
</ol>

<hr>
<h3>Step 1: Create an Engineering Account</h3>

<p>To log in to the machines in the Computer Science labs, or to connect remotely, you will need a <b>College of Engineering account</b>.</p>

<p>At this point, please go to <a href="https://ucsb.box.com/s/px12flf8g41m8g0gq4n6zqbbc9phkfrs" target="_blank">THIS LINK</a> and view the important presentation from Engineering Computing Infrastructure on the College of Engineering accounts and computer labs.</p>

<p>You can create an account online at <a href="https://accounts.engr.ucsb.edu/create" target="_blank">https://accounts.engr.ucsb.edu/create</a>.</p>

<p>If you are enrolled in <i>any</i> CoE course this quarter (including CS16), you can create your account immediately. If you are not, you will need to contact the ECI Help Desk at <a href="mailto:help@engineering.ucsb.edu">help@engineering.ucsb.edu</a>.</p> 

<hr>
<h3>Step 2: Open a Terminal</h3>

The first step in every assignment will be to open a <b>terminal window</b>, which will be the environment you use to write, compile, and run your programs.


* If you are working on a machine in the Phelps 3525
    please see [Step 2a](#step2a){: data-ajax="false"} for further instructions.

* If you are working on a machine in the Computer Science Instruction Lab (CSIL), you will be working 
    on one of the following machines: `csil-01.cs.ucsb.edu`, `csil-02.cs.ucsb.edu`, etc. 
    (though `csil-48.cs.ucsb.edu`).   Please see [Step 2a](#step2a){: data-ajax="false"} for further instructions.

If you are working on your laptop, whether Windows, Mac or Linux, the instructions below 
will tell you how to connect to a CSIL computer, like:

* `csil-01.cs.ucsb.edu`
* `csil-02.cs.ucsb.edu`, etc. 
* etc.
* through `csil-48.cs.ucsb.edu`

You will get much better performance on those individual machines, because they are much less heavily loaded and have
newer hardware, as compared to `csil.cs.ucsb.edu`.

* If you are working on your laptop and it is a Mac or Linux machine, go to [Step 2b](#step2b){: data-ajax="false"}.</p>
* If you are working on your laptop and it is a Windows machine, go to [Step 2c](#step2c){: data-ajax="false"}.</p>

<ol>
<h4><i><a name="step2a"></a>Step 2a: Opening a Terminal on a Phelps Lab Machine</i></h4>
<p>
<li>Log in to the machine using your account credentials (i.e. your username and password) created in Step 1.</li>
<li>Find the <i>Activities</i> menu, which is in the top-left corner of the screen. Click on it to open the menu.</li>
<li>Next, type "shell" in the search box. Then click the "Terminal" application which appears.</li>
<li>You should now see a terminal window open. You can open more tabs or windows from the Terminal applications menu.</li>
</p>
</ol>

<ol markdown="1">
<h4><i>Step 2b: Connecting to CSIL via SSH on Mac OS X or Linux</i></h4>
<p>To get started on Mac OS X or Linux, you first need to open a terminal program. This involves slightly different steps on either OS.</p>
<p>On Ubuntu (an example of a Linux OS):

<li>You will first want to find the search menu. It appears at the top of the Unity bar:</li>
<img src="ubuntu-menu.png" width="297" alt="Ubuntu Search Menu" />

<li>Click on that icon to open the search menu. Then type "terminal" and click on the "Terminal" application which appears:</li>
<img  src="ubuntu-search.png" width="357" alt="Ubuntu Terminal Application" />
</p>

<p>On Mac OS X:
<li>Open the "Terminal" application. It is found inside the <em>Applications</em> folder of your main drive, inside the <em>Utilities</em> subfolder. The icon looks like this:</li>
<img src="mac-terminal.png" width="79" alt="Mac OS X Terminal Icon" />

You can also find it using Spotlight by typing "terminal" and pressing ENTER.
</p>

<p>Once you have a terminal window open on your machine, you next need to <b>connect to the CSIL server remotely</b>. <br>
You will do this using a UNIX command (an internet protocol, really) called <em>SSH</em> (short for Secure Shell).</p>

<p>Type the following command in your terminal, replacing <b>USERNAME</b> with <b>your CSIL username</b>:</p>
<pre>$ ssh USERNAME@csil-10.cs.ucsb.edu</pre>

<p>SSH will first ask you a question which looks like this:</p>
<pre>The authenticity of host 'csil.cs.ucsb.edu (128.111.43.14)' can't be established.
RSA key fingerprint is 90:ab:6a:31:0b:81:62:25:9b:11:50:05:18:d3:1a:b5.
Are you sure you want to continue connecting (yes/no)? </pre>

<p>Type <b>yes</b> and then ENTER to continue. It will next ask for your CSIL account password. When you type it in, nothing will show on the screen (not even dots). However what you type is still being sent and once you are finished with your password, you can press ENTER to login.</p>

<p><b>You should now be remotely connected to CSIL!</b> You can make sure by typing the following command (which will tell you what machine you are currently issuing commands to):</p>
<pre>$ hostname</pre>

<p>This should show <b>csil-10.cs.ucsb.edu</b>. You can now do anything you could normally do in a terminal window in CSIL or the Phelps lab (except run graphical programs).</p>

<h4><em>Extra Note: Graphical Forwarding</em></h4>

<p>This is not required or necessary to use CSIL remotely, so if you are not interested, go ahead and skip this part.</p>

<p>If you have an X windows system installed you can get graphical applications running by <em>forwarding</em> X from CSIL to your machine. To do this, add the <b>-X</b> option to the SSH command like this:</p>
<pre>$ ssh -X USERNAME@csil-10.cs.ucsb.edu</pre>

<p>X windows is almost always installed on graphical Linux, and can be installed on Mac OS X as XQuartz (which can be found at <a href="http://xquartz.macosforge.org/landing/" target="_blank">http://xquartz.macosforge.org/landing/</a>).</p>

</ol>

<div style="margin-left: 3em;" markdown="1">
<h4>Step 2c: Connecting to CSIL via SSH with PuTTY</h4>

<p>To connect remotely on Windows machines, we recommend using a program called <em>PuTTY</em>. This program is a well-known and widely-used SSH client for the Windows OS.</p>

<p>First, download the program from <a href="http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html" target="_blank">http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html</a>. You only need the executable file <b>putty.exe</b>, but feel free to download any other programs that you want. The page includes portable versions and a version with an installer. <i>Always make sure to download PuTTY from this site</i>, so that you can make sure it is the correct program.</p>

<p>Once downloaded, run PuTTY like you would open other programs. If you just download the <b>putty.exe</b> file, you can open it from your downloads folder directly. You can also move it to any other location on your machine and open it from there. If you used the installer, open PuTTY from the Start Menu.</p>

<p>When PuTTY opens, you should see a window that looks like this:</p>
<img src="putty-empty.png" width="469" alt="Empty PuTTY window" />

<p>Type <b>csil.cs.ucsb.edu</b> into the box labeled "Host Name (or IP address)". Leave the "Port" setting at 22 and leave the "SSH" button checked. The window should now look like this:</p>
<img src="putty-full.png" width="472" alt="Completed PuTTY window" />

<p>Then click on the "Open" button to connect. PuTTY will then show a prompt which looks like this:</p>
<img  src="putty-hostkey.png" width="433" alt="PuTTY Host Key Prompt" />

<p>Click "Yes" to accept and have PuTTY remember the CSIL key.</p>

<p>Once a connection is made, CSIL will ask for both your username and then your password. Type in your CSIL username and password. The password will not be shown on the screen, but the characters you type are being used. This step will look something like this (with your username instead of "username"):</p>
<img src="putty-login.png" width="677" alt="PuTTY Login Prompt" />

<p>Once you have logged in successfully, you should be connected remotely to the CSIL server. Run the following command to make sure (this command shows the full host name of the machine you are logged in to):</p>
<pre>$ hostname</pre>

<p>This command should output <b>csil.cs.ucsb.edu</b>. You can now do anything in this terminal window that you could do on a CSIL machine or a Phelps lab machine, except run graphical applications.</p>

If you want to run graphical applications, instead of using puTTY, you can use other programs, such as [MobaXterm](http://mobaxterm.mobatek.net/){: target="_blank"}.

</div>


<hr>
<h3>Step 3: Create CS16 and Programming Assignment 01 Directories</h3>

<p>Now that your environment is set up, you next will need to create a directory (a folder is also called <i>directory</i> in Linux) that will contain all your work for the course. Then, inside that directory, you will need to create another directory to contain your work for this assignment.</p>

<p>To create your CS16 directory, use the <b>mkdir</b> command. Type the following in the terminal and press enter:</p>
<pre>$ mkdir cs16</pre>

<p>The <b>$</b> represents the terminal prompt; <i>you will not type this character</i>. Whenever you see it, that means that the following command is intended to be typed into the terminal window and run by pressing enter.</p>

<p>You can see list of files and directories in the current directory with <b>ls</b> command. Type the following in the terminal and press enter:</p>
<pre>$ ls</pre>

<p>You should be able to see the directory you just created i.e. <b>cs16</b> </p>

<p>Now move into that new CS16 directory with the <b>cd</b> command as follows:</p>
<pre>$ cd cs16</pre>

<p>And create and move into a LAB 01 directory:</p>
<pre>$ mkdir lab01
$ cd lab01   </pre>

<p>At any time, you can check what directory you are current in with the command <b>pwd</b>. It will output the full path of the current directory. For example, if you are inside your <b>lab01</b> directory, you might see:</p>
<pre>/cs/student/yourcsilname/cs16/lab01</pre>

<p>Knowing how to navigate a UNIX environment and issue UNIX commands is VERY valuable to computer scientists and engineers. To learn more UNIX commands, there are lot of cool Web resources and books on the topic. This is one website I found that has a good introductory page: 
<a href="https://www.tjhsst.edu/~dhyatt/superap/unixcmd.html" target="_blank">https://www.tjhsst.edu/~dhyatt/superap/unixcmd.html</a>.
</p>

<!--
<h3>Step 4: Create a C++ File</h3>

<p>Now that we have a directory to contain our work for the assignment, let us start writing our code. Create a file called <b>hello.cpp</b> with the <b>touch</b> command:</p>
<pre>$ touch hello.cpp</pre>

<p><span class="code">hello.cpp</span> is now a completely empty file that you will use throughout the rest of the assignment to write your C++ code.</p> -->

<hr>
<h3>Step 3: Editing text files for programming</h3>

<p>Let us take a little detour on how to best create and modify text files. These will carry all the code (regardless of computer language) that we want to assemble, compile, and execute.</p>

<p>You are surely all familiar with Microsoft Word as a widely-used "word processor", but please DO <b>NOT</b> USE MS WORD TO WRITE PROGRAMS!!! :)<br>
Instead, for programming, you have access to a very large number of excellent text editors - most of them are free to use! I will introduce you to just 4 of them below. If you already have a favorite editor and know how to use it well, then you do not have to change and use something else, just for this class.</p>

<p>In fact, <i>AND PLEASE NOTE THIS</i>, no one editor is necessarily "better" than another. It is a matter of your preference. This is a great time for you to explore multiple options and then pick one. Once you pick an editor of choice, STICK WITH IT!<br>

As you progress in your Computer Science education and, subsequently, your careers in CS, make sure you end up learning how to use more than one editor. You can still have a "favorite" that you excel at using, but at least have a working familiarity with others.</p>

<ol>
<li> <b>emacs</b> for UNIX-based OS</li>
	<ol>
	<p>emacs is a very popular editor that's available on just about every UNIX machine (including the ones that you're using in the CS labs) and UNIX-based machines (like MacOS computers).</p>
	<p>To run emacs on a UNIX machine or a MacOS machine, open up a terminal (see above for how to do that on Macs) and type:<br>
	<pre>$ emacs</pre></p>
	<p>To edit a file (let's say it's called "filename"), you'd type:</p>
	<pre>$ emacs <i>filename</i></pre></p>

	<p>To learn how to use emacs, there is no substitute for PRACTICE!!! Of course, there are multiple online resources that you can look at (especially given emacs' popularity) and here are some of them:<br>
	<li><a href="https://www.gnu.org/software/emacs/tour/" target="_blank">emacs tour from the GNU organization (makers of emacs)</a></li><br>
	<li><a href="https://www.gnu.org/software/emacs/refcards/pdf/refcard.pdf" target="_blank">emacs commands - a handy reference card</a></li><br>
	<li><a href="http://www.jesshamrick.com/2012/09/10/absolute-beginners-guide-to-emacs" target="_blank">a beginner's guide to emacs</a></li></p>
	</ol>
<li> <b>vim</b> for UNIX-based OS</li>
	<ol>
	<p>vim (or sometimes called vi) is another popular editor that's also available on just about every UNIX machine (including the ones that you're using in the CS labs) and UNIX-based machines (like MacOS computers).</p>
	<p>To run vim on a UNIX machine or a MacOS machine, open up a terminal (see above for how to do that on Macs) and type:<br>
	<pre>$ vim</pre></p>
	<p>To edit a file (let's say it's called "filename"), you'd type:</p>
	<pre>$ vim <i>filename</i></pre></p>
	<p>Again, to learn how to use vim, there is no substitute for PRACTICE!!! Again, there are multiple online resources that you can look at and here are some of them:<br>
	<li><a href="http://www.vim.org/about.php" target="_blank">About vim</a></li><br>
	<li><a href="http://tnerual.eriogerg.free.fr/vimqrc.html" target="_blank">vim commands - a handy reference card</a></li><br>
	<li><a href="https://www.fprintf.net/vimCheatSheet.html" target="_blank">another reference cheat sheet for vim</a></li></p>
	</ol>
<li> <b>Sublime Text 2</b> for Windows OS and MacOS X --- see <a href="https://www.sublimetext.com/" target="_blank">the product website</a> (it's a program that you'd have to download)</li>
<li> <b>Notepad++</b> for Windows OS --- see <a href="https://notepad-plus-plus.org/" target="_blank">the product website</a> (it's a program that you'd have to download)</li>
</ol>

<hr>
<h3>Step 4: Create and edit a file containing a C++ program</h3>

Now it's time to write the program! If you're comfortable with one of the reviewed text editors, then go ahead and use one. Otherwise, here are some [emacs hints](emacs_hints/) and some [vim hints](vim_hints/).

This assignment only needs you to write a program that prints out two lines on the display, and nothing else. <b>The output should look exactly as follows</b> (no space before or after each line, except the 2 newlines):

```
Hello, world!
CS16 Spring 2018.
```

Start with a "skeleton program" (or template) that contains the necessary structure but that does not do anything:

```cpp
#include <iostream>

using namespace std;

int main() {
    // Your printing code should go here
    // By the way, when a line in C++ starts with //, it's a comment

    return 0;
}
```
<p>Go ahead and type this in to the <b>hello.cpp</b> file. Alternatively, you can copy and paste it directly from this page.</p>

<p>Next, you will need to replace the comment with code to print out the expected output. Comments in C++ are lines that start with <b>//</b> or text between <b>/*</b> and <b>*/</b>. The second type can span multiple lines.</p>

<p><em>Important note: For students familiar with Python, remember that lines starting with the <b>#</b> character are not comments in C++. Rather, they are important include lines that allow your program to use the input and output functionality. Make sure to copy those lines in your program as well. Only <b>//</b> or <b>/*</b> create comments in C++.</em></p>

<p>To print out text to the terminal, you can use the <b>cout</b> stream. To output something use the <b>&lt;&lt;</b> operator as shown below:</p>
<pre>cout &lt;&lt; "This will be printed out to the terminal" &lt;&lt; endl;</pre>

<p>The <b>endl</b> command will cause a newline (i.e. a carriage return) to be printed and the next print to go on the next line.</p>

<p>You can adapt this line to achieve the objective of the assignment. <b>Remember that we need to print two lines, each with a newline at the end.</b> You can do this with one or two statements.</p>

<hr>
<h3>Step 5: Compile the Code</h3>

<p>Now that the code is written, we need to <em>compile</em> it. This will be done using a special program called a <em>compiler</em>.</p>

<p>Before moving on, <b>make sure you save your code</b> and close the text editor. The following step will be done in the terminal.</p>

<p>For C++ code we will use the <b>g++</b> compiler that's built-into many UNIX machines (it even works on most MacOS terminal programs). You can compile the <b>hello.cpp</b> file into an executable called <b>hello</b> with the following command:</p>
<pre>$ g++ -o hello hello.cpp</pre>

<p>This will compile your code and make an executable version of it. Specifically, it will tell the compiler to take the source code file <b>hello.cpp</b> and compile and link it to an executable called <b>hello</b>.</p>

<p>If the compilation is successful, you won't see any output from the compiler, but if you issue a UNIX <b>ls</b> command, you should see a new file has appeared: one called <b>hello</b>. You can then use the following command to run your program:</p>
<pre>$ ./hello</pre>

<p>Which means "in the current directory, as represented by the <b>.</b> character, run the program <b>hello</b>". You should then see the program output the two expected lines.</p>

<p>The other possibility is that the program may <b>not compile successfully</b>. What to do then?<br>
If you run the <b>g++</b> command and are unsuccesful with your compilation, then you might see an output that looks like this:</p>
<pre>hello.cpp: In function ‘int main()’:
hello.cpp:10:1: error: expected ‘;’ before ‘}’ token
 }
 ^</pre>

<p>The compiler will try to give you hints on the line (in this case, it is complaining about line 10) where the error occurs, and also about what the error is (in this case a missing semicolon). You will also note that, in this case, an output executable file is not produced.</p>

<p>If you encounter an error, use the compiler hints and examine the line in question. If the compiler messsage is not sufficient to identify the error (which happens more than sometimes), you can search online to see when the error occurs in general. Once you have fixed the error, run the compilation command again. De-bugging a program code is a necessary ritual in almost all programs written (even those written by expert coders). More on that in a later class.</p>

<!--
<p>You can find a list of common C++ errors and possible solutions at <a href="http://charlottehill.com/cpperrors.html">http://charlottehill.com/cpperrors.html</a>.</p>
-->

<hr>

<h3>Step 6: Write your second C++ program: COINS.CPP! </h3>

Write a program, called <b>coins.cpp</b> that allows the user to enter a number of quarters, dimes, and nickels and then outputs the monetary value of the coins in cents. For example, if the user enters 2 for the number of quarters, 3 for the number of dimes, and 1 for the number of nickels, then the program should output that the coins are worth 85 cents. 

Start off, like with the previous program, by starting up your favorite text editor (emacs, vim, or something else that can create simple text files -- AGAIN, NOT MS Word). Call your new file <b>coins.cpp</b>.

<b>Before you write the program</b>, think about what it would entail to get this code to work. In other words, <b>come up with the step-by-step algorithm</b>.

The program should print a string of text to the terminal (that is, the computer display, also known as the 'standard output' device) before getting each piece of input from the user. A session should look <b><i>exactly</i></b> like the following example (including whitespace and formatting), with possibly different numbers for inputs and the output (so the following is just ONE example of how the program might run, but the FORMATTING has to be exactly the same in order for you to get full credit):

```
Enter number of quarters:
3
Enter number of dimes:
2
Enter number of nickels:
4
The coins are worth 115 cents.
```

Each string printed by the program should include a newline at the end, but no other trailing whitespace (i.e. do not have extra space characters at the end of the line).

HINT:
Start with this template that contains the necessary structure but that does not do anything:

```cpp
#include <iostream>

using namespace std;

int main() {
    // 1. Declare your variables -- HINT: They are all integers
    // 2. Put a cout statement to print something to the display (a.k.a standard output)
    // 3. Put a cin statement to get something from the keyboard (a.k.a standard input)
    // 4. Repeat parts (2) and (3) twice more
    // 5. Calculate the total value of all the coins based on the 3 inputs you got in prior steps
    // 6. Put a cout statement to print that total value

    return 0;
}
```

The program example that I showed you in the 1st lecture should contain several clues as to how to complete this program.

<h3>Step 7: Compile your second C++ program</h3>
<p>Before moving on, <b>make sure you save your code</b> and close the text editor. The following step will be done in the terminal.</p>

<p>Again, we will use the <b>g++</b> compiler to create an executable called <b>coins</b> with the following command:</p>
<pre>$ g++ -o coins coins.cpp</pre>

<p>This will compile your code and make an executable version of it. Specifically, it will tell the compiler to take the source code file <b>coins.cpp</b> and compile and link it to an executable called <b>coins</b>.</p>

<p>If the compilation is successful, you will not see any output from the compiler, but if you issue a UNIX <b>ls</b> command, you should see a new file has appeared: one called <b>coins</b>. You can then use the following command to run your program:</p>
<pre>$ ./coins</pre>

<h3>Step 8: Submit your program for grading</h3>

<p>Once you are satisfied that your programs are correct, then it is time to submit them.</p>

<p><strong>Please remember that you must submit the programs to obtain any credit for the assignment; just completing the programs is not enough.</strong></p>

<p>For this example, let us assume that you only had to submit 1 program (hello.cpp). This applies to ANY C++ program you submit via this system:</p>
<hr>

<p>In this course we will use the <a href="https://submit.cs.ucsb.edu/" target="_blank">submit.cs.ucsb.edu</a> system. You can make a submission from either the command line on any CS machine, or from a Web browser.</p>

<p>If you do not have a submit.cs account, you will first need to create one. This can be done at 
<a href="https://submit.cs.ucsb.edu/form/user" target="_blank">https://submit.cs.ucsb.edu/form/user</a>.</p>

<p>Once you have an account created, login at <a href="https://submit.cs.ucsb.edu/session" target="_blank">https://submit.cs.ucsb.edu/session</a>.</p>

<p>Next, you need to join the CS16 course. Look for the "Join Class" link at the top of the page. It is in the top bar, as seen below:</p>
<img src="submit-topbar.png" width="542" alt="submit.cs Top Bar" />

<p>Once you see the list of all courses, click on the <b>"Join CS16_s18_matni"</b> button.</p>

<p>You should then see CS16 appear on your homepage when logging in to the submit.cs system. Click on the course now.</p>

<p>Now find "lab01" and click on the "Make Submission" button. It looks like this:</p>
<img src="make-submission-button.png" width="154" alt="Make Submission Button" />

<p>This is the Web interface for submitting your code for the assignment. You can now upload your source file directly on this page. The browser will open a dialog box and you will need to navigate to the directory containing your <b>hello.cpp</b> file and select it.</p>
	
<p>Once your file is uploaded, click "Submit 1 File":</p>
<img src="submit-file-button.png" width="129" alt="Submit 1 File Button" />

<p>Once you submit, you should see a page detailing your submission. The system will automatically grade your program and will show you the results on this page after about a 1 minute delay.</p>

<p>You can <em>alternatively</em> submit your code from the command line (i.e. in the terminal) on any CS machine, including the Phelps lab machines or the CSIL server. You can also use this method when logged in remotely. To submit the the <b>hello.cpp</b> file to this assignment by running the command:</p>
<pre>$ ~submit/submit -p 979 hello.cpp coins.cpp</pre>

<p>The program will ask you to login <b>with your submit.cs username and password</b>. The password will not be printed to the terminal, but what you type will be used. It will also offer the option to save your credentials, so that you do not have login next time you submit. You may choose to do this or not. After the submission succeeds, you should see the program output something like:</p>
<pre>Results will be available at: https://submit.cs.ucsb.edu/submission/xxxxx</pre>

<p>You can copy this URL and paste into a Web browser to reach the same submission result page as described above.</p>

<hr>
<h3>Step 9: Check Submission Results</h3>

<p>After the 1 minute delay, the submit system will show your score and give you feedback on your submission. <em>Refresh the webpage after a minute to see this information.</em> This usually takes one of three forms:</p>

<p>A correct submission with a score of 100. This means that your program passed all the tests for this assignment. Once you get to this point, you are finished with the assignment and will receive full credit. This case will look like this:</p>
<img src="correct-submission.png" width="233" alt="Correct Submission." />

<p>An incorrect submission with a score of 0 to 99. This means that your program failed 1 or more of the tests. For this assignment, the system will show both the expected output and the output your program generated side-by-side so that you can see what went wrong. You will need to fix your program, and then do Step 8 again to re-submit. This case will look like this:</p>
<img src="incorrect-submission.png" width="706" alt="Incorrect Submission." />

<p>Or a submission for which compilation failed. This means that your program caused compilation errors when the system tried to compile it. You will need to interpret the compiler output and fix the errors. The system will show you the compilation command that failed along with the full error message. This case will look like this:</p>
<img src="compilation-failure.png" width="499" alt="Compilation Failure." />

<p>You may submit your program multiple times before the deadline. You should really only submit after local compilation does not produce any errors and runs as expected - that is the most efficient and preferred way to do things. The score of the last submission uploaded before the deadline will be used as your assignment grade.</p>

<hr>
<h3>Step 10: Done!</h3>

<p>Once your submission receives a score of 100/100, you are done with this assignment. Congratulations on completing your first C++ programs!</p>

<p>If you are in the Phelps lab or in CSIL, <b>make sure to log out of the machine before you leave</b>. Also, make sure to close all open programs before you log out. Some programs will not work next time if they are not closed. Remember to save all your open files before you close your text editor.</p>

<p>If you are logged in remotely, you can log out using the <b>exit</b> command in UNIX:</p>
<pre>$ exit</pre>
