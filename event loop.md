Event loop is a mechanism by which it is able to manage concurrency, and execute handle I/O tasks even though its a single threaded system. 

### How the Event Loop Works:

1. **Call Stack:**
    
    - This is where JavaScript executes function calls. When a function is called, it is added (pushed) to the stack. When the function returns, it is removed (popped) from the stack.
2. **Web APIs / Node APIs:**
    
    - In the browser, Web APIs are provided by the browser environment (like DOM events, AJAX, setTimeout, etc.). In Node.js, similar functionalities are provided by Node APIs. These APIs can handle operations asynchronously.
3. **Event Queue:**
    
    - When an asynchronous operation completes, the callback function associated with that operation is placed in the event queue (also known as the callback queue).
4. **The Loop:**
    
    - The event loop constantly checks the [[call stack]]. If the call stack is empty (i.e., all currently running synchronous code has finished executing), it will take the first event from the queue and push it onto the call stack, which effectively runs the callback associated with the asynchronous event.
5. **Continual Checking:**
    
    - This proce ss repeats continuously, with the [[event loop]] constantly checking the call stack and pushing callbacks from the event queue to the call stack as it becomes available.

