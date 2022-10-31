# part 1
```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class Handler implements URLHandler {
    ArrayList<String> dictionary = new ArrayList<String>();

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            if (dictionary.size() == 0) {
                return "dictionary is empty";
            } 
            return dictionary.toString();
        } else if (url.getPath().equals("/add")) {
            String[] parameters = url.getQuery().split("=");
            dictionary.add(parameters[1]);
            return (parameters[1].toString() + " added");
        } else {
            System.out.println("path: " + url.getPath());
            if (url.getPath().equals("/search")) {
                String[] parameters = url.getQuery().split("=");
                String temp = "";
                if (parameters[0].equals("s")) {
                    int i;
                    for (i = 0; i < dictionary.size(); i++) {
                        if (dictionary.get(i).contains(parameters[1])) {
                            temp += dictionary.get(i) + " ";
                        }
                    }
                    if (temp == "") {
                        return "not found in dictionary";
                    }
                    return String.format(temp);
                }
            }
            return "not working";
        }
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

<img width="251" alt="Screen Shot 2022-10-14 at 1 29 58 AM" src="https://user-images.githubusercontent.com/68624067/195800562-b228601c-4105-4f9a-b1c0-169e8b0380cc.png">

```
- handleRequest method is called 
    - parameter passed into handleRequest is the host and path
    - in this case, the host is localhost:8000/ and the path is empty
- first if statement condition is true, executes block of code
- check dictionary size
- return "dictionary is empty" if the dictionary is empty, otherwise return values in the dictionary
```
<img width="328" alt="Screen Shot 2022-10-14 at 1 30 20 AM" src="https://user-images.githubusercontent.com/68624067/195800642-97417006-a9a4-4340-b53b-96cd04a5f9a4.png">

```
- handleRequest method is called 
    - parameter passed into handleRequest is the host and path
    - in this case, the host is localhost:8000/ and the path is add?s=test
- second if statement condition is true, executes block of code
- parameters array is declared, splits = (first parameter is everything before the =, 
second parameter is everything after the =)
- add the second parameter to dictionary (our keyword we are adding to the dictionary)
- return second parameter is added message
```
<img width="331" alt="Screen Shot 2022-10-14 at 1 30 50 AM" src="https://user-images.githubusercontent.com/68624067/195800739-39dced77-6326-44c2-9bbd-8765af900f32.png">

```
- handleRequest method is called 
    - parameter passed into handleRequest is the host and path
    - in this case, the host is localhost:8000/ and the path is search?s=te
- else statement condition is true, executes block of code
- print path to console
- check if path is /search
- parameters array is declared, splits = (first parameter is everything before the =, 
second parameter is everything after the =)
- temp string is declared
- check first parameter is s
- i int is declared in preparation for the next line
- checks every dictionary item for first parameter (our keyword we are searching in the dictionary) 
using a for loop with bounds i < dictionary.size()
- if there is a match, add the word to temp
- returns "not found in dictionary" if nothing could be found in temp, otherwise return temp 
(our keywords that matches the keyword we are searching in the dictionary)
```

# part 2
## ArrayExamples

<img width="611" alt="Screen Shot 2022-10-14 at 1 53 51 AM" src="https://user-images.githubusercontent.com/68624067/195805834-ea75978e-87e6-4ad6-9493-832c63511e77.png">

junit test screenshot

<img width="357" alt="Screenshot 2022-10-25 at 3 37 58 PM" src="https://user-images.githubusercontent.com/68624067/197895248-3445c12e-ba81-4646-98a1-24208e595a20.png">

junit terminal output

<img width="748" alt="Screenshot 2022-10-25 at 3 39 10 PM" src="https://user-images.githubusercontent.com/68624067/197895369-7375fdf5-5ebd-439b-8b14-fb5d7aa46aad.png">

fixed code i did to eliminate bug

<img width="314" alt="Screenshot 2022-10-25 at 3 40 04 PM" src="https://user-images.githubusercontent.com/68624067/197895483-ca94cda4-b5c3-4f05-8205-be46da5b5d55.png">

```
in the default code, it is altering the input array as well as referencing the input array for 
what value should be at a particular index.
in the example shown above, we were able to grab the first two numbers correctly, 
but the last number is incorrect because we are grabbing the changed number. 
our old input is now gone because it was altered.
```

## ListExamples

<img width="594" alt="Screenshot 2022-10-27 at 4 11 29 PM" src="https://user-images.githubusercontent.com/68624067/198414677-a2e77cec-099e-4c07-9b7c-787dce6b9334.png">

junit test screenshot

<img width="453" alt="Screenshot 2022-10-27 at 4 12 27 PM" src="https://user-images.githubusercontent.com/68624067/198414778-d3bc288c-750e-4515-add9-1ebc7787082a.png">

junit terminal output

<img width="614" alt="Screenshot 2022-10-27 at 4 13 17 PM" src="https://user-images.githubusercontent.com/68624067/198414874-c3857393-dcea-40f7-a622-9a56ece0a55f.png">

fixed code i did to eliminate bug

<img width="478" alt="Screenshot 2022-10-27 at 4 16 18 PM" src="https://user-images.githubusercontent.com/68624067/198415153-3d160747-8145-4c19-901b-5d49c380755a.png">


```
in the default code, it is sending all that matches our conditions to the front of the list
in the example shown above, it fails to output the output in the correct order. 
the contents of the output were correct. 
```

