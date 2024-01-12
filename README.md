<h1 align="center">Express JS Snippet 👋</h1>

This repository contains a Visual Studio Code snippet for quickly setting up a basic structure for an Express.js application. Ideal for developers looking to jumpstart their Express.js projects.

Give a ⭐️ if this project helped you!

## Snippet Description

The `express-app` snippet provides a foundational setup for a new Express.js application, including essential middleware, a basic route, and a simple 404 error handler. It's a great starting point for building web applications and APIs.

![video](https://github.com/cipotemanx/express-js-snippet/assets/53237299/0df73529-c548-4d1d-8465-0fcf696eb9b0)


## Installation

To use this snippet in Visual Studio Code, follow these steps:

1. Open Command Palette in VSCode (`Ctrl+Shift+P` on Windows/Linux, `Cmd+Shift+P` on macOS).
2. Type `Configure User Snippets` and select it.
3. Choose `JavaScript.json` (for JavaScript) or `TypeScript.json` (for TypeScript).
4. Paste the following JSON snippet into your chosen file:

   ```json
    {
        "Express Basic Template": {
            "prefix": "express-app",
            "body": [
                "const express = require('express');",
                "const morgan = require('morgan');",
                "",
                "const app = express();",
                "",
                "app.use(express.static('public'));",
                "",
                "// Settings",
                "app.set('appName', 'YourProject');",
                "app.set('port', 80)",
                "app.set('view engine', 'ejs')",
                "",
                "// Middleware",
                "app.disable('x-powered-by');",
                "app.use(express.json());",
                "app.use(express.urlencoded({ extended: true }));",
                "app.use(morgan('dev'));",
                "",
                "// ROUTES",
                "app.get('/', (req, res) => {",
                "    res.render('index', { title: 'YourProject' });",
                "})",
                "",
                "// 404 NOT_FOUND ROUTE",
                "app.use((req, res, next) => {",
                "    res.status(404).send();",
                "});",
                "",
                "app.listen(app.get('port'), () => {",
                "    console.log(`${app.get('appName')} - Server on port:`, app.get('port'));",
                "})"
            ],
            "description": "Basic Express Server Setup"
        }
    }
