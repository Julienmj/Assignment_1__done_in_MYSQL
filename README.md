E_COMMERCE PLATFORM

Problem statement

Its a platform where customers can browse products, place orders, provide delivery
addresses, and make secure payments. The database should store customer details such as their ID and name, product
information including product ID and name, and track orders placed by customers for
specific products. Each order should be associated with a customer and a product, and
the system should store the delivery details linking each order to a delivery record. Additionally, a view must be created to display comprehensive order details, including customer information, product names, and order IDs. 





DESCRIPTION OF SQL COMMANDS



1. DATABASE SELECTION

=> Use pl_assignment;

2. TABLES CREATION

=> Create table customer (customer_id int primary key,customer_name varchar(20)) ;

=> create table product (product_id int primary key,product_name varchar(20)) ;

=> create table orders (orders_id int primary key, customer_id int, product_id int, foreign key(customer_id) references customer (customer_id),foreign
key(product_id) references product (product_id) ) ;

=> create table delivery (delivery_id int primary key, customer_id int, orders_id int, foreign key(customer_id) references customer(customer_id), foreign
key(orders_id) references orders(orders_id) ) ;

3. INSERTING DATA INTO TABLES

=> insert into customer values (1,'mugisha julien'), (2,'kwizera sam'), (3,'hapa
pacific') ;

=> insert into product values (001,'mac'), (002,'hp'), (003,'dell') ;

=> insert into orders values (10,1,001), (20,2,002), (30,3,003) ;

=> insert into delivery values (100,1,10), (200,2,20), (300,3,30) ;

4 SELECTION OF TABLES - SCREENSHOT


![Screenshot (27)](https://github.com/user-attachments/assets/95c4024f-a828-4cf1-afc5-4b9726e2959c)

5. UPDATING AND DELETING A NEW CUSTOMER & SCREENSHOT

=> insert into customer values (4,'sam smith') ;

=> update customer set customer_id = 5 where customer_id = 4 ;

=> delete from customer where customer_id = 5 ;


![Screenshot (28)](https://github.com/user-attachments/assets/be52fbea-717a-4a58-805f-fd21dc906ea8)


6. VIEWS AND JOINS

=> Create view orders_details as select c.customer_id, c.customer_name, o.orders_id, p.product_id, p.product_name from customer c join orders o on
c.customer_id = o.customer_id join product p on o.product_id = p.product_id;

7. TABLE VIEWS AND JOINS - SCREENSHOT

 ![Screenshot (29)](https://github.com/user-attachments/assets/4de90969-f632-4189-9f7e-90e19dae56b6)
