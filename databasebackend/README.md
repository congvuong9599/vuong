# MyProject
# Đặng Công Vương
# Trần Quốc Vương
# Phạm Huỳnh Hải

# How to run
cd backend
1.Stop and remove old container: sudo docker stop backend && sudo docker rm backend
2.docker build -t backend .
3.docker run -d --name backend --env db_ip=172.17.0.2 -p 8080:8080 backend 
172.17.0.2 ( ip của cổng 5432) docker inspect coredb
172.17.86.33:8080 (ipconfig chạy bên postman)

# deploy db
 1.docker load --input postgres_11.2-alpine.tar
 2.docker run -d --restart unless-stopped --name coredb -e POSTGRES_PASSWORD=postgres -e POSTGRES_DB=postgres -v ~/northwind_db:/var/lib/postgresql/data -p 5432:5432 postgres:11.2-alpine
# DB
1.docker exec -it coredb bash
2.psql -U postgres
6.\l
7.create database KTgiuaki;
8.\c KTgiuaki;
9.\dt
10.select * from tblcustomers;
    select * from Categories;
    select * from Employees ,OrderDetails , Orders , Products, Shippers, Suppliers
    - Các bảng ở file : db/sql.txt
# Entity
# Customers
 - CustomerID
 - CustomerName
 - ContactName
 - Address
 - City
 - PostalCode
 - Country
# Categories 
 - CategoryID
 - CategoryName
 - Description 
# Employees
 - EmployeeID
 - LastName
 - FirstName
 - BirthDate
 - Photo
 - Notes
# OrderDetails
 - OrderDetailID
 - OrderID
 - ProductID
 - Quantity
# Orders
 - OrderID
 - CustomerID
 - EmployeeID
 - OrderDate
 - ShipperID
# Products
 - ProductID SERIAL
 - ProductName
 - SupplierID
 - CategoryID
 - Unit
 # Shippers
 - ShipperID
 - ShipperName
 - Phone
# Suppliers
 - SupplierID
 - SupplierName
 - ContactName
 - Address
 - City
 - PostalCode
 - Country
 - Phone
 # Xem cơ sở dữ liệu ở file : sql.txt
 # xem API ở file : app.py