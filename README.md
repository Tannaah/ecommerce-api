# Capstone 3 – E-Commerce API & WEB (Video Game Store)

## Project Overview
This project is a Spring Boot API for an e-commerce Video Game Store.  
It supports browsing products, filtering/searching, managing categories, and admin-only product/category management.  
A provided front-end web client consumes the API for browsing and shopping.

----------
## Tech Stack
- Java + Spring Boot
- MySQL (Workbench for Database setup)
- Insomnia (API Testing + Automated Test Suite)
- HTML/CSS/JavaScript front-end (Provided Client)

----------
## How To Run (Setup Process)
1. Create the database:
   - Open the provided SQL script in MySQL Workbench
   - Run it to create and seed the `videogamestore` database
2. Configure the API:
   - Verify `application.properties` points to your MySQL connection
3. Start the backend API:
   - Run the Spring Boot app (default: `http://localhost:8080`)
4. Run the front-end site:
   - Open the web project and launch `index.html` via the provided local server option

----------
## Authentication (Demo Users)
The database seed includes demo users (example: `admin`, `user`, etc.).  
Passwords for seeded accounts are typically: `password`.  
Use `/login` to get a JWT token and include it for protected endpoints.

----------
## API Testing using Insomnia
All base requirements were validated using the provided Insomnia collections.  
To run automated tests:
- Import the provided Insomnia YAML/JSON collections
- Select the "capstone 3 api" folder, select all tests, and click **Run Folder**
- Confirm all tests pass

Final Result: **All required Insomnia tests pass**
----------

