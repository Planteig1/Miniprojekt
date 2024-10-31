# Miniprojekt

# Hotel Room Distribution

This provides an overview of the different room types available in our hotel, along with the estimated number of rooms for each type. The distribution reflects a balance between luxury and standard options, with more affordable rooms available in greater numbers.

## Room Types and Availability

| Room Type          | Number of Rooms |
|--------------------|-----------------|
| **Spa Executive**  | 3               |
| **Grand Lit**      | 6               |
| **Standard Single**| 20              |
| **LOFT Suite**     | 4               |
| **Suite**          | 5               |This application is a Flask-based REST API that handles CRUD operations for room pricing information.
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

* ## API Gateway
  This API Gateway serves as an intermediary for various microservices in a hotel management system. It routes requests to the appropriate    services for managing guests, bills, bookings, room pricing, and room availability.

  The readme file inside of the repository of this microservice also contains a complete list over all available endpoints for the user.
  

  Link to repository - https://github.com/Planteig1/API-gateway

* ## Guests microservices
  This application is a Flask-based REST API that handles CRUD operations for the guest database. 

  Link to repository - https://github.com/LucasFJ-2023/microservices_guest.git

* ## Room pricing microservices
  This application is a Flask-based REST API that handles CRUD operations for room pricing information.

  Link to repository - https://github.com/LucasFJ-2023/microservice_room_prices.git

* ## Bill microservices
  This application is a Flask-based REST API that handles CRUD operations for bill information.

  Link to repository - https://github.com/christinetofft/bill-service.git

* ## Booking microservice
  This Flask-based microservice allows for creating a new booking and checks for room availability.

  Link to repository - https://github.com/Planteig1/booking-service

* ## Data retrieval microservice
  This Flask-based microservice allows end-users to retrieve various datasets related to bookings, guests, bills, room pricing, and rooms.

  Link to repository - https://github.com/Planteig1/data-retrieval-service

* ## Rooms service microservice
  This Flask-based microservice manages room availability, cleaning status, and provides a list of all rooms.

  Link to repository - https://github.com/Planteig1/room-service

##DOCKER COMMANDS
To run the containers on your own devices you have to follow these steps
* 1. Create the network
     Docker network create miniprojekt
* 2. Initialize the database
     ```
     docker run -it -v miniprojekt:/app/data database-creation-service      
* 3. Run all of the microservices (OBS!!! REMEBER TO PUSH TO DOCKER HUB AND CHANGE THE IMAGE)
     ```
     docker run -d --name gateway-service --network miniprojekt -p 5000:5000 -v miniprojekt:/app/data gateway-service
     ```
     ```
     docker run -d --name room-service --network miniprojekt -p 5001:5000 -v miniprojekt:/app/data room-service
     ```
     ```
     docker run -d --name booking-service --network miniprojekt -v miniprojekt:/app/data -p 5002:5000 booking-service
     ```
     ```
     docker run -d --name room-pricing-service --network miniprojekt -v miniprojekt:/app/data -p 5003:5000 room-pricing-service
     ```
     ```
     docker run -d --name data-retriveal-service --network miniprojekt -v miniprojekt:/app/data -p 5004:5000 data-retriveal-service 
     ```
     ```
     docker run -d --name guests-service --network miniprojekt -v miniprojekt:/app/data -p 5005:5000 guests-service
     ```
     ```
     docker run -d --name bill-service --network miniprojekt -v miniprojekt:/app/data -p 5006:5000 bill-service
     ```










