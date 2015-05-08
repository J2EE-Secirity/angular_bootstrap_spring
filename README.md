Еще мои ссылки
==========

###spring security angularjs example

* `[Angular JS and Bootstrap with Spring 4.0.2, Spring Security 4.0.0 and Hibernate 4.3.0](https://robertleggett.wordpress.com/2013/12/20/angular-js-and-bootstrap-with-spring-and-spring-security-and-hibernate/)`: [Robert-Leggett/angular_bootstrap_spring](https://github.com/Robert-Leggett/angular_bootstrap_spring)
* `dsyer/spring-security-angular`: [https://github.com/dsyer/spring-security-angular](https://github.com/dsyer/spring-security-angular)
* `Webinar: A Single-Page Application with Spring Security and Angular JS`: [https://spring.io/blog/2015/02/24/webinar-a-single-page-application-with-spring-security-and-angular-js](https://spring.io/blog/2015/02/24/webinar-a-single-page-application-with-spring-security-and-angular-js)
* `The Resource Server: Angular JS and Spring Security Part III`: [https://spring.io/blog/2015/01/20/the-resource-server-angular-js-and-spring-security-part-iii](https://spring.io/blog/2015/01/20/the-resource-server-angular-js-and-spring-security-part-iii)
* `Spring and Angular JS: A Secure Single Page Application`: [https://spring.io/blog/2015/01/12/spring-and-angular-js-a-secure-single-page-application](https://spring.io/blog/2015/01/12/spring-and-angular-js-a-secure-single-page-application)
* `>> Stateless Spring Security Part 2: Stateless Authentication`: [http://www.javacodegeeks.com/2014/10/stateless-spring-security-part-2-stateless-authentication.html](http://www.javacodegeeks.com/2014/10/stateless-spring-security-part-2-stateless-authentication.html)





angular_bootstrap_spring
========================

Angular JS with Bootstrap and Spring 4 and Spring Security

This example is an angular js single page application (SPA) with bootstrap for the widgets and styling.

The application has been broken into two modules API and CLIENT, both are built separately and both are deployed separately.

The API can run on any web server, but it has been tested against Tomcat 8, the server required http DELETE and PUT, so ensure your web server can support those http methods.

The CLIENT currently is run via grunt, for a production release you could extract the .zip artefact and run the static client via Apache.

Ensure that you proxy the API so that you have the same domain otherwise you will experience CORS related issues. (deployed artefacts only)

### Spring 4:
Used to create RESTful controller interfaces which in turn gets called through ajax requests.
	
### Spring Security 4:
Used for a stateless api that allows authentication via basic authentication or token authentication.

Upon authentication a token is attached to the header response which can in turn be used for sequential requests to be authenticated against.

When an authentication fails a 401 will always be returned.

### Login Details as per database inject.sql:
**Username =** user@tester.com.au

**Password =** password

Testing
====================
Simply run on the parent pom to have node and modules auto install and execute all tests. **(REQUIRED FOR FIRST RUN)**

Ensure you have Maven 3.1.0+

**mvn clean install**

To run specific profiles please run mvn clean install and simple pass the profile you wish to execute.

This will execute Java and Jasmine tests that will test both java classes and angular js files.

You can also run jasmine only tests if you wish via the front end:

**http://localhost:7777/test**

Running
====================

### Recommendations:

Use IntelliJ 14+ to run the application.

### Run the API via Tomcat 8:

Deploy exploded artefact to Tomcat 8 and ensure the root context is set to API.

### Run the CLIENT via gulp.js:

Where PATH is the directory to your checked out project.

**Gulp File:** PATH\angular_bootstrap_spring\client\gulpfile.js

**Tasks:** run

**Node Interpreter:** PATH\angular_bootstrap_spring\client\node\node.exe

**Gulp package:** PATH\angular_bootstrap_spring\client\node_modules\gulp

### The application is set to run on

**http://localhost:7777**
