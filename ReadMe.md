3D Rendering Web App/API using SHP File
This is a repository for a web application and API for 3D rendering using SHP (shape) files. The application allows users to upload their SHP files, visualize them in 3D, and customize their appearance. The API allows developers to incorporate 3D rendering functionality into their own applications.

Table of Contents
Installation
Usage
API Documentation
Contributing
License
Installation
To install the web application and API, follow these steps:

Clone this repository to your local machine.
Navigate to the root directory of the repository in your command prompt or terminal.
Install the required dependencies by running npm install.
Create a .env file in the root directory with the following environment variables:
PORT: The port number on which the server should listen.
DB_CONNECTION_STRING: The connection string for your MongoDB database.
Start the server by running npm start.
Usage
To use the web application, navigate to the URL where the server is running (e.g. http://localhost:3000) in your web browser. From there, you can upload your SHP file and customize its appearance using the provided tools.

To use the API, make requests to the appropriate endpoints using the HTTP method and parameters specified in the API documentation (see below).

API Documentation
The API provides the following endpoints:

GET /api/objects
Returns a list of all objects in the database.

Query Parameters:

name: (optional) Filter objects by name.
Example Request:

bash
Copy code
GET /api/objects?name=myObject
Example Response:

css
Copy code
[  {    "name": "myObject",    "vertices": [...],
    "faces": [...]
  },
  ...
]
POST /api/objects
Uploads a new object to the database.

Request Body:

name: The name of the object.
file: The SHP file to upload.
Example Request:

css
Copy code
POST /api/objects
Content-Type: multipart/form-data; boundary=------------------------<boundary>

--------------------------<boundary>
Content-Disposition: form-data; name="name"

myObject
--------------------------<boundary>
Content-Disposition: form-data; name="file"; filename="myObject.shp"
Content-Type: application/octet-stream

<file contents>
--------------------------<boundary>
Example Response:

json
Copy code
{
  "name": "myObject",
  "vertices": [...],
  "faces": [...]
}
GET /api/objects/:name
Returns the object with the specified name.

Path Parameters:

name: The name of the object to retrieve.
Example Request:

bash
Copy code
GET /api/objects/myObject
Example Response:

json
Copy code
{
  "name": "myObject",
  "vertices": [...],
  "faces": [...]
}
Contributing
If you'd like to contribute to this repository, please follow these steps:

Fork this repository to your own GitHub account.
Create a new branch for your changes.
Make your changes and commit them to your branch.
Push your branch to your forked repository.
Create a pull request from your branch to the main branch of this repository.