# URL Shortener Microservice

Build a full stack JavaScript app that is functionally similar to this:https://url-shortener-microservice.freecodecamp.rocks.

This code sets up a Node.js application using the Express.js framework to create a URL shortening service. The application listens on a specified port, interacts with a MongoDB database, and provides API endpoints for shortening and redirecting URLs. Here's an overview of the code:

Module Imports:

The dotenv module is imported to load environment variables from a .env file.
The express, cors, dns, and urlparser modules are imported.
The MongoClient class from the mongodb module is imported.
MongoDB Connection:

A MongoDB client is created using the provided DB_URL from the environment variables.
A database named urlshortner is selected, and a collection named urls is obtained.
Express Application Initialization:

An instance of the Express application is created using express().
Middleware Setup:

CORS middleware is used to enable Cross-Origin Resource Sharing.
Middleware for parsing JSON and URL-encoded data is configured.
The application serves static files from the "public" directory using the /public route.
Basic Routing:

When a request is made to the root route ("/"), the server sends the "index.html" file located in the "views" directory.
URL Shortening API Endpoint:

An API endpoint (/api/shorturl) is created to handle POST requests for shortening URLs.
The url parameter is extracted from the request body.
A DNS lookup is performed to validate the URL. If the lookup fails, an error response is sent.
If the URL is valid, the current count of documents in the urls collection is retrieved.
A new document with the original URL and a short URL count is inserted into the urls collection.
The response includes the original URL and the short URL count.
URL Redirect API Endpoint:

An API endpoint (/api/shorturl/:short_url) is created to handle GET requests for redirecting short URLs.
The short_url parameter is extracted from the request params.
A query is made to the database to retrieve the document associated with the provided short URL.
The client is redirected to the original URL stored in the document.
Server Listening:

The server starts listening on the port specified in the process.env.PORT variable or on port 3000 if not provided.
A message is logged to indicate that the server is running and listening on the specified port.
In summary, this code demonstrates how to create a simple URL shortening service using Node.js, Express.js, and MongoDB. The application provides endpoints for shortening URLs and redirecting users to the original URLs.
  
# Solution Challenge
In this challenge I tried to get as close as possible to your solution:
- Live Site URL: [Replit](https://replit.com/@AndresF-Sanchez/boilerplate-project-urlshortener)

# Author

- Author - [@AndresF-SanchezG](https://github.com/AndresF-SanchezG)
- School - [Freecodecamp](https://www.freecodecamp.org/)
- Curse - [URL Shortener Microservice](https://www.freecodecamp.org/learn/back-end-development-and-apis/back-end-development-and-apis-projects/url-shortener-microservice)







