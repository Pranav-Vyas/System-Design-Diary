- Bridge is a structural design pattern that lets you split a large class or a set of closely related classes into two separate hierarchies—abstraction and implementation—which can be developed independently of each other.

## Example 1 - Shape and Colors
- You have a geometric **Shape** class with a pair of subclasses-
  1. Circle
  2. Square
- You want to give colors to these classes, so you plan to create **Red** and **Blue** subclasses.
- Then you will have 4 classes-
  1. RedCircle
  2. RedSquare
  3. BlueCircle
  4. ClueSquare
<br>

![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/37580bba-5e55-46b1-b339-37594fdbf2a4)

<br>
- Adding new shape types and colors to the hierarchy will grow it exponentially. For example, to add a triangle shape you’d need to introduce two subclasses, one for each color.
- And after that, adding a new color would require creating three subclasses, one for each shape type.
- This problem occurs because we’re trying to extend the shape classes in two independent dimensions: by form and by color. 

#### Solution
- To solve it, you extract one of the dimensions into a separate class hierarchy, so that the original classes will reference an object of the new hierarchy, instead of having all of its state and behaviors within one class.
<br>

![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/e1732c57-46ff-4bfe-9404-4e80688f0bd2)

<br>
## Example 2 - Organism and breathing
- We will address a new issue in this example
- Suppose you have dog, fish and tree --> each having their seperate breathing process
- If you want to introduce a fourth breathing process, you will need to introduce a organism which uses that process
- See below picture for understanding-
<br>

![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/4ae54c82-dad5-4930-94d1-14fdb06e5da5)

<br>
- You can solve it by creating a seprate heirarchy of breathing process and reference them in organism class
<br>

![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/273c7d79-7389-4832-8143-bc0de6af5a7f)

## Example 3
- Uber has two services ---> Uber eats && Uber rides
- both uses navigation sytems
- navigation system has two types ----> Apple maps && Google maps
- we want to have common implementation for uber eats and rides

![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/6430eca3-82a1-4131-9490-a6da31d624de)


## Example 4
- vehicle has Bus and Bike
- we have workshop, workshop has produce and asemble
- each vehicle is using workshop
- Bus has to be produced and assembled
- similarily bike also be has to be produced and assembled

## Example 5
- Uber has two services ---> Uber eats && Uber rides
- payment ---> paypal, paytm, gpay
- each uber service should be able to use all three payment services



## UML
![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/5f1d3b3e-1b5c-41b5-9494-84b0906791b8)

## Abstraction and Implementation

- Abstraction (also called interface) is a high-level control layer for some entity. This layer isn’t supposed to do any real work on its own. It should delegate the work to the implementation layer (also called platform).

- Note that we’re not talking about interfaces or abstract classes from your programming language. These aren’t the same things.

- When talking about real applications, the abstraction can be represented by a graphical user interface (GUI), and the implementation could be the underlying operating system code (API) which the GUI layer calls in response to user interactions.

- Generally speaking, you can extend such an app in two independent directions:

- Have several different GUIs (for instance, tailored for regular customers or admins).
Support several different APIs (for example, to be able to launch the app under Windows, Linux, and macOS).
In a worst-case scenario, this app might look like a giant spaghetti bowl, where hundreds of conditionals connect different types of GUI with various APIs all over the code.

- You can bring order to this chaos by extracting the code related to specific interface-platform combinations into separate classes. However, soon you’ll discover that there are lots of these classes. The class hierarchy will grow exponentially because adding a new GUI or supporting a different API would require creating more and more classes.

- Let’s try to solve this issue with the Bridge pattern. It suggests that we divide the classes into two hierarchies:

- Abstraction: the GUI layer of the app.
- Implementation: the operating systems’ APIs.

- The abstraction object controls the appearance of the app, delegating the actual work to the linked implementation object. Different implementations are interchangeable as long as they follow a common interface, enabling the same GUI to work under Windows and Linux.
<br>

![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/5e0f71b1-90d9-47de-bdf5-0a032327d949)

