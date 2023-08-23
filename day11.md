# day 11  2023-8-22
# Types section:
- video#1:think deeply about JavaScript and understand its behaviour.
- video#2:the type of operator always return a string that contain the type of the variable even undefined or null always ahs to be in double quetes "" ""
- video#3:how BigInt differs from other numbers in JavaScript.
- video#4:various ways something can be empty in JavaScript: undefined, undeclared, and uninitialized.
- video#5: NAN===NAN is false and NAN- + * / 5 = NAN always!
- video#6:explains how operations on it can cause unexpected results.
# Coercion section:
### He provided an in-depth exploration of abstract operations in JavaScript, elucidating the language's nuanced approach to handling them and shedding light on its idiosyncratic and at times unpredictable behaviors within this context.



# deliverables:
## QUESTION 1:
    function convertStringToNumber(item) {

    if (typeof (item) === 'string') {

        return +item;

    }
    else {


        return {

            value: item,
            type: typeof (item)
        };
    }


    }
## QUESTION 2:
function checkNaN(item) {

    if (item !== item) {// the only case an number is nan is nan !== nan

        return true // so item is nan

    }
    else {
        return false;
    }

    }
## QUESTION 3:
    function isEmptyValue(item) {
    if (Boolean(item)) {


        return true;// its an null or undefined or empty string
    }
    return false;
    

    }
## QUESTION 4:
function compareObjects(ob1,ob2) {

    if (typeof (ob1) !== "object" || typeof (ob2) !== "object") {


        return [ob1, ob2];
    }
    else {

        return Object.is(ob1, ob2);

    }




        }
## QUESTION 5:



    function complexCoercion(input) { 

    if (typeof input === "number") {
        return Boolean(input.toString());
    } else if (typeof input === "string") {
        return Boolean(input);
    } else if (input === null || input === undefined) {
        return false;
    } else {
        return input;
    }}

# Philosophy of Coercion section:
### In his discussion, Kyle explores the differences between double equals and triple equals, clarifying common misconceptions. He delves into the decision-making process for choosing between them and the impact of linters on code quality. Additionally, Kyle closely examines the specifications for coercive equality to gain a comprehensive understanding of double equals' behavior. He illustrates his points with practical code examples, highlighting that many famous corner cases are derived from improbable scenarios.
# deliverables:
## question1:
                // Define a type for the resolved values of the promises.
        type PromiseResult<T> = T extends Promise<infer U> ? U : never;
        
        // Define an interface for the output object.
        interface ResultObject {
            sayHelloWorld: PromiseResult<typeof sayHelloWorld>;
            checkBoolean: PromiseResult<typeof checkBoolean>;
            returnObj: PromiseResult<typeof returnObj>;
        }
        
        // Correct the promises and wrap them with types.
        const sayHelloWorld = new Promise<string>((resolve, reject) => {
            resolve("Hello world!");
        });
        
        const checkBoolean = (boolean: boolean) => new Promise<boolean>((resolve, reject) => {
            if (boolean) {
                resolve(boolean);
            } else {
                reject(`Input is false :(`);
            }
        });
        
        const returnObj = new Promise<{ x: string; y: number }>((resolve, reject) => {
            resolve({
                x: "meow",
                y: 45,
            });
        });
        
        const promisesArray = [sayHelloWorld, checkBoolean(true), returnObj];
        
        // Define the convertToObj function.
        const convertToObj = (array: Promise<any>[]) => {
            const obj: Partial<ResultObject> = {};
        
            // Iterate through the promises and populate the object.
            array.forEach((promise, index) => {
                obj[`promise${index + 1}`] = promise.then((result) => result).catch((error) => error);
            });
        
            return obj as ResultObject;
        };
        
        // Call the convertToObj function.
        const resultObject = convertToObj(promisesArray);
        
        console.log(resultObject);
        
## question2:
          console.log(a);// we will see the value of a becusae its in the var scoping <the var scoping is function scoping not block scoping like the let or const> 
          console.log(b);// undefined because of the block scoping of the let key word
          console.log(c);// undefined because of the block scoping of the let key word


