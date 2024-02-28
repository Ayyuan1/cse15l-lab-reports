**_LAB REPORT 4_**

1. Logging on to ieng6 without a password
   
**_KEYS PRESSED:_** "ssh ayyuan@ieng6.ucsd.edu" `<enter>` I had to type the whole command to log onto the remote system.

 ![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/4b377691-4858-4b11-8d97-da1a39fe5dcd)

2. Cloning the repository using the SSH link
   
**_KEYS PRESSED:_** "git clone" `<ctrl> + <v> <enter>` To clone the repository I used git clone and then pasted the link.
   
![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/f6adec48-25ac-4bb6-aee6-f49c137e2f1a)

3. Running and observing that the intial tests fail
   
**_KEYS PRESSED:_** "cd la-" `<tab> <enter>` First I change to the lab7 directory and the I compile and run the tests with "bash te-" `<tab> <enter>`

![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/f2ff2c47-87f3-4200-9e5c-d4010c7915f7)

4. Editing the file to make the tests pass

**_KEYS PRESSED:_** "vim L-(istExamples)" `<tab>` ".(java)" `<tab>` First I use vim to edit the ListExamples file, "44j e x i 2 `<esc>` :wq `<enter>`" This sequence of commands moves down 44 lines to the line we need to edit
then moves to the end of the line with "e", deletes the 1 with "x", enters insert mode "i" then puts the 2, then I go back to normal mode and save and quit with ":wq". Then I rerun the test "`<up>` `<up>` `<enter>`" gets
me back to the bash command and runs it.

![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/4eb480d0-e96f-45d9-94fb-8e28313eb0f7)


![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/03242da9-d41c-4529-9503-bc2eadaf6308)

5. Committing and pushing changes to github

**_KEYS PRESSED:_**   "git init" First I initialize git then I add the files that I want to commit with "git add Li-(stExamples.java) `<tab>`" I then check to make sure 
I am ready to commit by using "git status". Then I "git commit -m "Done" `<enter>`" to commit my changes with a message. Lastly I push my changes by remote adding my repository "git remote add origin `<ctrl> + <v>`"
and using "git push -u or `<tab>` main"

![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/985171c1-b650-43d3-8cbf-a78c0b6ce1f9)

![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/407a40c9-a438-4e8f-9588-cd6e6bd36b72)

![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/b846ea60-4b99-4755-a9f3-59197d31bff5)
