# Setting up an ASP.NET Core MVC Project with Entity Framework Core for Visual Studio Code (VSC) on MacOS - ARM (Apple Silicon) with Azure Data Studio

## Prerequisites:
1. Ensure that you have [installed the .NET SDK](https://dotnet.microsoft.com/en-us/download).
2. Install Docker to manage SqlServer and Azure Data Studio for database connectivity. ([consult](https://lucidgen.com/en/how-to-install-sql-server-and-azure-for-mac/))

## Installations:

### Step 1: Create a new ASP.NET Core MVC project
Navigate to your project folder and execute the following commands:

```bash
dotnet new mvc -n YourProjectName
cd YourProjectName
```

### Step 2: Add Entity Framework Core packages
Run the following commands to add Entity Framework Core packages:

```bash
dotnet add package Microsoft.EntityFrameworkCore
dotnet add package Microsoft.EntityFrameworkCore.SqlServer
dotnet add package Microsoft.EntityFrameworkCore.Design
```

Note: If your current .NET SDK does not support the specified package versions, include the appropriate version at the end of the command. For example:

```bash
dotnet add package Microsoft.EntityFrameworkCore --version 7.0.0
```

### Step 3: Scaffold the Database Context
Use the following command to scaffold the database context and models:

```bash
dotnet ef dbcontext scaffold "Server=localhost; Database={DATABASE_NAME}; User Id=sa; Password={PASSWORD}; Trust Server Certificate=True;" Microsoft.EntityFrameworkCore.SqlServer -o Models
```

Make sure to replace {DATABASE_NAME} and {PASSWORD} with your actual database name and password.

This setup is designed for the latest version of the mentioned packages. Adjust the version numbers in the commands if needed.

Feel free to reach out if you encounter any issues or have further questions.
