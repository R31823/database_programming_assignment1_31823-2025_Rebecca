# database_programming_assignment1_31823-2025_Rebecca
Individual Assignment I: CTEs & SQL Window Functions Project

# Business scenario: Sales Management System ( Usind Oracle as RDBMS)

This README provides an overview of the Sales management database, designed for tables: Clients, Products and Orders

## Database Schema
### Clients , Products , Orders TABLES 
```sql
create table Clients(client_id int primary key, client_name varchar(50), email varchar(50), location varchar(40));
create table Products(product_id int primary key, product_name varchar(50), category varchar(50), price int);
create table Orders(order_id int primary key, order_date date, quantity int, client_id int,product_id,int constraint fk_Clients_Orders foreign key (client_id) references Clients(client_id), constraint fk_Products_Orders foreign key (product_id) references Products(product_id));
```
<img width="1366" height="438" alt="image" src="https://github.com/user-attachments/assets/2b4e863b-546f-4de8-8d2b-79c5b4e24c2a" />
<img width="971" height="313" alt="image" src="https://github.com/user-attachments/assets/5b03ad1a-793a-400b-9572-1ef182a28969" />
<img width="1358" height="723" alt="image" src="https://github.com/user-attachments/assets/9b93b609-72d0-4c92-8ebb-a5f1373480b9" />
<img width="1366" height="511" alt="image" src="https://github.com/user-attachments/assets/4802bb97-b29b-4586-966f-00fa0f6982e2" />

## ER Diagram

## CTE Implementations
### Simple CTE
<img width="659" height="568" alt="image" src="https://github.com/user-attachments/assets/abba8966-4086-4893-a541-30af52af3616" />
This query identifies high-value products priced above 500.
### Multiple CTEs
<img width="803" height="334" alt="image" src="https://github.com/user-attachments/assets/2c14473f-acee-4a6e-ae97-0ca18072f4a3" />
Uses two CTEs to first calculate total sales per product and then filter for those with high volume
### Recursive CTE
<img width="1003" height="375" alt="image" src="https://github.com/user-attachments/assets/e1e19b94-48c1-4873-a0a3-26f30bd5ae3e" />
This query tracks a 3-month payment cycle for a specific product
//Recursive wasn't used due to it not being by my oracle.
### CTE with Aggregation
<img width="777" height="312" alt="image" src="https://github.com/user-attachments/assets/f89954e2-47f7-45f8-a315-9a397a5eeb25" />
Calculates total expenditure per client.
### CTE combined with JOIN operations
<img width="1172" height="534" alt="image" src="https://github.com/user-attachments/assets/89ec476e-a110-4d71-9700-90391efa7611" />
Identify the best-selling product in each category.
## Window Functions Implementations
### Ranking Functions 
ROW_NUMBER() 
<img width="1187" height="284" alt="image" src="https://github.com/user-attachments/assets/b0d9c8bb-ea0c-4f04-951b-19eb1aaf6bb0" />

RANK() 
<img width="1144" height="315" alt="image" src="https://github.com/user-attachments/assets/3eaf281b-1bd1-4799-8420-0d801faeaa1c" />

DENSE_RANK() 
<img width="1109" height="434" alt="image" src="https://github.com/user-attachments/assets/427af67e-e15e-45de-9797-4117d3ae2b61" />

PERCENT_RANK() 
<img width="999" height="371" alt="image" src="https://github.com/user-attachments/assets/46d5dad5-19c6-47d6-99d8-6061796fd3a8" />

### Aggregate Window Functions
SUM() OVER() 
<img width="1366" height="729" alt="image" src="https://github.com/user-attachments/assets/c8fa05e9-db37-41fd-a27a-ca526a9f127e" />

AVG() OVER() 
<img width="1258" height="566" alt="image" src="https://github.com/user-attachments/assets/a0861702-1d6b-467c-872f-381598f8a716" />

MIN() OVER() 
<img width="1299" height="642" alt="image" src="https://github.com/user-attachments/assets/749b9664-522d-4046-811a-0fac9432c1ac" />

MAX() OVER() 
<img width="1234" height="619" alt="image" src="https://github.com/user-attachments/assets/b2d2cc45-03e2-44f7-bf7c-d35ddf7e0529" />

### Navigation Functions
LAG() 
<img width="1264" height="585" alt="image" src="https://github.com/user-attachments/assets/c6292bfb-0c35-4db8-9de3-71de05108641" />

LEAD() 
<img width="1209" height="564" alt="image" src="https://github.com/user-attachments/assets/1d346dd1-1b85-4e06-9f1a-174bbd0daf79" />

### Distribution Functions 
NTILE() 
<img width="1366" height="621" alt="image" src="https://github.com/user-attachments/assets/4e3e539e-a0ca-448c-a7d1-59587c3e7154" />

cume_dist()
<img width="1366" height="610" alt="image" src="https://github.com/user-attachments/assets/6963ada2-c868-4bbb-9322-c6f208a5d5d5" />

## Analysis and Findings
### Descriptive Analysis
There are currently three clients (Alice, Bob, and Charlie) who have each spent the same total amount (8560) in the system . The highest-priced item in the store is the Laptop at 1200, followed by the Smartphone at 800  Most orders occurred on June 26, and the Toaster is currently the only product that has not been sold.
### Diagnostic Analysis
The spending is balanced because each client purchased one high-value electronic item. The "Top Products" query showed no results because no single product reached the 50-unit sales threshold, indicating that while revenue is high due to prices, the total volume of items sold is still relatively low.
### Pescriptive Analysis
The company should focus on marketing the Toaster to increase its sales volume. Since the current revenue is heavily dependent on a few expensive electronics, the business should try to sell more of the lower-priced appliances to create a more balanced income stream.
## References
- Oracle SQL Documentatiom
- Course lecture notes
## Academic Integrity References
I hereby state that this is a work of my own.
