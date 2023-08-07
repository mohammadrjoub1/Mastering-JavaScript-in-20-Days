Day #2
2023-8-7+2023-8-8
 Values & data types section:
-	Video#1:she talked about different data types like string and number etc.. and she talked about value definition and the kinds of data(primitive vs objects) and null vs undefined.
-	Video#2:exercises(DONE)
-	Video#3:she talked about strings and that it an array of characters and talked about length method.
-	Video#4:she talked about the  string (its an array with 0 index way) and we used methods like indexof()  and include() etc.
-	Video#5: exercises(DONE).



Operators section:
-	Video#1:operators like +*/- , typeof etc
-	Video#2:Exercises (Done).
-	Video#3: returning a boolean when running comparison operators and discusses the differences between the triple equals === and double equals == equality operators ,:=== vs == vs !== vs!=.

Expressions section:
-	video#1: expression is a valid set of literals, variables, and operators that resolve to a single value.
-	video#2: declaring and assigning variables using let keyword.
-	video#3: declaring const and explaining about conatant variable keyword
-	video#4: Exercises (Done).
-	video#5: overview of what a variable is.
-	video#6: how JavaScript evaluates reassigning.
-	video#6: differences between statements and expressions.



Question#1:
let a = 0;
let b = "0";
let c = false;
let d = "false";

console.log(a == b); // output is True because the double equal It performs type coercion, which means it attempts to convert the values to a common type before making the comparison and since the value is identical this means that the output is true. 

console.log(b === c); // output is False because b is string and c Boolean.

console.log(!!d); // output is true because the strings is not empty so its initial Boolean value is true then ! will make it false and another added ! will remake it to true .



Question#2:
console.log(4 + 5 * "7"); //the output is 39 because js will convert the string “7” to number then the multiplication has will occur (7*5) because of its high priority then the addition will occur 


Question#3:

let result = 5 + 2 * 3 - 1; // we have to cases 1- if we don’t log out the result we will get undefined output 2-if we log the out we will get 10 as an output since the multiplication has the heights  priority here then addition and subtraction .
Question#4:
	let x = 10;
let y = '10';
console.log(x == y); // true because the double equal It performs type coercion, which means it attempts to convert the values to a common type before making the comparison and since the value is identical this means that the output is true. 

console.log(x === y); // false because x is number and y a string(char).

Question#5:
let num = "15";
let isPositive = true;
let result = (num > 10 && isPositive) || num < 0; 
console.log(result); 
// the num string type will be converted to number type because JavaScript performs type coercion to convert the string to a number before making the comparison, 
so num>10 is true && ispositive is true so all of the previous expression is true then num <0 is false so true || (or) falase will give us true result or output to the console




