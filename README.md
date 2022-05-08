
## Build Docker images

To create Docker build and push to Docker hub you have to login from terminal:

``docker login``

Now you can build Docker image and push it:

``make docker-build docker-push``

To bundle your operator to be used with OLM run:

``make bundle bundle-build bundle-push``

You can split it into 3 different commands:

``make bundle``
``make bundle-build``
``make bundle-push``

## Run/Deploy operator

To run it directly from source code:

``make deploy``

To run bundle with OLM:

``operator-sdk olm install``

Wait for olm to get up and execute:

Create namespace:

``kubectl create ns``

Run operator:

``operator-sdk run bundle docker.io/curuvija/query-exporter-operator-bundle:v0.0.1 --namespace query-exporter``

## Deploy QueryExporter

Make changes to the file ``config/samples/exporters_v1alpha1_queryexporter.yaml`` and run:

``kubectl apply -f config/samples/exporters_v1alpha1_queryexporter.yaml``