# Lab Report 5

Final lab report. After this it's done. No more. We can live our lives. We can go our separate ways. I'm gonna make sure to put everything into this lab report.
I'm gonna make it my very best. I won't procrastinate, I'll do it on time, I'll double, triple check it. This will be my best work. Just watch me.

Update: it's monday at 6 pm, i procrastinated lmaooo

---

## Edstem post

**Autograder errors**

*What environment are you using (computer, operating system, web browser, terminal/editor, and so on)?*

I'm using the VSCode terminal. I have a Windows laptop.

*Detail the symptom you're seeing. Be specific; include both what you're seeing and what you expected to see instead. Screenshots are great, copy-pasted terminal output is also great. Avoid saying “it doesn't work”.*

```
$ bash grade.sh https://github.com/ucsd-cse15l-f22/list-methods-corrected
Cloning into 'student-submission'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 3 (delta 0), pack-reused 0
Receiving objects: 100% (3/3), done.
Finished cloning
TestListExamples.java:24: error: cannot find symbol
      lazy LAZY = new lazy();
      ^
  symbol:   class lazy
  location: class TestListExamples
TestListExamples.java:24: error: cannot find symbol
      lazy LAZY = new lazy();
                      ^
  symbol:   class lazy
  location: class TestListExamples
2 errors
JUnit version 4.13.2
.E
Time: 0.002
There was 1 failure:
ListExamples.java not found
error: file not found: grading-area\ListExamples.java
Usage: javac <options> <source files>
use --help for a list of possible options
ListExamples.java failed to compile
```

Essentially, every time I try to run the bash script to autograde a GitHub repository, it spits out a bunch of errors. Also when it tries
to run the program, it says "ListExamples.java not found".

*Detail the failure-inducing input and context. That might mean any or all of the command you're running, a test case, command-line arguments, working directory, even the last few commands you ran. Do your best to provide as much context as you can.*

```
CPATH='.:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar'

rm -rf student-submission
rm -rf grading-area

mkdir grading-area

git clone $1 student-submission
echo 'Finished cloning'

if [[ -d student-submission/ListExamples.java ]] 
then
    cp student-submission/ListExamples.java grading-area
    cp TestListExamples.java grading-area
else
    echo 'ListExamples.java not found'
fi

javac grading-area/ListExamples.java
if [[ $? -ne 0 ]] 
then
    echo 'ListExamples.java failed to compile'
    exit
fi

cd grading-area

javac -cp ".;../lib/hamcrest-core-1.3.jar;../lib/junit-4.13.2.jar" *.java
java -cp ".;../lib/junit-4.13.2.jar;../lib/hamcrest-core-1.3.jar" org.junit.runner.JUnitCore TestListExamples
```

This bash script seems to be the problem. Although there are some errors related to the java files, the "ListExamples.java not found" message 
is suspicious.

--- 
## TA Response

Thank you for such detail in your question. So if the problem seems to be not being
able to find the file in question, is there anything wrong with the bash script when it comes to looking for the file?

---
## Student Response

Ohhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhh

I'm an idiot

So my if statement used "-d" instead of "-f". "-f" is the command for checking if a file exists. Also, I didn't include
exit if the file wasn't found, leading to the large output and the tests running. This is the if statement I changed:

```
if [[ -f student-submission/ListExamples.java ]] 
then
    cp student-submission/ListExamples.java grading-area
    cp TestListExamples.java grading-area
else
    echo 'ListExamples.java not found'
    exit
fi
```

And this is the output I got after running the exact same bash command:

```
$ bash grade.sh https://github.com/vlmontegrande/lab3.git
Cloning into 'student-submission'...
remote: Enumerating objects: 92, done.
remote: Counting objects: 100% (55/55), done.
remote: Compressing objects: 100% (35/35), done.
remote: Total 92 (delta 23), reused 42 (delta 18), pack-reused 37
Receiving objects: 100% (92/92), 1.39 MiB | 1.71 MiB/s, done.
Resolving deltas: 100% (27/27), done.
Finished cloning
JUnit version 4.13.2
...
Time: 0.016

OK (3 tests)
Finished cloning
JUnit version 4.13.2
...
Time: 0.015

OK (3 tests)
```

---
# Reflection

A topic that I learned from the second half of this class that I didn't know before was bash scripting.
I never knew what exactly bash was, and that hurt mme when I would do things like ctf's in high school. 
I really appreciated this class going over the basics of stuff like that. Now I can finally understand
bash scripts that people use to automate certain things.
