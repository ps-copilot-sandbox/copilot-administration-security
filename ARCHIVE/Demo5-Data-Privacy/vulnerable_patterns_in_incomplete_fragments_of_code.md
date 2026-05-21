# Vulnerable Patterns in Incomplete Fragments of Code

![abelberhane](../docs/images/abelberhane.png)

Examples by  [@abelberhane](https://www.github.com/abelberhane)

---
<!-- markdownlint-disable MD033 -->
## SQL Injection Vulnerability

### Incomplete Code Fragment (Python) #1 <img width="50px" src="../docs/images/python-logo.png" alt="Python">

```python
def get_user_data(user_id): query = "SELECT * FROM users WHERE id = " + user_id # ... database query execution 
```

#### Copilot's Contribution #1

>Copilot can recognize that concatenating a variable directly into a SQL query string is a common pattern leading to SQL injection vulnerabilities. It might suggest a modification using parameterized queries or ORM (Object-Relational Mapping) methods to prevent such issues.

#### Suggested Code #1

```python
def get_user_data(user_id): query = "SELECT * FROM users WHERE id = %s" params = (user_id,) # ... database query execution with parameters... 
```

---

## Cross-Site Scripting (XSS) in Web Applications

### Incomplete Code Fragment (JavaScript) #2 <img width="40px" src="../docs/images/node-js.png" alt="NodeJS">

```javascript
app.get('/search', function(req, res) { var searchTerm = req.query.term; res.send('Results for: ' + searchTerm); }); 
```

#### Copilot's Contribution #2

>Recognizing the pattern of directly including user input in the response, Copilot might suggest sanitizing the input or encoding the output to prevent XSS attacks.

#### Suggested Code #2

```javascript
app.get('/search', function(req, res) { var searchTerm = escape(req.query.term); res.send('Results for: ' + searchTerm); }); 
```

---

## Insecure Password Storage

### Incomplete Code Fragment (JavaScript) #3 <img width="40px" src="../docs/images/node-js.png" alt="NodeJS">

```javascript
function storeUser(username, password) { // Code to store username and password directly in the database } 
```

#### Copilot's Contribution #3

>Identifying the pattern of insecure password handling, Copilot could suggest implementing hashing with a strong algorithm like bcrypt before storing passwords.

#### Suggested Code #3

```javascript
const bcrypt = require('bcrypt'); function storeUser(username, password) { const salt = bcrypt.genSaltSync(10); const hash = bcrypt.hashSync(password, salt); // Code to store username and hashed password in the database } 
```

---

## Inadequate Encryption Use

### Incomplete Code Fragment (Python) #4 <img width="50px" src="../docs/images/python-logo.png" alt="Python">

```python
from Crypto.Cipher import AES import os def encrypt_message(message): key = os.urandom(16) # 16-byte key cipher = AES.new(key, AES.MODE_ECB) # ... 
```

#### Copilot's Contribution Python #4

>In this case, Copilot might highlight the use of ECB mode, which is generally considered insecure for encryption, and suggest using a more secure mode like CBC or GCM.

#### Suggested Code Python #4

```python
from Crypto.Cipher import AES import os def encrypt_message(message): key = os.urandom(16) # 16-byte key cipher = AES.new(key, AES.MODE_CBC, iv) # ...
```
