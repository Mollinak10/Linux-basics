Hi everyone! 👋
Welcome to Linux basic commands. You’ll learn how to navigate in Linux using the command line. 

**Getting started  
LINUX**   
I’ll be using **Ubuntu 24.04.1 LTS** on my windows desktop. You can also download the previous versions of Ubuntu. The command lines and prompts will be usable on earlier and future versions as well.  
While setting up your username keep in mind to use underscore (_) and set up a simple password like your name or 1234. 

**Structure** 
After setting your username and password, you will see something like this on the screen:  
__molly_k@DESKTOP-MBJ059:~$__    
You might see **$** or **#** depending on your system. Here “__molly_k__” is my username.   
You need to be careful about being case-sensitive while working on Ubuntu.   
A and a are not the same thing! ⚠️ So, keep this in mind while working. 

**NAVIGATION**  
How to navigate like a pro! 😄  
You need to know a few basic navigation commands to find your way while working. 

**mkdir**     
mkdir i.e. make directory is used to create a new directory.  
You can choose any name for your directory. Here I’m using linux (directory name).   
**~$ mkdir linux**

**ls**     
ls is used to list down all the content. It gives you a list of directories, comes in handy when you’re using multiple directories.  
**~$ ls**  
**linux**

**cd**     
cd stands for change directory which literally means to change directory. When you have multiple directories, you can use cd to open other directories and navigate between them.   
**~$ cd linux  
~/linux$** 

**cd ..**    
Now, if you want to go back a step, you can use cd ..   
**~/linux$ cd ..  
~$**

**pwd**    
pwd (print working directory) which shows the current directory i.e. the folder you are currently in. Since, the name of the directory is linux the command line shows full address like below.   
**~/linux$ pwd  
/home/molly_k/linux**

**nano**     
Do you want a text file with content? Use nano to create a text file. 
**~$ Nano mk.txt**
1. A new window will open.
2. Type your text. And press ctrl + X
3. Press the Y key on the keyboard for Yes.
4. Press enter-key and you’ll be back to your main page. 

**rm**   
To remove files, you can use this prompt.   
⚠️ But be careful while using rm! ⚠️  
**~$ ls   
linux   mk.txt  
~$ rm mk.txt   
~$** 

**rmdir**   
rm alone is not enough to remove directories, you need to use rmdir which is to remove (empty) directories    
⚠️ But be careful while using rmdir! ⚠️   
**~$ mkdir linux  
~$** 

**cat**     
To see the text content of your text file you can use this command.  
**~$ cat mk.txt  
My name is Molly.  
~$**

**echo**  
It prints out whatever you type.   
**~$ Echo “hi molly”   
hi molly** 



**grep**     
If you want to search a particular word from the contents of a file you can use grep.   
**~$ grep “name” molly.txt**   
**My** *name* **is Molly.** 

See you for the next lesson! 👋











