# Schema And Data Modelling in Power BI: A Comprehensive Guide

## Introduction

Power Bi is a powerful business intelligence tool used to analyze data and
create interactive reports and dashboards. However, the quality, performance,
and accuracy of Power Bi reports depend heavily on how the data is modeled.

### What is Data Modelling

Data modelling is the process of structuring data into tables and defining
relationships between them in a way that supports efficient analysis.

### What is a Schema

Schema refers to the organizational structure of your data model. Its the
specific arrangement or pattern you choose to organize your data tables and
their relationships.

### Define the Analysis Goal

Data modelling begins by identifying what needs to be analyzed.

Typical questions include:

- What is being measured?
- How will result be compared

Clear Goal guide the structure of the model

### Create the Fact Table

A fact table stores measurable data from business activities.

A table is a fact table if it:

- Contains numeric values
- Records transactions or events
- Grows continuously

Example:

- Sales transactions
- Orders
- Payments

Common fact table columns:

- SalesAccount
- Quantity
- OrderID
- ProductKey

### Create Dimension Tables

Dimension tables provides meaning to the facts.

They describe:

- Who performed the action
- What is involved
- When it happened
- Where it occurred

Example:

- Customer
- Product
- Date
- Location

Dimension allows data to be filtered, grouped, and summarized.

### Define Relationships

Relationships link dimension tables to the fact tables.

#### Key Rules for Defining Relationships

- Relationships are usually one-to-many
- Dimension tables are on the one side
- Fact tables are on the many side
- Filter flows from dimension to fact
- Single-direction filtering is preferred

Correct relationships ensure accurate results.

### Schema in Power Bi

A schema refers to the way table are structured and related within a data
model.Schema define how fact tables and dimension tables are organized to
support analysis and reporting.

Power Bi mainly uses two schema designs

- Star Schema
- Snowflake schema

#### Star Schema

A star schema is a data modelling design where a central fact table is directly
connected to multiple dimension tables. The structure resembles a star.
![Star Schema](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/j09gmuuibtxyexwfnnkl.png)

#### Advantages of Star Schema

- Easy to understand
- Faster query performance
- Simplifies DAX (Data Analysis Expression) calculation
- Reduces ambiguity in relationships
- Recommended by Microsoft for Power Bi

#### Disadvantages of Star Schema

- Uses more storage space
- Some data redundancy in dimension tables
- Less suitable for highly normalized data

Example:

- FactSales
- DimCustomer
- DimProduct
- DimDate
- DimRegion

Each Dimension connects directly to the fact table.

#### Snowflake Schema

A snowflake schema is a more complex version of a star schema where dimension
tables are normalized into multiple related tables.
![Snowflake Schema](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/jde16opc8my8txb1o7ku.png)

#### Advantages of Snowflake Schema

- Reduces data redundancy
- Uses less storage space
- Suitable for very large dimension tables
- Better normalization of data

#### Disadvantages of Snowflake Schema

- More complex due to many joins
- Slower performance due to many joins
- Harder to write and maintain DAX (Data Analysis Expression)
- More difficult to users to understand
- Not ideal for most Power Bi reports

Data Modelling is the foundation of effective Power Bi reporting. Understanding
schemas, fact and dimension tables and relationships allows analyst to build
models that are fast, accurate, easy to maintain.
