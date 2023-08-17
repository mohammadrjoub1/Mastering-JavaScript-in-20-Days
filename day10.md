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
# deliverables:
## question1:
const duck = {
  type: "bird",
  sound: "quack",
  color: "white",
  hasWings: true,
  legs: 2,
  canSwim: true,
  fly: function() {
    console.log("The duck is flying!");
  }
};

console.log(duck.type);     // Output: bird
console.log(duck.sound);    // Output: quack
console.log(duck.color);    // Output: white
console.log(duck.hasWings); // Output: true
console.log(duck.legs);     // Output: 2
console.log(duck.canSwim);  // Output: true

duck.fly(); // Output: The duck is flying!
## question2:
let dog = {
  name: "Buddy",
  breed: "Golden Retriever"
};

console.log(dog.name);   // Output: Buddy
console.log(dog.breed);  // Output: Golden Retriever
## question3:
let dog = {
  name: "Buddy",
  breed: "Golden Retriever",
  sayLegs: function() {
    return "This dog has 4 legs.";
  }
};

console.log(dog.sayLegs()); // Output: This dog has 4 legs.
## question#4:
let dog = {
  name: "Buddy",
  breed: "Golden Retriever",
  sayLegs: function() {
    return "This dog has 4 legs.";
  }
};

console.log(dog.sayLegs()); // Output: This dog has 4 legs.
## question#5:
function Dog() {
  this.name = "Buddy";
  this.color = "brown";
  this.numLegs = 4;
}
## question#6:

function Dog() {
  this.name = "Buddy";
  this.color = "brown";
  this.numLegs = 4;
}

let hound = new Dog();
## question#7:
function Dog(name, color) {
  this.name = name;
  this.color = color;
  this.numLegs = 4;
}

let terrier = new Dog("Max", "black");
## question#8:
function House(numBedrooms) {
  this.numBedrooms = numBedrooms;
}

let myHouse = new House(3);

console.log(myHouse instanceof House); // Output: true

## question#9:
function Bird(name) {
  this.name = name;
  this.numLegs = 2;
}

let duck = new Bird("Donald");
let canary = new Bird("Tweety");

let ownProps = [];

for (let property in canary) {
  if (canary.hasOwnProperty(property)) {
    ownProps.push(property);
  }
}

console.log(ownProps); // Output: ["name", "numLegs"]

## question#10:
function Dog(name, color) {
  this.name = name;
  this.color = color;
}

Dog.prototype.numLegs = 4;

let terrier = new Dog("Max", "black");

console.log(terrier.numLegs); // Output: 4

## question#11:
function Dog(name, color) {
  this.name = name;
  this.color = color;
}

Dog.prototype.numLegs = 4;

let beagle = new Dog("Snoopy", "white");

let ownProps = [];
let prototypeProps = [];

for (let property in beagle) {
  if (beagle.hasOwnProperty(property)) {
    ownProps.push(property);
  } else {
    prototypeProps.push(property);
  }
}

console.log(ownProps);       // Output: ["name", "color"]
console.log(prototypeProps); // Output: ["numLegs"]



## question#12:
function Dog(name, color) {
  this.name = name;
  this.color = color;
}

let beagle = new Dog("Snoopy", "white");

function joinDogFraternity(candidate) {
  return candidate.constructor === Dog;
}

console.log(joinDogFraternity(beagle)); // Output: true
## question#13:
function Dog(name, color) {
  this.name = name;
  this.color = color;
}

Dog.prototype = {
  numLegs: 4,
  eat: function() {
    console.log("nom nom nom");
  },
  describe: function() {
    console.log("My name is " + this.name);
  }
};

let terrier = new Dog("Max", "black");

terrier.eat();       // Output: nom nom nom
terrier.describe();  // Output: My name is Max
console.log(terrier.numLegs); // Output: 4
## question#14:
function Dog(name, color) {
  this.name = name;
  this.color = color;
}

Dog.prototype = {
  constructor: Dog, // Add this line to set the constructor property
  numLegs: 4,
  eat: function() {
    console.log("nom nom nom");
  },
  describe: function() {
    console.log("My name is " + this.name);
  }
};

let terrier = new Dog("Max", "black");

console.log(terrier.constructor === Dog); // Output: true
## question#15:
function Dog(name, color) {
  this.name = name;
  this.color = color;
}

