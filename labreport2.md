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

-The handleRequest method is called

-The relevant arguments are the substrings between s, and a the "&" , and between = and the newline.

-The values of the fields in the handleRequest method get changed everytime a new url is given. A list is created to split the query by the = character, then the username and the message are retrieved from that list and added to the ArrayList. That ArrayList is then changed to a string so it can be returned and printed to the page.

Full Path: https://0-0-0-0-1234-hl57qe2d1pgatedb9hpkjeedms.us.edusercontent.com/add-message?s=How%20are%20you&user=RandomGuy

![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/2b1ee516-2dcc-4612-a92e-294b9c814a63)

-The handleRequest method is called

-The relevant arguments are the substrings between s, and a the "&" , and between = and the newline.

-The values of the fields in the handleRequest method are updated with the new query. Thus, the ArrayList gains another element and two lines are now printed instead of one.

PART 2:

-Absolute path to private key

![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/f0462a72-755c-4a43-b773-93b5691ef6cd)


-Absolute path to public key

![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/33a7e610-2d0c-4c1a-b94d-d1f89ad6986d)


-Successfully logging on without entering password:

![image](https://github.com/Ayyuan1/cse15l-lab-reports/assets/156359241/3147f8b7-d009-49ca-b560-0c94cbaf5de1)

PART 3:

-Something new that I learned from the recent labs was how to code and run my own server using java. I had to learn how ports work and how to handle queries in the url to make changes to what is displayed on the webpage.
