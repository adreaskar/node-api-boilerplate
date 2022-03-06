# Node.js API Server Boilerplate using Express 
A boilerplate/starter project for quickly building APIs using Node.js with Express.

This repository was created for personal convenience and it is based on my way of building express projects.

## Setup
Starting a node project on the current directory:
```bash
npm init
```

Creating the main application file:
```bash
touch app.js
```

Installing dependencies: 
```bash
sudo npm install -g nodemon   # automatically restarts the node application when file changes are detected
npm i express body-parser ejs
```

## app.js
```javascript
//jshint esversion:6
const express = require("express");
const bodyParser = require("body-parser");

const app = express();
app.set('view engine', 'ejs');
app.use(bodyParser.urlencoded({extended:true}));
app.use(express.static("public"));

app.route("/")
    .get((req,res) => {
        res.render("index");
    })
    .post((req,res) => {
    });

const server = app.listen(3000, function () {
    console.log('Started on port 3000');
});
```

## Project Structure
```
project
 |--public\         # Static files directory
 |----css\          # Directory for all .css files
 |----js\           # Directory for all .js files
 |----views\        # Directory for all .ejs files
 |--app.js          # Express app
 ```
