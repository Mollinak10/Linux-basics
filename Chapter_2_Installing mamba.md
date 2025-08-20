Hi everyone! 😃   
Welcome to lesson 2️⃣ where we'll learn how to install a package manager.      
I prefer to use mamba but there are many other package managers like anaconda and conda.   

**Installing mamba** 💻   
**Step 1:** In your terminal download mamba using wget.   
<pre> wget https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-$(uname)-$(uname -m).sh </pre>    
**Step 2:** If your system asks permission (yes/no) type "yes" ✔️ at any step  
**Step 3:** running the script with Miniforge  
Type the command below to run your script 
<pre> bash Miniforge3-$(uname)-$(uname -m).sh </pre> 
➡️once you have followed the steps, restart the terminal and mamba would be activated. You’ll see a prefix (base) before your prompt.       
⚠️Remember not to install any tools or software in your (base) environment⚠️     
**Step 4:** Creating new environment  
<pre> mamba create -n test </pre>  
➡️here -n lets you name the environment and we named it “test”   
**Step 5:** To activate your environment   
<pre> mamba activate test </pre> 
and now instead of “base” you’ll see “test” 
<pre>(base)molly_k@DESKTOP-MBJ059:~$ 
(test)molly_k@DESKTOP-MBJ059:~$ </pre>
you can use multiple environments and to switch between them you can use the command below and then activate another envirnoment❗   
<pre> mamba deactivate </pre>   
⚠️remember to not use this command while in your “base” environment⚠️ 
















