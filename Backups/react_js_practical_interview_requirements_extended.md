# React Practical Interview Requirements (5 Years Experience)

------------------------------------------------------------------------

# Existing React Practical Tasks

## 1. Searchable User List

Fetch users from API and implement search with loading and error
handling.

## 2. Todo App with Local Storage

CRUD todos with localStorage persistence.

## 3. Form Handling with Validation

Registration form with validations.

## 4. Pagination Implementation

Paginated product list using API.

## 5. Performance Optimization

Optimize slow rendering components.

## 6. Context API Task

Theme switcher using Context.

## 7. Custom Hook Creation

Create reusable useFetch hook.

## 8. State Management Task

Cart using Redux or Zustand.

## 9. Routing Implementation

Multi-page app with dynamic routing.

## 10. Debugging Task

Fix common React bugs.

------------------------------------------------------------------------

# Additional Core JavaScript & React Practical Requirements

These are **very important for 5-year experience candidates**.

------------------------------------------------------------------------

## 11. Higher Order Component (HOC) Practical

**Requirement**

Create a reusable HOC:

withLoader(Component)

Features:

-   Show loading spinner while API call is running
-   Wrap any component
-   Pass props correctly
-   Reuse for multiple components

**Sample Task**

-   Create UserList component
-   Wrap it using HOC
-   Show loader until data loads

**What to Evaluate**

-   HOC understanding
-   Props forwarding
-   Reusability
-   Composition skills

------------------------------------------------------------------------

## 12. JavaScript Hoisting Practical

**Requirement**

Predict output of the following and fix issues:

Example:

function test() { console.log(a); var a = 10; }

test();

**Candidate Tasks**

-   Explain output
-   Rewrite using let/const
-   Fix hoisting-related bugs

**What to Evaluate**

-   var hoisting knowledge
-   let/const behavior
-   Temporal Dead Zone understanding

------------------------------------------------------------------------

## 13. Closure Practical

**Requirement**

Create function:

createCounter()

Expected Output:

const counter = createCounter(); counter(); // 1 counter(); // 2
counter(); // 3

**Advanced Task**

Implement:

-   private variable using closure
-   debounce function
-   throttle function

**What to Evaluate**

-   Closure behavior
-   State persistence
-   Functional thinking

------------------------------------------------------------------------

## 14. Scope Practical

**Requirement**

Predict output:

var x = 10;

function test() { var x = 20; console.log(x); }

test(); console.log(x);

**Candidate Tasks**

-   Explain output
-   Differentiate:
    -   Global scope
    -   Function scope
    -   Block scope

**Advanced Task**

Fix scope-related bug in given code.

**What to Evaluate**

-   Scope clarity
-   Shadowing knowledge
-   Block scope understanding

------------------------------------------------------------------------

## 15. Debounce Implementation Practical

**Requirement**

Implement:

debounce(function, delay)

Use Case:

-   Search input
-   Avoid multiple API calls

**What to Evaluate**

-   Closure usage
-   Timer handling
-   Performance optimization

------------------------------------------------------------------------

## 16. Throttle Implementation Practical

**Requirement**

Implement:

throttle(function, delay)

Use Case:

-   Scroll events
-   Resize events

**What to Evaluate**

-   Timing logic
-   Performance optimization

------------------------------------------------------------------------

## 17. Event Loop Practical

**Requirement**

Predict output:

console.log("Start");

setTimeout(() =\> { console.log("Timeout"); }, 0);

Promise.resolve().then(() =\> { console.log("Promise"); });

console.log("End");

**Candidate Tasks**

-   Predict exact output order
-   Explain event loop behavior

**What to Evaluate**

-   Microtask vs Macrotask knowledge
-   Async behavior understanding

------------------------------------------------------------------------

## 18. this Keyword Practical

**Requirement**

Predict output:

const obj = { name: "React", show: function () { console.log(this.name);
} };

obj.show();

**Advanced Task**

Fix broken this binding using:

-   bind
-   call
-   arrow functions

**What to Evaluate**

-   this binding understanding
-   Arrow vs regular functions

------------------------------------------------------------------------

# Highly Recommended Real Interview Mix

Use:

-   1 React Task
-   1 JavaScript Core Task
-   1 Debugging Task

This combination clearly identifies strong candidates.

------------------------------------------------------------------------

# Core JavaScript Skills Expected from 5-Year React Developers

-   Hoisting
-   Closures
-   Scope
-   Event Loop
-   Promises
-   Async/Await
-   Debounce
-   Throttle
-   this keyword
-   Prototype basics