Dog.prototype = {
  constructor: Dog,
  numLegs: 4,
  eat: function() {
    console.log("nom nom nom");
  },
  describe: function() {
    console.log("My name is " + this.name);
  }
};

let beagle = new Dog("Snoopy", "white");

console.log(Dog.prototype.isPrototypeOf(beagle)); // Output: true

## question#16:

function Bird(name) {
  this.name = name;
}

let duck = new Bird("Donald");

console.log(Object.prototype.isPrototypeOf(Bird.prototype)); // Output: true
console.log(Object.prototype.isPrototypeOf(duck)); // Output: true
console.log(duck.hasOwnProperty("name")); // Output: true

## question#17:
function Animal() { }

Animal.prototype = {
  constructor: Animal,
  eat: function() {
    console.log("nom nom nom");
  }
};

function Bird(name) {
  this.name = name;
}

Bird.prototype = Object.create(Animal.prototype);
Bird.prototype.constructor = Bird;

function Dog(name) {
  this.name = name;
}

Dog.prototype = Object.create(Animal.prototype);
Dog.prototype.constructor = Dog;

let duck = new Bird("Donald");
let beagle = new Dog("Snoopy");

duck.eat();  // Output: nom nom nom
beagle.eat(); // Output: nom nom nom

## question#18:
function Animal() { }
Animal.prototype.eat = function() {
  console.log("nom nom nom");
};

let duck = Object.create(Animal.prototype);
let beagle = Object.create(Animal.prototype);

duck.eat();   // Output: nom nom nom
console.log(duck instanceof Animal);  // Output: true

beagle.eat(); // Output: nom nom nom
console.log(beagle instanceof Animal); // Output: true

## question#19:
function Animal() { }
Animal.prototype.eat = function() {
  console.log("nom nom nom");
};

function Dog(name) {
  this.name = name;
}

// Set the prototype of Dog to be an instance of Animal
Dog.prototype = Object.create(Animal.prototype);
Dog.prototype.constructor = Dog;

let beagle = new Dog("Snoopy");

beagle.eat();  // Output: nom nom nom
console.log(beagle instanceof Animal);  // Output: true

## question#20:
function Animal() { }

function Bird(name) {
  this.name = name;
}
Bird.prototype = Object.create(Animal.prototype);
Bird.prototype.constructor = Bird;

function Dog(name) {
  this.name = name;
}
Dog.prototype = Object.create(Animal.prototype);
Dog.prototype.constructor = Dog;

let duck = new Bird("Donald");
let beagle = new Dog("Snoopy");

console.log(duck.constructor);  // Output: [Function: Bird]
console.log(beagle.constructor);  // Output: [Function: Dog]


## question#21:
function Animal() { }

Animal.prototype.eat = function() {
  console.log("nom nom nom");
};

function Dog() { }

// Set up inheritance from Animal
Dog.prototype = Object.create(Animal.prototype);
Dog.prototype.constructor = Dog;

// Add bark() method to Dog's prototype
Dog.prototype.bark = function() {
  console.log("Woof!");
};

let beagle = new Dog();

beagle.eat();  // Output: nom nom nom
beagle.bark(); // Output: Woof!


## question#22:
function Bird() { }

Bird.prototype.fly = function() {
  return "I'm flying!";
};

function Penguin() { }
Penguin.prototype = Object.create(Bird.prototype);
Penguin.prototype.constructor = Penguin;

// Override the fly() method for Penguin
Penguin.prototype.fly = function() {
  return "Alas, this is a flightless bird.";
};

let penguin = new Penguin();
console.log(penguin.fly()); // Output: Alas, this is a flightless bird.

## question#23:
let glideMixin = function(obj) {
  obj.glide = function() {
    console.log("Gliding smoothly!");
  };
};

let bird = {
  name: "Donald",
  numLegs: 2
};

let boat = {
  name: "Speedy",
  type: "sailboat"
};

glideMixin(bird);
glideMixin(boat);

bird.glide();  // Output: Gliding smoothly!
boat.glide();  // Output: Gliding smoothly!


## question#24:
let funModule = (function() {
  return {
    isCuteMixin: function(obj) {
      obj.isCute = function() {
        return true;
      };
    },
    singMixin: function(obj) {
      obj.sing = function() {
        console.log("Singing to the moon!");
      };
    }
  };
})();

let cat = {};
let dog = {};

funModule.isCuteMixin(cat);
funModule.singMixin(dog);

console.log(cat.isCute()); // Output: true
dog.sing(); // Output: Singing to the moon!









