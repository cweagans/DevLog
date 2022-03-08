---
id: xtejm3wwwe76a9b6zl8xrqp
title: Via a Result Set
desc: ''
updated: 1641413994976
created: 1641413994976
---


### Return via result set

```sql
USE AdventureWorks2012;  
GO  
IF OBJECT_ID('Sales.uspGetEmployeeSalesYTD', 'P') IS NOT NULL  
   DROP PROCEDURE Sales.uspGetEmployeeSalesYTD;  
GO  
CREATE PROCEDURE Sales.uspGetEmployeeSalesYTD  
AS    
 
   SET NOCOUNT ON;  
   SELECT LastName, SalesYTD  
   FROM Sales.SalesPerson AS sp  
   JOIN HumanResources.vEmployee AS e ON e.BusinessEntityID = sp.BusinessEntityID  
   
RETURN  
GO
```