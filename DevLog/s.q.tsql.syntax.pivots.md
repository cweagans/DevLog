---
id: gcfg3h4ykxwq9yirrtsq0ag
title: Pivots
desc: ''
updated: 1641413891718
created: 1641105063936
stub: false
isDir: false
---


### Pivoting

the Pivot is like a transcribe operator in excel. You take the top left point, anchor it and then flips the axis' and their values.

```sql
SELECT Name
	,pvt.Low
	,pvt.Med
	,pvt.High
	,pvt.Ultra
FROM Person
PIVOT
	(SUM(Total) FOR Level IN ([Low], [Med], [High], [Ultra])
	) AS pvt
```

### UN-pivoting

```sql
SELECT Name
	,upvt.Level
	,upvt.Total
FROM Person
UNPIVOT
	(Total FOR Level IN ([Low], [Med], [High], [Ultra])
	) AS upvt
```