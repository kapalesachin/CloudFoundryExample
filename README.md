Hello Spring Cloud Connectors
============

## Building the application

Use Maven to build the application:

~~~
$ mvn clean package
~~~

If you don't haven any Maven setup there is file kept under CloudFoundryExample\runnableJarfile

## Running the application on Cloud Foundry

To run the application on Cloud Foundry, first target and long into a Cloud Foundry environment, then run this command:

~~~
$ cf push
~~~

The application will be deployed using settings in the provided `manifest.yml` file. The output from the command will show the URL that has been assigned to the application. Browse to the provided URL to view information about the application.

### Creating and binding services

Using the provided manifest, the application will not be bound to any data services. The application UI will show default connections provided by Spring Boot. You can create relational database, Redis, MongoDB, and AMQP services and bind them to the application to test creation of service connections with Spring Cloud Connectors.

On [Pivotal Web Services](https://run.pivotal.io/) you can create and bind each type of service using these commands:

~~~
$ cf create-service cleardb spark mysql-service
$ cf bind-service hello-spring-cloud mysql-service


$ cf restart
~~~
