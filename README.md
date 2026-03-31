
# Team Name

21479 Group 5




## Team Members
Sydney James -  [@srj44873](https://github.com/srj44873)

Mary Earhart -  [@marykearhart](https://github.com/marykearhart)

Derek Quinlan - [@derekq111](https://github.com/derekq111)

Regan Taylor - [@nrt19057](https://github.com/nrt19057)
## Problem Description
Our data model is for a fictional company called "Terry Teas" the company is a tea shop selling nutrition teas. The database is for the day to day operation of the company. The database includes tables such as Customers, Orders, OrderDetails, LoyaltyPrograms, etc. Our database would help a manager visualise simple things such as listing all customer names, or a more complex query such as total quantity sold for each product. 

## Data Model
<img width="1060" height="413" alt="Screenshot 2026-03-29 at 4 11 20 PM" src="https://github.com/user-attachments/assets/47a9a5a7-d151-457f-a64f-f658ee9c2f93" />

Explanation of Data Model:
Our data model represents the structure of a retail and inventory management system that tracks customers, sales, products, suppliers, employees, and store operations.

At the core of the model is the Customers entity, which stores personal information such as name, contact details, and address. Each customer can make multiple purchases, which is why there is a one-to-many relationship between the Customers and Sales entities.

The Sales entity records each transaction, including the sale price, date, and payment method. Because a single sale can involve multiple products, we created an associative entity called Product Line, which connects Sales and Products. This resolves the many-to-many relationship between Sales and Products, allowing each sale to include multiple products and each product to appear in multiple sales.

The Products entity stores details about each item, including product name and type. Products are supplied by vendors, which is represented through the Suppliers entity. Since suppliers can provide multiple products and products can come from multiple suppliers, we use the Supplier Orders associative entity to connect Suppliers and Products. This table also links to Store Location, indicating where products are being delivered.

The Store Location entity represents different store branches, including attributes such as city and state. Supplier Orders are tied to specific locations, establishing a one-to-many relationship between Store Location and Supplier Orders.

Customer purchasing activity is further detailed through the Customer Orders and Customer Order Details entities. Customer Orders represent overall orders placed by customers, while Customer Order Details break down each order into specific products, quantities, shipping dates, and statuses. This creates a structured relationship where:
- One customer can have many orders
- One order can have many order details (products)

To manage promotions, we included a Discount Programs entity. This entity links customers, sales, and specific discount programs, allowing discounts to be applied to particular transactions. This creates relationships between Customers, Sales, and Discount Programs to track promotional usage.

On the organizational side, the Employees entity stores employee information such as name, email, and department. Each employee belongs to a Department, forming a many-to-one relationship (many employees per department). Additionally, the Employees table includes a self-referencing relationship (via PreviousChair), which models succession or reporting structure within the organization.

Finally, the Department entity defines different functional areas within the company, such as sales, management, or operations.

Overall, this data model efficiently captures the relationships between customers, transactions, products, suppliers, and employees, while resolving complex many-to-many relationships through associative entities like Product Line, Supplier Orders, and Customer Order Details.
## Data Dictionary
<img width="644" height="495" alt="Screenshot 2026-03-31 at 8 55 28 AM" src="https://github.com/user-attachments/assets/a159e98d-d290-429a-9012-96ed3f97e633" />

<img width="645" height="390" alt="Screenshot 2026-03-31 at 8 55 49 AM" src="https://github.com/user-attachments/assets/c4bcef76-d1e1-4685-8a57-e3bbb222e99e" />

<img width="635" height="439" alt="Screenshot 2026-03-31 at 8 56 04 AM" src="https://github.com/user-attachments/assets/25a52676-9995-4288-8916-3987ff47a638" />

<img width="637" height="409" alt="Screenshot 2026-03-31 at 8 56 40 AM" src="https://github.com/user-attachments/assets/944dd839-5eb4-4dc8-8ab9-798ca2b20c2b" />

<img width="661" height="714" alt="Screenshot 2026-03-31 at 8 57 51 AM" src="https://github.com/user-attachments/assets/69b60274-2930-42e7-b68a-aea048288005" />

<img width="638" height="245" alt="Screenshot 2026-03-31 at 8 58 12 AM" src="https://github.com/user-attachments/assets/1057a2e0-3626-415f-a92a-e3b06161f629" />

<img width="642" height="285" alt="Screenshot 2026-03-31 at 8 58 31 AM" src="https://github.com/user-attachments/assets/534819ec-4d87-44e7-aa8c-d0f78cc0825e" />

<img width="653" height="534" alt="Screenshot 2026-03-31 at 8 59 02 AM" src="https://github.com/user-attachments/assets/87a8301e-de7f-471b-b822-03efa64a1654" />

<img width="651" height="373" alt="Screenshot 2026-03-31 at 8 59 27 AM" src="https://github.com/user-attachments/assets/b20f6558-0ca5-4833-aac1-ee23d480404d" />

<img width="641" height="297" alt="Screenshot 2026-03-31 at 8 59 41 AM" src="https://github.com/user-attachments/assets/da65ded0-cd18-48cc-9df6-11b95a8a85f0" />

<img width="657" height="240" alt="Screenshot 2026-03-31 at 8 59 56 AM" src="https://github.com/user-attachments/assets/91820eaa-d4bd-48f4-9141-082ddd00b9d6" />

## Queries
<img width="717" height="336" alt="Screenshot 2026-03-29 at 5 16 21 PM" src="https://github.com/user-attachments/assets/980bfdf3-5a8b-468f-bc49-639a2e572fc1" />


  1. Query 1 - Simple Question: What customers are currently in the database? Why it matters: A manager may want a full customer list for outreach, customer service, or record review.

SELECT customerID, firstName, lastName, emailAddress, phoneNumber FROM Customers ORDER BY lastName, firstName;

Query Response:<img width="539" height="362" alt="Q1" src="https://github.com/user-attachments/assets/c2ee7f04-aa37-4391-99eb-7483eadc4860" />

Natural Language Description: This query retrieves all customers in the database, displaying their ID, first name, last name, email address, and phone number. The results are sorted alphabetically by last name and first name.

Managerial Relevance: Managers use this query to maintain an up-to-date customer directory. It supports customer outreach, verifies stored contact information, and helps ensure accurate records for communication and service.

  2. Query 2 - Simple Question: What products does the business carry? Why it matters: A manager may want a current list of products for catalog review, sales planning, or inventory coordination.

SELECT productID, productName, productType FROM Products ORDER BY productType, productName;

Query Response: <img width="404" height="326" alt="Screenshot 2026-03-30 203739" src="https://github.com/user-attachments/assets/2ab0b99f-55be-48aa-831e-21b82668f7ec" />

Natural Language Description:This query lists all products, including product ID, name, and type. The results are organized by product type and then alphabetically by product name.

Managerial Relevance:Managers can review the full product catalog to support sales planning, marketing strategies, and inventory management. It ensures the business has a clear understanding of its offerings.

  3. Query 3 - Simple Question: What suppliers are in the system? Why it matters: A manager may need a supplier directory when reviewing vendor relationships or sourcing issues.

SELECT SupplierID, supName FROM Suppliers ORDER BY supName;

Query Response: <img width="367" height="269" alt="Q3" src="https://github.com/user-attachments/assets/cee84f2b-31e0-4cac-bbee-d89d3cb2bd73" />

Natural Language Description:This query retrieves all suppliers along with their IDs and names, sorted alphabetically.

Managerial Relevance:Managers use this to evaluate vendor relationships, identify sourcing options, and confirm supplier records when making purchasing or supply chain decisions.

  4. Query 4 - Simple Question: What store locations are recorded in the database? Why it matters: A manager may want to review all operating locations for staffing or supplier coordination.

SELECT LocationID, city, state, areaCode FROM Store Location ORDER BY state, city;

Query Response: <img width="395" height="161" alt="Q4" src="https://github.com/user-attachments/assets/42f280db-44da-4867-bd04-1f343655fbf6" />

Natural Language Description:This query returns all store locations, including location ID, city, state, and area code. Results are sorted geographically.

Managerial Relevance:Managers can use this to analyze regional operations, allocate resources, coordinate staffing, and ensure all store locations are properly tracked.

5. Query 5 - Complex Question: Which customers have generated the most total order revenue? Why it matters: A manager can use this to identify the highest-value customers and focus retention efforts on them.

SELECT c.customerID, c.firstName, c.lastName, SUM(o.amount) AS total_spent FROM Customers c JOIN Orders o ON c.customerID = o.customerID GROUP BY c.customerID, c.firstName, c.lastName ORDER BY total_spent DESC;

Query Response: <img width="464" height="281" alt="Q5" src="https://github.com/user-attachments/assets/8e14a444-fbf2-4893-bdae-c7d33c5ff13c" />

Natural Language Description:This query joins Customers and Orders to calculate total spending per customer using SUM. Results are grouped by customer and sorted from highest to lowest spending.

Managerial Relevance:Managers can identify high-value customers and prioritize retention strategies, loyalty programs, and personalized marketing to maximize long-term revenue.

  6. Query 6 - Complex Question: Which products have sold the highest total quantity? Why it matters: A manager can use this to identify top-selling products and make pricing, stocking, and promotion decisions.

SELECT p.productID, p.productName, p.productType, SUM(od.orderqty) AS total_quantity_sold FROM Products p JOIN Order Details od ON p.productID = od.productID GROUP BY p.productID, p.productName, p.productType ORDER BY total_quantity_sold DESC;

Query Response:  <img width="539" height="312" alt="Q6" src="https://github.com/user-attachments/assets/a8f9db3e-e745-463a-95b4-d654365cd77a" />

Natural Language Description:This query joins Products and Order Details and calculates the total quantity sold for each product using SUM. Results are grouped and ranked by quantity sold.

Managerial Relevance:Managers use this to identify high-demand products, optimize inventory levels, and ensure popular products remain in stock.

  7. Query 7 - Complex Question: Which products have generated the most order revenue? Why it matters: A manager can use this to distinguish products that drive revenue, not just volume.

SELECT p.productID, p.productName, SUM(od.orderPrice * od.orderqty) AS total_product_revenue FROM Products p JOIN Order Details od ON p.productID = od.productID GROUP BY p.productID, p.productName ORDER BY total_product_revenue DESC;

Query Response: <img width="600" height="315" alt="Q7" src="https://github.com/user-attachments/assets/56b07101-7173-41a0-8db2-048ed7b6c502" />

Natural Language Description:This query calculates total revenue per product by multiplying price and quantity, then summing across all orders. Results are grouped and sorted by revenue.

Managerial Relevance:Managers can distinguish between products that sell frequently and those that generate the most profit, helping guide pricing, promotions, and product prioritization.

  8. Query 8 - Complex Question: Which products have never been included in any order? Why it matters: A manager can use this to identify underperforming or unused products that may need promotion or discontinuation.

SELECT p.productID, p.productName, p.productType FROM Products p WHERE NOT EXISTS ( SELECT 1 FROM Order Details od WHERE od.productID = p.productID ) ORDER BY p.productName;

Query Response:  <img width="571" height="304" alt="Q8" src="https://github.com/user-attachments/assets/234f0ec1-aa3f-418f-8a59-922fc7967857" />

Natural Language Description:This query uses a NOT EXISTS subquery to identify products that do not appear in any order records.

Managerial Relevance:Managers can identify underperforming or inactive products. This helps in deciding whether to promote, discount, or discontinue these items.

  9. Query 9 - Complex Question: Which customers have spent more than the average order amount in total? Why it matters: A manager can use this to identify above-average customers for loyalty offers or targeted marketing.

SELECT c.customerID, c.firstName, c.lastName, SUM(o.amount) AS total_customer_spent FROM Customers c JOIN Orders o ON c.customerID = o.customerID GROUP BY c.customerID, c.firstName, c.lastName HAVING SUM(o.amount) > ( SELECT AVG(amount) FROM Orders ) ORDER BY total_customer_spent DESC;

Query Response  <img width="536" height="279" alt="Q9" src="https://github.com/user-attachments/assets/ab2af1ba-c118-4e59-8a06-9dce792da22f" />

Natural Language Description: This query calculates total spending per customer and uses a subquery with AVG to filter customers whose total exceeds the average order amount. It also uses HAVING.

Managerial Relevance: Managers can identify above-average customers for targeted marketing campaigns, loyalty rewards, and upselling opportunities.

  10. Query 10 - Complex Question: How many products does each supplier provide to each store location? Why it matters: A manager can use this to evaluate supplier coverage by location and spot sourcing concentration or gaps.

SELECT s.supName, sl.city, sl.state, COUNT(so.productID) AS products_supplied FROM Suppliers s JOIN Supplier Orders so ON s.SupplierID = so.SupplierID JOIN Store Location sl ON so.LocationID = sl.LocationID GROUP BY s.supName, sl.city, sl.state ORDER BY s.supName, sl.state, sl.city;

Query Response: <img width="520" height="377" alt="Q10" src="https://github.com/user-attachments/assets/cb8e46d3-d774-4593-ab4f-ea3e8901c9be" />

Natural Language Description:This query joins Suppliers, Supplier Orders, and Store Location tables and counts how many products each supplier provides to each location.

Managerial Relevance:Managers can evaluate supplier coverage across locations, identify over-reliance on certain suppliers, and detect gaps in supply chain distribution.

## Database Information
Database Name: Group_21479_G5
