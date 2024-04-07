- Adapter is a structural design pattern that allows objects with incompatible interfaces to collaborate.

### Example
- suppose we have data in xml and 
- we have JsonAalyticsTool(3rd party tool) which accepts data in json
- we will add another class in between
- it will take data in xml and convert it in json. This is called Adapter
- to make it generic, we create an Interface having a request()
- concreate adapter will implement Adapter Interface
- 3rd party took has a method analizeData() to read json
- after converting xml to json, we need to call tool.analizeData() inside concreate adapter

![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/abb3ec7d-bfa7-4490-adfc-4f133a02a262)

##### Object adapter pattern
- to achieve that, we can make a "has-a" relationship between adapter and tool
- adapter has a field tool and it can call analizeData()
- the tool is known as adaptee.
- when the tool(adaptee) is member in class adapter, we call it as object adapter.

##### Class adapter pattern (not important)
- we can have "is-a" relationship between adapter and adaptee(tool).
- adapter can inherite from adaptee so that it can use methods like analizeData() of adaptee.

![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/0c98bc12-6d70-48e2-a396-19feaa57b28f)


