# Lab Report: Week 1
## CSE 15L Camille Phares 
1. Installing VScode  
    * Go [here](https://code.visualstudio.com/) to download. 
  Click the dropdown menu and change to match your computer, if necessary. 
    * If you also have a mac, drag the VSCode installer into the applications folder, and then launch it
<img width="1440" alt="Screen Shot 2022-09-30 at 5 28 57 PM" src="https://user-images.githubusercontent.com/103080777/193375776-0140fd80-bdc4-450c-a0f1-e6446b117b15.png">

2. Remotely Connecting
    * Open a terminal in VSCode through the terminal menu
    * In the terminal, input `$ ssh cs15lfa22zz@ieng6.ucsd.edu` 
          **note: $ stands for all the stuff already in the terminal, and replace the zz with the letters in your account*
     * A warning message will come up, continue anyways
     * Then the terminal will want your password. If you recently reset it, it might not work, so be patient. You might have to 
     reset it again the next way if it still is not working. I am resetting my password again, as I have had to do for another class
     already. 
<img width="764" alt="Screen Shot 2022-09-30 at 5 18 11 PM" src="https://user-images.githubusercontent.com/103080777/193376188-fbf52081-6c48-4982-8f8a-555564e791b0.png">
    * Once you successfully login, the terminal will tell you that you are on a remote server
3. Trying out commands 
    * `cd ~` changes directory to the home directory
    * `cd` changes working directoy. Use with the name of a directory to move into it.
    * `ls -lat` shows a list of all files, shown by date
    * `ls -a` shows all files, even hidden ones
    * `ls <directory>` where `<directory>` is `/home/linux/ieng6/cs15lfa22/cs15lfa22abc` with someone else's username shows their files
    * `cp /home/linux/ieng6/cs15lfa22/public/hello.txt ~/` copies hello.txt into the home directory
    * `cat /home/linux/ieng6/cs15lfa22/public/hello.txt` prints the output of hello.txt
    While I could play with these commands a little in the terminal on my computer, I couldn't get into the ssh and use them there :(((
    <img width="576" alt="Screen Shot 2022-09-30 at 5 51 51 PM" src="https://user-images.githubusercontent.com/103080777/193376852-c8011b11-97a8-4d48-a203-70ff5a65ccf4.png"

4. Moving files with `scp`
. Setting an SSH Key
. Optimizing Remote Running
