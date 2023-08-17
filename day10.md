# day10 2023-8-17
## classes and prototype section :
- video#1:why classes and prototypes are important to learn as a developer, and what will be learned in the upcoming sections. The core idea of development is covered to understand how code should be structured, and how developers write code to be easy to reason about, easy to add new functionality, and efficient. The argument is made that object oriented programming is all of these things.
- video#2:a scenario in order to make the argument for storing data and functionality together in one place. Dot notation is introduced as a way to allow users to assign and access elements in an object, including functions.
- video#3:The built-in function Object.create() is introduced as a way to create null objects that provide more control on the object. The concept of the generalized function to produce objects is introduced.
- video#4: an examples of a function that is generalized to accept properties that are assigned to a new object and returned. After demonstrating how easy it is to reason about and utilize in a codebase, Will makes the argument that the approach is unusable.
- video#5:the prototype chain, or __proto__ as a way to access functions that were set when Object.create() is used to instantiate an object.
- video#6: an example of a factory function that utilizes Object.create() with the argument of a function with desired functionality to create an object with a prototypal link to the functionality.
- video#7:Will answers questions from the audience regarding whether only functions can be referenced on the prototypal reference chain, and a clarification as to whether an Object.create() argument is always the __proto__ property. How to visually see the __proto__ property in the console is briefly covered. The execution context created when a function called on the prototypal reference chain is diagrammed, and it's demonstrated how the implicit parameter set in the execution context allows the function work with individual objects despite being shared.
- video#8: the hasOwnProperty method to determine whether an object has a specific property to clarify where the property is stored.
- video#9: introduces the use case where a function (or several) is created on a function store, and the question is posed as to what the this keyword gets assigned to when nested. The call and apply method are introduced as a way to take control of what this gets assigned to, which is different than more antiquated methods.
- video#10: diagrams an example that demonstrates that the normal this keyword rules are overridden when used with arrow functions, because of when arrow function contents are evaluated. A question is asked about what would happen if a method on an object is defined as an arrow function.
- video#11: diagrams an example that demonstrates that the normal this keyword rules are overridden when used with arrow functions, because of when arrow function contents are evaluated. A question is asked about what would happen if a method on an object is defined as an arrow function.
- video#12:Will reviews the last few sections, and how they relate to the standard way of object creation in the proceeding sections.
- video#13:Will introduces the new keyword that takes advantage of JavaScript's object-oriented system to automate a factory function.
- video#14:Will diagrams what the new keyword is doing under the hood when it's utilized to instantiate a new object. It's demonstrated how, through accessing the prototype object, it can automate much of the process that was demonstrated previously in the course.
- video#15:Will introduces the idiomatic way to define when the new keyword needs to be used to instantiate an object. In addition, the syntactic sugar of the class keyword is discussed, and how it really is no different under the hood than what was demonstrated in previous sections.



