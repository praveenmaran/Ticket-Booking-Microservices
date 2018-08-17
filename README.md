# Ticket-Booking-Microservices

Implemented with Spring security Basic authentication and Swagger for API Documentation
https://blitter.se/utils/basic-authentication-header-generator/  This API use to generate the basic encoded string.

Application URL and context:

Name : movieticket
Application URL : http://localhost:9090/movieticket
H2 Database console: http://localhost:9090/movieticket/h2-console

Step: 
1. Create user with user/add endpoint API
   Method : POST
   Role : admin , user
   Request Body : 
               {
                    "password": "test",
                    "role": "admin",
                    "username": "admin"
                  }

2. Add movie:
   Admin user only can add the movie
   Method : POST
   Request body: 
                 {
                    "movieName": "Race"
                  }
                  
3. Get All Movie:

    URL : http://localhost:9090/movieticket/movie/get/all
    Method :GET

4. Ticket booking API: 
    URL: http://localhost:9090/movieticket/movie/ticket/lock
    Method : POST
    Request body:
    
               {
                  "movieName": "Race",
                  "seats": [
                    1,2,3
                  ]
                }
                
    Response :
              {
                "referenceId": 1,  
                "status": true
              } 
             referenceId -> This ID used to confirm the ticket/seat
             
5. Ticket confirm API: 
    This API used to confirm the ticket/seat. The referenceId can get from the ticket booking api.
    Method : POST
    Request:
        http://localhost:9090/movieticket/movie/ticket/confirm/{referenceId}
        
        
