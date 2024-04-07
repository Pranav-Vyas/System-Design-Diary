- When we want to deal with object creation
- We are abstracting the creation process
- Factory is a class that will create objects

## Examples
#### Car
- SUV
- Luxury
- Economy

#### Product
- electronic
- books
- clothing

#### Hotel room
- single
- double
- tripple

#### Order
- dine-in
- takeout
- delivery

#### Video
- movie
- tv show
- documentary

#### Book
- fictional
- non fictional
### Points to be noted
- it is used when we want to create objects with similar behaviour
- but creation process of objects can be different
- creation process of takeout order can be different from that of delivery
- we want to encapsulate object creation process
- client does not need to know how you have implemented the classes
- client only wants a factory class which can create any object he wants
- the factory takes object name and creates an object
- we get runtime benefit. we take input in runtime and based on input we pass argument in factory
- if creation process is diff. we have diff. functions for creating diff. objects
- we may use if-else condition to check which object client wants to create
- we will have a static method in factory which will create required object, so that we won't have to create an object of factory
<br>

![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/0719f423-815e-4176-80db-3e64b5c5e12b)

<br>

![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/3650284b-82ba-44dd-a07f-1a6e66d572ca)

#### Note
- It is violating open/closed principle, that's why we have factory method








