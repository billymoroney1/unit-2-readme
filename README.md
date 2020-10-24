# unit-2-readme

### Starting a Node App
In the command line, cd into your directory and use the "npm init -y" command. Omit the -y if you wish to name the entry point to something besides the default index.js.

### Node Modules

Install any node modules you need via the command line (locally) with "npm i <name of module>". To use a node module that you have installed, at the top of your entry point use require()

i.e. const express = require('express')

### Adding Express to a Node App

1. Install express via the command line (npm i express)
2. Require express in entry point (const express = require('express'))
3. Create an instance of express (const app = express())

### Express Routes

You can call methods on an instance of express (app) to define your app's routes. For example, app.get() and app.post() are common Express routes. In any of these functions, you put the URL path you are getting/posting to ('/show', '/').

### Views

Somewhere in the top of your entry point, use app.set('view engine', 'ejs'). This will enable your routes to interact with .ejs files that you place in a Views folder in your project directory.

### Templates

The .ejs files in your Views folder are templates, meaning you can fill an HTML template with javascript. To use a template, the res.render() function you will use in many of your routes takes an argument that dictates which template to choose from.

### Layouts

In your views folder, you can make a layout.ejs file with HTML boilerplate that will surround the rest of your templates. A basic layout just needs <%- body %> between the boilerplate <body> tags so that express knows to where to inject the contents of the other .ejs files you'll be using. 

### Environment Variables

A node package, dotenv, allows you to create a .env file to store global variables. For example, API_KEY=3000. In any file that you want to access these environment variables, write require('dotenv').config() as early in the file as you can. After that, any variables you defined in your .env file can be accessed with process.env.<variable name>

### gitignore

A .gitignore file tells github which files to ignore when pushing, so that you don't clutter your repository with heavy node packages. Anything you wish to ignore you just type into the file, such as node modules.

### sequelize setup

To set up sequelize, use npm to install the pg and sequelize packages. Then, in your project directory, type sequelize init in the terminal. By default, you will wind up with a config file. Make sure that the protocol corresponds to the type of database you are using (i.e. postgres) and change the names to the name of your database. Once you run sequelize db:create, you will create your database. From there, create a model for any data that you inject into that database by running sequelize model:create followed by --name <> --attributes ... Anything following attributes must not have any spaces. i.e. title:string, Once you have created your model, run the sequelize db:migrate command. 