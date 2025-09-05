# Linux Basics - Chapter 1A

In this module, we'll be learning about some basic file manipulation in terminal. 90%+ of a Bioinformaticians work is performed in the temrinal, so knowing is a crucial aspect of your skillset.

Since what we need is data that we can work on, we'll first download it from our Github repo.
`wget` is a command-line utility to download files from the Internet. So simply either copy and paste the command below or navigate to the shared Github repo, click the file and then download it manually through the GUI. 

<pre> wget https://github.com/Mollinak10/Linux-basics/blob/main/exercise_files.tar.gz </pre>

If this method somehow did not work, download it the normal way through the GUI and we'll simply copy the file. 
The command used to copy files is called `cp`, and your Downloads folder will be on the following path.

<pre> cp /mnt/c/Users/<your username>/Downloads/exercise_files.tar.gz . </pre>

This is the full path to your file, input your OS username in the <your username> area, which you can see by double-pressing the Tab key. The `.` in the command signifies the destination, and the `.` means the current directory where you are. So if you are in the home directory, `.` will copy your file from the Downloads directory to the home directory.

Now that we have downloaded our file, we need to unpack/decompress our file. `tar` is another command-line utility that allows you to compress and decompress files. `tar.gz` is one of the many compression formats. So we'll use the following command to decompress our file.

<pre> tar -xzvf exercise_files.tar.gz </pre>

This will print the directories and files being decompressed. Now, we'll move in the newly formed `data` directory, and use `ls` to list the contents in the directory. What do you see?

You can also use `ls` to peek into the subdirectories without the need to change your current directory. As always, you can use `cd` to move further into one of the BacteriaData or VirusData subdirectories. 

#### Exercise: What are the subdirectories present in each of the BacteriaData and VirusData subdirectories?

As you can see, inside each of the subdirectories contain 4 more subdirectories, and inside each contain the full genome assemblies and protein annotations of the organism. You'll find that it's very disorganised, and we'll learn how to organise them using the `mv` command.

`mv` serves two purposes: to move/cut a file or directory and also to rename a file/directory, so be very careful! 

An example of moving a file from one directory to another is:
<pre> cd BacteriaData
  cd a_baumannii
  ls a_baumannii
</pre>

You'll see that `a_baumannii` contains 2 files: 
<pre> ls
a_baumannii_nt.fa  flu_nt.fa
</pre>

Similar cases can be found all over, and it's our job to organise them, which we can do in several ways:
<pre> 
  mv flu_nt.fa ../../VirusData/influ-A/
</pre>

What we did here was go two steps back using `../../` and so we are back at the spot where both BacteriaData and VirusData are present, then we specified `VirusData/influ-A` in addition, to finally specify the destination. 

As we said there are several ways, and all of them involve you providing a source and a destination, another example here of moving the same file being:
<pre> cd ../../ (move two steps back, now you're in the data dir)
  mv BacteriaData/a_baummannii/flu_nt.fa (your source file) VirusData/influ-A/ (this is your destination) 
</pre>

#### Now your job is to find all the mismatched in both BacteriaData and VirusData and organise them.

For our final exercise, we'll create two subdirectories, called assemblies and annotations. 

<pre> mkdir assemblies annotations </pre>

If you noticed, all assemblies and annotations have a common suffix across all files, `_nt.fa` for assemblies and `_aa.fa` for annotations, so use a single command to copy `cp` all the assemblies to the `assemblies` dir and all protein FASTA files to the `annotations` dir.
