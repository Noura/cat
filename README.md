Connect Anything
================

ConnectAnyThing helps people prototype connected physical systems of inputs and outputs on the Galileo board without having to write code.

This repo is the front end code of that application. It  periodically gets ported over to https://github.com/IntelOpenDesign/ConnectAnyThing

For more information about this project, please see https://github.com/IntelOpenDesign/ConnectAnyThing

Setup Option 1: Galileo
-----------------------
Please follow the instructions at https://github.com/IntelOpenDesign/ConnectAnyThing

Setup Option 2: Localhost
-------------------------
Though the real purpose of this project is to create interconnected physical systems, which requires the Galileo hardware, during front end development it's helpful to just work using localhost, with test-server.js substituting for the Galileo's web server.

Requirements:
* node (I am on 0.10.29), nodejs-websocket
* Python (I am on 2.7.2)

Steps:
1. There are some connection settings near the top of static/js/app.js
  a. cat.on_hardware = false
  b. If you just want to test on your local machine, set cat.test_server_url = 'ws://localhost:8001'. If you want other devices to connect to your local machine, set cat.test_server_url = 'ws://<local IP>:8001', where you can find your machine's local IP address with the ifconfig shell command
2. In the terminal run: node test-server.js
3. Simultaneously also run: python -m SimpleHTTPServer
4. Navigate to http://localhost:8000 or http://<local IP>:8000 depending on (1)(b). Please note that only Chrome is offically supported.
