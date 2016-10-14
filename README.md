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

8. SELECT Invoice.Total, Customer.FirstName || ' ' || Customer.LastName AS "Name", Customer.Country, Employee.FirstName || ' ' || Employee.LastName AS "Employee Name" FROM Customer
JOIN Employee ON Customer.SupportRepId = Employee.EmployeeId
JOIN Invoice ON Customer.CustomerId =  Invoice.InvoiceId

9. SELECT COUNT(Invoice.Total) FROM Invoice
WHERE Invoice.InvoiceDate LIKE "%2009%" OR Invoice.InvoiceDate LIKE "%2011%"
SELECT SUM(Invoice.Total) FROM Invoice
WHERE Invoice.InvoiceDate LIKE "%2009%"
SELECT SUM(Invoice.Total) FROM Invoice
WHERE Invoice.InvoiceDate LIKE "%2011%"

10.SELECT SUM(InvoiceLine.InvoiceId) FROM InvoiceLine
WHERE InvoiceLine.InvoiceId = "37"

11. SELECT COUNT(*) FROM InvoiceLine
GROUP BY InvoiceLine.InvoiceId

12. SELECT Track.Name, InvoiceLine.InvoiceLineId FROM InvoiceLine
JOIN Track ON InvoiceLine.TrackId = Track.TrackId

13. SELECT Artist.Name, Track.Name, InvoiceLine.InvoiceLineId FROM InvoiceLine
JOIN Track ON InvoiceLine.TrackId = Track.TrackId
JOIN Album ON Track.AlbumId = Album.AlbumId
JOIN Artist ON Album.ArtistId = Artist.ArtistId

14. SELECT Invoice.BillingCountry, COUNT(Invoice.Total) FROM Invoice
GROUP BY Invoice.BillingCountry

15. SELECT Playlist.Name, COUNT(PlaylistTrack.TrackId) AS "Count" FROM Playlist
JOIN PlaylistTrack ON Playlist.PlaylistId = PlaylistTrack.PlaylistId
GROUP BY Playlist.Name

16. SELECT Album.Title, MediaType.Name, Genre.Name, Track.Name FROM Album
JOIN Track ON Album.AlbumId = Track.AlbumId
JOIN Genre ON Track.GenreId = Genre.GenreId
JOIN MediaType ON Track.MediaTypeId = MediaType.MediaTypeId
ORDER BY Album.Title

17. SELECT COUNT(InvoiceLine.InvoiceLineId) AS "Invoice Line Cout" FROM Invoice
JOIN InvoiceLine ON Invoice.InvoiceId = InvoiceLine.InvoiceId
GROUP BY Invoice.InvoiceId
