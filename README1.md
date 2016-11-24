
luminous-app

This is the application shell for the collection of luminous elements which communicate with the luminous-controller app on a raspberry pi,


### Configure Application
    
### Start the development server
Currently there is no ui or automatic discovery of devices so we need to manually configure each luminous-chrome element for each device.

    open src/my-lights.html
    add the luminous-chrome element with the deviceurl parameter under the closing style tag,

A configured element looks like the following
    `<luminous-chrome deviceurl="http://192.168.1.112:3000"></luminous-chrome>`

This command serves the app at `http://localhost:8080` and provides basic URL
routing for the app:

    polymer serve --open
    



### Build

This command performs HTML, CSS, and JS minification on the application
dependencies, and generates a service-worker.js file with code to pre-cache the
dependencies based on the entrypoint and fragments specified in `polymer.json`.
The minified files are output to the `build/unbundled` folder, and are suitable
for serving from a HTTP/2+Push compatible server.

In addition the command also creates a fallback `build/bundled` folder,
generated using fragment bundling, suitable for serving from non
H2/push-compatible servers or to clients that do not support H2/Push.

    polymer build

### Preview the build

This command serves the minified version of the app at `http://localhost:8080`
in an unbundled state, as it would be served by a push-compatible server:

    polymer serve build/unbundled

This command serves the minified version of the app at `http://localhost:8080`
generated using fragment bundling:

    polymer serve build/bundled

### Run tests

This command will run
[Web Component Tester](https://github.com/Polymer/web-component-tester) against the
browsers currently installed on your machine.

    polymer test

