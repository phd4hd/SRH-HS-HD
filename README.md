Teaching lecture about system development using the example of a fullstack application

May, 31st, 2023, 1:30 pm

[Slides of the lectures](link)

## Before: A view words about me

A short introduction of myself can be found in the slides found [here](link)

# Building a fullstack application (Techniques, Tools, and Frameworks)

A fullstack application consist of more than one software components, normally a backend and a frontend.
In most cases the backend handles to connection to a database (e.g. MongoDB) and the frontend consist of an user interface (e.g. website).

## Setting up the database

We will use a MongoDB NoSQL Document Store database to manage the application data. It's about books borrowed from [Open Library](https://openlibrary.org/) and their reviews.

### 1. Using a virtual machine (e.g. Oracle Virtual Box)

The fastest way would be to download my [Open Virtual Appliance file](https://cloud.nstweb.de/s/b8BnXxajW9eqLr8)
with Linux Alpine, Docker, MongoDB and the initial database 'fullstack_db' with the 'books' collection.

You need the software [Oracle Virtual Box](https://www.virtualbox.org/wiki/Downloads) (the actual version should be fine),
and after installation, import the OVA file (via Tools and the curved arrow going leftwards) and start the machine.

The MongoDB should now be available via **mongodb://localhost:27017** (the NAT settings of Virtual Box should route inside the machine).
Username is 'madmin' and the password is 'geheim123'.

For convenience the [Portainer app](https://www.portainer.io/) is also installed and can be accessed via **https://localhost:9443**,
with username 'admin' and password 'docker123geheim'.

All above information is also available in the OVA description.

### 2. Using MongoDB Atlas

## Managing the data


## Writing the backend

Find the source code of the **backend** [here on GitHub](https://github.com/phd4hd/fullstack-backend)

## Writing the frontend

Find the source code of the **frontend** also [here on GitHub](https://github.com/phd4hd/fullstack-frontend)

## Deploying





## Links and Sources

- [Full Stack Development with Java Spring Boot, React, and MongoDB – Full Course](https://www.youtube.com/watch?v=5PdEmeopJVQ)
  - [Source Code of the backend](https://github.com/fhsinchy/movieist)
  - [Source Code of the frontend](https://github.com/GavinLonDigital/movie-gold-v1)
- [JDK Development Kit 17.0.7 downloads](https://www.oracle.com/java/technologies/downloads/#java17)
- [MongoDB Atlas](https://www.mongodb.com/atlas/database)
- [Spring Initializr](https://start.spring.io/)
- [Node.js](https://nodejs.org/en)
- [Open Library](https://openlibrary.org/)
