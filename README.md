# Multi User Chat Application

I followed a tutorial on YouTube to build this multiple user chat application. You can watch the tutorial for detailed instructions on how to create a similar application:

[Github](https://github.com/ali-bouali/one-to-one-chat-spring-boot-web-socket) by [Bouali Ali](https://www.youtube.com/watch?v=7T-HnTE6v64)

!! Docker file is changed
```yml
services:
  mongodb:
    image: mongo
    container_name: mongo_db
    ports:
      - 27017:27017
    volumes:
      - mongo:/data
    environment:
      - MONGO_INITDB_ROOT_USERNAME=fatih
      - MONGO_INITDB_ROOT_PASSWORD=fatih
  mongo-express:
    image: mongo-express
    container_name: mongo_express
    restart: always
    ports:
      - 8081:8081
    environment:
      - ME_CONFIG_MONGODB_ADMINUSERNAME=fatih
      - ME_CONFIG_MONGODB_ADMINPASSWORD=fatih
      - ME_CONFIG_BASICAUTH_USERNAME=fatih
      - ME_CONFIG_BASICAUTH_PASSWORD=fatih
      - ME_CONFIG_MONGODB_SERVER=mongodb

volumes:
  mongo: { }
```

- ## Used Technologies

During the development of this application, I utilized the following technologies:

- [Spring Boot](https://spring.io/projects/spring-boot): A powerful Java framework for building web applications.
- [WebSocket](https://spring.io/guides/gs/messaging-stomp-websocket/): A communication protocol for real-time, full-duplex communication between a client and a server.
- [STOMP (Simple Text Oriented Messaging Protocol)](https://stomp.github.io/): A messaging protocol that defines the format and rules for data exchange.
- [SockJS](https://github.com/sockjs/sockjs-client): A JavaScript library that provides a WebSocket-like object in browsers that don't support WebSocket.
- [MongoDB](https://www.mongodb.com/): A NoSQL database program, MongoDB stores data in flexible, JSON-like documents.
- [Docker](https://www.docker.com/): Docker provides a way to package and distribute software in containers, making it easier to deploy and run applications consistently across different environments.

## How to Run

1. Clone this repository to your local machine.
2. Make sure you have Java and Maven installed.
3. Navigate to the project directory in your terminal.
4. Run the following command to start the application:

```maven
mvn spring-boot:run
```
## Screenshots

Here are some screenshots of the chat application:

![Screenshot 2](https://github.com/MuhammetFatihAktug/multi-chat-app/blob/master/src/main/resources/static/img/1.png)

![Screenshot 1](https://github.com/MuhammetFatihAktug/multi-chat-app/blob/master/src/main/resources/static/img/2.png)


## Additional Resources

For further information, you can refer to the following resources:

- [Spring Framework Reference Documentation](https://spring.io/projects/spring-framework): You can explore the official documentation for detailed information about Spring Boot and other Spring technologies.
- [WebSocket API Documentation](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API): Visit the WebSocket API documentation on MDN Web Docs for more information about WebSockets.
- [MongoDB Documentation](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API): The official MongoDB documentation provides comprehensive guides and references for using MongoDB.
- [Docker Documentation](https://docs.docker.com/get-docker/): Explore Docker documentation for detailed instructions on how to use Docker for containerization and deployment.
