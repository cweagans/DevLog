---
id: 7iyhzkl8e72rmndl8sy29ae
title: Select Data into Json
desc: ''
updated: 1641413928375
created: 1641105063937
stub: false
isDir: false
---


```sql
SELECT TOP (1000) *
  FROM [DataBase].[schema].[table] AS t
  FOR JSON PATH, ROOT('RootNode')
```

---

- Reference:
  - [Reference Docs](https://docs.microsoft.com/en-us/sql/relational-databases/json/format-query-results-as-json-with-for-json-sql-server?view=sql-server-ver15)