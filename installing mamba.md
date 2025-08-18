Installing mamba
In your terminal download mamba using wget. If your system asks permission (yes/no) type yes. 
wget https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-$(uname)-$(uname -m).sh
running the script with Miniforge 
bash Miniforge3-$(uname)-$(uname -m).sh
once you have followed the steps, restart the terminal and mamba would be activated. You’ll see a prefix before your prompt. 
Remember not to install any tools or software in your (base) environment 
How to create new environment
mamba create -n test
here -n lets you name the environment and we named it “test” 
to activate your environment 
mamba activate test 
and now instead of “base” you’ll see “test” 
you can use multiple environments and to switch between them you can use 
mamba deactivate  
remember to not use this command while in your “base” environment 


