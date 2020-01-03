# API-TEMPLATE-NODEJS-EXPRESS
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
- Create .gitignore file https://www.gitignore.io/api/node