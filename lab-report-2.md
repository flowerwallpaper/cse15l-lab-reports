```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.

    ArrayList<String> stringCheese = new ArrayList<>();

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format("Hi there!!");
        } 
        else if (url.getPath().equals("/add")) {
            String[] args = url.getQuery().split("=");
            stringCheese.add(args[1]);
            return String.format("Added " + args[1] + "!");
        } 
        else if (url.getPath().contains("/search")) {
            String[] args = url.getQuery().split("=");
            for(int i = 0; i < stringCheese.size(); i ++){
                if(stringCheese.get(i).contains(args[1])){
                        return stringCheese.get(i);
                }
            }
        }
        else return String.format("404 Not Found!");
        return null;
    }
}

class SearchEngine {
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





<img width="368" alt="Screen Shot 2022-10-28 at 4 42 25 PM" src="https://user-images.githubusercontent.com/103080777/198751828-5b989be8-72e4-42b7-abfe-c936405b6316.png">

<img width="395" alt="Screen Shot 2022-10-28 at 4 42 01 PM" src="https://user-images.githubusercontent.com/103080777/198751780-380cf008-0a3c-4f5e-8b3a-fc6eb130f504.png">

<img width="519" alt="Screen Shot 2022-10-28 at 4 48 17 PM" src="https://user-images.githubusercontent.com/103080777/198751898-95b0f6f0-cc49-4443-99fa-fda3b01b0211.png">

