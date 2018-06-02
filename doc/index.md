# Smark
A smark spark application builder from developers and for developers.

## What is Smark?
Smark is a lean framework on top of Apache spark aims to facilitate spark application development.

## Why do we need smart?
Apache spark is now a de facto big data transformation tool on Hadoop ecosystem due to its scalability, simple, powerful API and SQL support; With the spark 2.2 release, it uniforms the data access through commonly used SQL to a variety of data sources, it also introduced cost based optimizer, columnar data storage and code generation techniques to make queries fast, all of sudden, SQL become one of best features in spark applications.

SQL is the language to deal with structured data, but programming SQL with spark is full of challenges: 
  * Embedding SQL in Java/Scala code reduces the code maintainability;
  * Intermediate table/views are ephemeral ,which means they are only available when spark application is running, the table/view schema is not available at development time; while inspecting intermediate result is critical in debuting the SQL statements.
  * SQL itself is not strongly typed language, its syntactical errors can only be caught when the SQL get ran;
