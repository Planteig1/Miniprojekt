# Miniprojekt
## INTRODUCTION TO THE PROJECT (WIP)



# Hotel Room Distribution

This provides an overview of the different room types available in our hotel, along with the estimated number of rooms for each type. The distribution reflects a balance between luxury and standard options, with more affordable rooms available in greater numbers.

## Room Types and Availability

| Room Type          | Number of Rooms |
|--------------------|-----------------|
| **Spa Executive**  | 3               |
| **Grand Lit**      | 6               |
| **Standard Single**| 20              |
| **LOFT Suite**     | 4               |
| **Suite**          | 5               |
| **Standard Double**| 15              |
| **Junior Suite**   | 7               |





# Microservices 
This provides an overview over all of the microservices that's connected to project

* ## Database creation microservice
  This microservice provides an easy method for the creation of all the different databases used by the microservices

  The databases is stored using volumes to allow access for all microservices running in containers
  To initialize the databases, run following code in the terminal 

  ```
  docker run -it -v miniprojekt:/app/data planteig/miniprojekt:database-creation-service
  ```
  Link to repository - https://github.com/Planteig1/database_creation_service

* ## Guests microservices
  This application is a Flask-based REST API that handles CRUD operations for the guest database. 

  Link to repository - https://github.com/LucasFJ-2023/microservices_guest.git





