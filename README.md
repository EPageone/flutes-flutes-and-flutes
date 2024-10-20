# Code Institute Milestone Project 4 – Online Flute Store called Flutes, Flutes & Flutes

## Description
The purpose of this project was to create an ecommerce website for flautists that want to purchase flutes of different types and styles. As I am in a band and my instrument is the flute, I wanted to create a website that is for flutes and only flutes. This is my final project for Code Institute Level 5 Diploma in Web Application Development.

To login into the Heroku app please use: https://ep-flutes-flutes-and-flutes-31bc05f84613.herokuapp.com

To get into the Django admin and be a superuser for the Project Management for the app please follow: 

Username = epage1

Password = Brasseye123

To make a purchase in the Checkout Page please use the CVC as follows: 

CVC = 4242 4242 4242 4242    04/29  424  24242


## UX

## User Goals
Access to different types of flutes: As a flautist I want to browse and purchase flutes and score music.
To be able to register and login to and create my own account for the website. 
To be able to read a description of the flute I want to purchase. 
To be able to purchase a flute or score music. 

## Business Goals
Increase sales and revenue: The primary business goal is to increase sales of flutes by providing a user-friendly website for people that want to browse and purchase flutes. To provide different types of flutes so the user can choose what they wish to purchase. 

## User Stories

### Viewing and Navigation
1.	Shopper	View a list of products (flutes)	Select some to purchase
2.	Shopper	View a specific category of products	Quickly find products I'm interested in without having to search through all products
3.	Shopper	View individual product details	Identify the price, description, product rating, product image and available types
4.	Shopper	Quickly identify deals, clearance items, and special offers	Take advantage on special savings on products (flutes)I'd like to purchase
5.	Shopper	Easily view the total of my purchases at any time	Avoid spending too much and get the right flute

### Registration and User Accounts
6.	Site User	Easily register for an account	Have a personal account and be able to view my profile
7.	Site User	Easily login or logout 	Access my personal account information
8.	Site User	Easily recover my password in case I forget it 	Recover access to my account
9.	Site User	Receive an email confirmation after registering	Verify that my account registration was successful
10.	Site User	Have personalised user profile	View my personal order history and order confirmation, and save my payment information

### Sorting and Searching
11.	Shopper	Sort the list of available products (flutes)	Easily identify the best rated, best priced and categorically sorted products (flutes)
12.	Shopper	Sort a specific category of product (flute)	Find the best price or rated product (flute) in a specific category, or sort the products in that category by name
13.	Shopper	Sort multiple categories of products simultaneously	Find the best priced or best rated products (flutes)across categories such as "piccolos" or "wooden flutes"
14.	Shopper	Search for a product by name or description	Find a specific product I'd like to purchase
15.	Shopper	Easily see what I've searched for and the number of results	Quickly decide whether the product I want is available

### Purchasing and Checkout
16.	Shopper	Easily select the type and quantity of a product (flute)when purchasing it	Ensure I don't accidentally select the wrong product (flute), quantity or type
17.	Shopper	View items in my bag to be purchased	Identify the total cost of my purchase and all items I will receive
18.	Shopper	Adjust the quantity of individual items in my bag	Easily make changes to my purchases before checkout
19.	Shopper	Easily enter my payment information	Check out quickly and with no hassles
20.	Shopper	Feel my payment and personal information is safe and secure	Confidently provide the needed information to make a purchase
21.	Shopper	View an order confirmation after checkout	Verify that I haven't made any mistakes
22.	Shopper	Receive an email confirmation after checking out	Keep the confirmation of what I've purchased for my records

### Admin and Store Management
23.	Store Owner	Add a product	Add new items to my store
24.	Store Owner	Edit/update a product	Change product prices, descriptions, images, and other product criteria
25.	Store Owner	Delete a product	Remove items that are no longer for sale

