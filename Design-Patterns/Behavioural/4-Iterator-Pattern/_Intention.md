- Iterator is a behavioral design pattern that lets you traverse elements of a collection without exposing its underlying representation (list, stack, tree, etc.).
- collections are data structures to store elements like list, stack, tree...
- but we need some way to iterate those elements
- clients does not need to know how you store elements in it
- he just wants to iterate
- The main idea of the Iterator pattern is to extract the traversal behavior of a collection into a separate object called an iterator.

#### Music System
- you play next song based on singer, rating, alphabetical, popularity, etc.

#### Tree implementation
- you can iterate next node based on preorder, inorder, postorder,...
<br>
- As a user, you want to only iterate
- you don't need to know on what basis it is iterating
- as a developer, you want to make the process generic
- collection contains all elements(songs, nodes, videos, etc.) to be iterated
- iterator has list of products called collections
- it has first product, hasNext() to check if next product exists, next() method to move forward to next product
- next() can be implemented in any way depending upon buisness needs
- in the below diagram, getNext means next(), hasMore means hasNext()

![image](https://github.com/Pranav-Vyas/System-Design-Diary/assets/86347266/45590f2c-a56f-48ae-b134-7d05b7d5dfbb)
