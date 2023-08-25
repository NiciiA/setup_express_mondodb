# Setting Up a REST API with Node.js and Express
## Introduction
Creating a robust and efficient REST API is a crucial aspect of modern web development. In this guide, we will walk through the process of setting up a RESTful API using Node.js and the Express framework. We will cover the basics of routing, handling requests and responses, as well as integrating data storage using a MongoDB database.

## Prerequisites
Before we begin, ensure you have the following tools installed:

- Node.js (version 12 or later)
- npm (Node Package Manager)
- MongoDB

## Step 1: Project Initialization
1. Open your terminal and navigate to the desired project directory.
2. Run the following command to create a new Node.js project: npm init -y
3. Install the Express framework by running: npm install express

## Step 2: Creating the Server
1. Create a new file named server.js.
2. Import Express and initialize the application:
```javascript
const express = require('express');
const app = express();
```
3. Define a route for the root URL that sends a basic message:
```javascript
app.get('/', (req, res) => {
    res.send('Welcome to our REST API');
});
```
4. Start the server on a specified port (e.g., 3000):
```javascript
const PORT = process.env.PORT || 3000;
app.listen(PORT, () => {
    console.log(`Server is running on port ${PORT}`);
});
```

## Step 3: Handling Routes
1. Create a new directory named routes in your project folder.
2. Inside the routes directory, create a file named api.js.
3. Import Express and create a router instance:
```javascript
const express = require('express');
const router = express.Router();
```
4. Define routes within the router using the HTTP methods (GET, POST, PUT, DELETE):
```javascript
router.get('/products', (req, res) => {
    // Retrieve and send a list of products
});

router.post('/products', (req, res) => {
    // Create a new product
});
```
5. Export the router to make it accessible in other parts of the application:
```javascript
module.exports = router;
```

## Step 4: Integrating MongoDB
1. Install the mongoose library to interact with MongoDB: npm install mongoose
2. In your server.js file, import and connect to your MongoDB database:
```javascript
const mongoose = require('mongoose');

mongoose.connect('mongodb://localhost/mydatabase', {
    useNewUrlParser: true,
    useUnifiedTopology: true
}).then(() => {
    console.log('Connected to MongoDB');
}).catch((error) => {
    console.error('Error connecting to MongoDB:', error);
});
```

## Conclusion
Congratulations! You have successfully set up a basic REST API using Node.js and Express. You've learned how to handle routes, manage HTTP requests and responses, and integrate MongoDB for data storage. This foundation can be extended to build more complex and feature-rich APIs for your web applications.

Remember that this guide covers only the essentials. As you continue your journey in web development, you can explore authentication, error handling, middleware, and other advanced topics to create powerful and scalable APIs.
