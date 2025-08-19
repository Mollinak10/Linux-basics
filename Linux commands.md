Hi everyone! 👋  
Welcome to lesson 1️⃣ on Linux basic commands. You’ll learn how to navigate in Linux using the command line. 

**Getting started  
LINUX**   
I’ll be using **Ubuntu 24.04.1 LTS** on my windows desktop. You can also download the previous versions of Ubuntu. The command lines and prompts will be usable on earlier and future versions as well.  
Set up your username and use a simple password like your name or 1234. 

**Structure**   
After setting your username and password, you will see something like this on the screen: 
<pre> molly_k@DESKTOP-MBJ059:~$ </pre>

You might see **$** or **#** depending on your system. Here “ **molly_k** ” is my username.   
You need to be careful about being case-sensitive while working on Ubuntu.   
A and a are not the same thing! ⚠️ So, keep this in mind while working. 

**NAVIGATION**  
How to navigate like a pro! 😄  
You need to know a few basic navigation commands to find your way while working. 

**mkdir**     
mkdir i.e. make directory is used to create a new directory.  
You can choose any name for your directory. Here I’m using linux (directory name).   
<pre>~$ mkdir linux </pre>

**ls**     
ls is used to list down all the content. It gives you a list of directories, comes in handy when you’re using multiple directories.  
<pre>~$ ls
linux </pre>

**cd**     
cd stands for change directory which literally means to change directory. When you have multiple directories, you can use cd to open other directories and navigate between them.   
<pre>~$ cd linux  
~/linux$ </pre> 

**cd ..**    
Now, if you want to go back a step, you can use cd ..   
<pre>~/linux$ cd ..  
~$ </pre>

**pwd**    
pwd (print working directory) which shows the current directory i.e. the folder you are currently in. Since, the name of the directory is linux the command line shows full address like below.   
<pre>~/linux$ pwd  
/home/molly_k/linux </pre>

**nano**     
Do you want a text file with content? Use nano to create a text file. 
<pre>~$ Nano mk.txt </pre>
1. A new window will open.
2. Type your text. (I typed My name is Molly)  And press ctrl + X
3. Press the Y key on the keyboard for Yes.
4. Press enter-key and you’ll be back to your main page.

**cat**     
To see the text content of your text file you can use this command.  
<pre>~$ cat mk.txt  
My name is Molly.  
~$ </pre>

**echo**  
It prints out whatever you type.   
<pre>~$ Echo “hi molly”   
hi molly </pre> 


**grep**     
If you want to search a particular word from the contents of a file you can use grep.   
<pre>~$ grep “name” molly.txt   
My *name* is Molly. </pre>

**rm**   
To remove files, you can use this prompt.   
⚠️ But be careful while using rm! ⚠️  
<pre>~$ ls   
linux   mk.txt  
~$ rm mk.txt   
~$ </pre>

**rmdir**   
rm alone is not enough to remove directories, you need to use rmdir which is to remove (empty) directories    
⚠️ But be careful while using rmdir! ⚠️   
<pre>~$ rmdir linux  
~$ </pre>




See you for the next lesson! 😄 👋


























