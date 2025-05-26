# **Phase 1 - Basics of Node.js (Part 1)**

## **1. Introduction to Node.js and Why Learn It**<!-- {"collapsed":true} -->

Node.js is a runtime environment that allows you to run JavaScript outside the browser, primarily on the server. It is built on Chrome's V8 JavaScript engine and is designed for building scalable network applications.

- **Use Cases:**
    - Backend web servers and APIs
    - Real-time applications (chat, games)
    - Command-line tools
    - Microservices

**Video Reference:**  
[Node.js & Express.js Crash Course ](https://youtu.be/H9M02of22z4?si=V3BZ_TkUU2_7_6N0)

---

## **2. Node.js Architecture & Event Loop**<!-- {"collapsed":true} -->

Node.js uses an event-driven, non-blocking I/O model.

- **Single-threaded**: Handles many connections using a single thread via the event loop.
- **Non-blocking I/O**: Operations like file/network access do not block the main thread.

```javascript
const fs = require('fs');
console.log('Start');
fs.readFile('file.txt', 'utf8', (err, data) => {
    if (err) throw err;
    console.log('File content:', data);
});
console.log('End');
```

**What happens internally:**
- The event loop delegates I/O to the OS/libuv.
- When the operation completes, the callback is queued and executed.

**Video Reference:**  
[What is the Event Loop? (JSConf)](https://youtu.be/8aGhZQkoFbQ)

---

## **3. Core Modules in Node.js**<!-- {"collapsed":true} -->

Node.js comes with built-in modules for common tasks.

| Module | Purpose | Example |
|-|-|-|
| fs | File system | Read/write files |
| http | Web server | Create HTTP server |
| path | Path utilities | Manipulate file paths |
| os | OS info | Get system info |
| events | Event emitter | Custom events |

```javascript
const fs = require('fs');
const path = require('path');
const http = require('http');
const EventEmitter = require('events');
```

**Example: Creating a simple HTTP server**
```javascript
const http = require('http');
const server = http.createServer((req, res) => {
    res.end('Hello from Node.js!');
});
server.listen(3000, () => console.log('Server running'));
```

**Video Reference:**  
[Node.js Modules & require](https://youtu.be/xHLd36QoS4k)

---

## **4. NPM (Node Package Manager) & package.json**<!-- {"collapsed":true} -->

NPM is the default package manager for Node.js.

- **Install a package:** `npm install express`
- **package.json** keeps track of dependencies and scripts.

```json
{
  "name": "my-app",
  "version": "1.0.0",
  "main": "index.js",
  "dependencies": {
    "express": "^4.18.2"
  },
  "scripts": {
    "start": "node index.js"
  }
}
```

**Video Reference:**  
[NPM Crash Course](https://youtu.be/jHDhaSSKmB0)

---

## **5. Asynchronous Programming in Node.js**<!-- {"collapsed":true} -->

Node.js uses callbacks, promises, and async/await for async operations.

**Callback Example:**
```javascript
fs.readFile('file.txt', 'utf8', (err, data) => {
    if (err) throw err;
    console.log(data);
});
```

**Promise Example:**
```javascript
const fs = require('fs').promises;
fs.readFile('file.txt', 'utf8')
  .then(data => console.log(data))
  .catch(err => console.error(err));
```

**Async/Await Example:**
```javascript
async function readFile() {
    try {
        const data = await fs.readFile('file.txt', 'utf8');
        console.log(data);
    } catch (err) {
        console.error(err);
    }
}
readFile();
```

**Video Reference:**  
[Async JS Crash Course](https://youtu.be/PoRJizFvM7s)

---

## **6. The Event Emitter Pattern**<!-- {"collapsed":true} -->

Node.js uses the EventEmitter class for event-driven programming.

```javascript
const EventEmitter = require('events');
const emitter = new EventEmitter();

emitter.on('greet', (name) => {
    console.log(`Hello, ${name}`);
});

emitter.emit('greet', 'Alice');
```

**Internal Working:**  
- Listeners are registered for events.
- When `.emit()` is called, all listeners for that event are invoked.

---

## **7. File System (fs) Module**<!-- {"collapsed":true} -->

**Reading and Writing Files:**
```javascript
const fs = require('fs');

// Async read
fs.readFile('file.txt', 'utf8', (err, data) => {
    if (err) throw err;
    console.log(data);
});

// Sync write
fs.writeFileSync('output.txt', 'Hello Node.js!');
```

**Streams for Large Files:**
```javascript
const readStream = fs.createReadStream('bigfile.txt');
readStream.on('data', chunk => {
    console.log('Received chunk:', chunk.length);
});
```

---

## **8. Creating a Simple Web Server**<!-- {"collapsed":true} -->

```javascript
const http = require('http');
const server = http.createServer((req, res) => {
    res.writeHead(200, {'Content-Type': 'text/plain'});
    res.end('Welcome to Node.js server!');
});
server.listen(3000, () => console.log('Server running on port 3000'));
```

---

## **9. Introduction to Express.js**<!-- {"collapsed":true} -->

Express.js is a minimal and flexible Node.js web framework.

- Simplifies routing, middleware, and error handling.
- Makes building APIs and web apps easier.

**Install:**  
`npm install express`

**Basic Example:**
```javascript
const express = require('express');
const app = express();

app.get('/', (req, res) => {
    res.send('Hello Express!');
});

app.listen(3000, () => console.log('Express server running'));
```

**Video Reference:**  
[Express.js Crash Course](https://youtu.be/L72fhGm1tfE)

---

## **10. Express.js Routing and Middleware**<!-- {"collapsed":true} -->

**Routing Example:**
```javascript
app.get('/users/:id', (req, res) => {
    res.send(`User ID: ${req.params.id}`);
});
```

**Middleware Example:**
```javascript
app.use((req, res, next) => {
    console.log(`${req.method} ${req.url}`);
    next();
});
```

**Error Handling:**
```javascript
app.use((err, req, res, next) => {
    res.status(500).json({ error: err.message });
});
```

---

## **11. REST APIs with Express.js**<!-- {"collapsed":true} -->

**CRUD Example:**
```javascript
let items = [];

app.get('/items', (req, res) => res.json(items));
app.post('/items', (req, res) => {
    items.push(req.body);
    res.status(201).json(req.body);
});
app.put('/items/:id', (req, res) => {
    items[req.params.id] = req.body;
    res.json(req.body);
});
app.delete('/items/:id', (req, res) => {
    items.splice(req.params.id, 1);
    res.status(204).end();
});
```

---

## **12. Connecting to a Database (MongoDB Example)**<!-- {"collapsed":true} -->

```javascript
const mongoose = require('mongoose');
mongoose.connect('mongodb://localhost/myapp');

const userSchema = new mongoose.Schema({ name: String, email: String });
const User = mongoose.model('User', userSchema);

app.post('/users', async (req, res) => {
    const user = new User(req.body);
    await user.save();
    res.status(201).json(user);
});
```

---

## **13. Security Best Practices**<!-- {"collapsed":true} -->

- Use `helmet` for HTTP headers
- Use `cors` for cross-origin requests
- Validate user input
- Use environment variables for secrets

```javascript
const helmet = require('helmet');
const cors = require('cors');
app.use(helmet());
app.use(cors());
```

---

## **14. Useful Tools and Debugging**<!-- {"collapsed":true} -->

- Use `nodemon` for auto-reloading: `npm install -g nodemon`
- Use `console.log`, `debug`, or VSCode debugger for troubleshooting

---

## **15. Deployment Basics**<!-- {"collapsed":true} -->

- Use `pm2` for process management
- Deploy on platforms like Heroku, Vercel, or DigitalOcean

---

## **16. Further Learning and References**<!-- {"collapsed":true} -->

- [Node.js Official Docs](https://nodejs.org/en/docs/)
- [Express.js Official Docs](https://expressjs.com/)
- [The Net Ninja Node.js Playlist](https://www.youtube.com/playlist?list=PL4cUxeGkcC9jLYyp2Aoh6hcWuxFDX6PBJ)
- [Academind Node.js Playlist](https://www.youtube.com/playlist?list=PL55RiY5tL51q4D-B63KBnygU6opNPFk_q)

---

> **Tip:** Practice by building small projects like a REST API, a CLI tool, or a real-time chat app!

---
