# day#5:
## 2023-8-10

# conditionals section:
- video#1:if and else statements to execute code only under the specified conditions.
- video#2: exercise (DONE)
- video#3:logical concepts!
- vidoe#4:iterate over a function multiple times while only running a single statement using loops. The += and ++ increment operators.
- video#5:DONE exercise
- video#6:DONE exercise
- video#7:DONE exercise


  # map &filter:
  - video#1 :using the filter method to process an array for specified data and the map method to call a function on each item and create a new array.
  - video#2:practice work (DONE)
  - video#3:spreading our data
 
  # doggos game:
  - video#1:quiz game overview and explaining.
  - video#2:while loops to run a section of code repeatedly until a defined condition is true.
  - video#3:quiz explainations.
  - video#4:Implementing both the random item and shuffle utility functions.
  - video#5:reviewing the quiz more
  - video#6:asynchronous function by setting a task to a to-do list by running it in a setTimeout function.
 
# Question #1:
function checkSign(num) {

  return (num>0)?"positive":(num<0)?"negative":"zero"

}

checkSign(10);

# question#2:

  const ratings =watchList.map(film=>({title:film["Title"],rating:film["imdbRating"]}));
  # question #3:
const filteredList = watchList
  .filter(movie => {
    return parseFloat(movie.imdbRating) >= 8.0;// return the film incase the rating is >= 8 this return will not return a bloeean value it return something else
  })
  .map(movie => {
    return {
      title: movie.Title,
      rating: movie.imdbRating
    };
  });


console.log(filteredList);
# question4:
const names = ["Hole-in-one!", "Eagle", "Birdie", "Par", "Bogey", "Double Bogey", "Go Home!"];

function golfScore(par, strokes) {
  const index = Math.min(strokes - par + 2, names.length - 1);
  return names[index];
}

// Change these values to test
console.log(golfScore(5, 4));  // Output: "Birdie"

