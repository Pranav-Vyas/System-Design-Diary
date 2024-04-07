Template Method is a behavioral design pattern that defines the skeleton of an algorithm in the superclass but lets subclasses override specific steps of the algorithm without changing its structure.

#### Amazon
- suppose in amazon we have
  1. local delivery system
  2. International delivery system
- local delivery system has
  1. verify order
  2. assign delivery partner
  3. track delivery
- international delivery system also want to implement the same
- international delivery system should have atleast function of local sytem
- it can have more as well
- we can make a template ---> OrderProcessionTemplate
- OrderProcessionTemplate has processOrder()
- processOrder() has {
	verifyOrder()
	assignDeliveryAgent()
	trackDelivery()
}
- OrderProcessionTemplate also has following abstract methods
1. verifyOrder()
2. assignDeliveryAgent()
3. trackDelivery() 
- every class implementing OrderProcessionTemplate has to have these 3 functions
- child class can override these 3 methods according to their needs
- but it cannot override processOrder()
- processOrder() should work same in every child class
- Concrete Classes can override all of the steps, but not the template method itself.
- here the steps are verifyOrder, trackDelivery, etc. and template is processOrder()

![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/f22f8d6f-345a-4d94-ba91-9d5da6fa839d)


#### Another example
- Imagine that you’re creating a data mining application that analyzes corporate documents.
- Users feed the app documents in various formats (PDF, DOC, CSV), and
- it tries to extract meaningful data from these docs in a uniform format.
- The first version of the app could work only with DOC files.
- In the following version, it was able to support CSV files.
- A month later, you “taught” it to extract data from PDF files.
- a lot of duplicate code is here
- the code for dealing with various data formats was entirely different in all classes,
- but the code for data processing and analysis is almost identical.
- Wouldn’t it be great to get rid of the code duplication, leaving the algorithm structure intact?
<br>
The Template Method pattern suggests that you break down an algorithm into a series of steps, turn these steps into methods, and put a series of calls to these methods inside a single template method. The steps may either be abstract, or have some default implementation. To use the algorithm, the client is supposed to provide its own subclass, implement all abstract steps, and override some of the optional ones if needed (but not the template method itself).













