Domain Selected: Online Retail Application

Entities:
Customers - People who buy products
Products - Items available for sale
Categories - Product classifications
Orders - Customer purchases
Order_Items - Individual products in orders
Payments - Payment transactions
Reviews - Customer feedback on products

Relationships:
CUSTOMERS → ORDERS | One-to-Many (1:M)
ORDERS → PAYMENTS | One-to-One (1:1)
ORDERS → ORDER_ITEMS | One-to-Many (1:M)
PRODUCTS → ORDER_ITEMS | One-to-Many (1:M)
CATEGORIES → PRODUCTS | One-to-Many (1:M)
CATEGORIES → PRODUCTS | One-to-Many (1:M)
PRODUCTS → REVIEWS | One-to-Many (1:M)
CUSTOMERS → REVIEWS | One-to-many (1:M)


Primary Keys:
customer_id in customers table
category_id in categories table
product_id in products table
order_id in orders table
order_item_id in order_items table
payment_id in payments table
review_id in reviews table

Foreign Keys:
category_id in products → categories(category_id)
customer_id in orders → customers(customer_id)
order_id in order_items → orders(order_id)
product_id in order_items → products(product_id)
order_id in payments → orders(order_id)
customer_id in reviews -> customers(customer_id)
product_id in  reviews -> products(product_id)


ER Diagram:
CUSTOMERS
     |
     │ 1 : M        1 : 1
     ├───── ORDERS ────── PAYMENTS
     |         |
     │         │1 : M            M : 1         1 : M
     │         └──── ORDER ITEMS ──── PRODUCTS ──── CATEGORIES
     |
     │ 1 : M          M :1
     └───── REVIEWS ────── PRODUCTS
