# Movie Reservation System built with Spring Boot, Spring Security, HTML, CSS, JS, and JWT
This is a project proposed by Roadmap.sh for the backend. URL: https://roadmap.sh/projects/movie-reservation-system

## Technologies Used

- **Programming Languages**: Java, JavaScript, HTML, CSS
- **Frameworks**: Spring Boot
- **Databases**: PostgreSQL
- **Build Tools**: Maven
- **Version Control**: Git
- **Hosting Platform**: GitHub
- **Other Technologies**: JWT

**User Authentication and Authorization**
For authentication, users can register and log in using a username and password, which are encrypted with bcrypt, a functionality provided by Spring Security. Two main roles were implemented: USER and ADMIN. By default, when a person registers, they have the USER role.

**LOGIN ROUTE:** POST '/auth/login'
**INTERFACE**

![image](https://github.com/user-attachments/assets/4cfb4627-8f48-4682-b883-ad02474b4b5b)

**REGISTER ROUTE** POST '/auth/register'
**INTERFACE**

![image](https://github.com/user-attachments/assets/18e97dd4-0808-4bd0-9459-93c3d17ded68)

**POSTMAN**

In login and registration, the API generates a token. In the image, the username and the default role are added.

When added to the database, the password is already encrypted.

![image](https://github.com/user-attachments/assets/c03d585a-0b00-4c37-8b4a-15912ee71695)

![image](https://github.com/user-attachments/assets/1954589f-ee09-4582-8e84-6334685ef435)

# Regular Users (User)

They can access basic functions such as viewing movies, schedules, and making reservations.

**ROUTE TO DISPLAY ALL MOVIES** GET '/user/movie'

**ROUTE TO VIEW A MOVIE** GET '/user/movie/{id}'

**POSTMAN**

![image](https://github.com/user-attachments/assets/2f633131-5626-4462-9b25-44a6a38c2e93)

**INTERFACE**

The interface only needs to extract the "id" and "posterImage" to create the cards. The movie id will be used later for reservations.

![image](https://github.com/user-attachments/assets/ec339aeb-8381-4f07-825c-0ecdcb91be15)

**NOTE: THE INTERFACE FOR DISPLAYING SCHEDULES IS MISSING, BUT THE ROUTES IN THE CONTROLLER ARE ENABLED**

**ROUTE TO VIEW SCHEDULES** GET '/admin/horario' (Currently an ADMIN function)

**ROUTE TO VIEW RESERVATIONS** GET '/user/reservation'

**ROUTE TO MAKE A RESERVATION** POST '/{horarioid}/add-seats' Each schedule consists of a movie, a time, and a cinema room. The "reservations" entity was created to manage seats for each movie.

**ROUTE TO CHECK OCCUPIED SEATS** GET '/{horarioid}/occupied-seats'

![image](https://github.com/user-attachments/assets/e68d5e47-e013-4a9a-a83f-cabdcf2685f2)

The billing system was planned to be improved, but due to time constraints, it remained as is. However, seats are reserved and locked, so they cannot be selected again.
It uses horarioId to ensure an exclusive space for each cinema function.

![image](https://github.com/user-attachments/assets/7ede1caf-0dc7-472c-ac06-ab65742ed647)

![image](https://github.com/user-attachments/assets/13474aa6-f001-4312-8616-346d1b6a74c8)

![image](https://github.com/user-attachments/assets/85c5c34a-891b-4b0c-9efe-dc2b36a21367)

**ALL RESERVATIONS WERE SUCCESSFULLY ADDED**

![image](https://github.com/user-attachments/assets/e9b04078-f379-411b-9d0b-2af4236360a8)

# Administrators (Admin)

They have access to advanced functions such as movie and schedule management, user administration, and report generation.

**WHEN AN ADMIN USER LOGS IN**

They have a set of routes they can use to manipulate database records, including users, movies, schedules, and cinema rooms. The admin has all permissions: GET, POST, DELETE, and search records by ID.

**ADMIN ROUTES**

![image](https://github.com/user-attachments/assets/587be1bc-e70d-4e5f-855a-98bb82b17d40)

![image](https://github.com/user-attachments/assets/cc34f9f6-e600-482e-9032-7dd40614a787)

![image](https://github.com/user-attachments/assets/ba5f04c9-00e2-431d-929d-d00e9cc99594)

![image](https://github.com/user-attachments/assets/2b2e8402-e8e9-42fe-9edb-a66fdb0dcc6d)

