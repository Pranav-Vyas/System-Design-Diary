Observer is a behavioral design pattern that lets you define a subscription mechanism to notify multiple objects about any events that happen to the object they’re observing.

### Examples
#### Weather app
- it has 3 kinds of displays ---> digital, analog, graphical display
- whenever the weather changes, our displays in all three should change

#### Traffic light
- red, yellow, green, pedestrian
- after the timer ends, a change should be there in required lights

### There are two things here
1. Subject / Publisher ---> when there is a change in state of subject
2. Observer / Subscriber ---> I will take action acordingly

#### Zomato
- when an order is placed
- we need to notify restaurant, customer, delivery driver, call center
- order ----> subject | customer -----> observer
- So we are changing the behaviour of observer.

<br>

- one subject ---> many observers
- one to many relationship
- it is aggregation

<br>

- to add a new observer, we register/attach/subscribe
- to remove, we unregister/detach/unsubscribe
- when state change happen in subject, we call notify() to notify the observers
- subject has update()
- notify() is also called update()
- both subject and observer has different update()
- subject has notify() to let observer know that a change has happened
- in this notification, they call each observer's update() to perform their specific actions

<br>

![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/ecb6c465-fa9e-4506-8781-6ae76387c9e7)

<br>

![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/09eb211d-c13e-4fb0-9a71-a209d3b292ae)





