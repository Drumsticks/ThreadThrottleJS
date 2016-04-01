# Thread Throttle JS
Queues up multiple executions of a function and throttles a set amount of simultaneous executions.  
=========
Demo: http://plnkr.co/edit/hBrLJzVmCT7Mi45aIMl1?p=preview

For example: A function has been executed 10 times and the set throttle limit is 2.  
Therefore, only 2 out of the 10 functions queued to run can execute at a time.  
The other 8 remain in a queue.  
As one function finishes executing, the next function in the queue takes its place and gets executed.  
The number of simultaneous executions remain at 2 at a time until all 10 functions have been executed.

Simply initiate the following code to start the process:

threadThrottle = threadThrottle.threadThrottle(thread);
threadThrottle.setFunctionName(simulatedSuccessResponse);
threadThrottle.setLimit(2);
threadThrottle.setQueue(5);
threadThrottle.start();

function YourFunction() {
    ...
    Your Code
    ...
    
    threadThrottle.complete();

    return ...
}

DEFINITIONS:
--------- 
threadThrottle = threadThrottle(thread); - Initiate and instantiate the threadThrottle object.

threadThrottle.setFunctionName(YourFunction) - Set the name of your function. Please note that there are no quotes around your function name.

threadThrottle.setLimit(n) - Set the throttle limit to a number (n) of simultaneous threads to be executed at a time.

threadThrottle.setQueue(n) - Set the Queue to a number (n) of functions to be executed.

threadThrottle.start() - Start the execution process! This only needs to be fired once to begin the entire process.

threadThrottle.complete() - Once your function has completed, at the bottom of your function, tell threadThrottle that the process has completed.

##############
By Ryan Hinton
© Copyright 2016 
