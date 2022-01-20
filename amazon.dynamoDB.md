Let's talk about Amazon DynamoDB. At its most basic level, DynamoDB is a database. It's a serverless database, meaning you don't need to manage the underlying instances or infrastructure powering it. 

With DynamoDB, you create tables. A DynamoDB table, is just a place where you can store and query data. Data is organized into items, and items have attributes. Attributes are just different features of your data. If you have one item in your table, or 2 million items in your table, DynamoDB manages the underlying storage for you. And you don't need to worry about the scaling of the system, up or down. 

DynamoDB stores this data redundantly across availability zones and mirrors the data across multiple drives under the hood for you. This makes the burden of operating a highly available database, much lower. 

DynamoDB, beyond being massively scalable, is also highly performant. DynamoDB has a millisecond response time. And when you have applications with potentially millions of users, having scalability and reliable lightning fast response times is important. 

Now, DynamoDB isn't a normal database. In the sense that it doesn't use the very widely used query language, sequel, or SQL. Relational databases, like a standard MySQL Database, require that you have a well defined schema, in place. That might consist of one, or many tables that might relate to each other. You then use SQL to query the data. 

This works great for a lot of use cases, and has been the standard type of database historically. However, these types of rigid SQL databases, can have performance and scaling issues when under stress. The rigid schema also makes it so that you cannot have any variation in the types of data that you store in a table. So, it might not be the best fit for a dataset that is a little bit less rigid, and is being accessed at a very high rate. 

This is where non-relational, or NoSQL, databases come in. DynamoDB is a non-relational database. Non-relational databases tend to have simple flexible schemas, not complex rigid schemas, laying out multiple tables that all relate to each other. 

With DynamoDB, you can add and remove attributes from items in the table, at any time. Not every item in the table has to have the same attributes. This is great for datasets that have some variation from item to item. Because of this flexibility, you cannot run complex SQL queries on it. Instead, you would write queries based on a small subset of attributes that are designated as keys. 

Because of this, the queries that you run are non-relational databases tend to be simpler, and focus on a collection of items from one table, not queries than span multiple tables. This query pattern, along with other factors, including the way that the underlying system is designed, allows DynamoDB to be very quick in response time, and highly scalable. 

So, things to remember: DynamoDB is a non-relational, NoSQL database. It is purpose built. Meaning it has specific use cases, and it isn't the best fit for every workload out there. It has millisecond response time. It's fully managed, and it's highly scalable. One awesome example is on Prime Day in 2019, across the 48 hours of Prime Day, there were 7.11 trillion calls to the DynamoDB API, peaking at 45.4 million requests per second. That's insanely scalable, all without the underlying database management. That's pretty cool.