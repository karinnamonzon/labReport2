# Part 1
## Creating a Web Server

Creating a web server uses two other files, an interface called URLHandler and a class called Server. 

`URLHandler`
```
interface URLHandler {
  String processRequest(URI uri);
}
```

`Server`
```
static void start(int port, URLHandler handler) { ... }
```

These will allow the program for the web server in a Java file to run the web server functions.

In this example we will be making a web server called `StringServer`. It will allow us to concatenate Strings to a new line using `/add-message?s=<string>` in the web server path.

There are two methods in the `StringServer.java` that implement the function of the web server.

![Handler Method](https://github.com/karinnamonzon/labReport2/blob/main/handlerMethod.png?raw=true)

The handler method implements the function of StringServer based on the path in the URL.

![StringServer class](https://github.com/karinnamonzon/labReport2/blob/main/StringServerMethod.png?raw=true)

![Launching StringServer](https://github.com/karinnamonzon/labReport2/blob/main/Screenshot%202023-01-27%20141124.png?raw=true)

![`/add-message?s=Hello`](https://github.com/karinnamonzon/labReport2/blob/main/Screenshot%202023-01-27%20140334.png?raw=true)

![`/add-message?s=How are you`](https://github.com/karinnamonzon/labReport2/blob/main/Screenshot%202023-01-27%20140425.png?raw=true)

# Part 2

# Part 3

In lab in week 2 I learned how to clone and push repositories from different servers. I thought it was very helpful to be able to have access to files and folders that are not actually on my local computer and modify them and then be able to push those changes back to the origin. In week 3, I learned about identifying bugs and symptoms from code and using testers and how to use them alongside programs. It allowed me to figure out what was wrong with the code such as logic errors, and change them so te output would be correct. 
