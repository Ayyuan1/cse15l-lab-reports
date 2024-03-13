__Original Post from Student:__

Hey everyone,

I'm having trouble with my Java program. It's supposed to read a list of numbers from a file and compute their average, 
but it's giving me the wrong result. I've attached a screenshot showing the output when I run the program. 
I think the bug might have something to do with how the program is reading the numbers from the file. 

Any help would be appreciated!

![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/4dc24d9f-c404-407a-85a3-908509c50b9c)

__Response from TA:__

Hi there,

Thanks for reaching out. It looks like you are trying read numbers from a file and are getting an error when trying to scan the 
integer 10. Notice the whitespace after 10 in the quotation marks, how might this be causing problems for the scanner or parseInt function?
Let me know what you find!

__Screenshot/Terminal Output after Trying TA's Suggestion:__

After closer inspection of the input.txt file, I noticed some of the numbers having an extra whitespace at the end of the line which was causing 
the error. The error went away when I deleted the extra spaces, but I decided to try and improve my code to account for cases where this would be an issue. 
I added in a line that gets rid of extra whitespaces in the file before attempting to iterate through it with the scanner.

__Wrap up:__

The file & directory structure needed: The workspace needs to have the Main.java file and a bash script called run.sh and a file called input.txt. The
program only accepts files with this name.

The contents of each file before fixing the bug: See below.

The full command line (or lines) you ran to trigger the bug: `bash run.sh`

A description of what to edit to fix the bug: Add these lines:
`String line = scanner.nextLine().trim(); // Trim extra whitespace`
                
                if (!line.isEmpty()) { // Skip empty lines`

__Main.java__
```
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        try {
            File file = new File("input.txt");
            Scanner scanner = new Scanner(file);
            
            int sum = 0;
            int count = 0;
            
            while (scanner.hasNextLine()) {

                //These lines were added after consulting the TA for help
                String line = scanner.nextLine().trim(); // Trim extra whitespace
                if (!line.isEmpty()) { // Skip empty lines

                int num = Integer.parseInt(line);
                sum += num;
                count++;
    }
}
            
            double average = (double) sum / count;
            System.out.println("Average: " + average);
            
            scanner.close();
        } catch (FileNotFoundException e) {
            System.out.println("File not found.");
        }
    }
}
```

__input.txt__
```
10
20
30 
40
```

__run.sh__
```
javac Main.java
java Main
```

__Reflection:__
Something interesting I learned in lab in the second half of this quarter was how to utilize tools such as jdb and vim to view, edit, and fix files
from just the termimnal/command line. I always pictured coding to have both a workspace in tandem with the terminal so it was interesting to learn that you
only need a terminal to code.
