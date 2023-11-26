# Vulnerable Patterns in Incomplete Fragments of Code

![abelberhane](docs/images/abelberhane.png)

Examples by  [@abelberhane](https://www.github.com/abelberhane) 

---

<br><br><br>

# SQL Injection Vulnerability

## Incomplete Code Fragment (Python) <img width="50px" src="docs/images/python-logo.png">

```python
def get_user_data(user_id): query = "SELECT * FROM users WHERE id = " + user_id # ... database query execution ... 
```

### Copilot's Contribution

>Copilot can recognize that concatenating a variable directly into a SQL query string is a common pattern leading to SQL injection vulnerabilities. It might suggest a modification using parameterized queries or ORM (Object-Relational Mapping) methods to prevent such issues.

### Suggested Code

```python
def get_user_data(user_id): query = "SELECT * FROM users WHERE id = %s" params = (user_id,) # ... database query execution with parameters... 
```

---

<br><br><br>

# Cross-Site Scripting (XSS) in Web Applications

## Incomplete Code Fragment (JavaScript) <img width="40px" src="docs/images/node-js.png">

```javascript
app.get('/search', function(req, res) { var searchTerm = req.query.term; res.send('Results for: ' + searchTerm); }); 
```

### Copilot's Contribution

>Recognizing the pattern of directly including user input in the response, Copilot might suggest sanitizing the input or encoding the output to prevent XSS attacks.

### Suggested Code

```javascript
app.get('/search', function(req, res) { var searchTerm = escape(req.query.term); res.send('Results for: ' + searchTerm); }); 
```

---

<br><br><br>

# Insecure Password Storage

## Incomplete Code Fragment (JavaScript) <img width="40px" src="docs/images/node-js.png">

```javascript
function storeUser(username, password) { // Code to store username and password directly in the database } 
```

### Copilot's Contribution

>Identifying the pattern of insecure password handling, Copilot could suggest implementing hashing with a strong algorithm like bcrypt before storing passwords.

### Suggested Code

```javascript
const bcrypt = require('bcrypt'); function storeUser(username, password) { const salt = bcrypt.genSaltSync(10); const hash = bcrypt.hashSync(password, salt); // Code to store username and hashed password in the database } 
```

---

<br><br><br>

# Inadequate Encryption Use

## Incomplete Code Fragment (Python) <img width="50px" src="docs/images/python-logo.png">

```python
from Crypto.Cipher import AES import os def encrypt_message(message): key = os.urandom(16) # 16-byte key cipher = AES.new(key, AES.MODE_ECB) # ... 
```

## Copilot's Contribution:

>In this case, Copilot might highlight the use of ECB mode, which is generally considered insecure for encryption, and suggest using a more secure mode like CBC or GCM.

## Suggested Code:

```python
from Crypto.Cipher import AES import os def encrypt_message(message): key = os.urandom(16) # 16-byte key cipher = AES.new(key, AES.MODE_CBC, iv) # ...
```