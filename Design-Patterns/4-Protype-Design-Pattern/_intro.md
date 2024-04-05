## Intent
- it says that cloning the object is the responsibility of the class itself of which the object we are trying to clone
- Say you have an object, and you want to create an exact copy of it. How would you do it?
- First, you have to create a new object of the same class.
- Then you have to go through all the fields of the original object and copy their values over to the new object.
- Nice! But there’s a catch.
- Not all objects can be copied that way because some of the object’s fields may be private and not visible from outside of the object itself.
- Below method is dangerous
```
ProductPrototype product1 = new Product("Laptop", 999.99);
ProductPrototype product2 = new Product();
product2.name = product1.name;
product2.price = product1.price;
```

## Solution
- Every class which has to implemente a clone method should follow a interface.
- This Interface has a ```clone``` method.
- Cloning procedure is almost similar for all classes.
- This avoid naming conflict in classes.
- Because class can use different names like doClone, clone, getClone,...

![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/d57935f7-1cfc-4eb8-aeaa-67eb7fe6e961)
