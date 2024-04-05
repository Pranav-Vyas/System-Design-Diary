## Problem addressed
- so many parameters in constructors
## Example
- suppose we want to create a desktop.
- desktops --> dell, hp, sony
- different steps to create desktop - ram, rom, processor,...
- different desktop can have different config. - config. is different, creation is complex
- construction process is same, so we created Builder interface
- Builder interface with methods build ram(), build processor(), build monitor(), ...
- whichever class implements Builder will have to implement these methods.
- interface sets template
- class who implements interface is called concrete class
- so many parameters to pass in constructor that's why Builder Interface.
- Concrete builders ---> Dell Destop Builder, HP Desktop builder and Sony Desk. Buider
- In Director, we will pass concrete builder
- inside director, we will call methods
- director knows the construction process in a sequence. In future if we want to change the steps, we can change in director and it will be reflected everywhere

#### Suppose we want to build a house
- we have to build floor, ceiling, kitchen, window, ...
- we have diff. types of houses like marble house, wooden house, ...
- in every house construction process is same and but conf. is diff.
- House is the product, House Builder is interface
- Civil engineer is director who takes builder as parameter and calls methods in s sequence.
- methods like getProduct can be in director also
- director.getProduct() will return builder.getProduct()

#### Suppose we have a word doc
- we want to convert it into diff. formats like text, pdf, graphic, ...
- Builder will have Build para, Build highlighted txt, Build bold char
