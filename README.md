# Northwind-ERD


1. SELECT Customer.FirstName || " " || Customer.LastName AS "Name", Customer.CustomerId, Customer.Country  FROM Customer
WHERE Customer.Country != "USA";

2. SELECT Customer.FirstName || " " || Customer.LastName AS "Name", Customer.CustomerId, Customer.Country  FROM Customer
WHERE Customer.Country = "Brazil";

3. SELECT Customer.FirstName || " " || Customer.LastName AS "Name", Invoice.InvoiceId, Invoice.InvoiceDate, Invoice.BillingCountry  FROM Customer
JOIN Invoice on Customer.CustomerId = Invoice.CustomerId
WHERE Customer.Country = "Brazil"

4. SELECT * FROM Employee
WHERE Employee.Title = "Sales Support Agent"

5. SELECT Invoice.BillingCountry FROM Invoice
GROUP BY Invoice.BillingCountry

6. SELECT Customer.FirstName || " " || Customer.LastName AS "Name", Customer.Country, Invoice.Total  FROM Customer
JOIN Invoice ON Customer.CustomerId = Invoice.CustomerId
WHERE Customer.Country = "Brazil"

7. SELECT Employee.FirstName || " " || Employee.LastName AS "Name", Invoice.InvoiceId FROM Employee
JOIN Customer ON Employee.EmployeeId = Customer.SupportRepId
JOIN Invoice ON Customer.CustomerId = Invoice.CustomerId
