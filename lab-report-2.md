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

Uses the argument "banana" on the add method. The arraylist stringCheese starts out without any values, and this puts "banana" in it. 
<img width="368" alt="Screen Shot 2022-10-28 at 4 42 25 PM" src="https://user-images.githubusercontent.com/103080777/198751828-5b989be8-72e4-42b7-abfe-c936405b6316.png">


Also uses the add method, this time with the argument "apple". The arrayList stringCheese gets it as a new argument. 
<img width="395" alt="Screen Shot 2022-10-28 at 4 42 01 PM" src="https://user-images.githubusercontent.com/103080777/198751780-380cf008-0a3c-4f5e-8b3a-fc6eb130f504.png">

Uses the search method, finds that the first argument in stringCheese contains "banana", and returns it. No values change in this method. 
<img width="519" alt="Screen Shot 2022-10-28 at 4 48 17 PM" src="https://user-images.githubusercontent.com/103080777/198751898-95b0f6f0-cc49-4443-99fa-fda3b01b0211.png">


For the method Reversed, I gave it this test:
```
@Test
public void testReversed2(){
    int[] input2 = {1, 2, 3, 4};
    assertArrayEquals(new int[]{4, 3, 2, 1}, ArrayExamples.reversed(input2);
    }
```
The symptom was that the array gave the wrong result-- the first element came back as 0 instead of 4. The bug was using the value of the element at length - i - 1. There is no element before element 0, so there was a null value. My solution was to make a new array with the reversed order, and then put the values from that into the original array. 



//The failure-inducing input (the code of the test)
The symptom (the failing test output)
The bug (the code fix needed)
Then, explain the connection between the symptom and the bug. Why does the bug cause that particular symptom for that particular input?//

For the method Merge, I used this test. 
```
@Test
public void testMerge(){
List<String> listerine1 = Arrays.asList("x", "y", "z");
List<String> listerine2 = Arrays.asList("a", "b, "c");
List<String> toCompare = Arrays.asList("a", "b", "c", "x", "y", "z");

assertEquals(toCompare, ListExamples.merge(listerine2, listerine1);
}
```
The symptom was the program producing the error java.lang.OutOfMemoryError: Java heap space. This is because the program creates an infinite while loop. It's supposed to end when the index gets bigger than the list, but the index increases with the list, so it never ends. 


