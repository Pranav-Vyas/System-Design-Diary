Strategy is a behavioral design pattern that lets you define a family of algorithms, put each of them into a separate class, and make their objects interchangeable.
### Problems
#### Uber
- suppose you have tier 1, tier 2, tier 3 cities.
- in order to find the best ride, you have different algorithms of finding the driver
- in tier 1, you may want to find based on location, rating, route, etc.
- in tier 3, you may only want to find based on location
- How would you implement?

#### Payment
- suppose you want to offer different payment options to make transaction
  1. Credit card (cc)
  2. Paypal
  3. crypto
- user will select the payment method and you will use the respective algorithm
- How to implement?
- we might think of using if-else statements to decide algos conditionaly
```
PaymentProcessor {
  void processPayment(amount, method){
    if (method == "CC"){
      // .....
    } else if (method == "paypal"){
      // .....
    } else if (method == "crypto"){
      // .....
    }
  }
}
```
- now this is violating SOLID princ.
- So, we use strategy pattern
- extract all algo. into seperate classes called strategies
- The original class, called context, must have a field for storing a reference to one of the strategies.
- The context isn’t responsible for selecting an appropriate algorithm for the job.
- Instead, the client passes the desired strategy to the context.
- It works with all strategies through the same generic interface, which only exposes a single method for triggering the algorithm encapsulated within the selected strategy.
- This way the context becomes independent of concrete strategies, so you can add new algorithms or modify existing ones without changing the code of the context or other strategies.

#### Uber
- Strategy ---> Interface
- concreate strategy ----> rating based, location based
- strategy will have execute()
- Driver Allocation Manager(DAM) ----has a----> strategy [composition]

#### Payment
- concreate strategy ----> credit card, paypal, crypto
- strategy will have makePayment()
- Payment Processor ---- has a -----> strategy

![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/985951bf-fd81-44b3-81a8-cb45a4c5e708)

#### Some points
- we are encapsulating the family of algos.
- allowing runtime behaviour
- Context is the object where we are doing the process
- we are using composition










