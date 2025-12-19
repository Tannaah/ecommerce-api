# 🎮 Capstone 3 – E-Commerce API & WEB (Video Game Store)

## 🧾 Project Overview
This project is a Spring Boot API for an e-commerce Video Game Store.  
It supports browsing products, filtering/searching, managing categories, and admin-only product/category management.  
A provided front-end web client consumes the API for browsing and shopping.

--------------------
## 🛠️ Tech Stack
- Java + Spring Boot
- MySQL (Workbench for Database setup)
- Insomnia (API Testing + Automated Test Suite)
- HTML/CSS/JavaScript front-end (Provided Client)

--------------------
## 🚀 How To Run (Setup Process)
1. Create the database:
   - Open the provided SQL script in MySQL Workbench
   - Run it to create and seed the `videogamestore` database
2. Configure the API:
   - Verify `application.properties` points to your MySQL connection
3. Start the backend API:
   - Run the Spring Boot app (default: `http://localhost:8080`)
4. Run the front-end site:
   - Open the web project and launch `index.html` via the provided local server option

--------------------
## 🔐 Authentication (Demo Users)
The database seed includes demo users (example: `admin`, `user`, etc.).  
Passwords for seeded accounts are typically: `password`.  
Use `/login` to get a JWT token and include it for protected endpoints.

--------------------
## ✅ API Testing using Insomnia
All base requirements were validated using the provided Insomnia collections.  
To run automated tests:
- Import the provided Insomnia YAML/JSON collections
- Select the "capstone 3 api" folder, select all tests, and click **Run Folder**
- Confirm all tests pass

🎉 Final Result: **All required Insomnia tests pass!**

--------------------
## 🧩 What I Implemented & Fixed (How I Got Everything Passing)

### 🗂️ Phase 1: Categories & Products
I started with updating the `MySqlCategoryDao` Class and gave it functionality. Then I updated and fixed the `CategoriesController` Class, that then passed all of the tests regarding the Categories.

Lastly, I updated and fixed the `MySqlProductDao` Class and the `search` Method. This filtering logic made it so all product search tests passed.

I also implemented missing DAO methods in `MySqlCategoryDao` and completed `CategoriesController` endpoints and added required annotations. As well as added ADMIN-only authorization for creating/updating/deleting categories.

--------------------
### 🐛 Phase 2: Bug Fixes
Fixed product search/filter logic so query parameters return correct results.
  - (Search filters were applying incorrect constraints, causing results to be too broad or mismatched.)

Fixed product update behavior so updates do **not** create duplicate products.
  - (Product updates were inserting new rows instead of updating the existing product.)

--------------------
## 🔗 Key Endpoints
- `POST /login` (returns JWT)
- `GET /products` (filters: `cat`, `minPrice`, `maxPrice`, `subCategory`)
- `GET /products/{id}`
- `GET /categories`
- `GET /categories/{id}`
### 👮 Admin-only:
 - `POST /categories`
 - `PUT /categories/{id}`
 - `DELETE /categories/{id}`
 - `POST /products`
 - `PUT /products/{id}`
 - `DELETE /products/{id}`

--------------------
## 🖼️ Screenshots

### 🗂️ `MySqlCategoryDao` & `CategoriesController` (The Before & After Insomnia Tests)

#### ❌ Before
<img width="842" height="628" alt="Screen Shot 2025-12-18 at 16 19 28 PM" src="https://github.com/user-attachments/assets/092734dc-dc3e-41a8-93e8-d725adfca256" />

#### ✅ After
<img width="450" height="624" alt="Screen Shot 2025-12-18 at 16 24 13 PM" src="https://github.com/user-attachments/assets/1d2ce40c-2fee-4584-a758-f0edd2726329" />

--------------------
### 🛒 `MySqlProductDao` (The Before & After Insomnia Tests)

#### ❌ Before
<img width="680" height="83" alt="Screen Shot 2025-12-18 at 16 19 40 PM" src="https://github.com/user-attachments/assets/28ae4970-ef23-4e7c-beb1-6a518118eb1b" />

#### ✅ After
<img width="251" height="84" alt="Screen Shot 2025-12-18 at 16 24 25 PM" src="https://github.com/user-attachments/assets/2d8fac67-e9ed-43e6-832f-73ace7e10dd1" />

--------------------
## 🏁 All Required Insomnia Tests Pass!

<img width="423" height="907" alt="Screen Shot 2025-12-18 at 16 36 01 PM" src="https://github.com/user-attachments/assets/2d92300d-3076-47d4-8871-917a18934280" />
<img width="447" height="153" alt="Screen Shot 2025-12-18 at 16 36 10 PM" src="https://github.com/user-attachments/assets/3c2ce95c-4120-4690-bf58-68e77a6d83fc" />

--------------------
## 🕹️ Video Game Store Website
(With functioning category option + minumum & Maximum price values, etc.)

<img width="1919" height="956" alt="Screen Shot 2025-12-18 at 16 42 53 PM" src="https://github.com/user-attachments/assets/5150160f-de71-43e9-8091-e2af4c2031a5" />

--------------------
## 🧠 MySQLWorkbench
(With videogamestore Database)

<img width="881" height="997" alt="Screen Shot 2025-12-18 at 16 39 38 PM" src="https://github.com/user-attachments/assets/db5ef62f-9eaf-480b-94f4-a11d6cba8715" />

--------------------
## 🌟 Interesting Code Spotlight
One of the most important fixes was correcting the product update behavior so updates modify the existing row instead of inserting duplicates.

Why it’s interesting: it prevented duplicate products and made admin updates safe and reliable.

--------------------
<img width="911" height="860" alt="Screen Shot 2025-12-18 at 15 45 00 PM" src="https://github.com/user-attachments/assets/15bc9e76-c625-42dc-b925-be2f1a27049f" />

--------------------
## ⏳ Future Improvements
- Add stronger validation & clearer error responses.
- Write more unit tests for edge cases.
- Improve admin UX / front-end workflow.

--------------------
## 🧱 A Problem I Overcame
A big problem I overcame was debugging the product search/filter feature. Some queries were returning incorrect results, so I traced the SQL logic and fixed how filters were applied (category, price range, subcategory). After the change, all search related Insomnia tests passed consistently.

--------------------
## 😄 A Piece of Code that was Fun to Write
There were actually two pieces of code I really enjoyed writing. The first was fixing the product search method in MySqlProductDao. That was fun because it felt like real backend work, handling query parameters, building the SQL logic correctly, and using prepared statements to safely return the right results.

The second was implementing admin-only protection in CategoriesController. I liked this part because it demonstrates security and clean API design by ensuring only users with the ADMIN role can create, update, or delete categories.

--------------------
## 🧠 Reflection and Closing
This capstone strengthened my confidence working in a real backend codebase where I had to debug existing functionality, implement missing endpoints, and validate everything through automated API tests in Insomnia. I improved my understanding of building REST APIs with Spring Boot, writing DAO logic with SQL and PreparedStatements, and applying role-based security (ADMIN-only access) in controllers. The most valuable part of this project was learning how to isolate issues through testing and make focused fixes without breaking other features. Overall, this project felt like real-world backend development, and I’m proud to finish with all required tests passing and a working front-end experience.

Thank you for reviewing my capstone. I’m proud of the progress I made and enjoyed the challenge of taking an existing codebase and turning it into a fully working, tested solution. I am excited for what’s next.

--------------------
### 🌐 Front-end GitHub Link
https://github.com/Tannaah/ecommerce-web

--------------------
# 👨‍💻 Developed by Tanner Hodges.
