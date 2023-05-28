Teaching lecture about system development using the example of a fullstack application

May, 31st, 2023, 1:30 pm

[Slides of the lectures](link)

## Before: a few information about me

A short introduction of myself can be found [in these slides](link)

# Building a fullstack application (Techniques, Tools, and Frameworks)

A fullstack application consist of more than one software components, normally a backend and a frontend.
In most cases the backend handles to connection to a database (e.g. MongoDB) and the frontend consist of an user interface (e.g. website).

## Step 1 : Setting up the database

We will use a MongoDB NoSQL Document Store database to manage the application data. It's about books borrowed from [Open Library](https://openlibrary.org/) and their reviews.

### Option 1. Using a virtual machine (e.g. Oracle Virtual Box)

The fastest way would be to download my [Open Virtual Appliance file](https://cloud.nstweb.de/s/b8BnXxajW9eqLr8)
with Linux Alpine, Docker, MongoDB and the initial database 'fullstack_db' with the 'books' collection.

You need the software [Oracle Virtual Box](https://www.virtualbox.org/wiki/Downloads) (the actual version should be fine)
to run the virtual machine,
and after installation, import the OVA file (via Tools and the curved arrow going leftwards) and start the machine.

The MongoDB should now be available via **mongodb://localhost:27017** (the NAT settings of Virtual Box should route inside the machine).
Username is 'madmin' and the password is 'geheim123'.
In the backend example (see the section below) we are using this setting for the development stage.

For convenience the [Portainer app](https://www.portainer.io/) is also installed and can be accessed via **https://localhost:9443**,
with username 'admin' and password 'docker123geheim'.

All this machine information is also available in the OVA description.

### Option 2. Using MongoDB Atlas

When you plan to exceed the development stage and going into production online you need a database hosted in the cloud.
There are many providers next to [Google Cloud](https://cloud.google.com/), [Amazon Web Services](https://aws.amazon.com),
and [Microsoft Azure](https://azure.microsoft.com/en-gb/). I chose [MongoDB Atlas](https://www.mongodb.com/atlas/database),
where you can host a small database for free.

Click 'Try free', register with a valid email address, verify your email address, finish the small survey, select **M0** (free)
on the right side, choose a provider (AWS has a data center in Frankfurt), and click 'Create'
(sometimes you need to verify that you are not a robot).

In next step you need to setup a username and password. Choose freely (not the same like your account), but don't forget
this credential information, we need it later to access the database.

Afterward you have to determine from where you database can be accessed. The system has automatically added your IP to this list.
You can keep this as it is, if you intend to use this database for development purpose only from you working computer.
Or you can open it world wide with the IP address **0.0.0.0** and remove the other one (My IP Address).

The last thing is to connect (right next to your cluster name) and no matter which connection method you use
(best to use Compass because we will need it in the next section),
the important information is the connection string, similar to
**[mongodb+srv://user:password@cluster0.6ifwjf9.mongodb.net](mongodb+srv://user:password@cluster0.6ifwjf9.mongodb.net)**.
Copy this information and then you are finished and can start using the database.
Because it is freshly created it is empty, so see next section.

## Step 2 : Managing the data

There are many database managing tools, some for SQL databases and some more for NoSQL databases. Some are free, some has
a limited free testing period, and others cost money. We choose a free one, not the best one, but sufficient for our purpose.
We download [MongoDB Compass](https://www.mongodb.com/try/download/compass) and install it.

After launching the app, you can setup a new connection. Either paste the connection string in the URI field, or use
the Advanced Connection Options to choose Connection Scheme, Host name, Authentication (Username/Password). If you are
using the virtual machine, the connection string '**mongodb://madmin:geheim123@localhost:27017**' should be fine. For the
MongoDB Atlas you should have copied the connection string as described above.

After connecting you should see your databases on left side of the application. There are already some databases there
even if you setup the database freshly. This is 'admin', 'local', and sometimes 'config'. Just ignore these and create
a new database with the '+' sign next to the database headline. In the dialog you can enter the database name 'fullstack_db'
and can also define a collection 'books'. These two information should be fine to create the database.

After creating the collection has no data, so we can add some data by clicking 'ADD DATA' and then 'Import JSON or CVS file'.
When you download the 'books.json' file, then select this one, leave to import dialog as it is, and click 'Import'.
You have now 12 documents (and 1 indexes) in your database.

The other needed collection 'reviews' don't need to be setup, it will be automaticall created by the backend as soon as
data comes in.

## Step 3 : Writing the backend

Find the instructions and the source code of the **backend** [here on GitHub](https://github.com/phd4hd/fullstack-backend)

## Step 4 : Writing the frontend

Again, find the instruction and the source code of the **frontend** also [here on GitHub](https://github.com/phd4hd/fullstack-frontend)

## Step 5 : Deploying

The example we discussed is for the development stage only. We have a local Mongo database (if you're using the virtual machine),
the backend is running on the local machine (via port 8080) and the frontend is also running on the local machine (port 80).

The next stage is the testing stage. Therefore the QA team should have access to both server, the backend and the frontend.
If your QA team is working in the same network segment the development setting might be fine to access the services from another
computer. But 

### Option 1. Using tunnel (e.g. ngrok)


### Option 2. Deploying on Google App Engine


## Links and Sources

- Another lecture about fullstack development (YouTube, similarity is intended)
  - [Full Stack Development with Java Spring Boot, React, and MongoDB – Full Course](https://www.youtube.com/watch?v=5PdEmeopJVQ)
    - [Source Code of the backend](https://github.com/fhsinchy/movieist)
    - [Source Code of the frontend](https://github.com/GavinLonDigital/movie-gold-v1)
- Books and Cover images
  - [Open Library](https://openlibrary.org/)
  - [Books JSON Datafile]()
- Cloud, Storage and Computing Power provider
  - [Google Cloud](https://cloud.google.com/)
  - [Amazon Web Services](https://aws.amazon.com)
  - [Microsoft Azure](https://azure.microsoft.com/en-gb/)
- Database provide
  - [MongoDB Atlas](https://www.mongodb.com/atlas/database)
- Database tools
  - [MongoDB Compass](https://www.mongodb.com/try/download/compass)
- Other stuff
  - [JDK Development Kit 17.0.7 downloads](https://www.oracle.com/java/technologies/downloads/#java17)
  - [Spring Initializr](https://start.spring.io/)
  - [Postman](https://www.postman.com/downloads/)
  - [Node.js](https://nodejs.org/en)
