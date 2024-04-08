# react-node-init
How to Setup React & Node JS

React

to start react project simple run below commond

npx create-react-app {appName}

Node JS

npm init -y // tihs will create package.js file for node server
npm install express mysql cors nodemon // required npm packages

1) make new server.js file 
2) in package json file add this line in "scripts" after "test" : "start" : "nodemon server.js"

// server js
const express = require('express');
const mysql = require('mysql');
const cors = require('cors');

const app = express();
app.use(express.json());
app.use(cors());

const db = mysql.createConnection({
  host: config.DB_HOST,
  user: config.DB_USER,
  password: config.DB_PASSWORD,
  database: config.DB_NAME
});

app.get("/", (req, res) => {
  return res.json("From backend side");
});

app.listen(7072, () => {
  console.log("Server Listen on Port : 7072");
});

