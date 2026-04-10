# HTML Questions for React Interviews (With Answers)

## 1. What is the difference between HTML and JSX?

**Answer:**

-   HTML → Standard markup language\
-   JSX → JavaScript XML (used in React)

Key differences:

  HTML                       JSX
  -------------------------- ------------------------
  class                      className
  for                        htmlFor
  Allows invalid structure   Strict structure
  Strings                    JS expressions allowed

Example:

``` jsx
<div className="container">
  {user.name}
</div>
```

------------------------------------------------------------------------

## 2. Why can't we use `class` in React?

**Answer:**

Because `class` is a reserved keyword in JavaScript.

So React uses:

``` jsx
className="container"
```

------------------------------------------------------------------------

## 3. What is the difference between `htmlFor` and `for`?

**Answer:**

In HTML:

``` html
<label for="email">Email</label>
```

In React:

``` jsx
<label htmlFor="email">Email</label>
```

Reason: - `for` is a JS keyword → replaced with `htmlFor`

------------------------------------------------------------------------

## 4. What are semantic HTML elements and why are they important in React?

**Answer:**

Semantic elements:

-   `<header>`
-   `<nav>`
-   `<main>`
-   `<section>`
-   `<article>`
-   `<footer>`

**Importance in React:**

-   Improves accessibility
-   Improves SEO
-   Helps maintain clean component structure

------------------------------------------------------------------------

## 5. How do you handle forms in React using HTML?

**Answer:**

Using controlled components.

``` jsx
const [name, setName] = useState("");

<input
  type="text"
  value={name}
  onChange={(e) => setName(e.target.value)}
/>
```

------------------------------------------------------------------------

## 6. What is the difference between controlled and uncontrolled inputs?

**Answer:**

**Controlled:**

``` jsx
<input value={value} onChange={handleChange} />
```

**Uncontrolled:**

``` jsx
<input ref={inputRef} />
```

Preferred → Controlled

------------------------------------------------------------------------

## 7. What is the role of `key` in lists in React?

**Answer:**

Keys help React identify elements efficiently.

``` jsx
items.map(item => (
  <li key={item.id}>{item.name}</li>
))
```

Without keys: - Wrong re-rendering - Performance issues

------------------------------------------------------------------------

## 8. How do you conditionally render HTML in React?

**Answer:**

``` jsx
{isLoggedIn ? <Dashboard /> : <Login />}
```

or

``` jsx
{isVisible && <Component />}
```

------------------------------------------------------------------------

## 9. How do you add inline styles in React?

**Answer:**

``` jsx
<div style={{ color: "red", fontSize: "20px" }}>
  Hello
</div>
```

------------------------------------------------------------------------

## 10. What is `dangerouslySetInnerHTML`?

**Answer:**

Used to render raw HTML.

``` jsx
<div dangerouslySetInnerHTML={{ __html: htmlContent }} />
```

⚠️ Risk: - XSS attacks

Use only when necessary.

------------------------------------------------------------------------

## 11. What are fragments in React and why are they needed?

**Answer:**

Avoid extra HTML nodes.

``` jsx
<>
  <h1>Title</h1>
  <p>Text</p>
</>
```

------------------------------------------------------------------------

## 12. How do you handle accessibility in React?

**Answer:**

Use:

-   Semantic tags
-   aria-\* attributes
-   Proper labels

``` jsx
<button aria-label="Close">X</button>
```

------------------------------------------------------------------------

## 13. Why should we avoid direct DOM manipulation in React?

**Answer:**

Because React manages DOM.

Avoid:

``` javascript
document.getElementById()
```

Use:

-   State
-   Props
-   Refs

------------------------------------------------------------------------

## 14. How do you handle images in React?

**Answer:**

``` jsx
<img src="/image.png" alt="desc" />
```

or

``` jsx
import img from "./image.png";

<img src={img} alt="desc" />
```

------------------------------------------------------------------------

## 15. What is lazy loading in images?

**Answer:**

``` html
<img src="img.png" loading="lazy" />
```

Improves performance.
