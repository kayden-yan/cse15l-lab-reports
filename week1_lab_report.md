# CSE 12L Lab Report 1
___
This will be a tutorial for incoming student about how to access our class remote server on ieng6
___
## Step 1: Lookup Account and Reset Password
First, you want to log in with your student AD on this website to lookup your class-specific account for accessing remote server:
https://sdacs.ucsd.edu/~icc/index.php

Please do follow the tutorial that is provided on lab instructions, [link here](https://docs.google.com/document/d/1hs7CyQeh-MdUfM9uv99i8tqfneos6Y8bDU0uhn1wqho/edit). The UI interface on password change request site is very confusing and there is no interactive button to submit the request. (It was enter or return key on your keyboard to submit the request)

After you see the page that says the global password change results is success, please wait about 15 mins or so for it to take effective.
___
## Step 2: Install Visual Studio Code
The VSCode is a terminal that allows you to use command lines to link and interact with the server.

Here is the Visual Studio Code website:
https://code.visualstudio.com/

After you have successfully installed, it should looks like the following image:
![lab1vscode](https://user-images.githubusercontent.com/122576038/212785652-fae48e11-d271-414f-86ad-d6a7985cbe32.jpg)


___
## Step 3: Connect to Remote Server
Once you installed VSCode and Git if you are using Windows, you are all set to connect to the remote server.

Open VSCode first, then click on Terminal -> New Terminal in the menu

Following command will set connection between your computer and the remote server ieng6:
```
ssh YourAccountNameHere@ieng6.ucsd.edu
```

For your very first connection to the server, it would ask you for a authentication, please read and follow the steps in the lab instruction.

One tricky part on the login process is that the password input won't shows up when you typing in like most of website does, just do keep in mind that the input field is actually receiving your keyboard input despite the field is empty all the time.

The terminal should looks like this if login was successful:
![lab1login](https://user-images.githubusercontent.com/122576038/212785796-e1fcbbcf-8e3d-454b-9511-f70d25e67499.jpg)

___
## Step 4: Control and Navigate in Remote Server
There are many useful commands that are provided in lab instructions. Here is an example of how I used those commands:
![lab1commands](https://user-images.githubusercontent.com/122576038/212785816-6649fed8-8c47-47f7-a493-b410ac4b5bfb.jpg)

Make sure to use `exit` to close the connection once you finish working on the server.
