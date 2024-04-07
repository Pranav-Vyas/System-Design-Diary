- Facade is a structural design pattern that provides a simplified interface to a library, a framework, or any other complex set of classes.
- Used when we have to hide te system complexity from the client
- A facade is a class that provides a simple interface to a complex subsystem which contains lots of moving parts.
- A facade might provide limited functionality in comparison to working with the subsystem directly.
- However, it includes only those features that clients really care about.

Having a facade is handy when you need to integrate your app with a sophisticated library that has dozens of features, but you just need a tiny bit of its functionality.
#### Note
- we should not force the client to use facade
- client can also directly interact with system if he wants

### Example - creating order
- suppose you want to create order
- creating and placing order has several steps
  1. getProductDetails()
  2. makePayment()
  3. generateInvoice()
  4. sendNotification()
- if client directly iteract with system, it has to follow all these steps in specific order
- what if in future there are any changes in these methods or if new step is introduced
- client will also have to follow the changes
- so we introduce a facade layer in between
- facade will have a method createOrder(), which will execute all the above steps in the correct sequence
<br>

![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/52d4d394-0aa0-454b-8160-36a3cd27cba3)
![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/4ab33df7-83e6-46df-b10c-ab8729db8392)

## UML

![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/a46fa691-ff33-4823-828a-388c17624df3)

![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/749faa5f-5570-411f-9810-a912cd4e08ca)

## Note
- An app can have multiple facades using each other
- facade 1 -----> facade 2 ----------> facade 3
![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/9525073f-733d-415c-ba61-7cdc87a5644b)


