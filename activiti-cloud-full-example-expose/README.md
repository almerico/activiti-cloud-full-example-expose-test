# An example chart for an Activiti Cloud Application

An example that includes all the basic components of an Activiti cloud application. If you have DNS available then to get started:

1) Do `helm repo add activiti-cloud-charts https://activiti.github.io/activiti-cloud-charts/`
2) Run `helm install activiti-cloud-full-example-expose`

There is a flag in the values.yaml to enable a demo ui if desired and commented sections that can be uncommented to enable security policies.

You can use a postman collection to explore the example. Download https://github.com/Activiti/activiti-cloud-examples/blob/master/Activiti%20v7%20REST%20API.postman_collection.json and import the collection into your postman (we recommend installing the app and not using the chrome one). Set the value of the gateway to the gateway url on your cluster and idm to the keycloak url on your cluster.

Call the refresh endpoint in gateway to refresh it.
Call the getKeycloakToken endpoint to get a keycloak token.
Call startProcess to start a process instance.
Call queryProcessInstances in query to check that query can see the process instance. Call getEvents in audit to check that the event was audited. You should also see this process instance in the UI that you checked in iv.

The example is a starting-point - plug in your images if you have them and add further runtime-bundles and connectors to customise.

To enable postgres rather than h2 set db.deployPostgres. See individual charts for more options.
