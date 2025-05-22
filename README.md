Better Buys Fashion - E-Commerce Application
Overview
Better Buys Fashion is a simple e-commerce application built using Spring Boot for the backend and Thymeleaf for the frontend. The application allows customers to browse products, add them to a shopping cart, and proceed to checkout, while providing admins with the ability to manage products and orders. It includes user authentication and role-based access control using Spring Security.
This project fulfills the following user stories:

As a customer, I want to browse products and view their details.
As a customer, I want to add products to my shopping cart.
As a customer, I want to view my shopping cart and proceed to checkout.
As a customer, I want to register/login to the application to manage my orders.
As an admin, I want to add new products to the store and manage existing products.
As an admin, I want to view orders and update their status.

Technologies Used

Backend: Spring Boot, Spring Data JPA, Spring Security
Frontend: Thymeleaf, Spring MVC, Bootstrap 5.3.3
Database: MySQL (configurable for PostgreSQL)
Build Tool: Maven
Deployment: Heroku (or other cloud platforms like AWS, Azure)

Project Setup Instructions
Prerequisites

Java 17 or higher
Maven 3.6+
MySQL (or PostgreSQL) installed and running
Git
IDE (e.g., IntelliJ IDEA, Eclipse)

Steps to Set Up

Clone the Repository
git clone https://github.com/yourusername/better-buys-fashion.git
cd better-buys-fashion

(Replace yourusername with your GitHub username after uploading the project to GitHub.)

Configure the Database

Create a MySQL database named better_buys_fashion.
Update the src/main/resources/application.properties file with your database credentials:spring.datasource.url=jdbc:mysql://localhost:3306/better_buys_fashion
spring.datasource.username=yourusername
spring.datasource.password=yourpassword
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true




Build the Project
mvn clean install


Run the Application
mvn spring-boot:run

The application will be accessible at http://localhost:8080.

Access the Application

Customer Login: Register as a new user or use a default user (e.g., email: customer@example.com, password: password123).
Admin Login: Use the default admin credentials (e.g., email: admin@example.com, password: admin123).



Features
Backend (Spring Boot)

User Authentication & Authorization:
Defined roles: USER (customers) and ADMIN.
Restricted access using Spring Security (e.g., /admin/* endpoints are accessible only to admins).


Product Management:
CRUD APIs for products (/api/products).
Entities: Product (id, name, description, price, image, category).
Repository: ProductRepository using Spring Data JPA.


Order Management:
APIs for placing orders (/api/orders) and viewing order history (/api/orders/history).
Entities: Order (id, user, products, total, status), with relationships to User and Product.


RESTful APIs:
Designed endpoints for frontend interaction (e.g., GET /api/products, POST /api/orders).
Used appropriate HTTP methods (GET, POST, PUT, DELETE) for CRUD operations.



Frontend (Thymeleaf)

UI Components:
Product listing page with categories (e.g., Tote Bag, Make Up, Shoes, Clothes).
Shopping cart page to view and manage cart items.
Order summary and checkout page.
Admin dashboard for product and order management.


Styling:
Used Bootstrap 5.3.3 for responsive design and modern styling.


Integration:
Fetches product data from backend APIs using Thymeleaf (th:each for looping).
Handles user authentication via login/register forms.


Cart & Checkout:
Add/remove products to/from the cart.
Calculates total price during checkout.


Forms:
Login and registration forms with server-side validation.
Admin forms for adding/editing products.


Static Resources:
Managed CSS, JavaScript, and images in src/main/resources/static/.



Additional Features

Error Handling:
Implemented global exception handling in Spring Boot.
Displayed user-friendly error messages in Thymeleaf templates.


Validation:
Used Spring validations for form inputs (e.g., email format, required fields).


Deployment:
Deployed on Heroku (URL: [insert deployment URL here after deployment]).


Source Code:
Pushed to GitHub: [insert GitHub repository URL here].
Shared via Google Classroom under the assignment: https://classroom.google.com/c/Nzc3NTAxMTgwNjMw/a/Nzc3NTAxNDA1NjEz/details.



Project Structure
better-buys-fashion/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/example/betterbuysfashion/
│   │   │       ├── config/          # Spring Security configuration
│   │   │       ├── controller/      # REST and MVC controllers
│   │   │       ├── entity/          # JPA entities (Product, Order, User)
│   │   │       ├── repository/      # Spring Data JPA repositories
│   │   │       ├── service/         # Business logic
│   │   │       └── BetterBuysFashionApplication.java
│   │   ├── resources/
│   │   │   ├── static/              # CSS, JS, images
│   │   │   │   ├── css/
│   │   │   │   ├── js/
│   │   │   │   └── img/
│   │   │   ├── templates/           # Thymeleaf templates
│   │   │   │   ├── base.html
│   │   │   │   ├── index.html
│   │   │   │   ├── login.html
│   │   │   │   ├── register.html
│   │   │   │   └── admin/
│   │   │   └── application.properties
│   └── test/                        # Unit tests
├── pom.xml                          # Maven dependencies
└── README.md

Deployment on Heroku

Install Heroku CLI:Download and install the Heroku CLI from https://devcenter.heroku.com/articles/heroku-cli.
Login to Heroku:heroku login


Create a Heroku App:heroku create better-buys-fashion


Add MySQL Add-on:heroku addons:create cleardb:ignite

Retrieve the database URL:heroku config | grep CLEARDB_DATABASE_URL

Update application.properties with the Heroku database URL.
Deploy the Application:git push heroku main


Open the App:heroku open



Future Improvements

Add product reviews and ratings.
Implement payment gateway integration (e.g., PayPal, Stripe).
Enhance the UI with more interactive features using JavaScript frameworks like Vue.js.

Contributing
Feel free to fork the repository, create a feature branch, and submit a pull request. For major changes, please open an issue to discuss your ideas.
License
This project is licensed under the MIT License - see the LICENSE file for details.
