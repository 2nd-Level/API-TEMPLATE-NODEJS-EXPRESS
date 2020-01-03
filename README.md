# API-TEMPLATE-NODEJS-EXPRESS

###Start with a simple nodejs server
- Started File Structure
  ![GitHub Logo](/images/filestructure.png)
- inside of index.js
    *       const http = require('http'); 

                const hostname = '127.0.0.1';
                const port = 3000; 

                const server = http.createServer((req, res) => {
                res.statusCode = 200; 
                res.setHeader('Content-Type', 'text/plain'); 
                res.end('Hello World from Node\n'); 
                });

                server.listen(port, hostname, () => {
                
                console.log(`Server running at http://${hostname}:${port}/`);
                });
    *   node index.js, to start server, Open a browser and visit: http://localhost:3000; localhost and the ip address 127.0.0.1 point to the same thing: your local computer. The browser should show the message: “Hello World from Node”. There you have it,a web server, built from scratch using nothing but Node.js.


###Add more code to get Simple Server With Express
- Create .gitignore file https://www.gitignore.io/api/node
- Create package.json npm init -y
- Change Script object in package.json
    *       "scripts": {
                "start": "node index.js",
                "server": "nodemon index.js"
            },       
- Install express, dotenv and helmet `npm install express dotenv helmet`
- Install nodemon as dev dependency `npm install nodemon -D`
- Inside of api folder add server.js file
    *       const express = require('express');
                const helmet = require('helmet');



                const server = express();
                server.use(helmet())

                module.exports = server;  
- Re configure the index.js file
    *       require('dotenv').config()
            const server = require('./api/server.js');
            server.get('/', (req, res) => {
                res.send('HELLO, YOU HAVE ENTERED MY SERVER')
            })

            const port =process.env.PORT || 4000
            server.listen(port, () => console.log(`\n*** Server Running on http://localhost:${port} ***\n`))
- `npm start`

