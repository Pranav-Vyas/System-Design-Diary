- Proxy is a structural design pattern that lets you provide a substitute or placeholder for another object. A proxy controls access to the original object, allowing you to perform something either before or after the request gets through to the original object.

![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/c8e311fb-dd6d-4e66-892e-2ff4f66dc6cf)

![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/e3656f88-2d48-4181-8657-f9bab4029d92)

<br>

- A credit card is a proxy for a bank account, which is a proxy for a bundle of cash. Both implement the same interface: they can be used for making a payment.
<br>

![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/f677549c-a32c-445e-81b5-facfbd5081ac)

<br>
- when client deals with real object, we introduce a proxy object in between
- request goes through proxy

### Uses
- Caching: proxy decide if data is in cache or not
- Access Restriction
- Pre-processing/Post-processing: when we want to do something before and after a work like logging, publishing,etc.

- suppose we have an emplyoee table interface EmpDao which has
	- create()
	- delete()
	- get()
- then we have concreate class EmpDaoImpl
- and we have a proxy class EmpDaoProxy implementing the same interface
- proxy also has object of EmpDaoImpl and it also has some validation methods
- client will interact with proxy and proxy will validate the request and uses EmpDaoImpl to perform operations in database
- we can have multiple proxies also

![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/1c8cf38c-0389-4344-8ffa-fa1f81ec2c88)
![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/a9b3dbd3-36de-4d42-900d-cdc1fe075d9c)
![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/119cbe99-dbdf-42d9-bc36-c92bcf200439)
![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/f6b6e6ff-75f6-46d2-9bf8-36ec90b0380b)


