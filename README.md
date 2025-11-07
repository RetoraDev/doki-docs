# DokiDocs Web Documentation

## Key Features:

1. Dual Environment Support: Works in both Node.js and browsers
2. Extensible Tag System: Register custom tags with registerTag()
3. Syntax Highlighting: Integrated with Google's Prettify.js
4. Table Support: Easy table syntax with header support
5. Media Support: Images, videos, iframes
6. Styling: Comprehensive CSS with dark mode support
7. No Dependencies: Self-contained

## Usage:

### Browser

Include the CSS and JS files, then use DokiDocs syntax in your HTML.

```javascript
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>DokiDocs Example</title>
    <link rel="stylesheet" href="doki-docs.css">
</head>
<body class="doki-hidden">
    [title: "My Documentation"]
    
    [heading: "Introduction"]
    
    [subheading: "Code Example"]
    [codeblock js]
function helloWorld() {
  console.log("Hello, World!");
  return true;
}
    [/codeblock]

    [subheading: "Table Example"]
    [table header]
    [ Name | Age | Occupation ]
    [ John Doe | 30 | Developer ]
    [ Jane Smith | 25 | Designer ]
    [/table]
    
    [note: "This is an important note!"]
    
    [warning: "Be careful with this operation!"]
    
    [image: "https://picsum.photos/400/200" alt="Example image" width=400px]
    <script src="doki-docs.js"></script>
</body>
</html>
```

You can also import it from [jsDelivr](https://www.jsdelivr.com/package/npm/doki-docs)
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/RetoraDev/doki-docs@main/doki-docs.css">
<script src="https://cdn.jsdelivr.net/gh/RetoraDev/doki-docs@main/doki-docs.js"></script>
```

### Node.js:

You can require DokiDocs as a module. Note that it is made for browser environments where `document` is defined, for example nw.js or a website served with Node.JS.

There are two main ways to import Dokidocs:

#### Importing from NPM

Run `npm install doki-docs` then require it
```javascript
const DokiDocs = require('doki-docs');
```

#### Importing from the source file
Simply import the js file as a module
```javascript
const DokiDocs = require('./doki-docs.js');
```

Then you can use it on Node

```javascript
const DokiDocs = require('./doki-docs.js');
const doki = new DokiDocs();

// Parsing Doki markup
const html = doki.parse('[title: "Hello World"]');
```
The framework automatically processes the document when loaded in a browser and provides a clean API for programmatic use in Node.js.

### Required file structure

DokiDocs expects some important files to be in their place, following the following structure:
```plaintext

├── doki-docs.css        # Core styling for DokiDocs components and themes
├── prettify
│   ├── prettify.css     # Syntax highlighting styles for code blocks
└   └── prettify.js      # Google's code prettifier for syntax highlighting
```

# License

**DokiDocs**: MIT License

**Prettify.JS**: http://code.google.com/p/google-code-prettify/ - Apache License 2.0 (http://www.apache.org/licenses/LICENSE-2.0)