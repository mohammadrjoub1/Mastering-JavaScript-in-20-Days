
# Day #4
## 2023-8-9

# Functions section !
- video#1:creating a function
- video#2:return values
- video#3:DONE questions and pracitsing material
- video#4:creating unnamed functions using the arrow syntax to declare the function
- video#5:questions done !
- video#6:project is done
- video#7:project is done
- video#8+9:Are quiz exsercises and they are done.
- video#10:scoping and code block mentality
- video#11:scoping for let
- video#12:scoping var


# Event and handler section !
- video#1:what is event listeners are
- video#2:Events are fired to notify code of "interesting changes" that may affect code execution.
- video#3:Exercise is Done.

# Question#1:
  // Declare the myGlobal variable below this line
let myGlobal=10;


function fun1() {
  // Assign 5 to oopsGlobal here
  oopsGlobal=5;

}

// Only change code above this line

function fun2() {
  let output = "";
  if (typeof myGlobal != "undefined") {
    output += "myGlobal: " + myGlobal;
  }
  if (typeof oopsGlobal != "undefined") {
    output += " oopsGlobal: " + oopsGlobal;
  }
  console.log(output);
}

# Question#2:
function myLocalScope() {
  // Only change code below this line
  let myVar;

  console.log('inside myLocalScope', myVar);
}
myLocalScope();

// Run and check the console
// myVar is not defined outside of myLocalScope
console.log('outside myLocalScope', myVar);

# Question#3:
// Setup
const outerWear = "T-Shirt";

function myOutfit() {
  // Only change code below this line
  let outerWear ="sweater";

  // Only change code above this line
  return outerWear;
}

myOutfit();
# question#4:
function nextInLine(arr, item) {
  // Only change code below this line
  
  arr.push(item);
  return arr.shift();
  // Only change code above this line
}

// Setup
let testArr = [1, 2, 3, 4, 5];

// Display code
console.log("Before: " + JSON.stringify(testArr));
console.log(nextInLine(testArr, 6));
console.log("After: " + JSON.stringify(testArr));
  
