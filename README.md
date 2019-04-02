# demo-app-nodejs
A demo nodejs web app to use for testing GCP app engine. 

## Running a Deployment

To run a deployment, execute the following command from the root folder of your application, i.e., where the app.yaml and package.json reside. Note: you must be [logged in to GCP](https://cloud.google.com/sdk/gcloud/reference/auth/login) before executing this command.

```
gcloud app deploy
```

When deploying an application to App Engine, deployment related settings are kept in the app.yaml file. The following is what the app.yaml file looks like in this demo; it declares that we are deploying a service named `demo-service-app` and it should be deployed to a standard environment with a nodejs runtime.

```
runtime: nodejs
env: standard
service: demo-app-nodejs
```

*A few things to note:*

* If no service is specified it will deploy with the service name default.
* When deploying to a standard environment, only the following runtimes are available: python, java, php, go, nodejs. If another runtime is required, you'll need to deploy to a flexible environment.
* A particular version of a runtime can be specified by including the number, e.g., nodejs8.
* There are a plethora of other [settings](https://cloud.google.com/appengine/docs/standard/nodejs/config/appref) that can be included in the app.yaml file.

