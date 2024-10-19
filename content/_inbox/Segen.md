2023-11-27
Tags: #interview #project 


SQL container set-up: https://learn.microsoft.com/en-us/sql/linux/quickstart-install-connect-docker?view=sql-server-ver16&pivots=cs1-bash


```
docker run -e "ACCEPT_EULA=Y" -e "MSSQL_SA_PASSWORD=Strong@Passw0rd" -p 1433:1433 --name sql1 --hostname sql1 -d mcr.microsoft.com/mssql/server:2022-latest
```

Should change password after setup as it's accessible as an environment variable

```
CREATE DATABASE segenDev;
GO

USE segenDev
CREATE TABLE Items (id INT, name NVARCHAR(50), quantity INT);
INSERT INTO Items VALUES (1, 'banana', 150); INSERT INTO Items VALUES (2, 'orange', 154);
GO
```

---
# References
