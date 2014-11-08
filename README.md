# socketio-gcmvm

A quick demo for node.js and socket.io on Google App Engine Managed VMs using Custom Runtimes.

## Usage

Start by cloning this repository.

To run the app locally in the dev appserver:

~~~~
gcloud preview app run .
~~~~

To deploy the app in production:

~~~~
gcloud --project YOUR-PROJECT-NAME-HERE preview app deploy --server preview.appengine.google.com .
~~~~
