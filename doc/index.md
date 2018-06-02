# Smark
A smark spark application builder from developers and for developers.

## What is Smark?
Smark is a lean framework on top of Apache spark aims to facilitate spark application development.

## Why do we need smart?
Apache spark is now a de facto big data transformation tool on Hadoop ecosystem due to its scalability, simple, powerful API and SQL support; With the spark 2.2 release, it uniforms the data access through commonly used SQL to a variety of data sources, it also introduced cost based optimizer, columnar data storage and code generation techniques to make queries fast, all of sudden, SQL become one of best features in spark applications.

SQL is the language to deal with structured data, but programming SQL with spark is full of challenges: 
  * Embedding SQL in Java/Scala code reduces the code maintainability;
  * Intermediate table/views are ephemeral ,which means they are only available when spark application is running, the table/view schema is not available at development time; while inspecting table schema and check query result are primary routine work for data engineers.
  * SQL itself is not strongly typed language, its syntactical errors can only be caught when the SQL get ran.
  
## How Smark is smart?
  
  From high level, all spark batch applications start with loading data from some data sources and then transform the data with the spark APIs, especially SQL is preferred when the data is structured and then save the result to back or other data resources.

Spark provide very succinct API to load, transform and save data from/to different data sources, including text file, JSON, parquet, AVRO, ORC, RDBC through JDBC, HIVE etc. Obviously to load data from different sources, developers need to specify the configurations for a specific data source, take CSV file as an example, delimiter, header, quote character, escape character is needed to load CSV, actually loading and persisting data in spark is not a concern, even though the configurations for various data source is not strongly typed defined as part of API to provide the configuration flexibility, it is still once-off coding.

Transformation part is the challenging part, since we need to write multiple SQLs or call data frame APIs to implement the real business data transformation, such as filtering, mapping, aggregation, segregation. etc.

Smark provides a very thin layer on top of spark, it externalizes the data loading, transformation , data persisting configurations including SQL statements  into a standalone configuration file, and then the executor will read the configuration in and execute the tasks.

Smark does not  stop there, it provides the GUI application to help developers to compose the spark task specifications , which make the developers to write the spark applications with interactive SQLs and with SQL autocompletion

When the Smart specification is ready, the full-fledged  java/scala application including unit tests is ready in the developer’s favourite IDE, within the IDE, developers could do whatever is necessary to customize or extend, in return, the customized code for SQL user defined functions are available as autocompletion candidates in the GUI SQL interactive console.
