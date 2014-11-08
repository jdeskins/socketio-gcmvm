# socketio-gcmvm

A quick demo for node.js and socket.io on Google App Engine Managed VMs using Custom Runtimes.

## Usage

Start by cloning this repository.

To run the app locally in the dev appserver:

~~~~
gcloud preview app run .
~~~~

The demo chat app is then available at:  http://[DOCKER-IP]:3000

For example: http://192.168.59.103:3000

You will see an error message in the console indicating request to '/_ah/start' failed.  This is due to the sdk looking for that route on port 8080 - which doesn't exist.

To deploy the app in production:

~~~~
gcloud --project YOUR-PROJECT-NAME-HERE preview app deploy --server preview.appengine.google.com .
~~~~

Since this app is using port 3000, you will need to go into the Managed VM console and edit the Network firewall to allow access to this port.  The app will then be available from the VM's external IP address on socket 3000.  Example:  http://[VM-EXTERNAL-IP]:3000

You cannot access the app through the *.appspot.com host.  You have to look up the external IP of your VM and use that.  Another option is to assign the Managed VM a static external ip address and allow your front-end code to use that to access the app.
