# Reverse Engineered Sequelize ORM Code

In this tutorial we will delve into the codebase of a functioning application and the . The necessary starter code for a basic project has been provided for you. Within the Develop folder, there are subfolders containing the files that will be called upon to execute the application. 

It must be noted that this tutorial is specific for Windows platform only. The specific tools used in this walk through are Visual Studio Code, My SQL Workbench and GitHub.

The first topic that needs to be reviewed is the file dependencies. We will start with the first folder in the Develop folder and work our way through them sequentially.

### Config folder:

#### mMddleware folder:
* isAuthenticated.js - standard Connect middleware which restricts routes a user is not allowed to access if they are not logged in. If authentication is successful (i.e. logged in), the user is directed to the restricted route (members.html)
* config.json - loads configuration to connect to server
* passport.js - contains javascript logic that is used to authenticate requests. In our case, telling passport we want to log in with an email address and password

#### Models folder:
* index.js - connects to database via the config.js code and imports users log in data
* user.js - script that defines and secures the user data in the  “passport_demo” database. The user model requires "bcrypt" for password hashing

#### Public folder:
* Login.html, members.html, and signup.html are the general front-end framework. They define the layout of the html page, and require respective js and css files 

##### Js folder:
* login.js, members.js, and signup.js files - general javascript that defines the functionalities of the html elements  

##### Stylesheets folder:
* style.css - defines the general styling of the html pages

#### Routes folder:
* api-routes.js - define the routes for signing up, logging in/out and requesting user data. It requires the passport.json file (see folder 1) and the model.js files (see folder 2), to display the user data on the client side
* html-routes.js - verifies if the user has an account, if they are signed in/out, or needs to create an account, and directs them to the respective html page. It requires the  isAuthenticated.js file (folder 1) to authenticate user credentials

#### Additional files in the Develop folder:
* package.json - contains all package info, node modules used, version info, etc
* server.js - requires the npm packages installed, middleware, model files, * route files, sets up the PORT and syncs the database.
* schema.sql - defines the basic database where user data is stored

### A Basic Codebase Tutorial

1. In VS Code, open the integrated terminal and install the following node packages by typing “npm install (node name)":
- sequelize
- express
- express-session
- bcryptjs
- passport
- passport-local
- mysql2

2. Open the config.json file, in the config folder. Under “development”, update the username and password with your personal MySQL credentials.

3. Create a file in the Develop folder named schema.sql and create a database called “passport-demo” using the boilerplate code. Open the file in MySQL workbench and execute the code (the yellow lightning bolt).

4. In the integrated terminal, type “node server.js”. This will connect to the server specified in the config.json file. You should see “Listening on port 8080. Visit http://localhost:8080/ in your browser.” in the terminal. This confirms that you are connected to the server.

5. To confirm that we are connected to the server, navigate to your internet browser and type the following, “http://localhost:8080” in the search bar. You should see the following html page: 

<img src="/img/confirmation.PNG" alt="confirmation screenshot">


### GITHUB URL:

https://github.com/wkgrant78/Reverse-Engineered-Sequelize-ORM-Code.git

### Google Doc URL:

https://docs.google.com/document/d/175yW7dGqul28BgJYQH3MxRf4zBIA-j1HlFtM2jWQzZQ/edit?usp=sharing
