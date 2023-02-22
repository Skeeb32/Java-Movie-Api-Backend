# Java Movie API Backend

## Overview
The Java, Springboot backend Movie-API database using MongoDB is a web application that serves as a backend for a movie database. It is built using the Springboot framework and MongoDB as the database management system. The API allows users to perform CRUD (Create, Read, Update, Delete) operations on movies, directors, and actors.

The movie database API provides various endpoints for interacting with the database. Users can create new movies, retrieve information about movies, update movie information, and delete movies. Similarly, users can create, retrieve, update, and delete information about directors and actors. Additionally, the API provides endpoints for filtering and sorting movies by various criteria such as genre, release date, and rating.

The API is built using the Java programming language and uses the Springboot framework to provide a robust and scalable web application. MongoDB is used as the database management system, providing a flexible and scalable data storage solution. The use of MongoDB also allows for the easy storage and retrieval of complex data structures, such as arrays and nested documents.

The application uses a RESTful API architecture, allowing for easy integration with other applications and services. It also utilizes JSON as the primary data format, providing a lightweight and flexible data exchange format.

Overall, the Java, Springboot backend Movie-API database using MongoDB provides a scalable and flexible backend for managing movie databases. With its easy-to-use API and powerful data management capabilities, it is an excellent choice for building web applications that require robust data storage and retrieval capabilities.

## Guidelines
Here's a guideline on how to run a Java SpringBoot backend Movie-API with MongoDB:

1. Install MongoDB on your local machine or set up a remote MongoDB server.

2. Create a new SpringBoot project in your preferred IDE using https://start.spring.io/

3. Add the required dependencies to the pom.xml file for MongoDB and Spring Web.

4. Create a new Java package to hold all the classes related to the Movie-API.



## Continuation with Source Code 

Source code for the example is located in /src/main/java/dev/shaqib/movies/Movie.java.  The followings overview of how it communicates with API calls supported by the Java adapter:

5. Create a new Java class called Movie with the following attributes:

```java

    @Id
    private ObjectId id;
    private String imdbId;
    private String title;
    private String releaseDate;
    private String trailerLink;
    private String poster;
    private List<String> backdrops;
    private List<String> genres;
    @DocumentReference
    private List<Review> reviews;

```
   Here is a list of attributes you can call on.

6. Add the @Document annotation to the Movie class to specify that it is a MongoDB document.

```java
@Document(collection = "movies")
public class Movie {
  //...
}
```
   

7. Create a new Java interface called MovieRepository that extends the MongoRepository interface:

 ```java
@Repository
public interface MovieRepository extends MongoRepository<Movie, ObjectId> {
    Optional<Movie> findMovieByImdbId(String imdbId);
}

```

8.  Create a new Java class called MovieController with the following annotations:

```java
@RestController
@RequestMapping("/api/v1/movies")
public class MovieController {
  //...
}

```

9. Autowire the MovieRepository interface into the MovieController class.

```java
@Autowired
private MovieRepository movieRepository;

```

10. Create optional API endpoints for creating, reading, updating, and deleting movies:

```java
@GetMapping
public List<Movie> getAllMovies() {
  //...
}

@GetMapping("/{id}")
public ResponseEntity<Movie> getMovieById(@PathVariable(value = "id") String movieId) {
  //...
}

@PostMapping
public Movie createMovie(@Valid @RequestBody Movie movie) {
  //...
}

@PutMapping("/{id}")
public ResponseEntity<Movie> updateMovie(@PathVariable(value = "id") String movieId,
                                         @Valid @RequestBody Movie movieDetails) {
  //...
}

@DeleteMapping("/{id}")
public ResponseEntity<?> deleteMovie(@PathVariable(value = "id") String movieId) {
  //...
}

```

11. Implement the logic for each API endpoint by calling methods on the MovieRepository interface.

12. Run the SpringBoot application using your preferred method (e.g., running the main method in your IDE).

13. Test the API endpoints using a tool like Postman or cURL.

That's it! You now have a functional Java SpringBoot backend Movie-API with MongoDB.

## Run the example of embedding HTML5 application into a Java Swing window


## More Info
Pleae reach out if you have any questions

## Disclaimers
* This is a starter example and intended to demonstrate to app providers a sample of how to approach an implementation. There are potentially other ways to approach it and alternatives could be considered. 
* Its possible that the repo is not actively maintained.


## Built With:
<a href=“https://www.mongodb.com/“ target=“_new”>• MongoDB</a> - MongoDB Atlas <img src="https://www.vectorlogo.zone/logos/mongodb/mongodb-icon.svg" width='30' /> </br>  


<a href=“https://start.spring.io/“ target=“_new”>• Springboot</a> - Microserves Tool <img src='https://www.vectorlogo.zone/logos/springio/springio-icon.svg' width='30'/> </br> 


<a href=“https://www.oracle.com/java/“ target=“_new”>• Java</a> - Java library for building user interfaces <img src='https://github.com/MarikIshtar007/MarikIshtar007/blob/master/images/java.svg' width='30'/> </br> 


## Authors
<a href=“https://www.github.com/skeeb32“ target=“_new”>Skeeb32 Github</a> - https://www.github.com/skeeb32


## Support
Please enter an issue in the repo for any questions or problems. 
<br>
