# Nimap_Machine_Test
**Product Management API**

This project provides a RESTful API for managing product categories using Spring Boot, MySQL, and JPA.

**Prerequisites**

Ensure you have the following installed:

Java 17

Maven

MySQL

Postman (for API testing)

Getting Started

**Clone the Repository**

$ git clone https://github.com/Yvmore/Nimap_Machine_Test

$ cd Nimap_Machine_Test

**Setup MySQL Database**

Create a database named product_category12 and run the following script to set up the categories and products tables:

**SQL Script**

create database product_category12;

use product_category12;

create table categories (id int not null auto_increment primary key,name varchar(50) not null,description varchar(255) default null);

insert into categories (name, description) values('electronics', 'devices and gadgets'),('books', 'various genres and titles'),('clothing', 'fashion and apparel'),('toys', 'games and toys for children');

create table products (id int not null auto_increment primary key,name varchar(50) not null,category_id int not null,foreign key (category_id) references categories(id));

insert into products (name, category_id) values('smartphone', 1), ('laptop', 1),('fiction book', 2),('t-shirt', 3); 

**Configure application.properties**

In src/main/resources/application.properties, update the database configuration:

spring.datasource.url=jdbc:mysql://localhost:3306/product_category12

spring.datasource.username=yourUsername

spring.datasource.password=yourPassword

spring.jpa.hibernate.ddl-auto=update

**Build and Run the Application**
