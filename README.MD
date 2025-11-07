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
