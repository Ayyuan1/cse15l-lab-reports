PART 1:
Code for ChatServer.java

```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class Handler implements URLHandler {
    ArrayList<String> userList = new ArrayList();
    String stringUserList = userList.toString();
    
    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format(stringUserList);
        }  else {
            if (url.getPath().contains("/add")) {
                String[] parameters = url.getQuery().split("=");
                int and = parameters[1].indexOf("&");
                String message = parameters[1].substring(0,and);
                String user = parameters[2];
                userList.add(user + ": " + message + "\n");
                String stringList = userList.toString();
                return String.format(stringList).replace(",", "").replace("[", "").replace("]", "").replace("+"," ");
               
            }
            return "404 Not Found!";
        }
    }
}

class ChatServer{
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```
Full Path: https://0-0-0-0-1234-hl57qe2d1pgatedb9hpkjeedms.us.edusercontent.com/add-message?s=Hello&user=Ayden

![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/7f947bda-d827-43b2-9b41-d7eb1cba271c)

-The `handleRequest` method is called

-The relevant arguments are the substrings between s, and a the "&" , and between = and the newline.

-The values of the fields in the handleRequest method get changed everytime a new url is given. A string list  `parameters` is created to split the query by the = character, then the username and the message are stored in their respective `message` and `user` variables. The `user` and `message` variables are added to userList with the correct formatting. `userList` is then changed to a string called `stringList` so it can be returned and printed to the page. Additional formatting is required to remove the brackets that come default when printing a list.

Full Path: https://0-0-0-0-1234-hl57qe2d1pgatedb9hpkjeedms.us.edusercontent.com/add-message?s=How%20are%20you&user=RandomGuy

![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/2b1ee516-2dcc-4612-a92e-294b9c814a63)

-The `handleRequest` method is called

-The relevant arguments are the substrings between s, and a the "&" , and between = and the newline.

-The values of the fields in the handleRequest method are updated with the new query. This means `user`, `message`, and `parameters` are overwritten with the new information. This new info is formatted the same way and appended to `userList`. Thus, the ArrayList gains another element and two lines are now printed instead of one.

PART 2:

-Absolute path to private key

![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/9a9e2b65-a05d-48bc-81d3-0f1c58937435)



-Absolute path to public key

![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/bff0ad1e-8351-4f6c-837d-1fcd14e7ff35)



-Successfully logging on without entering password:

![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/3147f8b7-d009-49ca-b560-0c94cbaf5de1)

PART 3:

-Something new that I learned from the recent labs was how to code and run my own server using java. I had to learn how ports work and how to handle queries in the url to make changes to what is displayed on the webpage.
