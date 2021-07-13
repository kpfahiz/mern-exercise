**Install nodemon in Globally**
===========================
npm install -g nodemon 

	  Create Server
		=============
Create server.js inside of backend folder.And enter the code inside the server.js:

const express = require('express');
const cors = require('cors');

require('dotenv').config();

const app = express();
const port = process.env.PORT || 5000;

app.use(cors());
app.use(express.json());

app.listen(port,() =>{
    console.log(`Server is running on port: ${port}`);
});


Start Server
============
`nodemon server`

		Create MongoDB
		==============

1)Register on mangodb.com
2) Create Cluster 
		Connect DB
		==========
const mongoose = require('mongoose');


const uri = process.env.ATLAS_URI;
mongoose.connect(uri,{ useNewUrlParser: true, useCreateIndex: true });

const connection = mongoose.connection;
connection.once('open',() => {
  console.log("MongoDB database connection established successfully");
 })


Create env
==========
create a .env folder inside of backend folder type following below:

ATLAS_URI = mongodb+srv://fahiz:<password>@cluster0.h0vna.mongodb.net/myFirstDatabase?retryWrites=true&w=majority


Create Models
=============
create models folder in backend folder.


Create Api
==========
1)create api folder in backend folder and create files(apis)
2)mention the apis in server:
   const apiname = require('./apifoldername/api');

   app.use('/api',apiname);



Install Axios in React to send data to backend
==============================================
npm install axios
