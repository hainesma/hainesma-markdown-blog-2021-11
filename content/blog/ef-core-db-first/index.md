---
title: Database-First Approach to Entity Framework Core
Category: Technical
tags: .Net, Entity Framework
author: Mark Haines
date: 2018-03-09
---
Test change
Test2

Entity Framework maps models in a .Net project to tables in a SQL database, allowing us to manipulate the database from within our .Net app.

There are two approaches to setting up an EF Core project: 
1) Create the database and tables first. Then use EF Core to scaffold the database and generate the models and database context.
2) Write the models and database context first in C#. Then use EF Core to migrate the database.

For this project, I will use the database-first approach. There are two reasons for this. One, I find that it's faster to write the SQL query than to write the C# models. But more importantly, it saves a lot of work to have Entity generate the database context, which manages the connection to the database.


## Steps
1. Create SQL database and tables
2. Create a new ASP.NET Core project
3. Install EF Core packages
4. Scaffold the database
    - generates a model for each table
    - generates the DbContext
5. Set up DbContext service in Startup.cs
6. Create database controller

Frontend Steps Using Angular
7. Generate service
7. Generate a component for each view
8. Create models
9. Pass data to components


### Install EF Core packages

Open the NuGet package manager

