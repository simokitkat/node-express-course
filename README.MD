# 📝 Node.js & Express Fundamentals

## What is Node.js?

- Node.js is an environment that allows you to run JavaScript outside of the browser.
- It was built on Chrome's V8 JavaScript engine, which is the tool in the browser that compiles JavaScript to machine code. The creator of Node essentially "ripped out" this engine so it could run independently.
- A primary benefit is the ability to build full-stack applications (both frontend and backend) using a single language: JavaScript.

## Browser vs. Server: The Key Differences

Understanding what Node _cannot_ do is essential for beginners. Node.js is a server-side environment, not a browser.

### What Node.js Does NOT Have

- You have **no access** to browser-specific APIs.
- There is no **`window`** object.
- There is no **`document`** object, which means you cannot use methods like `document.querySelector`.
- There is no **`fetch`** (the browser's built-in version) or **`geolocation`**.
- Node applications consist of "pure logic" and do not have a graphical interface.

### What Node.js Offers Instead

- You can access the **file system** (to read or write files).
- You can get info about the **operating system (OS)**.
- You can create a server that **responds to network requests**.
- **Stable Versioning:** A Node app depends on the Node.js version it was built with, not on a user's browser version. You can keep running an app on an older Node version without being forced to upgrade.
- **Modules by Default:** Unlike in a browser, modules are a default feature in Node.js. It uses the CommonJS library for modules, which has a slightly different syntax than the ES6 modules you may be used to.

## Installation and Setup

- Navigate to **`nodejs.org`**.
- Download and install the **LTS (Long Term Support)** version, as this is recommended for production applications.
- Always install the _current_ LTS version offered on the site, even if it's newer than the one shown in the tutorial. The content will still work.
- To verify the installation, open your terminal and type `node -v` (or `node --version`). If you see a version number, you are ready to go.
- If the installation fails, you will need to use a search engine to troubleshoot the error for your specific setup.

## How to Run Node.js Code

There are two ways to evaluate your Node.js code.

### Option 1: REPL (The "Playground")

The REPL (Read-Eval-Print Loop) is a console for quickly "playing around" with JavaScript code outside of a file.

1.  Open your terminal and type `node`.
2.  You will see a `>` prompt.
3.  You can now type JavaScript, such as `const name = 'john'`, and press Enter to evaluate it.
4.  To exit the REPL, press `Control + C` twice.

### Option 2: CLI (The "Serious" Way)

The Command Line Interface (CLI) is how you will run your actual applications.

1.  Create a new folder for your project (e.g., `my-tutorial`).
2.  Open this folder in your code editor (like VS Code).
3.  Create a new file, such as `app.js`.
4.  Write your JavaScript program inside `app.js`. For example:

    ```javascript
    const amount = 12;

    if (amount < 10) {
      console.log('small number');
    } else {
      console.log('large number');
    }

    console.log('hey it's my first node app');
    ```

5.  To run this file, open your terminal and navigate to your project folder.
6.  Type `node app.js` and press Enter.
7.  The output (`large number` and `hey it's my first node app`) will be printed directly to your terminal.

> **Pro Tip:** Use your code editor's integrated terminal (in VS Code, the shortcut is `Control + ~`). It opens directly in your project folder, so you can skip the navigation step and just run `node app.js`.
> Here is the summary of the next section of the tutorial, covering globals and the module system.

## Global Variables in Node.js

Unlike in browser JavaScript where you have a `window` object, Node.js does not have a `window`. Attempting to access `window` will throw an error and crash your app.

However, Node provides its own set of **global variables** that are accessible anywhere in your application, no matter how nested your files are.

Here are the most important ones to know:

- `**__dirname`\*\*: Provides the path to the current directory (folder).
- `**__filename`\*\*: Provides the file name (including the full path).
- `**require`\*\*: A function used to import modules (we'll cover this next).
- `**module`\*\*: An object that contains information about the current module (file).
- `**process`\*\*: A powerful object that provides information about the environment where the program is currently executing. This is useful for making decisions based on whether your app is in development or on a production server (like Heroku or Digital Ocean).

Other globals you might recognize from the browser are also available, such as `console`, `setInterval`, and `setTimeout`.

### Useful Terminal Tips

- **Run Command:** You can run your app by typing `node app.js` or just `node app`.
- **Command History:** In your terminal, press the **Up Arrow** key to cycle through your previous commands.
- **Clear Console:** Type `clear` to clear your terminal screen.

### A Note on `node app.js`

You've probably noticed it's annoying to stop (`Ctrl+C`) and restart (`node app.js`) your app every time you make a change. This is temporary. Later in the course, we will install an external package (using NPM) that automatically restarts the application for you whenever you save a file.

## Node.js Modules

The most important concept in Node is its module system.

### Why Use Modules?

Does all your code have to be in one `app.js` file? No. That would be "literally insane" for a real application.

The solution is to **split your code into modules** (i.e., separate files) and import them when needed. This keeps your code organized, structured, and in smaller, more manageable files.

### How Modules Work: CommonJS

Node.js uses the **CommonJS** module system. The rules are simple:

1.  **Every file is a module**.
2.  **Modules are encapsulated (private)**. By default, variables and functions created in a file are _not_ accessible from any other file. This prevents conflicts and keeps your code clean.

#### 1\. Exporting (Sharing Code)

To make code available to other files, you must explicitly **export** it.

When you `console.log(module)`, you'll see it's an object with a property called `exports`, which is itself an empty object: `exports: {}`.

**Whatever you add to this `module.exports` object is what you can share**.

**Example:** Let's split our app. We'll move our variables to `names.js` and our function to `utils.js`.

**`4-names.js`**

```javascript
// This variable stays LOCAL to this file
const secret = "SUPER SECRET";
// These variables will be SHARED
const john = "john";
const peter = "peter";

// We attach our shared variables to the exports object
module.exports = { john, peter };
```

**`5-utils.js`**

```javascript
const sayHi = (name) => {
  console.log(`Hello there ${name}`);
};

// When exporting a single item, we can set module.exports to it directly
module.exports = sayHi;
```

#### 2\. Importing (Using Code)

To use code from another module, you use the global `require` function.

**Crucial Rule:** When importing your _own_ modules, the path **must** start with `./`. If you just write `require('names')`, Node will look for a built-in module or a third-party package. You can omit the `.js` file extension.

**`app.js`**

```javascript
// Import the object from 'names.js'
const names = require("./4-names.js");
// Import the function from 'utils.js'
const sayHi = require("./5-utils.js");

// 'names' is now the object: { john: 'john', peter: 'peter' }
sayHi("susan");
sayHi(names.john);
sayHi(names.peter);

// This would fail, because 'secret' was not exported
// console.log(names.secret);
```

### Alternative Export Syntax

Because `module.exports` is just an object, you can also add properties to it one by one. This is functionally the same.

**`6-alternative-flavor.js`**

```javascript
// Add 'items' as a property on the exports object
module.exports.items = ["item1", "item2"];
// Add 'singlePerson' as another property
module.exports.singlePerson = { name: "bob" };
```

When you `require('./6-alternative-flavor.js')`, you'll get an object with both `items` and `singlePerson`.

### Mind Grenade: Importing a Module _Executes_ It

What happens if you import a file that doesn't export anything, but just runs a function?

**`7-mind-grenade.js`**

```javascript
const num1 = 5;
const num2 = 10;

function addValues() {
  console.log(`the sum is : ${num1 + num2}`);
}

// The function is INVOKED inside this file
addValues();
```

**`app.js`**

```javascript
// We just require the file, we don't even assign it to a variable
require("./7-mind-grenade.js");
```

When you run `node app.js`, your console will show **"the sum is : 15"**.

**Why?** When you `require` a module, you aren't just _accessing_ its exports; you are **invoking the file**. Any code in the global scope of that file (like the `addValues()` function call) will run the moment it is imported.
Here's the summary for the next section on built-in modules.

## Built-In Modules

Node.js comes with many powerful, built-in modules that you can use freely in your apps. This section will cover the general setup for using them and introduce a few of the most important ones, including OS, Path, File System (FS), and HTTP.

The full list of modules is massive, so we won't cover every property and method. If you want to learn more, the official Node.js documentation (`nodejs.org`) has extremely detailed information on every module.

### General Setup for Built-in Modules

To use a built-in module, you must `require` it by its name.

- **You do not need to install it**.
- **You do not use `./`**. Unlike your own modules, you just use the module's name in the string (e.g., `require('os')`). Node knows this means you are looking for a built-in module.

```javascript
// Example of requiring a built-in module
const os = require("os");
```

Once imported, you can access all its methods from the variable (e.g., `os.uptime()`) or destructure specific methods you need.

### 1\. `os` (Operating System) Module

This module provides properties and methods for interacting with the operating system and the server.

- `const os = require('os')`
- **Key Methods:**
  - `os.userInfo()`: Returns information about the current user, like their home directory.
  - `os.uptime()`: Returns the system uptime (how long the computer has been running) in seconds.
  - `os.type()`: Returns the name of the operating system (e.g., "Darwin" for macOS, "Windows_NT" for Windows).
  - `os.release()`: Returns the operating system's release version.
  - `os.totalmem()`: Returns the total amount of system memory in bytes.
  - `os.freemem()`: Returns the amount of free system memory in bytes.

### 2\. `path` Module

This module is very useful as it allows you to interact with file paths in a reliable, platform-independent way.

- `const path = require('path')`
- **Key Properties & Methods:**
  - `path.sep`: Returns the platform's specific path separator (e.g., `/` for Mac/Linux, `\` for Windows).
  - `path.join()`: Joins a sequence of path segments together using the platform-specific separator. It also returns a "normalized" path, which cleans up extra slashes (`//`) automatically.
    - _Example:_ `const filePath = path.join('/content/', 'subfolder', 'test.txt')`.
  - `path.basename(filePath)`: Returns the last portion of a path (e.g., `test.txt`).
  - `path.resolve()`: This is a critical method. It resolves a sequence of paths into an **absolute path**. This is essential because the path to a file on your local machine will be different from the path on a production server. Using `__dirname` with `path.resolve` ensures you always have a correct, absolute path to your resources.
    - _Example:_ `const absolute = path.resolve(__dirname, 'content', 'subfolder', 'test.txt')`.

### 3\. `fs` (File System) Module

Node.js has a built-in module for interacting with the file system, named `fs`.

This module has two "flavors" for its methods:

1.  **Synchronous (Blocking):** The operation runs, and your code stops and waits for it to finish before moving to the next line.
2.  **Asynchronous (Non-blocking):** The operation starts, and your code immediately moves to the next line, without waiting. The operation's result is handled later in a callback function.

We will cover both, starting with the synchronous (blocking) approach.

### File System: Synchronous (Sync) Methods

These methods are **blocking**. They are generally _not_ recommended for servers because they stop all other code from executing, which means your server cannot handle any other users until the task is complete.

You can import (destructure) the specific methods you need from the `fs` module.

```javascript
const { readFileSync, writeFileSync } = require("fs");
```

#### `readFileSync(path, encoding)`

This method reads the contents of a file.

- **`path`**: The path to the file you want to read (e.g., `./content/first.txt`).
- **`encoding`**: Tells Node how to interpret the file's data. Without this, you'll get a raw `buffer`. Use `utf-8` for text files.

```javascript
// Read the contents of two files
const first = readFileSync("./content/first.txt", "utf-8");
const second = readFileSync("./content/second.txt", "utf-8");

console.log(first, second);
```

#### `writeFileSync(path, value, [options])`

This method writes content to a file.

- **`path`**: The file you want to write to. If the file does not exist, Node will create it.
- **`value`**: The content (e.g., a string) you want to write into the file.

**By default, `writeFileSync` will completely overwrite the file's contents**.

```javascript
// This will create 'result-sync.txt' and put the content of 'first' and 'second' inside it
writeFileSync(
  "./content/result-sync.txt",
  `Here is the result: ${first}, ${second}`
);
```

To **append** to a file instead of overwriting it, pass a third argument (an options object) with the `flag` property set to `'a'`.

```javascript
// This will ADD "hello world" to the end of the file
writeFileSync("./content/result-sync.txt", "hello world", { flag: "a" });
```

### File System: Asynchronous (Async) Methods

This is the **non-blocking** approach and is what you should use for servers.

These methods work by using **callback functions**. A callback is a function you provide that Node will run _only when the task is complete_.

```javascript
const { readFile, writeFile } = require("fs");
```

#### `readFile(path, encoding, callback)`

- **`path` / `encoding`**: Same as the sync version.
- **`callback`**: The function to run when the file has been read. This callback function _must_ accept two parameters: `(err, result)`.
  - **`err`**: Will be `null` if everything worked, or an error object if it failed.
  - **`result`**: The content of the file (if successful).

**Important:** Always check for the error first.

```javascript
console.log("start");

readFile("./content/first.txt", "utf-8", (err, result) => {
  if (err) {
    console.log(err);
    return;
  }
  console.log(result);
  console.log("done with this task");
});

console.log("starting next task");
```

### Sync vs. Async: The "Why"

The difference in execution order is the most important concept in Node.js.

- **When you run the _Sync_ code:**
  1.  `console.log('start')`
  2.  `readFileSync` **blocks** the code. The app _waits_.
  3.  `console.log('done with this task')`
  4.  `console.log('starting next task')`
- **When you run the _Async_ code:**
  1.  `console.log('start')`
  2.  `readFile` starts and **"offloads"** its task.
  3.  The code _does not wait_. It immediately continues to the next line.
  4.  `console.log('starting next task')`
  5.  Sometime later, the file reading finishes. The callback function is _finally_ executed.
  6.  `console.log(result)`
  7.  `console.log('done with this task')`

This non-blocking model allows your server to "offload" time-consuming tasks (like reading files or database queries) and continue serving other users in the meantime.

#### The Problem: "Callback Hell"

The async approach is better, but it has a major downside. What if you need to read one file, _then_ read a second file, _then_ write a third file?

You are forced to nest your callbacks inside each other, creating a messy, hard-to-read "pyramid" structure.

```javascript
// This is "Callback Hell"
readFile('./content/first.txt', 'utf-8', (err, result) => {
  if (err) { ... }
  const first = result;
  readFile('./content/second.txt', 'utf-8', (err, result) => {
    if (err) { ... }
    const second = result;
    writeFile('./content/result-async.txt', `...`, (err, result) => {
      if (err) { ... }
      console.log('Task complete');
    });
  });
});
```

This nesting is a pain. Later, the course will show you how to solve this using **Promises** and **Async/Await**.

### 4\. The `http` Module (Your First Web Server)

This section covers the basics of the built-in `http` module, which is what allows Node.js to set up a web server.

While a large part of the course will use **Express.js** (which is an abstraction, or a simpler way to work with the `http` module), it's important to understand the fundamentals first.

### Basic Server Setup

1.  **Require the module:**

    ```javascript
    const http = require("http");
    ```

2.  **Create the server:**
    The `http.createServer()` method is used to create a server instance. This method takes a callback function that executes _every time_ a user hits your server.

    This callback function provides two crucial parameters, commonly named `req` and `res`:

    - `req` (Request): This object represents the **incoming request** from the client (e.g., the browser). It contains information like the URL the user is trying to access and the method (e.g., GET).
    - `res` (Response): This object is what you use to **send a response back** to the client.

3.  **Listen for requests:**
    After creating the server, you must tell it to "listen" on a specific port. The port number is arbitrary in development (e.g., 5000), but it's the "door" that your server listens through.

### Example: A Simple Server

```javascript
const http = require("http");

const server = http.createServer((req, res) => {
  // This code runs for every request

  // 1. Write the response
  res.write("Welcome to our homepage");

  // 2. End the response (THIS IS MANDATORY)
  res.end();
});

server.listen(5000);
```

To run this:

1.  Save the code as `app.js`.
2.  Run `node app.js` in your terminal.
3.  Notice that your program does **not** exit. The server is now running and "listening" for requests.
4.  Open your browser and go to `localhost:5000`. You will see "Welcome to our homepage".

### Basic Routing with `req.url`

You can send different responses based on the URL the user is visiting. This information is available in the `req.url` property.

- The homepage (root) is `/`.
- An "about" page would be `/about`.

You can use an `if` statement to check the URL and send different content. You can also send HTML directly.

```javascript
const http = require("http");

const server = http.createServer((req, res) => {
  const url = req.url;

  // Home Page
  if (url === "/") {
    res.end("Welcome to our home page");
  }

  // About Page
  else if (url === "/about") {
    res.end("Here is our short history");
  }

  // 404 - Page Not Found
  else {
    // You can write HTML directly in the response
    res.end(`
      <h1>Oops!</h1>
      <p>We can't seem to find the page you are looking for</p>
      <a href="/">back home</a>
    `);
  }
});

server.listen(5000);
```
