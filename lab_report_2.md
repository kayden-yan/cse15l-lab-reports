# CSE 15L Lab Report 2
___
## Part 1: Write a web server called StringServer
___
Following is the code of StringServer.java, I used implementation of Server.java provided in our Week 3 Lab.
```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
   String display = "";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return display;
        } 
        else if (url.getPath().equals("/add-message")) {
            System.out.println("Path: " + url.getPath());
            String[] parameters = url.getQuery().split("=");
            if(parameters.length == 1){
                return "Input is empty";
            }
            else{
                display += parameters[1] + "\n";
                return display;
            }
        }
        else if (url.getPath().equals("/empty")){
            display = "";
            return "Content emptied";
        }
        else {
            return "404 Not Found";
        }
    }
}

class StringServer {
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

Following is the command I used in the terminal to start up the local website:
```
javac StringServer.java Server.java
java StringServer 4400
```

After I complie and run the script for the website to startup, I entered the following url in the browser to test the functionality:

```
http://localhost:4400/add-message?s=Hello%20World
```
Screenshot:
![part1img1](https://github.com/kayden-yan/cse15l-lab-reports/blob/main/image/lab2/part1img1(1).png?raw=true)
This url invokes the Handler class and handleRequest method to check my input. Which in this case, if path equals "/add-message", it adds the input query to the class variable "display", then let it displays on the webpage by returning it.

```
http://localhost:4400/empty
```
Screenshot:
![part1img2](https://github.com/kayden-yan/cse15l-lab-reports/blob/main/image/lab2/part1img2(1).png?raw=true)
This url invokes the Handler class and handleRequest method to check my input. Which in this case, if path equals "/empty", it changes the class variable "display" to a empty string, then display that the content we inputed before was emptied successfully.

Which if we input something new:
```
http://localhost:4400/add-message?s=New%20Message
```
Screenshot:
![part1img3](https://github.com/kayden-yan/cse15l-lab-reports/blob/main/image/lab2/part1img3.png?raw=true)
It will not show up the "Hello World" we entered before.
___
## Part 2: Choose One of the Bugs From Lab 3
Method reverseInPlace:

Non-Failure-inducing input: ```{1}```
![part2img2](https://github.com/kayden-yan/cse15l-lab-reports/blob/main/image/lab2/part2img2(3).png?raw=true)


Failure-inducing input: ```{1,2,3}```. This was discovered by the Assertion test, as it can't outputs as expected.
Symptom: ```{3,2,3}```
![part2img1](https://github.com/kayden-yan/cse15l-lab-reports/blob/main/image/lab2/part2img1.png?raw=true)

Bug: The method reverseInPlace actually mirrors the last part of the input array. It modifies the original array so once the index runs on the later half of the  original array, it fails to obtain the information that was overwritten by the method on the first half.

Before the fix:
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```
After the fix:
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length / 2; i += 1) {
      int stored = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = stored;
    }
  }
```

___
## Part 3: Describe Something You Learned From Lab
I learned how to create a local website by setting up with java files and command lines. Moreover, setting up a website on a remote server such that every machine on the network can access the website and manipulate contents with url requests. I learned how to debug a java method by using JUnit and trying to logically trace the code by each line. 

