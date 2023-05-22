4. Log into ieng6 `<up> <enter>` 

*The ssh command of `ssh cs15lsp23oh@ieng6.ucsd.edu, <enter>` was the last command I executed, using the up arrow I was able to get to it efficiently.*
![image](https://github.com/vlmontegrande/cse15l-lab-reports/blob/main/images/Screenshot%202023-05-21%20223151.png)
  
5. Clone your fork of the repository from your Github account `git clone https://github.com/vlmontegrande/lab7.git, <enter>`

*I had to manually type the git clone command, copying and pasting the GitHub URL from the GitHub repository page*
![image](https://github.com/vlmontegrande/cse15l-lab-reports/blob/380ff8a23c05f9f4fe2d5c04d1a7b31b2f218ad2/images/REPORT.png)

7. Run the tests, demonstrating that they fail 
```
cd lab7, <enter>
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java, <enter>
ava -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ..., <enter>
```

*I had to manually type these too, as I didn't have any of them saved in my command history.*
![image](https://github.com/vlmontegrande/cse15l-lab-reports/blob/878993126c941e4a5e3a4063b8b20179beae94be/images/Screenshot%202023-05-21%20224959.png)

9. Edit the code file to fix the failing test
```
vim L <tab> . <tab> <enter>
?i <enter>
5l
r2
:wq <enter>
```


11. Run the tests, demonstrating that they now succeed
12. Commit and push the resulting change to your Github account (you can pick any commit message!)
