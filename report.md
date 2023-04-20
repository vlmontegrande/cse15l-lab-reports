# **Remote Server Tutorial**

For CSE 15L, connecting to the remote server is one basic skill that you will need to learn. Good thing there's a perfectly good tutorial right here for you to use!
In this tutorial, I'll go through the three steps that I used to connect my course account on ieng6: 
  - Installing VSCode
  - Remotely Connecting
  - Using Commands
 
---

## **Installing VSCode**

If you don't already have the code editor VSCode, you'll have to get it. Not only will it be useful in this course, many professionals use it in their workflow. 
However, I didn't download VSCode because I already had it on my computer. If you don't already have VSCode, you can download it at this link: [VSCode](https://code.visualstudio.com/). Once you download and install it, the home page should look something like this: ![Image](https://i.imgur.com/TqmWXIy.png)

---

## **Remotely Connecting**

After installing VSCode, you're going to have to install [Git](https://gitforwindows.org/). I downloaded Git for Windows and installed it. After, I opened Git Bash in VSCode. To do it, I: 
  - Opened the terminal with *CTRL* + *\`* 
  - Opened the command palette with *CTRL* + *SHIFT* + *P* 
  - Typed "Select Default Profile" 
  - Selected the Git Bash option, and finally
  - Clicked the *+* icon in the terminal

The Git Bash terminal looks something like this: ![image](https://i.imgur.com/KSMN74f.png)

To connect to the remote server, type "ssh cs15lsp23??@ieng6.ucsd.edu" with ?? replaced by the letters of your course account.
If you get a message about the authenticity of the host, type yes. When it prompts you for your password, type your password (keep in mind that when you type your password, you can't see what is being written). After all of that, you should be connected to the server. It should look something like this: 

![Image](https://i.imgur.com/jHKKhfa.png)

Congratulations! You have connected to the remote server. Now it's time to get comfortable with commands.

---

## **Using Commands**

Now is the time to try some commands! Using commands like cd, ls, pwd, and mkdir, you can do some interesting things in the terminal! 
I especially like moving around the file directory and exploring what's in where. I also made new directories and removed them. Here's what it looked like: 

![Image](https://i.imgur.com/gNi3ORf.png)

When looking at the command line, it is easy to be overwhelmed! However, once you understand what every command does, you can see what its output means. Here are different commands and what they do:

   - cd: stands for change directory. You can put a relative or absolute path as an argument, allowing you to navigate to that directory. Also, there are special characters that act as shortcuts. "cd ~" takes you back to your home directory. "cd /" takes you back to your root directory. "cd .." takes you back to the parent directory. As you can see, cd doesn't give an output. That's how you know it worked.
   - ls: stands for list. This command allows you to list all the files and folders in your working directory. As you can see, when I navigate to different directories, such as the home or root directories, it shows different files. When I go into the perl5 directory, it doesn't show anything. That means that there is nothing in the directory. Also, you can add arguments to ls. For example, I added "-lat". This shows all files sorted by date. I couldn't fit them all in the screen, as there are a total of 1247 files shown.
   - mkdir and rmdir: stands for make directory and remove directory, respectively. They are pretty self explanatory. You can make a new directory with mkdir and you can remove any directory with rmdir. In my particular example, I navigated to the perl5 directory, created a directory with mkdir, showed it existed with ls, and removed it with rmdir. It didn't show up upon running ls.
