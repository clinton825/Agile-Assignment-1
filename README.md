## Docker Assignment - Agile Software Practice.

__Name:__ Clinton Bempah (20097793)

__Demo:__ (https://www.youtube.com/watch?v=WrozjD2fK4w)

This repository contains the containerization setup for a multi-container application that includes a Movies API, MongoDB database, Redis cache, and Mongo Express for database administration. The application's architecture is illustrated below.

![image](https://github.com/user-attachments/assets/c2e03bed-6c19-4392-9fde-9909d2ebb4aa)


### Database Seeding.

For development purposes, the MongoDB database is automatically seeded with sample movie data. The seeding is handled by an initialization script or file which populates the database on startup. This seeding process is excluded in the production environment.

### Running the Application
To start the application, use Docker Compose:

# docker-compose up --build


### M.ulti-Stack.
The application supports both development and production stack options, with distinct configurations:

Development Stack: The full stack is deployed, including Mongo Express for MongoDB management and a seeding process to populate the database with sample data.

Production Stack: In production, Mongo Express is not deployed, and no seeding takes place.

### Development Stack
To run the application in development mode, use the default docker-compose.yml file with all services, including Mongo Express and database seeding enabled.

### Production Stack

For production, run the application without Mongo Express and without seeding. Update the docker-compose.yml file or create an override file (docker-compose.prod.yml) to remove the Mongo Express service and any seeding-related configurations.

# docker-compose --profile dev up --build

### Usage

Once the application is running:

Access the Movies API endpoints via http://localhost:9000

Access Mongo Express for MongoDB administration (development only) at http://localhost:8081.

Redis caching and rate-limiting are applied to the "get all movies" endpoint.