## Data Models
![image](https://github.com/user-attachments/assets/7ff53d7e-979e-44ea-a061-ad196730872c)

## Tables:
a. Customers
•	customer_id (Primary Key)
•	first_name
•	last_name
•	email
•	phone_number
•	shipping_address (Foreign Key to Address Table)
•	billing_address (Foreign Key to Address Table)
•	account_created_date
•	password

b. Products (Flutes)
•	product_id (Primary Key)
•	name
•	description
•	price
•	brand
•	model
•	material
•	flute_type (e.g., classical, piccolo, wooden,student)
•	inventory_id (Foreign Key to Inventory Table)

c. Inventory
•	inventory_id (Primary Key)
•	product_id (Foreign Key to Products Table)
•	stock_quantity
•	warehouse_location
•	last_stock_update

d. Orders
•	order_id (Primary Key)
•	customer_id (Foreign Key to Customers Table)
•	order_date
•	shipping_address (Foreign Key to Address Table)
•	billing_address (Foreign Key to Address Table)
•	order_status (e.g., Pending, Shipped, Delivered)
•	total_amount

e. Order_Items
•	order_item_id (Primary Key)
•	order_id (Foreign Key to Orders Table)
•	product_id (Foreign Key to Products Table)
•	quantity
•	unit_price

f. Payments
•	payment_id (Primary Key)
•	order_id (Foreign Key to Orders Table)
•	payment_date
•	payment_method (e.g., Credit Card, PayPal)
•	payment_status (e.g., Completed, Pending, Failed)
•	total_amount

g. Shipping
•	shipping_id (Primary Key)
•	order_id (Foreign Key to Orders Table)
•	shipping_method (e.g., Standard, Expedited)
•	tracking_number
•	shipping_date
•	estimated_delivery_date

h. Reviews
•	review_id (Primary Key)
•	customer_id (Foreign Key to Customers Table)
•	product_id (Foreign Key to Products Table)
•	review_rating (e.g., 1-5 stars)
•	review_text
•	review_date

i. Address
•	address_id (Primary Key)
•	customer_id (Foreign Key to Customers Table)
•	address_line1
•	address_line2
•	city
•	state
•	postal_code
•	country

2. Relationships:
•	A Customer can place many Orders, but an Order belongs to one Customer.
•	An Order can have many Order_Items, but each Order_Item corresponds to one Product.
•	A Customer can provide multiple Reviews, but a Review relates to one Product.
•	Each Product is related to its Inventory, maintaining stock information.
•	Payments are linked to Orders, ensuring that each order has payment tracking.


### Design Choices

1.	Minimalistic Design: The design follows a minimalistic approach with a clean and uncluttered layout. This ensures that the content remains the focal point and enhances readability.

2.	Responsive Layout: The template utilizes Bootstrap, a popular CSS framework, to ensure responsiveness across various devices and screen sizes. This allows the website to adapt seamlessly to different viewport dimensions, providing a consistent user experience.

3.	Clear Navigation: The navigation menu is intuitive and easy to navigate, with collapsible options for smaller screens. This ensures that users can access different sections of the website effortlessly.

4.	Attention to Detail: The design includes subtle elements such as icons, hover effects, and form styling to enhance user interaction and visual appeal. For example, the search form includes dropdown options for selecting the search category, improving usability.

5.	Branding Elements: Branding elements like the title and colour scheme are consistent throughout the website, contributing to website identity and recognition.


### Wireframes

![Home Page](https://github.com/user-attachments/assets/e18b7650-53fe-495a-91cb-ab104fbc60b2)
![Sign Up_Register](https://github.com/user-attachments/assets/734080bc-992a-403a-b66c-0680cac6fb2a)
![Sign In](https://github.com/user-attachments/assets/b7f8d50d-cc3e-477b-b0da-90438eb832ba)
![Flute Description Page](https://github.com/user-attachments/assets/fe7e3a41-58be-49c4-8a94-d19bdc13bff9)
![Added to Basket Page](https://github.com/user-attachments/assets/0deda5ee-6338-4950-81f5-3b79eda7800c)
![Check Out Page](https://github.com/user-attachments/assets/f10ad502-61e4-4338-940f-78aaa64cb95d)
![Tablet Home Page](https://github.com/user-attachments/assets/a1b88dc0-5181-497a-869b-177d6f823d77)
![Tablet Sign Up_Register Page](https://github.com/user-attachments/assets/1ced6c4b-ea2a-41e1-831f-2d29d3e04c62)
![Tablet Sign In Page](https://github.com/user-attachments/assets/40c2b4fe-765a-4e8e-a819-8334579583d0)
![Tablet Flute Description Page](https://github.com/user-attachments/assets/776255cf-81f3-4b17-900c-04fa2e8f20b8)
![Tablet Added to Basket Page](https://github.com/user-attachments/assets/bd7987d5-300f-4abd-9b49-3f94d27037ca)
![Tablet Check Out Page](https://github.com/user-attachments/assets/7b1b3bf2-803d-4788-95a7-792602dd5263)
![Mobile Home Page](https://github.com/user-attachments/assets/b9227b4d-14fd-4756-9ce9-0a71f94ec995)
![Mobile Sign Up_Register Page](https://github.com/user-attachments/assets/93c0348a-45b4-4fd3-8cbd-a532fa4ba907)
![Mobile Sign In Page](https://github.com/user-attachments/assets/6b2ae290-d0c9-4734-88b3-06ad9fa7da35)
![Mobile Flute Description Page](https://github.com/user-attachments/assets/c8e2402c-a3e9-4abf-8060-c51a6fadc9aa)
![Mobile Added Basket Page](https://github.com/user-attachments/assets/966148ac-a71a-4312-9338-40ddcdacc317)
![Mobile Check Out Page](https://github.com/user-attachments/assets/f46c01d3-5349-4f6c-8ac5-071332790f58)


### Root Directory

![image](https://github.com/user-attachments/assets/9f9808a7-8cce-417d-9fd2-953f436ac0d4)

## Features

### Existing Features

Flutes, Flutes & Flutes comprises of 4 Django apps, each working harmoniously to deliver a seamless user experience, harnessing the power of Django. Their purposes are as follows:

•	Bag: Manages the functionality of the user's bag, allowing products to be added, edited, and removed, preserving them throughout the user's session on the website.
•	Checkout:  Orchestrates the checkout experience, including data validation, handling webhooks, and caching the session.

•	Products: Manages the database and functionality of the shopping platform, allowing users to browse, review, and purchase items. Superusers have the ability to modify and augment the catalogue.

•	Profiles: Handles the functionality of user profiles across the site, enabling them to view and update their addresses, as well as review past orders.


### Technologies Used

•	**Django**: Django is a high-level Python web framework that encourages rapid development and clean, pragmatic design. It follows the DRY (Don't Repeat Yourself) principle, reducing the amount of code needed for common web development tasks and promoting code reusability.

•	**Python**: Python is a versatile and beginner-friendly programming language known for its readability and simplicity. It offers a vast ecosystem of libraries and frameworks, making it ideal for web development projects like Flutes, Flutes & Flutes.

•	**HTML/CSS/JavaScript**: These are the fundamental technologies for building web pages and adding interactivity to web applications. HTML provides the structure, CSS enhances the presentation and styling, and JavaScript adds dynamic behaviour to the website, improving user experience.

•	**PostgreSQL/SQLite**: PostgreSQL and SQLite are powerful relational database management systems (RDBMS) used for storing and managing data in the Flutes, Flutes & Flutes project. PostgreSQL offers advanced features like ACID compliance, while SQLite is lightweight and easy to set up, making it suitable for development and testing environments.

•	**Crispy Forms**: Crispy Forms is a Django application that helps with rendering forms in a Bootstrap-friendly manner. It simplifies form styling and layout customization, enhancing the visual appeal and usability of forms in Flutes, Flutes & Flutes.

•	**Django Allauth**: Django Allauth is a Django-based authentication app that provides robust user authentication, registration, and account management features out of the box. It saves development time and effort by handling common authentication tasks, such as login, logout, and password reset, with minimal configuration.

•	**AWS (Amazon Web Services)**: AWS is a cloud computing platform that offers a wide range of services, including storage, compute, database, and networking services. Flutes, Flutes & Flutes utilizes AWS for static and media file storage, leveraging the scalability, reliability, and security features provided by AWS.

•	**Stripe**: Stripe is a popular payment processing platform that enables businesses to accept payments securely online. Integrating Stripe into Flutes, Flutes & Flutes allows for seamless and secure payment transactions, enhancing the user experience and facilitating business transactions.

•	**HTML**: Markup language for structuring web pages.

•	**CSS**: Stylesheet language for styling HTML elements.

•	**JavaScript**: Programming language for adding interactivity to web pages.

•	**Bootstrap**: Front-end framework for building responsive websites. Provides pre-designed components for rapid development.

•	**JQuery**: JavaScript library for simplifying DOM manipulation and event handling. Streamlines development with a concise API.

•	**Git**: Distributed version control system for tracking changes in source code. Facilitates collaboration and code sharing among developers.


### Libraries I had to install

•	**Django** – I had to install an earlier version of Django as the latest version would not allow the project to work. 

•	**Allauth** – I had to install an earlier version of allauth as the latest version kept upgrading Django and the site would not work correctly. 
•	**Django countries** – I installed this so the countries drop down in the checkout app would work correctly. 

•	**DJ database url**

•	**Gunicorn** – so the site could be deployed to Heroku

•	**Pillow** – so the images could be loaded with the loaddata command.

•	**Boto3** – to run the AWS services for static files. 


### Testing

I tested my HTML and CSS code using the W3Schools Validation tools. I also completed manual testing and tested out all functions to make sure they worked. I tested my JSon with Json Lint.
I also ran tests for models, views and urls within the site so I could keep on track of the progression within the building of the site. 

**W3Schools Validation** and **JSonLint**

![image](https://github.com/user-attachments/assets/5baa169d-f3f5-4126-9b2a-c0cd2ba007ce)
![image](https://github.com/user-attachments/assets/b766c494-a55e-4ade-8340-1c7ca7633ef8)
![image](https://github.com/user-attachments/assets/8bd2d129-056a-4171-9a3b-ee37d8c2a6b4)
![image](https://github.com/user-attachments/assets/c6597292-ecaa-40d1-a931-14b8a562bcdd)
![image](https://github.com/user-attachments/assets/5a9c2c56-aad3-4d57-af8d-c225fe6bf583)

I ran tests for my models, forms, views in my bag app, checkout app and products. 

![image](https://github.com/user-attachments/assets/b2fa5123-1f4b-4e6b-af3b-0b9949437298)
![image](https://github.com/user-attachments/assets/0668f890-0843-4923-b987-cfc46d749d70)
![image](https://github.com/user-attachments/assets/68178e4d-1ee0-4c9f-a485-5e64453acfb4)
![image](https://github.com/user-attachments/assets/abfad63a-cc64-40d4-95b1-2c2cd1c72687)
![image](https://github.com/user-attachments/assets/1e4fa230-9988-4186-ac8c-5cd02dd03876)
![image](https://github.com/user-attachments/assets/6ec9708b-0e9e-4ea1-b4a9-8b7e48b337dc)


### Manual Testing

|  **Feature**   | **Action**   | **Expected Result**  | **Tested**   | **Passed**  |
|:---------------|:-------------|:---------------------|:-------------|-------------|
|  Home Page     | All Products,| User can search for  | Yes          | Yes         |
|                |  Flutes,     | products using All   |              |             |
|                |  Music Books |    Products dropdown |              |             |
|                |              |     using Pricing,   |              |             |
|                |              |  Category, Rating.   |              |             |
|                |              |  User can search All |              |             |
|                |              |  Flutes using the    |              |             |
|                |              |   dropdown for       |              |             |
|                |              |   Classical Flutes,  |              |             | 
|                |              |   Student Flutes,    |              |             |
|                |              |   Piccolos and Wooden|              |             |
|                |              |    Flutes. Users can |              |             |
|                |              |    search All Music  |              |             |
|                |              |    Books using the   |              |             |
|                |              |    dropdown menu for |              |             |
|                |              |     Classical Music  |              |             |
|                |              |    Books,            |              |             |
|                |              | Student Music Books, |              |             |
|                |              |  Flute Repertoire    |              |             |
|                |              |  Music Books and     |              |             |
|                |              |  Flute Duet          |              |             |
|                |              |  Music Books.        |              |             |
|:---------------|:-------------|:---------------------|:-------------|:------------|                  
|Register and    | User directed| User can sign up and |  Yes         |  Yes        |
|  Login         |  to Register | sign in and use their|              |             |
|                |  and or Login| profile, which will  |              |             |
|                |              | allow users to update|              |             |                                                        
|                |              | information and      |              |             |
|                |              | keep orders in the   |              |             |
|                |              | order summary.       |              |             |
|:---------------|:-------------|:---------------------|:-------------|:------------|
|                |              |                      |              |             |
|                |              |                      |              |             |                
| Product        |Add Products, | Superuser can add,   |  Yes         |  Yes        |
| Management     |   edit and   | edit and delete      |              |             |
|                |   delete     | products. Normal     |              |             |
|                |  (only for   | users cannot do this.|              |             |
|                |  superusers) |                      |              |             |
|:---------------|:-------------|:---------------------|:-------------|-------------|               
|                |              |                      |              |             |
| Logout         | Users can    |  User can logout,    | Yes          |  Yes        |
|                | logout       | returns to Login     |              |             |
|                |              | Page                 |              |             |
|                |              |                      |              |             |
|:---------------|:-------------|:---------------------|:-------------|:------------|



### Problems in Development

There were many problems using up to date Django and had to install a lower version of Django and allauth so the code could work whilst following the Code Institute walkthrough to support me through this project. I had many problems with deployment as well. The terminal commands for Heroku are updated and I could not use the walkthrough that much, so I had to use Slack, Stack Overflow and Heroku documentation. 

### Deployment

Project was deployed to Heroku with quite a few issues but managed to complete this in the end. Created Procfile and requirements.txt for dependencies. Created new Heroku app and set environment variables. Linked my Github and environment with Heroku pushed to Heroku. 

My link for Heroku is: https://ep-flutes-flutes-and-flutes-31bc05f84613.herokuapp.com

My link for Github is: https://github.com/EPageone/flutes-flutes-and-flutes


### Acknowledgments

I used https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400..900;1,400..900&display=swap for my fonts on the site. 

I used https://code.jquery.com/jquery-3.4.1.slim.min.js

I used https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/js/bootstrap.min.js

I also used a lot of support from the Code Institute Boutique Ado Walkthrough Project and Slack, Stack Overflow and tutor support and fellow student support. 











































