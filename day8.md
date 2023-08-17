# day#8 2023-8-16
# closure section :
- video#1:how to let functions remember its state local variables, usually after the function is done any local memory will be gone.
- video#2:function func1() {


    function func2(num) {


        return num * 2;
    }

    return func2;

}


const f = func1();//now f has the return value f2 we user () so we call the function we need to excuted 

f(2);// now we have access on func2() even we are not accessing func1()
using a member from a function without calling the function for example we can return a function from the main function and we put the return in a variable then we can use the variable() to call the function was inside that function without calling the  main function.

- video#3:making function2 inside function1 and calling function 2 inside function1 and editing value of counter in function 1 from function 2 by counter ++ and seeing the effect.


- video#6:key functionality of closure that allows a function to have a permanent stored data cache. The caveats of the functionality are discussed, as well as the hidden property of [[scope]] afforded to functions.
- video#7:the concept of lexical or static scope as the key as to why closure works, and defines in technical terms what is occuring when closure is used. A clarification is also taken regarding reassigning variables with the backpack attached.
- video#8:Emphasis is placed on whether the original instance of the closure affects the secondary instance
- video#9:examples of where closure is used, including helper functions, iterators, generators, modules, and asynchronous JavaScript. Real use cases are discussed for clean, professional code.
  # asynchrounous javaScript section:
  video#1:how JavaScript executes code through a single thread.
  video#2:what issues could be posed by having only a single thread of execution when calling to an API. The additional features on top of JavaScript that have to be introduced to explain the functionality of a setTimeOut function are defined as web browser or Node background APIs, promises, and the event loop, callback/task queue, and microtask queue.
- video#3:some of the key features that the browser provides. To interact with the features that the browser offers, JavaScript offers "facade functions" that look like JavaScript, but are actually part of the browser. Examples of these functions include console, fetch, document, and setTimeout.
- video#4:what is happening when setTimeout is called, and demonstrates why it doesn't break the rule of JavaScript being single-threaded.
- video#5: how the function that is used by the "facade functions" keep state, and how the call stack works when asynchronicity is introduced. These questions are used to preface the point that there needs to be clearly defined rules for how this functionality works.
- video#6:the concept of a callback queue, then diagrams an example that demonstrates the functionality of the event loop, which ties the call stack and callback queue together
- video#7:about what would happen if the one of the functions were to return an augmented variable, a clarification on the previous example, and what would happen if the function's order was augmented.
- video#8:Questions (DONE)




