# Exception Handling: Best Practices in C#

Exception handling is crucial for building a robust, reliable, user-friendly, and maintainable application. Exception handling is applicable in C++, C#, and Java, here we will explore C#, breaking it down with clear relatable example for intermediate developers familiar with OOP basics.

Scope:
*	What is Exception and Exception Handling?
*	Why Handle Exception?
*	Exception Handling Syntax
*	Best Practices for Smooth Functioning
*	Quick Assessment

## Exception and Exception Handling

Have you ever experienced a YouTube or Instagram crash when your phone is critically low on storage?

This is because the app is trying to function normally- loading main UI, temporary logs, run background services and so on which requires some storage. The app wasn’t designed to handle this unexpected “insufficient storage” scenario. It gets confused, freezes, or even crashes.
In C#, this unexpected scenario is called an Exception – a runtime error that hinders the normal flow of a program.
Examples include:
*	Dividing by zero
*	Accessing a null object
*	Opening a missing file
*	Reading from a corrupted stream

Let’s go back to the app crash, but with a backup plan. Application checks for available storage before trying to load content. If it lacks sufficient storage, it displays a message:
 “Insufficient Storage, Free up space.”
No crash. Just clear user-friendly response.
This process of detection and handling is called exception handling.

In C#, Exception Handling is a mechanism that allows a program to:
* Detect runtime issues
*	Handle appropriately without crashing
*	Continue execution smoothly. 

## Why is Exception Handling Important?

Exceptions are unexpected conditions that the compiler cannot predict. Without proper handling, they cause erratic application behaviour and crashes.
Benefits:
*	Preventing crashes
*	Improves user experience
*	Reliable clean code 
*	Easy debugging
*	Cleaner error recovery

 That’s why exception handling matters: it gives developers a way to catch failure, inform users, and keep the app stable instead of letting it crash.

## Exception Handling Syntax in C#
Exceptions are handled in a structured way using keywords:
* try
* catch
* finally
* throw
![image](https://gist.github.com/user-attachments/assets/3d0e68ad-6ec8-4cda-9e30-212cc62f0ccc)

*Let’s break it down:*

![image](https://gist.github.com/user-attachments/assets/f9088d79-75d7-444e-9c23-ef2179154cbd)
![image](https://gist.github.com/user-attachments/assets/08997282-ec0e-40b8-9f9b-21d818297a9a)
 trying to write temporary data to a file. If everything works fine, the program continues normally.

 ![image](https://gist.github.com/user-attachments/assets/a1016ce7-fa67-4803-897d-e2f151877223)
If an exception occurs (specifically an IO Exception when the disk is full or unavailable), ![image](https://gist.github.com/user-attachments/assets/a172b2c4-3216-474e-b731-278cadd0ad2f)
 “catches” it, instead of crashing.
 
Prints message: “Storage full. Please free up space to continue.”

Then ![image](https://gist.github.com/user-attachments/assets/e3336805-ab1c-4d34-88e9-e8ffd9d75376)
  manually raises exception and rethrows the exception, allowing other parts of the program or higher-level handlers to be aware of the error or log it.
  
  ![image](https://gist.github.com/user-attachments/assets/3848e406-da72-4fcf-83c0-63284cf18117)
![image](https://gist.github.com/user-attachments/assets/ba3e8602-5f9e-4dc0-93bd-5044af82668a)
is for cleanup tasks or final actions, like closing files, releasing resources, or simply logging that an attempt was made. It runs regardless of exception occurrence. Here, prints a message to confirm the save operation occurred.

## Best Practices

For a smoother and readable application, there are some best practices to be followed:
* Catch Specific Exceptions:

  Catch precise exceptions (e.g., ![image](https://gist.github.com/user-attachments/assets/21f9c140-c806-4408-b93d-a0d2ba77b639)
 ) instead of a generic Exception. This helps to handle each error properly.
 
* Avoid Empty Catch Blocks:

  Never catch exceptions without action. Always log or inform the user to avoid silent failures.
 
* Use ![image](https://gist.github.com/user-attachments/assets/ba32052e-37e0-43c8-a226-59c8c4973431)
 for Cleanup:
 
  Use ![image](https://gist.github.com/user-attachments/assets/cb0c49c7-f82a-4993-828a-07717c8870d4)
 to release resources or perform cleanup, whether an exception occurred or not.
 
* Don’t Use Exceptions for Normal Flow:

  Exceptions should handle unexpected problems, not control regular program logic.

* Throw Clear Exceptions:

  Provide clear messages when throwing exceptions, like an app warning “Insufficient Storage.”

* Create Custom Exceptions When Needed:

  Use custom exceptions for app-specific errors to keep error handling clear.

* Log Exceptions:

  Record exception details for easier debugging.

* Avoid Throwing Exceptions in  ![image](https://gist.github.com/user-attachments/assets/ea884a34-a136-44a9-9c69-1d36e3eaada7) :

  Don’t throw new exceptions inside ![image](https://gist.github.com/user-attachments/assets/dda13695-c9d2-4862-94cf-5e3581082635)
blocks as they can hide original errors.

*Example*

![image](https://gist.github.com/user-attachments/assets/ea32f337-ab9e-40d6-a10f-b177ad257411)

This helps app respond gracefully instead of crashing—just like YouTube or Instagram showing a storage warning instead of freezing. Good exception handling improves user experience and makes your software more reliable.

## Custom Exceptions

Sometimes built-in exceptions don’t clearly describe what went wrong. That’s where custom exceptions help — by letting you define errors that fit your app’s specific logic.
Imagine Instagram doesn’t allow users under 18 to sign up. A custom exception makes that rule clear and easy to handle.

![image](https://gist.github.com/user-attachments/assets/0384087b-1e21-4caa-b62b-44a1bb6a3568)

This throws a custom exception if the user is underage, instead of behaving unpredictably.

## When to Use Custom Exceptions?

* Built-in exceptions don’t describe the issue well.
*	You want clearer, more maintainable error handling for domain-specific rules.

## Conclusion

Exception handling in C# is essential for building stable, user-friendly applications. By handling errors properly, writing clean exception logic, and using custom exceptions when needed, you make your code more reliable and easier to maintain. A well-handled exception is the difference between a crash and a helpful message.

## Quick Assessment

1.	Keyword used in C# to define a block of code that always executes, whether or not an exception occurs?
 * a.	 try
 * b.	 catch
 * c.	 finally
 * d.	 throw
 
   
2. What is the purpose of exception handling in C#?
 * a. To ignore runtime errors
 * b. To detect and handle runtime errors without crashing
 * c. To make the program run faster
 * d. To avoid writing code
   
  
 3.	Which of the following is a valid reason to create a custom exception?
  * a.	To replace all built-in exceptions
  * b.	To handle syntax errors
  * c.	 To represent domain-specific errors
  * d.	To avoid using try and catch
  
   
 4. Why would you create a custom exception in C#?
  * a. To replace all built-in exceptions
  * b. To better represent specific application errors
  * c. To avoid using try-catch blocks
  * d. To improve program speed
    
   
  5. Write a C# method named *LoginUser* that takes a string parameter *username*.
  * If the username is *null* or empty, the method should throw an *ArgumentNullException* with the message: *"Username cannot be empty."*
  * Otherwise, the method should print: *"User logged in: [username]"*. 
  
  ### Answers:
  1. c
  2. b
  3. c
  4. b
