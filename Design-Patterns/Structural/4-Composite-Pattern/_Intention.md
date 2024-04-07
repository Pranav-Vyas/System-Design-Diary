- Also known as Object tree
- Composite is a structural design pattern that lets you compose objects into tree structures and then work with these structures as if they were individual objects.
- Using the Composite pattern makes sense only when the core model of your app can be represented as a tree.
<br>

![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/efe70eba-2d79-40cf-8497-06e40718f2f1)

<br>

### File system
- suppose we have a heirarchy or tree of files and folder
- a node can either be a file or a folder
- leaf node is a node which is last and a composite node can have further children
- a node will be called component which can be a file/leaf or composite/directory
- a composite is a container/list of components/nodes
- every node (file or folder) has execute()
- this execute() can be:
	1. getSize()
	2. getDate()
	3. modified()
	4. addChild()
	5. removeChild()
	etc.
- execute() will be in both leaf and composite
- in case of leaf/file, it can directly execute getSize() to calc. its size
- in case of composite, it will have to get the sizes of all its children to calc. its own size
Relationship
- composite "has a" list of components [can be aggregation or composition]
<br>

![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/6230e506-0b15-4dfd-97c2-ec95d61f54fc)


### Employees
- in a tree of emp. each node can be either employee, team or department
- employee is leaf node
- and department is a composite which contains teams
- a team can further contains employees
- a node can have methods like
  1. getInfo()
  2. getSalary()
- we are treating employee, department and team as same
 
<br>

![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/3620b4ef-1b0a-45bc-b461-0b558cebc852)


## Structure
![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/c795a5f6-f35e-41ab-ad7a-fa534912b741)

## Pseudocode
![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/07c5c26f-ac8f-4752-9237-71bb5675a0c4)



