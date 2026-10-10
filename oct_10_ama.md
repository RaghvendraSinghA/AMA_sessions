# AMA Q&A

## 1. (Aditya Sharma): What is `JsonResponse`?

- `JsonResponse` is a Django class used to return data in JSON format from a view to the client.
- It is commonly used in AJAX requests and APIs.
- It automatically converts a Python dictionary into a JSON response.

Example:

```python
from django.http import JsonResponse

def get_data(request):
    data = {
        "name": "Aditya",
        "age": 22
    }
    return JsonResponse(data)
```

## 2. (Alok Kumar): What is an alternate key?

- An alternate key is a candidate key that is not selected as the primary key.
- A candidate key is a column or combination of columns that can uniquely identify each record.
- A table can have multiple candidate keys, but only one is selected as the primary key.

Example:

Consider an `Employees` table with `employee_id`, `email`, and `name`.

- `employee_id` is selected as the primary key.
- `email` is another candidate key if it is unique.
- Therefore, `email` is an alternate key.

## 3. (Amit Chandra Dey): What is normalization?

- Normalization is the process of organizing data in a database to reduce data redundancy and prevent data anomalies.
- It involves dividing data into related tables and establishing relationships between them.

Common normal forms:

- 1NF (First Normal Form): Each column contains atomic values, with no repeating groups.
- 2NF (Second Normal Form): The table is in 1NF, and every non-key attribute depends on the entire candidate key.
- 3NF (Third Normal Form): The table is in 2NF and has no transitive dependencies of non-key attributes on candidate keys.

Example:

Instead of storing a student's name repeatedly for every course, we can maintain separate `Students` and `Courses` tables and connect them through a relationship table.

## 4. (Atul Kumar): How do you make a second `div` scrollable in HTML?

- We can make the second `div` scrollable using CSS `overflow` and a fixed or constrained height.
- The parent container can use Flexbox to arrange two child elements.
- The second `div` needs a constrained height so its content can overflow.

Example:

```html
<div class="container">
    <div class="first">
        First div
    </div>

    <div class="second">
        <p>Scrollable content</p>
        <p>Scrollable content</p>
        <p>Scrollable content</p>
        <p>Scrollable content</p>
        <p>Scrollable content</p>
    </div>
</div>
```

```css
.container {
    display: flex;
    flex-direction: column;
    height: 300px;
}

.first {
    flex-shrink: 0;
    padding: 10px;
}

.second {
    flex: 1;
    min-height: 0;
    overflow-y: auto;
}
```

- `overflow-y: auto` adds vertical scrolling when required.
- `flex: 1` allows the second `div` to occupy the remaining space.
- `min-height: 0` allows the flex child to shrink below its default minimum content size.

## 5. (Bokam Manikanta): Explain the difference between `Promise.race()` and `Promise.any()`.

- `Promise.race()` settles as soon as the first promise settles, whether it fulfills or rejects.
- `Promise.any()` fulfills as soon as the first promise fulfills. It rejects with an `AggregateError` only when all promises reject.

Example:

```javascript
const p1 = new Promise((resolve, reject) => {
    setTimeout(() => reject("First failed"), 100);
});

const p2 = new Promise((resolve) => {
    setTimeout(() => resolve("Second succeeded"), 200);
});

Promise.race([p1, p2])
    .then(console.log)
    .catch(console.error);

// Output: First failed
```

```javascript
Promise.any([p1, p2])
    .then(console.log)
    .catch(console.error);

// Output: Second succeeded
```

Key difference:

- `race()` returns the result of the first promise to settle.
- `any()` returns the result of the first promise to fulfill.

## 6. (Pantham Adinarayana): What is a promise?

- A Promise is a JavaScript object that represents the eventual completion or failure of an asynchronous operation.
- It has three states: pending, fulfilled, and rejected.
- We commonly handle promises using `.then()`, `.catch()`, and `.finally()`, or with `async/await`.

Example:

```javascript
const promise = new Promise((resolve, reject) => {
    const success = true;

    if (success) {
        resolve("Operation successful");
    } else {
        reject("Operation failed");
    }
});

promise
    .then(result => console.log(result))
    .catch(error => console.error(error))
    .finally(() => console.log("Operation completed"));
```

## 7. (Rahul Raj): What is the difference between `UNION` and `UNION ALL`?

- `UNION` combines the results of two or more compatible `SELECT` queries and removes duplicate rows.
- `UNION ALL` combines the results without removing duplicate rows.
- `UNION ALL` is generally faster because it does not need to eliminate duplicates.

Example:

```sql
SELECT name FROM employees
UNION
SELECT name FROM managers;
```

This returns distinct names.

```sql
SELECT name FROM employees
UNION ALL
SELECT name FROM managers;
```

This returns all names, including duplicates.

Note: Both queries must have the same number of columns, with compatible data types in corresponding positions.

## 8. (Sai Ganesh Lanka): What is a module?

- A module is a file that contains reusable code, such as variables, functions, or classes.
- Modules help organize code and make it easier to maintain and reuse.
- In JavaScript, we use `export` to expose code and `import` to use it in another module.

Example:

`math.js`

```javascript
export function add(a, b) {
    return a + b;
}
```

`main.js`

```javascript
import { add } from "./math.js";

console.log(add(10, 20));
```

Output:

```text
30
```

## 9. (Santosh Anil Gurkhe): What is a model?

- A model is a representation of data and its structure in an application.
- In Django, a model is a Python class that usually maps to a database table.
- Model fields define the table's columns, and Django's ORM allows us to perform database operations using Python code.

Example:

```python
from django.db import models

class Student(models.Model):
    name = models.CharField(max_length=100)
    age = models.IntegerField()
    email = models.EmailField(unique=True)
```

Here:

- `Student` is the model.
- `name`, `age`, and `email` are model fields.
- Django uses the model to create and interact with the corresponding database table through migrations and the ORM.

## 10. (Sibsankar Manna): What is `load_dotenv()`?

- `load_dotenv()` is a function provided by the `python-dotenv` package.
- It reads variables from a `.env` file and loads them into the process environment, making them accessible through `os.environ` or `os.getenv()`.
- It is commonly used to manage configuration values, such as database credentials and API keys, outside the source code.

Example:

Install the package:

```bash
pip install python-dotenv
```

`.env`

```env
DEBUG=True
SECRET_KEY=my-secret-key
```

Python code:

```python
import os
from dotenv import load_dotenv

load_dotenv()

debug = os.getenv("DEBUG")
secret_key = os.getenv("SECRET_KEY")

print(debug)
print(secret_key)
```

Output:

```text
True
my-secret-key
```

Important points:

- Add `.env` to `.gitignore` if it contains secrets.
- Do not commit real passwords, API keys, or secret keys to a public repository.
- `load_dotenv()` does not normally override existing environment variables unless `override=True` is specified.
