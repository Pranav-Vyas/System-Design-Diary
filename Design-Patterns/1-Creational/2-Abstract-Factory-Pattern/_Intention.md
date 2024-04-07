- Here, we are creating factory of factories.
- as we are increasing the layers of products, we have to create sub factories
- A factory is a class that returns products of a particular kind. For example, the ModernFurnitureFactory can only create ModernChair, ModernSofa and ModernCoffeeTable objects.

### Problem
Imagine that you’re creating a furniture shop simulator. Your code consists of classes that represent:

1. A family of related products, say: Chair + Sofa + CoffeeTable.

2. Several variants of this family. For example, products Chair + Sofa + CoffeeTable are available in these variants: Modern, Victorian, ArtDeco.

![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/e7c1cee4-da88-47f5-8538-100490abdfd3)

- You need a way to create individual furniture objects so that they match other objects of the same family. Customers get quite mad when they receive non-matching furniture.

![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/a08392af-0b6a-45e6-be0c-700727a0e287)

### Other examples

![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/0b509a68-d493-4204-808d-1bcd172096a0)

![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/00017f49-3e09-4d56-9b8f-3ea45a558480)

![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/3c5a14fe-75d2-4d71-bfe1-bd9f1b0d296a)
