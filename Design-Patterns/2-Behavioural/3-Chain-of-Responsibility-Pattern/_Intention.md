- Chain of Responsibility is a behavioral design pattern that lets you pass requests along a chain of handlers.
- Upon receiving a request, each handler decides either to process the request or to pass it to the next handler in the chain.
- Next handler can be declared at the starting or can be decided at runtime also.

![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/28343d2e-1f51-42b8-aae9-6d5c5b2d6740)

- Also after a handler process a request, it can also send the request to next handler.
- Depending upon our implementation, we can decide whether we want all handlers to get a chance to process request
- or only first handler which proccessed will send the response and breaks the chain
- for example in ordering system, you want to put authentication, authorization, validation, caching, etc. before use is able to order.

![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/d99e0558-ea4b-41a7-a42b-c0ccbec64fb8)

- In this system putting them in a chain is a better idea.
- each handler will have reference to next handler.
- At runtime we can decide which way to go.

![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/7000fc71-c273-4edc-af4a-b29657adefab)

- This can also be implemented in payment system
- if payment succeed ----> go ahead like placing order, etc.
- if payment failed ----> go to notification manager
- on the fly we are deciding which way to go

<br>

- But in implementation of ATM Machine, if a handler processes a request,
- we may not want to send the request to next handler
- suppose we have handlers which handles different amount withrawals
- h1 --> 100, h2 ---> 200, h3 --> 300 and user wants to withdraw 200 Rs
- req. goes to h1, it cannot process, so it sends to next handler h2
- h2 can process, so it handles it and does not send to next handler and breaks the chain
- in this we don't have to decide the next handler at runtime

![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/64f24d6d-3d44-4d55-a235-a897bb872815)

### Application Uses
- ATM Machine
- Design logger
- Vending machine

