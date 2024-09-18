# Bookstore Application - E-commerce Online Shopping

## Overview
This project is an e-commerce bookstore application designed to handle various functionalities such as product management, user management, order processing, and more. The application is divided into several modules, each responsible for different aspects of the system.

## Modules and Database Schema

### 1. Admin Module
**Functionality:** Manage administrative functions like product management, order tracking, and user management.

**Table: Admin**
- `id`: Primary Key, auto-increment
- `username`: Unique, not null
- `email`: Unique, not null
- `password`: Encrypted, not null
- `created_at`: Timestamp

### 2. Product Module
**Functionality:** Add, update, delete, and view products.

**Table: Product**
- `id`: Primary Key, auto-increment
- `name`: String, not null
- `description`: Text
- `price`: Decimal, not null
- `stock`: Integer, not null
- `author`: String
- `category`: String
- `created_at`: Timestamp
- `updated_at`: Timestamp

### 3. User Module
**Functionality:** Handle user registration, login, and profile management.

**Table: User**
- `id`: Primary Key, auto-increment
- `username`: Unique, not null
- `email`: Unique, not null
- `password`: Encrypted, not null
- `created_at`: Timestamp

### 4. Cart Module
**Functionality:** Manage items added to the cart by users.

**Table: Cart**
- `id`: Primary Key, auto-increment
- `user_id`: Foreign Key (User), not null
- `created_at`: Timestamp

**Table: CartItem**
- `id`: Primary Key, auto-increment
- `cart_id`: Foreign Key (Cart), not null
- `product_id`: Foreign Key (Product), not null
- `quantity`: Integer, not null

### 5. Wishlist Module
**Functionality:** Save products for later consideration.

**Table: Wishlist**
- `id`: Primary Key, auto-increment
- `user_id`: Foreign Key (User), not null
- `created_at`: Timestamp

**Table: WishlistItem**
- `id`: Primary Key, auto-increment
- `wishlist_id`: Foreign Key (Wishlist), not null
- `product_id`: Foreign Key (Product), not null

### 6. Customer Details Module
**Functionality:** Manage user profiles and update customer details.

**Table: CustomerDetails**
- `id`: Primary Key, auto-increment
- `user_id`: Foreign Key (User), not null
- `name`: String, not null
- `email`: String, not null
- `address`: Text
- `phone_number`: String

### 7. Order Module
**Functionality:** Handle order processing, tracking, and history.

**Table: Order**
- `id`: Primary Key, auto-increment
- `user_id`: Foreign Key (User), not null
- `total_amount`: Decimal, not null
- `order_status`: Enum (Pending, Shipped, Delivered, Cancelled), not null
- `created_at`: Timestamp

**Table: OrderItem**
- `id`: Primary Key, auto-increment
- `order_id`: Foreign Key (Order), not null
- `product_id`: Foreign Key (Product), not null
- `quantity`: Integer, not null
- `price`: Decimal, not null

### 8. Feedback Module
**Functionality:** Collect and display user feedback on products.

**Table: Feedback**
- `id`: Primary Key, auto-increment
- `user_id`: Foreign Key (User), not null
- `product_id`: Foreign Key (Product), not null
- `rating`: Integer (1-5), not null
- `comment`: Text
- `created_at`: Timestamp

## Application Flow

### Admin Functions
Admins register and log in, and upon successful login, they gain access to manage products and orders.

### User Registration & Login
Users can register and log in to access the bookstore’s functionalities, including browsing products, managing their cart, and placing orders.

### Product Management
Admins can add, update, and delete products. Users can view the product list and details.

### Cart & Wishlist
Users can add products to their cart for immediate purchase or save them to a wishlist for later consideration.

### Order Processing
Users place orders for items in their cart, and the system tracks order status.

### Customer Profile
Users can update their personal details, such as address and contact information.

### Feedback
Users can submit feedback on products, which is displayed for other users to view.

## Getting Started

### Prerequisites
- Java, Spring Boot
- Maven
- A database (PostgreSQL)

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/Debajyotidatta1/Book-Store-Application.git
2. Make sure that you have downloaded all the necessary dependencies available in pom.xml
3. Navigate to the BookStoreApplication.java file to run the project. 