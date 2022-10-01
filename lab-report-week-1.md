# Lab Report: Week 1
## CSE 15L Camille Phares 
1. Installing VScode  
    * Go [here](https://code.visualstudio.com/) to download. 
  Click the dropdown menu and change to match your computer, if necessary. 
    * If you also have a mac, drag the VSCode installer into the applications folder, and then launch it
<img width="440" alt="Screen Shot 2022-09-30 at 5 28 57 PM" src="https://user-images.githubusercontent.com/103080777/193375776-0140fd80-bdc4-450c-a0f1-e6446b117b15.png">

2. Remotely Connecting
    * Open a terminal in VSCode through the terminal menu
    * In the terminal, input `$ ssh cs15lfa22zz@ieng6.ucsd.edu` 
          **note: $ stands for all the stuff already in the terminal, and replace the zz with the letters in your account*
     * A warning message will come up, continue anyways
     * Then the terminal will want your password. If you recently reset it, it might not work, so be patient. You might have to 
     reset it again the next way if it still is not working. I am resetting my password again, as I have had to do for another class
     already. 
     * Once you successfully login, the terminal will tell you that you are on a remote server

<img width="764" alt="Screen Shot 2022-09-30 at 5 18 11 PM" src="https://user-images.githubusercontent.com/103080777/193376188-fbf52081-6c48-4982-8f8a-555564e791b0.png">

3. Trying out commands 
    * `cd ~` changes directory to the home directory
    * `cd` changes working directoy. Use with the name of a directory to move into it.
    * `ls -lat` shows a list of all files, shown by date
    * `ls -a` shows all files, even hidden ones
    * `ls <directory>` where `<directory>` is `/home/linux/ieng6/cs15lfa22/cs15lfa22abc` with someone else's username shows their files
    * `cp /home/linux/ieng6/cs15lfa22/public/hello.txt ~/` copies hello.txt into the home directory
    * `cat /home/linux/ieng6/cs15lfa22/public/hello.txt` prints the output of hello.txt
    While I could play with these commands a little in the terminal on my computer, I couldn't get into the ssh and use them there.

<img width="576" alt="Screen Shot 2022-09-30 at 5 51 51 PM" src="https://user-images.githubusercontent.com/103080777/193376852-c8011b11-97a8-4d48-a203-70ff5a65ccf4.png">

4. Moving files with `scp`
   * The command `scp` can copy files from a computer to a remote one. 
   * NOT logged into ieng6, run the command `scp <filename>.java cs15lfa22zz@ieng6.ucsd.edu:~/`. You'll have to enter your password. Then, the file should be in the home directory
   * Where I had to leave of b/c couldn't log in :/
  <img width="623" alt="Screen Shot 2022-09-30 at 6 37 49 PM" src="https://user-images.githubusercontent.com/103080777/193378080-e4be7266-bb5b-420b-8afd-8c03945c07df.png">
5. Setting an ssh Key
* Using ssh keys uses downloaded files on the client and server instead of a password. 
* On client: put in $ssh-keygen. It'll ask where you want to put it, you can hit enter to save it in the default place. Then enter the computer's password. 
* Then, find the public key in a file id_rsa.pub in the .ssh directory. Next, sign in to ieng6, and enter the public key to the .ssh directory. 
* Now you can ssh or scp between devices without using the password.
<img width="662" alt="Screen Shot 2022-09-30 at 6 52 36 PM" src="https://user-images.githubusercontent.com/103080777/193378531-5a2af8e7-d1d7-4a70-bf08-0a73f9e82c0d.png">

6. Optimizing Remote Running
* In ssh, run a command in quotes to run it on the remote server and exit
* Use semicolons to run multiple commands on the same line
* Use the up arrow to scroll through previous commands 
* I can't play around on the remote server yet, so I don't know how else to optimize :/

