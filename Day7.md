# day #7 2022-8-13

# javaScript princibles Section
- video #1:how JavaScript traverses code
- video #2:how the exuction of code happens in terms of memmory and threading , each element and variable in the global code excute one by one , and all the element inside a function doesnt saved in the same place that the outside variables.
- video #3:in simple terms the global() meaning that the global scope elements are always at the bottom of the call stack and any new function call has been called it always go to the top of the call stack.

# Function and callBacks
- video#1:how to make your functions more efficient and make your code shorter.
- video#2:function that uses an array as a parameter,and then we trace every element there and check the order of excution of the line by line , then we observe the call stack there.
- video#3 :A higher-order function is a function that takes another function as its parameter, resulting in two execution contexts [scope(), func1, func2] in the call stack. Therefore, each function existing within the overall scope represents a new execution context.
- video#4 :an example of highe-order functions p.s: when we call the function and with an argument with type function  we dont put () becuase we are not calling the function that we put it in the argument insted we pass the function to the parameter variable (calling back)0.
- video#5: q and a , one of them was asking about when passing an argument this argument doesnt been copied in value it copied in refrence.
- video#6:any function that takes a function as a parameter or return a function called higher order function and any function passed as a parameter in the higher order function called a call back function becuase we do call it back when we have it.
- video#7:anonymous functions are used under the hood when an arrow function is instantiated. The drawbacks of using arrow functions on overall understanding and readability is then discussed, and a question is asked about whether there are memory considerations when using an arrow function .
  # challenges:
## challenge #1:
function addTwo(input) {


    return input + 2;
}
## challenge #2:
function addS(input) {


    return input + 's';
}
## challenge #3:
function map(array, func) {
    let newArray = [];
    for (let i = 0; i < array.length; i++) {

        newArray.push(func(array[i]))

    }
    return newArray;


}
## challenge#4:

function forEach(array, callback) {
    for (let i = 0; i < array.length; i++) {
        callback(array[i])
    }

}


let alphabet = '';
forEach(['a', 'b', 'c', 'd'], char => alphabet += char);
console.log(alphabet);  

## challenge#4:
let finalArray= '';
function forEach(array, callback) {

    for (let i = 0; i < array.length; i++) {

        callback(array[i])
    }



}
console.log(forEach(['a', 'b', 'c', 'd'], item => finalArray += item))
 ## challenger #5:
function mapWith(array, func) {
    let newArray = [];
    array.forEach(function (item,index,array) {

        newArray.push(func(item));

    })
    return newArray;


} 
## challenge #6:
function reduce(array, callback, initialValue) {
    let acc = initialValue
    for (let i = 0; i < array.length; i++) {
        acc = callback(acc, array[i])
    }
    return acc
}
console.log(reduce([4, 1, 3], (a,b)=>a+b, 0));   


## challenge 7:


