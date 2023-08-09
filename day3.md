# Day #3
## 2023-8-8+2023-8-9
 # Arrays section:
- video#1: the array index, finding the .length of an array, and how to check if an array contains a specific value. Replacing, removing, and appending array items are also demonstrated in this segment.
- 




 # Objects Section:
 - video#1:access the values of an object's properties and how to make new prop in the object.
 - video#2:what happens when creating and accessing information in a JavaScript object
 - video#3:exercises and freeze() and spread
 - video#4:nestead object formula and methods!(nestead world)
 - video#5:exercises DONE.
 - video#6:we always have been using object and nested things
 - video#7: objects in JavaScript, including document, console, Math, and String
 - video#8:we used document.querySelector("#board > div:nth-child(3)") to accses things

 # quiz project:
- DONE  i made all the todooooos!!

# delieverables!
## question1
function forecast(arr) {
  // Only change code below this line

  return arr.slice(2,4);
}

// Only change code above this line
console.log(forecast(['cold', 'rainy', 'warm', 'sunny', 'cool', 'thunderstorms']));
## question2

function spreadOut() {
  let fragment = ['to', 'code'];
  let sentence=["learning",...fragment,"is","fun"]; // Change this line
  return sentence;
}

console.log(spreadOut()); 

## question3
const contacts = [
    {
      firstName: "Akira",
      lastName: "Laine",
      number: "0543236543",
      likes: ["Pizza", "Coding", "Brownie Points"],
    },
    {
      firstName: "Harry",
      lastName: "Potter",
      number: "0994372684",
      likes: ["Hogwarts", "Magic", "Hagrid"],
    },
    {
      firstName: "Sherlock",
      lastName: "Holmes",
      number: "0487345643",
      likes: ["Intriguing Cases", "Violin"],
    },
    {
      firstName: "Kristian",
      lastName: "Vos",
      number: "unknown",
      likes: ["JavaScript", "Gaming", "Foxes"],
    },
  ];
  
  function lookUpProfile(name, propp) {
    for (let i = 0; i < contact.length; i++) {
        if(name===contacts[i].firstName){
            if(propp===contacts[i].likes){
                return contacts[i].prop;
            }
            else{
                return "no likes there";
            }

        }
        else{
            return "No Name there!";
        }
        
    }
  }
  
  lookUpProfile("Akira", "likes");
  ## question 4:
  function reusableFunction (){


    console.log("Hi World");
}
reusableFunction();

  ## question 5:

  // Setup
let sum = 0;

function addThree() {
  sum = sum + 3;
}

// Only change code below this line

function addFive(){
  sum+=5;
}
// Only change code above this line

addThree();
addFive();
## question#6:

function timesFive(num){


  return num*5;
}
 
