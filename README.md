# What is Spring MVC?

## Learning Goals

- Define MVC architecture.
- Explain Spring MVC architecture.

## Introduction

The Model-View-Controller (MVC) architecture can be used to create different
kinds of loosely coupled web applications. We will take a look at the components
of the MVC architecture and then explore how Spring Web MVC uses this
architecture.

## What is MVC?

The MVC architecture allows us to separate our code into distinct logical units
called models, views, and controllers. Here’s what each unit does:

- **Model:** Defines data representation and relationships.
- **View:** Presents data to the user and handles user interaction.
- **Controller:** Controls data flow between models and views.

When a user sends a request to a URL it gets sent to a method in the controller
which gets the required data using the model. The controller then passes the
data to the view and gets back the data representation for the user. This data
is sent back to the user.

The view layer can form a complete webpage and send it back to the client. For
example, the view layer can form an HTML file with the required data and send it
to the client which can display it without additional data manipulation.

We can also configure the view layer to send back a simple data representation
such as JSON instead of a fully formed webpage. The client has to define its own
logic to manipulate and display the data.

## Spring MVC

In order to process user requests in HTTP, we need a servlet container (web
server). A servlet container processes HTTP requests and interfaces with a Java
application so that the Java application doesn’t have to implement the
communication layer.

![Spring MVC Overview](https://curriculum-content.s3.amazonaws.com/java-spring-2/spring-mvc-overview.png)

Spring MVC uses a `DispatcherServlet` that processes HTTP requests. Here are the
steps of a full request-response cycle:

1. The client makes an HTTP request.
2. The web server accepts the request and delivers it to the dispatcher servlet.
   This servlet manages the HTTP flow for the rest of the cycle.
3. The dispatcher sends the HTTP request to the Handler Mapping component.
4. The handler component sends back the HTTP method and path to the dispatcher.
5. The dispatcher uses the information to call the corresponding method in the
   right controller.
6. The controller method provides the view name and data needed to render the
   view.
7. The dispatcher uses the View Resolver component to find the view that needs
   to be rendered.
8. An HTTP response is sent back to the client.
9. The client side renders the view.

![Spring MVC Detailed](https://curriculum-content.s3.amazonaws.com/java-spring-2/spring-mvc-detailed.png)

Note that when we are building an API the View Resolver is not required. After
step 5, the controller method returns the value that needs to be sent to the
client. The response is sent to the client through the web server.

## Conclusion

We have learned about the MVC architecture and how it is implemented in Spring.
In the next few lessons, we will create our own API with the Spring Web
dependency.

## References

-[Spring Web MVC Documentation](https://docs.spring.io/spring-framework/docs/3.2.x/spring-framework-reference/html/mvc.html)

