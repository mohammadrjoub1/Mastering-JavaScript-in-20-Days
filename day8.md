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


- video#4:




