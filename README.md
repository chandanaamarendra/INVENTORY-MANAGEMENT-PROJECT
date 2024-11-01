 
# INVENTORY MANAGEMENT SYSTEM

This project is a comprehensive SQL-based Inventory Management System designed to manage suppliers, products, stock, customers, orders, and purchase records. It includes several database tables, constraints, stored procedures, triggers, and a billing view for enhanced database functionality.

### Project Structure 
1. Database: INVENTORY
2. Tables: Supplier, Product, Stock, Customer, Orders, Purchase
3. Procedures: Add new suppliers, products, customers, and orders; automatic ID generation
4. Views: Billing view to calculate and display order total
5. Triggers: For automatic stock updates on order placement and product deletion

## Getting Started
#### Prerequisites
Ensure you have:

SQL Server or a compatible SQL database engine installed
A basic understanding of SQL for executing scripts and creating databases

## Installation
1. Clone the repository:git clone (https://github.com/chandanaamarendra/INVENTORY-MANAGEMENT-PROJECT)
2. Open the SQL script file and run it in your SQL editor.
3. Verify that all tables, constraints, views, procedures, and triggers have been created.

## Usage
1. Creating Tables: Run the CREATE TABLE commands to set up the required tables for managing inventory.
2. Inserting Data: Use the provided INSERT INTO statements to populate the tables with sample data.
3. Stored Procedures: Execute procedures like NEW_SUPPLIER, NEW_PRODUCT, and AUTO_ID_SUP to add records with or without manually specified IDs.
4. Triggers: Place orders or delete products to trigger stock updates or cascaded deletions.

## Key Features
1. Supplier Management: Tracks supplier details with unique identifiers and constraints.
2. Product Inventory: Manages product details, including categories, prices, and supplier relationships.
3. Stock Tracking: Keeps stock quantity, reorder level, and minimum order quantity data up to date.
4. Order Processing: Manages customer orders, calculates total amounts, and reduces stock automatically.
5. Data Integrity: Enforces data integrity with primary and foreign key constraints, check constraints, and unique constraints.
6. Automation: Automatically generates sequential IDs for new entries and updates stock based on orders.

## Database Entities
1. Supplier: Contains details about suppliers including name, address, and contact information.
2. Product: Details of available products, with price, category, and associated supplier ID.
3. Stock: Tracks product quantities, reorder levels, and minimum order quantities.
4. Customer: Holds customer details, including name, address, and contact details.
5. Orders: Stores order details such as product, customer, order date, and quantity.
6. Purchase: Records purchase history, linking products and suppliers.

## View: VIEW_BILL
Generates a bill view that displays customer order information along with the total amount.

## Triggers
1. TRI_on_ORDERS: Automatically decreases stock quantity upon order placement.
2. TRI_ON_PRO: Deletes stock details when a product is removed.
3. TRI_UPDATE_ORDER: Adjusts stock based on order quantity updates.
## Example Usage
 1. Add a new supplier
   
     EXEC NEW_SUPPLIER 'S0011', 'Kishan', 'Balaji Nagar', 'Eluru', '8965896455', 'kishan@gmail.com';

 2. Create a new order
   
     EXEC AUTO_ID_ORDER 'P0004', 'C0006', 50;

3. View all stock details
   
    SELECT * FROM STOCK;

 4. See the total bill
   
     SELECT * FROM view_Bill

## License
This project is licensed under the MIT License.

