 
# 50 Rapid-Fire Interview Questions with Answers
JavaScript + Node.js (0–2 Years Experience)

Quick one-line answers for rapid interview prep.

---

# JavaScript Fundamentals (1–20)

1. **What is JavaScript?**  
   A programming language for web development, both frontend and backend.

2. **Difference between var, let, const?**  
   `var` → function-scoped, `let` → block-scoped, `const` → block-scoped and immutable.

3. **What is hoisting?**  
   Moving variable and function declarations to the top of scope before execution.

4. **What is a closure?**  
   A function that remembers variables from its outer scope.

5. **What is the event loop?**  
   Handles asynchronous operations in JavaScript by checking call stack and callback queue.

6. **What is a promise?**  
   Represents a value that may be available now, later, or never.

7. **What is async/await?**  
   Syntactic sugar to handle promises synchronously in code.

8. **Difference between == and ===?**  
   `==` → compares value with type coercion, `===` → strict comparison (value + type).

9. **Difference between null and undefined?**  
   `null` → assigned empty value, `undefined` → variable declared but not initialized.

10. **What is NaN?**  
    Not a Number – invalid number operation result.

11. **typeof null?**  
    `"object"`

12. **What is destructuring?**  
    Unpacking values from arrays or objects.

13. **What is the spread operator?**  
    Expands elements (`...arr`) for arrays or objects.

14. **What is the rest operator?**  
    Collects remaining elements (`...args`) in function arguments.

15. **What is an arrow function?**  
    Shorter function syntax without its own `this`.

16. **Difference between function declaration and expression?**  
    Declarations are hoisted, expressions are not.

17. **What is a higher-order function?**  
    A function that accepts another function as argument or returns a function.

18. **What is callback hell?**  
    Nested callbacks that make code hard to read.

19. **What is event bubbling?**  
    Event propagates from child to parent elements.

20. **What is event delegation?**  
    Attaching a single event listener to a parent to handle child events.

---

# JavaScript Advanced (21–30)

21. **What is prototype?**  
    Object from which other objects inherit properties.

22. **What is prototypal inheritance?**  
    Objects inherit properties/methods from other objects via prototype chain.

23. **What is this keyword?**  
    Refers to the object executing the current function.

24. **Difference between call, apply, bind?**  
    `call` → executes function with `this` and arguments individually  
    `apply` → executes function with `this` and arguments as array  
    `bind` → returns new function with bound `this`

25. **What is memoization?**  
    Caching function results to optimize performance.

26. **What is debouncing?**  
    Limiting function execution after a delay.

27. **What is throttling?**  
    Limiting function execution to once in a time interval.

28. **What are microtasks and macrotasks?**  
    Microtasks: promises, process.nextTick; Macrotasks: setTimeout, setImmediate.

29. **What is Temporal Dead Zone (TDZ)?**  
    `let` and `const` cannot be accessed before initialization.

30. **Difference between shallow copy and deep copy?**  
    Shallow copy → references nested objects; Deep copy → copies everything recursively.

---

# Node.js Basics (31–40)

31. **What is Node.js?**  
    JavaScript runtime built on Chrome V8 for backend development.

32. **Why is Node.js single-threaded?**  
    Uses event loop + non-blocking I/O to handle multiple requests efficiently.

33. **What is non-blocking I/O?**  
    Operations do not block execution; handled asynchronously.

34. **What is the event loop in Node.js?**  
    Handles async operations using phases: timers, I/O callbacks, idle, check.

35. **What is process.nextTick()?**  
    Executes callback immediately after current operation, before promise or setTimeout.

36. **What is setImmediate()?**  
    Executes a callback in the check phase of the event loop, after I/O events.

37. **Difference between setTimeout and setImmediate?**  
    setTimeout → timer phase, setImmediate → check phase; order may vary.

38. **What is a stream?**  
    Efficient way to read/write large data in chunks.

39. **What is Buffer?**  
    Stores binary data in Node.js.

40. **What is package.json?**  
    Contains project metadata, dependencies, and scripts.

---

# Express & Backend (41–50)

41. **What is Express.js?**  
    Node.js web framework for building APIs and web apps.

42. **What is middleware?**  
    Functions that run between request and response; used for logging, auth, etc.

43. **What is REST API?**  
    Architectural style using HTTP methods (GET, POST, PUT, PATCH, DELETE).

44. **Difference between PUT and PATCH?**  
    PUT → replaces entire resource, PATCH → updates specific fields.

45. **What is JWT?**  
    JSON Web Token used for authentication.

46. **What is CORS?**  
    Cross-Origin Resource Sharing; allows/restricts resource requests from other domains.

47. **What is status code 200?**  
    OK – successful request.

48. **What is status code 404?**  
    Not Found – resource does not exist.

49. **Difference between authentication and authorization?**  
    Authentication → verify identity; Authorization → verify access rights.

50. **How do you handle errors in Express?**  
    Using error-handling middleware: `(err, req, res, next) => {...}`

---

# Tips for Rapid-Fire Round

- Speak clearly and confidently  
- Keep answers short (1–2 lines)  
- Give examples if asked  
- Revise key concepts and Node.js event loop

---

End of 50 Rapid-Fire Questions with Answers
```

---

If you want, I can also create a **complete Backend Developer Interview Kit** combining:

* JavaScript fundamentals
* Node.js concepts
* Express + MongoDB
* REST APIs
* Rapid-fire + coding questions

This would be a **full 200+ Q&A Markdown guide** for interviews.

Do you want me to make that?
