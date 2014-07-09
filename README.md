Connect Anything
================

ConnectAnyThing helps people prototype connected physical systems of inputs and outputs on the Galileo board without having to write code.

This repo is the front end code of that application. It  periodically gets ported over to https://github.com/IntelOpenDesign/ConnectAnyThing

For more information about this project, please see https://github.com/IntelOpenDesign/ConnectAnyThing

How to get up and running with this code
----------------------------------------

### Requirements
* node (I am on 0.10.29), nodejs-websocket
* Python (I am on 2.7.2)

### Server setup
Change the server settings near the top of static/js/app.js depending on your use case.
* If you are testing on the Galileo, just change cat.on_hardware to true and follow the setup instructions on https://github.com/IntelOpenDesign/ConnectAnyThing
* If you are hosting test-server.js on your local machine, then cat.on_hardware should be false. To test only on your local machine, and no other devices, no internet connection is required and you can set cat.test_server_url = 'ws://localhost:8001'. If you want to use other devices too, you need internet, and change the <localhost> part to be your local machine's internal IP address, which you can find with the ifconfig command.

### Running it
* To run it on the Galileo, follow the instructions at https://github.com/IntelOpenDesign/ConnectAnyThing
* To run with test-server.js, in this directory, on two command lines, get both going at the same time:
    - node test-server.js
    - python -m SimpleHTTPServer

### Viewing it
Supporting Chrome only
* If you're using test-server.js, navigate to http://localhost:8000 on your local machine or your http://<local IP address>:8000. (It's on port 8000 because python's Simple HTTP Server will automatically host it on port 8000, though there is an option to change this if needed.)
* If you're using the Galileo, connect to the wifi hotspot it is broadcasting, which is probably called ConnectAnyThing or something similar. Then navigating to any URL should redirect you to the web app.
