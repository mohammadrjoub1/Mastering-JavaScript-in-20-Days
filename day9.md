# day9 2023-17-8:
# promises section:
- video #1:what JavaScript was like before ES6, and explains why promises are an extremely powerful feature today. The two-pronged "facade" functions that were introduced to initiate background web browser work, then return a placeholder object to JavaScript are introduced.

- video#2:what is happening behind the scenes when a call to a Twitter API is made using fetch. The two pronged functionality stemming from the fetch promise is explored.
- video#3:the built-in method that calls methods that depend on the returned data. The rest of the example is diagrammed in full to demonstrate how the combination of fetch and then can pull data from an external API, and halt execution of methods that depend on the data until the data is received
- video #4: a more complex example involving both web browser APIs and promises. The problem begins by instantiating functions into the global memory, then a setTimeout function is called, and a fetch call is made to a Twitter API. It's demonstrated how each of these things end up in the context of the web browser, callback queue, or call stack.
- video #5:diagramming the example involving both web browser APIs and promises. The promise is returned by the fetch call, and the "then" statement is reached and the function call is placed on the callback queue. The thread of execution is then blocked by a function, and a log statement is reached
- video#6:diagramming the example involving both web browser APIs and promises. The event loop reports back that the call stack is clear, so the callback (or task) queue is addressed. The concept of a microtask queue is introduced.

- video#7:questions from the audience regarding the returned data from the fetch function, whether functions are passed by reference or by value when passed to a web API, arguments within the function passed into the web API, what precedence objects take within the queues, and which functions go into the microtask queue and which go in the callback queue
-  video#8:problems of promises, including that most developers don't understand them. The benefits introduced include error handling. The features of Promises, web APIs, and the callback, microtask queues, and event loop are reviewed. A final question is asked regarding whether the async await has the same functionality
  # deliverables:
  ## Question1:
  const task1 = (cb) => setTimeout(() => {
  const message = "Task 1 has executed successfully!";
  cb(message);
}, 3000);

const task2 = (cb) => setTimeout(() => {
  const message = "Task 2 has executed successfully!";
  cb(message);
}, 0);

const task3 = (cb) => setTimeout(() => {
  const message = "Task 3 has executed successfully!";
  cb(message);
}, 1000);

const task4 = (cb) => setTimeout(() => {
  const message = "Task 4 has executed successfully!";
  cb(message);
}, 2000);

const task5 = (cb) => setTimeout(() => {
  const message = "Task 5 has executed successfully!";
  cb(message);
}, 4000);

const asyncTasks = [task1, task2, task3, task4, task5];

const executeInSequenceWithCBs = (tasks, callback) => {
  const results = [];
  let count = 0;

  function executeTask(task) {
    task((message) => {
      results.push(message);
      count++;

      if (count === tasks.length) {
        callback(results);
      }
    });
  }

  for (const task of tasks) {
    executeTask(task);
  }
};

executeInSequenceWithCBs(asyncTasks, (messages) => {
  console.log(messages);
});
## question2:
const axios = require('axios'); // Make sure to install the axios library using npm or yarn

const apis = [
  {
    apiName: "products", 
    apiUrl: "https://dummyjson.com/products",
  }, 
  {
    apiName: "users", 
    apiUrl: "https://dummyjson.com/users",
  }, 
  {
    apiName: "posts", 
    apiUrl: "https://dummyjson.com/posts",
  }, 
  {
    apiName: "comments", 
    apiUrl: "https://dummyjson.com/comments",
  }
];

const executeInSequenceWithPromises = async (apis) => {
  const results = [];

  for (const api of apis) {
    try {
      const response = await axios.get(api.apiUrl);
      results.push({
        apiName: api.apiName,
        apiUrl: api.apiUrl,
        apiData: response.data
      });
    } catch (error) {
      console.error(`Error fetching ${api.apiName} API: ${error.message}`);
    }
  }

  return results;
};

executeInSequenceWithPromises(apis)
  .then((results) => {
    console.log(results);
  })
  .catch((error) => {
    console.error(`Error in execution: ${error.message}`);
  });

## question3:
