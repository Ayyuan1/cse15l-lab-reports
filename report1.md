Lab Report 1: 

`cd`  (no arguments) 

![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/360f3664-9bb7-42b1-905b-5e93faac6da5)


-`/home` 

-There is no output because nothing will happen unless you state which directory you would want to change to. If you are in a directory deeper than the home directory and call cd, you will be returned to the home directory.

-This output is not an error; there is no error message.

`cd` (path to a directory)

![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/24b1dba6-6881-448b-a71d-2637cd0b346a)

-`/home/lecture1/`

-The command line now shows that we are in the lecture1 directory by displaying it where we will type our next command.

-This is not an error, it is intentional to show the user that they have successfully changed directories.

`cd` (path to a file)

![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/dacfcf31-04cd-4eb9-a50c-a52470a6cedb)

-`/home/lecture1/messages`

-The output is telling us we cannot us cd to a file because a file is not a directory.

-This is and error because the cd command is stricty for changing into other directories, which a file is not, as displayed in the error message.

`ls` (no arguments)

![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/975f7a5a-ac71-4c7a-9d79-a3668ac4fb31)

-`/home`

-The output shows us a list of files and directories in the directory that we are in.

-Not an error

`ls` (path to a directory)

![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/d2347ceb-911a-4cf1-a4e9-d31d12a3c6b4)

-`/home`

-By including a path to a directory in our argument, this command now shows us the files and directories within the directory that we specified in the command.

-Not an error

`ls` (path to a file)

![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/4f8d0419-143c-4000-8ce5-24dd066d963d)

-`/home/lecture1/messages`

-The output just prints the name of the file on the next line.

-Not an error

`cat` (no argument)

![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/05989bff-51eb-49ec-aa2d-3889255a4fe7)

-`/home`

-After using `cat` the terminal starts the read the users input and just repeats it back to them.

-Not an error

`cat` (path to a directory)

![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/8462be7e-823d-4dc9-b529-c5bb932efc64)

-`/home`

-The output just tells us that the directory we chose is indeed a directory but does nothing else.

-Not an error

`cat` (path to a file)

![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/b7650829-2e1c-4e88-820b-c8ad5f40c76b)

-`/home/lecture1/messages`

-The output of running this command on a file prints the contents of the file. Multiple files can be used in the argument and they will both be printed.

-Not an error








