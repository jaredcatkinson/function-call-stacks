# Function Call Stack Repository
This project is meant to serve as a respository for Windows API Function Call Stacks. A Function Call Stack is a representation of the relationship between explicitly called API functions and the implicitly called functions that occur in the background.
For a more detailed explanation of the Function Call Stack idea, we recommend reading my [Understanding the Function Call Stack](https://posts.specterops.io/understanding-the-function-call-stack-f08b5341efa4) blog post.
As an example of a Function Call Stack for the kernel32!OpenProcess function we see the follow:
kernel32!OpenProcess
api-ms-win-core-processthreads-l1-1-0!OpenProcess
kernelbase!OpenProcess
ntdll!NtOpenProcess
syscall!NtOpenProcess

While it is nice to have a picture of these relationships in one's head, we've found that it is useful to display them visually. This allows for the connection of Function Call Stacks in the context of a tool implementation.
To do this visualization, we prefer to use [APC Jones' Arrow Tool](https://arrows.app) application. One issue we've run into as we've built graphs for numerous tools is the redundancy in the appearance of functions. Many malware samples are built on the same functions that have already been analyzed.
This project stores the json representation of each function, independent of the Tool Graph that it was first analyzed within. This allows the use of the visualization application's import feature to more easily build new Tool Graphs.
