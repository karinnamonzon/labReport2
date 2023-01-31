# Part 1
## Creating a Web Server

Creating a web server uses two other files, an interface called `URLHandler.java` and a class called `Server.java`. 

`URLHandler.java`
```
interface URLHandler {
  String processRequest(URI uri);
}
```

`Server.java`
```
static void start(int port, URLHandler handler) { ... }
```

These will allow the program for the web server in a Java file to run the web server functions.

In this example we will be making a web server called `StringServer`. It will allow us to concatenate Strings to a new line using `/add-message?s=<string>` in the web server path.

There are two methods in the `StringServer.java` that implement the function of the web server.

![Handler Method](https://github.com/karinnamonzon/labReport2/blob/main/handlerMethod.png?raw=true)

The handler method implements the function of StringServer based on the path in the URL.

![StringServer class](https://github.com/karinnamonzon/labReport2/blob/main/StringServerMethod.png?raw=true)

This is the StringServer method that is used to create the local host for the web server. It uses the IOException import in order to throw an exception. A port number from `1024 to 49151` must be entered, if it is not in between then it is an invalid number and would throw an error.

To put the web server online use the commands
```

```
This is what the terminal should look like:
![go online](https://github.com/karinnamonzon/labReport2/blob/main/creating.png?raw=true)

![Launching StringServer](https://github.com/karinnamonzon/labReport2/blob/main/Screenshot%202023-01-27%20141124.png?raw=true)

This is what the local web server looks like when `/add-message?s=Hello` is added to the end of the URL:
![`/add-message?s=Hello`](https://github.com/karinnamonzon/labReport2/blob/main/Screenshot%202023-01-27%20140334.png?raw=true)

This is what the local web server looks like when `/add-message?s=How are you` is added to the end of the URL and after `/add-message?s=Hello` had been added:
![`/add-message?s=How are you`](https://github.com/karinnamonzon/labReport2/blob/main/Screenshot%202023-01-27%20140425.png?raw=true)

It adds a new String to a new line 

# Part 2
Lab 3 focused on looking at bigs and symptoms from files. One method that had had bugs and synmptoms was `reverseInPlace()` this 

This is the original code for `reverseInPlace()` which did not reverse the array correctly:
```
static void reverseInPlace(int[] arr) {
    int[] tempArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      tempArray[0] = arr[i];
      arr[i] = arr[arr.length - i - 1];
    }
  }
```
The following are examples of JUnit tests for `reverseInPlace()`
This is an example of a JUnit test for `reverseInPlace()` that results in a failure:
```
@Test
public void testReverseInPlace() {
  int[] input1 = {1, 2, 3, 4};
  ArrayExamples.reverseInPlace(input1);
  assertArrayEquals(new int[]{4, 3, 2, 1}, input1);
}
```

This is an example of a JUnit test for `reverseInPlace()` that does not result in a failure:
```
@Test
public void testReverseInPlace() {
  int[] input1 = {3};
  ArrayExamples.reverseInPlace(input1);
  assertArrayEquals(new int[]{3}, input1);
}
```

Running these tests results in this:
![Image](https://github.com/karinnamonzon/labReport2/blob/main/failures.png?raw=true)

This is the new code for `reverseInPlace() ` that fixes the bigs and allows it to reverse an array correctly:
```
static void reverseInPlace(int[] arr) {
    int[] tempArray = new int[arr.length];
    for(int i = 0; i < arr.length/2; i += 1) {
      tempArray[0] = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = tempArray[0];
    }
  }
```

With this code and urunning it with the JUnit tests from earlier it produces this:
![Image](https://github.com/karinnamonzon/labReport2/blob/main/correct.png?raw=true)



# Part 3

In lab in week 2 I learned how to clone and push repositories from different servers. I thought it was very helpful to be able to have access to files and folders that are not actually on my local computer and modify them and then be able to push those changes back to the origin. In week 3, I learned about identifying bugs and symptoms from code and using testers and how to use them alongside programs. It allowed me to figure out what was wrong with the code such as logic errors, and change them so te output would be correct. 
