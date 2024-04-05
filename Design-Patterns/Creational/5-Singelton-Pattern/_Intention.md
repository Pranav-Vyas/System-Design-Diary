- There are some features where we want only one global object.
- Singleton is a creational design pattern that lets you ensure that a class has only one instance,
- while providing a global access point to this instance.

### Examples
#### Configuration
- suppose we want to implement dark/light theme. we can use one global instance.
- or we want to send a message to all modules that we are not working/we are closed.
- we can use one config object

- suppose we are logging and have different logger objects 1, 2, 3.
- logger 1 is working for file 1, logger 2 ---> file 2, ..........
- we want one logger object to avoid conflicts

- payment gateway function is also one more example

### Problems
- The Singleton pattern solves two problems at the same time, violating the Single Responsibility Principle:

#### Ensure that a class has just a single instance
- The most common reason for this is to control access to some shared resource—for example, a database or a file.
- Here’s how it works: imagine that you created an object,
- but after a while decided to create a new one. Instead of receiving a fresh object, you’ll get the one you already created.
- Note that this behavior is impossible to implement with a regular constructor
- since a constructor call must always return a new object by design.

#### Provide a global access point to that instance
- Just like a global variable,
- the Singleton pattern lets you access some object from anywhere in the program.
- However, it also protects that instance from being overwritten by other code.

### Implementation

- Make the default constructor private, to prevent other objects from using the new operator with the Singleton class.
- Create a static creation method that acts as a constructor. 
Under the hood, this method calls the private constructor to create an object and saves it in a static field. 
All following calls to this method return the cached object.

![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/72067130-3251-4170-924a-495b10451127)

It has 3 things
1. Static instance
2. private constructor
3. Static public getInstance

```
public static getInstance(){
  if (instance == null){
    instance = new Singleton();
  }
  return instance;
}
```
- we first check if instance exist in cache or not
- if not, we create one and return at the end
- But there is a problem
- what if two threads goes to "if" statement simultaneously?
- both will create new instance
- so to tackle this problem, we use mutext-lock

```
public static getInstance(){
  lock()
  if (instance == null){
    instance = new Singleton();
  }
  unlock()
  return instance;
}
```

- But one more problem with this
- every time we call getInstance, we create a lock irrespective of whether instance exist or not
- so we put one more if-statement

```
public static getInstance(){
  if (instance == null){
    lock()
    if (instance == null){
      instance = new Singleton();
    }
    unlock()
  }
  return instance;
}
```

- This is called **Double Checked Locking**
- Double checked locking will be used when we use **Lazy Initialization**
- Lazy inititalization is initializing object only when we need it. Follows **YAGNI**
- When we don't initialize object at the starting
- It will be created any time when we need it
- So, we have to implement **Double Checked Locking**

##### Early/Eager Initialization
- suppose we have just started the system and we only have one thread in the begining
- we don't want to implement Double Checked Locking and we want that any thread should not go inside if-statement
- so, we create one instance at the begining whether we need it or not
- by doing that we ensure that one instance always exist
- and any thread will not create new instance
- so, we don't need to use mutex-lock














