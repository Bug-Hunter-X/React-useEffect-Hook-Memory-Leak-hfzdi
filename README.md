# React useEffect Hook Memory Leak
This repository demonstrates a common error in React applications: forgetting to include a cleanup function in the useEffect hook, leading to memory leaks.
The `bug.js` file contains the buggy code. The `bugSolution.js` file shows the corrected code, with a cleanup function to stop the interval when the component unmounts.
## How to Reproduce
1. Clone the repository.
2. Navigate to the directory.
3. Run `npm install` to install dependencies.
4. Run `npm start` to start the development server.
5. Observe that the count continuously increments even after navigating away from the component, indicating a memory leak.
## Solution
The solution provided in `bugSolution.js` adds a return statement to the useEffect hook. This return statement contains a function that clears the interval using `clearInterval` when the component is unmounted. This prevents the memory leak.