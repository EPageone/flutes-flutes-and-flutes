# Code Institute Milestone Project 4 – Online Flute Store

## Description
The purpose of this project was to create an ecommerce website for flautists that want to purchase flutes of different types and styles. As I am in a band and my instrument is the flute, I wanted to create a website that is for flutes and only flutes. This is my final project for Code Institute Level 5 Diploma in Web Application Development.

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
1	Shopper	View a list of products (flutes)	Select some to purchase
2	Shopper	View a specific category of products	Quickly find products I'm interested in without having to search through all products
3	Shopper	View individual product details	Identify the price, description, product rating, product image and available types
4	Shopper	Quickly identify deals, clearance items, and special offers	Take advantage on special savings on products (flutes)I'd like to purchase
5	Shopper	Easily view the total of my purchases at any time	Avoid spending too much and get the right flute
### Registration and User Accounts
6	Site User	Easily register for an account	Have a personal account and be able to view my profile
7	Site User	Easily login or logout 	Access my personal account information
8	Site User	Easily recover my password in case I forget it 	Recover access to my account
9	Site User	Receive an email confirmation after registering	Verify that my account registration was successful
10	Site User	Have personalised user profile	View my personal order history and order confirmation, and save my payment information
### Sorting and Searching
11	Shopper	Sort the list of available products (flutes)	Easily identify the best rated, best priced and categorically sorted products (flutes)
12	Shopper	Sort a specific category of product (flute)	Find the best price or rated product (flute) in a specific category, or sort the products in that category by name
13	Shopper	Sort multiple categories of products simultaneously	Find the best priced or best rated products (flutes)across categories such as "piccolos" or "wooden flutes"
14	Shopper	Search for a product by name or description	Find a specific product I'd like to purchase
15	Shopper	Easily see what I've searched for and the number of results	Quickly decide whether the product I want is available
### Purchasing and Checkout
16	Shopper	Easily select the type and quantity of a product (flute)when purchasing it	Ensure I don't accidentally select the wrong product (flute), quantity or type
17	Shopper	View items in my bag to be purchased	Identify the total cost of my purchase and all items I will receive
18	Shopper	Adjust the quantity of individual items in my bag	Easily make changes to my purchases before checkout
19	Shopper	Easily enter my payment information	Check out quickly and with no hassles
20	Shopper	Feel my payment and personal information is safe and secure	Confidently provide the needed information to make a purchase
21	Shopper	View an order confirmation after checkout	Verify that I haven't made any mistakes
22	Shopper	Receive an email confirmation after checking out	Keep the confirmation of what I've purchased for my records
### Admin and Store Management
23	Store Owner	Add a product	Add new items to my store
24	Store Owner	Edit/update a product	Change product prices, descriptions, images, and other product criteria
25	Store Owner	Delete a product	Remove items that are no longer for sale

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







