- Decorator is a structural design pattern that lets you attach new behaviors to objects by placing these objects inside special wrapper objects that contain the behaviors.

#### Example 1
- suppose you have pizza and burger
- you have toppings like extra cheeze, extra sauce, extra onion, etc.
- you should be able to add any no of toppings on pizza and burger in run time
- and after adding topping, it will still be a pizza

#### Solution
- we have interface FoodItem
- we have concreate class Pizza and burger implementing FoodItem
- we have Decorator Interface implementing FoodItem because they are also food items
- we have classes of decorators like ExtraCheezeDecorator, ExtraSauceDecorator implementing Decorator 
- all the decorators will have food item like pizza and burger
- so decorator has a food item because they have a member in them
- and also decorator is a food item because they are implementing FoodItem Interface
- functionality of adding decorator on pizza will be inside decorator and it will return the new food item

![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/c2361e17-6020-4005-80c2-8df498266fc6)

### Real world analogy
Wearing clothes is an example of using decorators. When you’re cold, you wrap yourself in a sweater. If you’re still cold with a sweater, you can wear a jacket on top. If it’s raining, you can put on a raincoat. All of these garments “extend” your basic behavior but aren’t part of you, and you can easily take off any piece of clothing whenever you don’t need it.

### UML
![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/b6afe9c2-a86c-46dd-a357-e0ab93b1ab28)
