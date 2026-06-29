# database_programming_assignment1_31823-2025_Rebecca
Individual Assignment I: CTEs &amp; SQL Window Functions Project

# Business scenario: Sales Management System ( Usind Oracle as RDBMS)

This README provides an overview of the Sales management database, designed for tables: Clients, Products and Orders

## Database Schema
### Clients , Products , Orders TABLES 

create table Clients(client_id int primary key, client_name varchar(50), email varchar(50), location varchar(40));
create table Products(product_id int primary key, product_name varchar(50), category varchar(50), price int);
create table Orders(order_id int primary key, order_date date, quantity int, client_id int,product_id,int constraint fk_Clients_Orders foreign key (client_id) references Clients(client_id), constraint fk_Products_Orders foreign key (product_id) references Products(product_id));


## ER Diagram

## CTE Implementations
### Simple CTE

### Multiple CTEs

### Recursive CTE

### CTE with Aggregation

### CTE combined with JOIN operations

## Window Functions Implementations
### Ranking Functions

### Aggregate Window Functions

### Navigation Functions

### Distribution Functions 

## Analysis and Findings
### Descriptive Analysis

### Diagnostic Analysis

### Pescriptive Analysis

## References
Oracle SQL Documentatiom
Course lecture notes
## Academic Integrity References
I hereby state that this is a work of my own.
