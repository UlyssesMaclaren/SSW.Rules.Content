---
type: rule
title: Do you have an understanding of 'schema changes' and their increasing complexity?
uri: do-you-have-an-understanding-of-schema-changes-and-their-increasing-complexity
created: 2009-10-06T23:32:50.0000000Z
authors:
- id: 1
  title: Adam Cogan

---

 This field should not be null (Remove me when you edit this field). 

```
ALTER TABLE dbo.Employees
    ADD Gender bit NOT NULL
GO
```

Figure: Add a column (Easy) 

```
ALTER TABLE dbo.Employees
    DROP COLUMN TitleOfCourtesy
GO
```

Figure: Delete a column (Easy) 

```
EXECUTE sp_rename N'dbo.Employees.HireDate', N'Tmp_StartDate_1', 'COLUMN'
GO
EXECUTE sp_rename N'dbo.Employees.Tmp_StartDate_1', N'StartDate', 'COLUMN'
GO
```

Figure: Rename a column (Medium) 

```
CREATE TABLE dbo.Tmp_Employees
(
......
Gender char(2) NULL,
......
) ON [PRIMARY]
TEXTIMAGE_ON [PRIMARY]
......
IF EXISTS(SELECT * FROM dbo.Employees)
    EXEC('INSERT INTO dbo.Tmp_Employees (......, Gender,......)
                    SELECT ......,Gender ,...... 
                    FROM dbo.Employees WITH (HOLDLOCK TABLOCKX)
              ') 
......
GO
DROP TABLE dbo.Employees
GO
EXECUTE sp_rename N'dbo.Tmp_Employees', N'Employees', 'OBJECT'
GO
```

Figure: Change data type (Hard) e.g. Bit to Integer. The above is abbreviated, see [the full .SQL file](/Standards/CodeAndApplicationDesign/RulesToBetterSQLServerSchemaDeployment/Documents/EmployeesBitToInt.sql) 

```
CREATE TABLE dbo.Tmp_Employees
(
......
Gender int NULL,
......
) ON [PRIMARY]
TEXTIMAGE_ON [PRIMARY]
......
IF EXISTS(SELECT * FROM dbo.Employees)
    EXEC('INSERT INTO dbo.Tmp_Employees (......, Gender,......)
                    SELECT ......,CASE Gender WHEN ''F'' THEN ''0'' 
                                              WHEN ''M'' THEN ''1''
                                              WHEN ''NA'' THEN ''2''
                                              WHEN ''U'' THEN ''3''
                                              ELSE ''-1''
                                  END AS Gender ,...... 
                    FROM dbo.Employees WITH (HOLDLOCK TABLOCKX)
              ')
......
GO
DROP TABLE dbo.Employees
GO
EXECUTE sp_rename N'dbo.Tmp_Employees', N'Employees', 'OBJECT'
GO
```

Figure: Change data type (Very Hard) e.g. Text to Integer. Text to Integer and data conversion requires ["Data Motion Scripts"](/Standards/CodeAndApplicationDesign/RulesToBetterSQLServerSchemaDeployment/Pages/DoYouUnderstandADataTypeChangeDataMotionScripts.aspx). The above is abbreviated, see [the full .SQL file](/Standards/CodeAndApplicationDesign/RulesToBetterSQLServerSchemaDeployment/Documents/EmployeesCharToInt.sql)    
 And the point of know this. Well no tool out there, not Redgate's SQL Compare, not Microsoft's Data Dude, nor SSW's SQL Deploy will do this automagically for you. So you better understand that this stuff is delicate.   
