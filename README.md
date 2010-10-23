HUMMINGBIRD
===========

Site tracking and analytics storage


Description
---------------

Hummingbird serves a 1x1 tracking pixel to users.  In the browser's GET request it
sends back tracking data generated by javascript.


Requirements
-------------------

 * node.js v0.1.96
 * mongodb


Installation
--------------

    git clone git://github.com/mnutt/hummingbird.git
    cd hummingbird

    # Update submodules
    git submodule update --init --recursive
    # If you are running a *really* old version of git, you may have to run the following instead:

    # build the native mongo db driver
    cd deps/node-mongodb-native; make

    # Copy the default configuration file
    cp config/app.json.sample config/app.json


Running Hummingbird
------------------------------

To start the analytics server, run the following:

    mongod &   (or start mongo some other way)
    node server.js

By default a dashboard will be run on port 8080.  You can disable it for production use in
config/app.json.  The dashboard is just html served out of public/; you can serve it using
any webserver.


Specs
--------

    sudo gem install jspec
    jspec run --node


Tips
-----

 * To run the UI locally but stream data from your production server, use the url http://localhost:8080/?ws_server=your-host.com&ws_port=12345


Contributors
------------

 * Michael Nutt <michael@nuttnet.net>
 * Benny Wong <benny@bwong.net>


License
-------

Hummingbird is licensed under the MIT License. (See LICENSE)
