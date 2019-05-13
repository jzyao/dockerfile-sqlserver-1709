# dockerfile-sqlserver-1709

## How to use this image
Start a mssql server instance
docker run -d -p 1433:1433 -e sa_password=<sa_password> -e ACCEPT_EULA=Y microsoft/mssql-server-windows-developer

Connect to Microsoft SQL Server
You can connect to the SQL Server instance from inside the same container by using the sqlcmd utility, or from outside the container by downloading SQL Server Management Studio (SSMS). Follow this blog for detailed steps on how to connect to the SQL Server instance from inside or outside the container.

Environment Variables
ACCEPT_EULA: Confirms acceptance of the end user licensing agreement found here.

sa_password: The system administrator (userid = 'sa') password used to connect to SQL Server once the container is running. The password must meet the password complexity requirements found here,

attach_dbs (optional parameter): The configuration for attaching custom DBs (.mdf, .ldf files). The following example shows all parameters in action:

ldf']}]" microsoft/mssql-server-windows-developer
If you are trying to use attach_dbs in an ENV in a Dockerfile or docker-compose file on Windows use this format:

ENV attach_dbs='[{"dbName":"mydb","dbFiles":["C:\\temp\\mydb.mdf","C:\\temp\\mydb.ldf"]}]'
