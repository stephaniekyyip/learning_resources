# [Udacity: Intro to Backend](https://www.udacity.com/course/intro-to-backend--ud171)

**Table of Contents**

[Lesson 1: How the Web Works](#Lesson-1-How-the-Web- Works)

[Lesson 3: Forms and Inputs](#lesson-3-forms-and-inputs)

[Lesson 4: Templates](#lesson-4-templates)

[Lesson 6: Databases](#lesson-6-databases)

[Lesson 7: Blog](#lesson-7-blog)

[Lesson 8: User Accounts and Security](#lesson-8-user-accounts-and-security)

---

### Lesson 1: How the Web Works

- Web basics: HTML, URLs, HTTP, web apps 

- Word Wide Web:

  - Collection of HTML documents

- Browsers make requests via Internet to server using a protocol called HTTP

- Servers respond with files that the browser displays

- **HTTP**: The main protocol of the web

- **Server**: Computers that host the files that make up the web

- **Internet**: The world’s largest computer network

- **Browser**: A program that runs on your computer to display files found on the web.

- **HTML**: HyperText Markup Language

  - Made out of text content, markup (what it looks like), references to other docs, links to other pages

- `em` tag: For emphasis, to make things italicized

- HTML attributes

  - `<tag attr=”value”>content</tag>`
  - Anchor tag `<a href = “url”></a>` 
  - Image tag `<img src = “url” alt = “text”>`

- Void tag- no closing tag needed

  - E.g. `img`, `br` (break)

- inline elements: `br`, `em`, `img`, `span`

- block element: `p`, `div`, `form`

- URL: Uniform Resource Locator

  - http => protocol
  - `www.udacity.com` => host
  - / => path

- Query Parameters

  - E.g. `http://example.com/foo?p=1&q=neat`
    - Formatting: name = value (i.e. name => p and value => 1)

- Fragment

  - E.g. `http://www.example.com/foo#fragment`
  - Request is not sent to server. Fragment only exists in browser.

- Port

  - E.g. `http://localhost:8000/`

- HTTP: HyperText Transfer Protocol

  - Browser uses this to talk to web servers
  - Request line: `GET /foo HTTP/1.1`
    - method => GET (or POST)
    - path => /foo
    - version: HTTP/1.1 (or 1.0)

- Request headers

  - E.g. User-Agent: Chrome
  - Sent in HTTP request

- HTTP Responses

  - Request (request line): `GET /foo HTTP/1.1`
  - Response (status line): `HTTP/1.1 200 ok`
    - 200 => status code
    - ok => reason phrase
  - Status Codes
    - 200 => success
    - 300 => do something different to find doc (i.e. located somewhere else)
    - 400 => error on the browser side
    - 500 => error on the server side
  - Headers
    - Date, Server (i.e. Apache/ 2.2.3), Content-Type (i.e. text/ html), Content-Length

- Servers

  - Purpose: respond to HTTP requests
  - Server response types:
    - static: pre-written file, images
      - dynamic: content made on the fly by a web application

---

### Lesson 3: Forms and Inputs

- Form method

  - Default: get
  - Options: get, post

- GET method

  - Parameters (data) are included in the url
  - Used for fetching documents
  - Limited by a max URL length
  - Ok to cache (so you don’t have to request it new every time)
  - Shouldn’t change the server. Can make multiple of the same GET requests and the server shouldn’t change.

- POST method

  - Parameters included the request body
  - Used for updating data
  - No max length
  - Not ok to cache b/c updating data on the server
  - Ok to change server (that’s the point of a post request)

- Form input types

  - Default: text
  - Password type: Should be used for entering passwords on forms, but the password is not sent securely to your server since the parameter is shown in the URL
  - **Checkbox**: The value for the parameter is “on” when checked. The parameter doesn’t appear in the URL if it is left unchecked.
  - **Radio**: Behaves the same way as checkboxes, except you cannot uncheck them.
    - Give all the radio buttons in a group the same “name”, so that only one option can be selected at a time. Then, give each option an appropriate “value” parameter, so that the URL will reflect the selected radio button option accurately.

- Label element

  - Used to label each input in a form

    ```html
    <form>
    <label>
      One
    <input type = "radio" name = "q" value = "one">
    </label>
    </form>
    ```

- Dropdown

  ```
    <form>
    <select name = "q">
    <option value = “1”>One</option>
    <option value = “2”>Two</option>
    <option value = “3”>Three</option>
    </select>
    </form>
  ```

- Form Validation

  - User could input junk into the server, so must validate the query parameters    
  - String substitution (Python)
    - E.g. `“My name is %s” % Stephanie`
    - E.g. `**“Here are two things: %(hobby)s and %(color)s” %{“hobby”: “reading”, “color”: “blue”}**`

- Escaping

  - Prevents HTML from being rendered as HTML tags. 
  - Can import cgi module in python to use the “cgi.escape” function to escape string
    - “  => `"`
    - \> => `>`
    - < => `<`
    - & => `&amp;`

- Redirect after form submission, so that reloading the page doesn’t resubmit the form and so that you can separate forms and submission successful pages.

---

### Lesson 4: Templates

- Use a string to enter html (with triple quotes)
  - E.g. `html = """ """`
- Template Library: Library to build complicated strings (i.e. html)
  - E.g. `jinja` in Python
    - Escape all user input before displaying it on the page or processing to prevent HTML injection
  - Make sure to enable auto-escaping for all variables in the templating language
- Use templates to:
  - Minimize HTML in code (separate the two)
  - Make code more readable and organized
  - Make more secure websites (escaping user input)

---

### Lesson 6: Databases

- **Database**: A program that stores and retrieves large amounts of data.

- Types of databases

  - Relational: Uses SQL. E.g. Postgresql, MySQL, sqlite, Oracle
  - NoSQL: E.g. mongo, couch

- SQL: Structured Query Language

  - E.g. `SELECT * FROM links WHERE submitter_id = 5 AND votes > 23`
  - Order by
    - E.g. `SELECT * FROM links WHERE votes > 10 ORDER BY votes DESC`
    - Default: Ascending `ASC`
  - Joins
    - Used for multiple tables, but rarely used in web software
    - E.g. `SELECT link.* FROM link, user WHERE link.user_id = user.id AND user.name = ‘spez’`
      - Finds the name ‘spez’ in the table ‘user’ and then finds where ‘user_id’ in the table ‘link’ matches the ‘id’ in the table ‘user.’

- Sequential scan

  - Loop through all entries in table to find the specific item
  - Slow with a lot of data

- Indexes (i.e. Hash tables)

  - Increases the speed of queries
  - Maps a key to a value

- Hash table

  - Not sorted, but look-ups are fast (constant time)

- Tree

  - Sorted, but look-ups are slower (log n time)

- To grow a database that won’t fit on one machine, shard the database, meaning the data is spread across multiple machines. 

- ACID

  - **Atomicity**: All parts of a transaction succeed or fail together
    - A transaction groups together multiple commands
  - **Consistency**: The DB will always be consistent
    - DB will move from one valid transaction to the next (i.e. items that get updated under the same conditions must all get updated)
  - **Isolation**: No transaction can interfere with another transaction
  - **Durability**: Once the transaction is committed, it won’t be lost
    - Even if DB crashes, the data won’t be lost

- Trade-offs exists with every DB system

- HTML `<pre>`: Preformatted text (preserves whitespace)

---

### Lesson 7: Blog

- Replace `\n` with `<br>` in order to render the new lines in the text that the user submits

---

### Lesson 8: User Accounts and Security

- Cookies: Small (< 4Kb) piece of data stored in the browser for a website. 

  - Format: name = value (i.e. user_id = 12345)
  - Usually stores temporary info that a browser wants to store, like if you’re logged into a website

- Browser sends request to server. Server sends back cookie data in a http header as a response.

- Browser stores the cookie that is associated with the website. So, every time the browser returns to the website, it sends the cookie back to the server.

- Browser-enforced limitations: ~20 cookies/ website, < 4kb / cookie, cookie associated with only 1 particular cookie for security reasons

- Cookies are sent in HTTP headers

  - Http response e.g: `set-cookie: user_id = 12345; domain: www.reddit.com; path = /; Expires: Tue, 1 Jan 2005 00:00:00 GMT`
  - Http request e.g.: `cookie: user_id = 12345; last-seen: Dec 25 1985`
  - Can restrict a cookie to a specific path on the website
  - Domain controls which domain a browser will send a cookie to
  - Domain must contain at least two periods (i.e. `www.reddit.com` or `.reddit.com` or `foo.reddit.com`, NOT `reddit.com`)
  - Can set cookies to expire at a particular time. By default, cookies expire when the browser is closed i.e. when the session has ended.

- In Mac/ Linux terminal to see the headers:
    E.g. `curl -I google.com`

- Cookies can also be set in the browser using dev tools

  - In JavaScript console: `document.cookie=”visits=1001”`

- Hash: A function that can be applied to some data to produce some output. 

  - H(x) -> y, where x is data and y is a fixed length bit string (~32-256 bits)
  - Difficult to generate a specific y
  - Infeasible to find x for a given y (cannot be reverse engineered)
  - Can’t modify x without modifying y

- Hash algorithms

  - **crc32**: checksums used to verify that the entire file has been received properly, collisions are easy to find but doesn’t matter b/c not used for security, fast
  - **md5**:  fast, seemed secure but not anymore, collisions are easy to find
  - **sha1**: secure-ish
  - **sha256**: pretty good, but slow
  - **Collision**: Two inputs hash to the same value. Collisions should be hard to find.

- Hashing in Python

  ```python
  import hashlib
  x = hashlib.md5(“foo”)
  ```

- Hashing Cookies

  - `set-cookie: visits = 5, [hashed value]`
  - To check if a cookie has been tampered with, make sure that the rehashed value is equal to the hash that was sent. Otherwise, reset or discard cookie value.
  - However, if the hashing algorithm is known, a hacker could use that algorithm to hash the new value of the cookie. To combat this, instead of just hashing the value, you would hash the value + secret. 
  - **HMAC**: Hash-based Message Authetication Code
    - Similar to `hashlib` for hashing, but also incorporates a secret to create the hash value. 

      ```python
      import hmac
      hmac.new("secret", "message").hexdigest()
      ```

- Password hashing

  - Passwords should not be stored as plain text in a database (in the case of the database being compromised), but should instead be stored as a hashed value.

  - However, even hashed passwords are not completely safe.

  - **Rainbow table**: Comprehensive hash table mappings of plain text to hashed values. Makes it easy to look up the mappings for a given hash algorithm.

  - **Salt**: Similiar to secrets, but consists of random characters that are added to the plan text values before being hashed.

  - Be careful about 3rd party libraries for password hashing.

  - Most hashing functions are designed to be fast, which is fine in the case of verifying cookies. But in the case of verifying passwords, it might be better to have a slower hashing function to account for computers getting faster. 

    - **bcrypt** (instead of sha256) uses an additional parameter that determines how slow the hashing will take

- HTTPs

  - When submitting passwords in forms, the values can be easily seen in the URL. The passwords are also being sent in plaintext over the Internet.  

  - The solution is to use HTTPs, which is HTTP encrypted over SSL. 
