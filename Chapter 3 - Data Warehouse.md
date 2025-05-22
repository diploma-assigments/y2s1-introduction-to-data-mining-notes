### What is data warehouse?
> Central database that store historical, cleaned, integrated data to help organization analyze and make decisions.
> 
> * Decision support system
> * Seperate from operational database

### OLTP vs OLAP
| Feature                | OLTP                         | OLAP                                      |
| ---------------------- | ---------------------------- | ----------------------------------------- |
| **Users**              | Clerk, IT professional       | Knowledge worker                          |
| **Function**           | Day-to-day operations        | Decision support                          |
| **DB Design**          | Application-oriented         | Subject-oriented                          |
| **Data**               | Current, up-to-date,         | Historical, summarized, multidimensional, |
|                        | detailed, flat relational,   | integrated, consolidated                  |
|                        | isolated                     |                                           |
| **Usage**              | Repetitive                   | Ad-hoc                                    |
| **Access**             | Read/write, index/hash on PK | Lots of scans                             |
| **Unit of Work**       | Short, simple transaction    | Complex query                             |
| **# Records Accessed** | Tens                         | Millions                                  |
| **# Users**            | Thousands                    | Hundreds                                  |
| **DB Size**            | 100MB–GB                     | 100GB–TB                                  |
| **Metric**             | Transaction throughput       | Query throughput, response                |
> Basically, OLTP is DB for normal users, production applications. 
> OLAP is DB specialized only for data mining, storing results and decision making.

### Why seperate data warehouse (OLAP)

| OLTP                               | OLAP                                             |
| ---------------------------------- | ------------------------------------------------ |
| constant read and write            | optimized for complex queries (read)             |
| store current data (username, DOB) | store historical data (trend of number of users) |

### 3 Data Warehouse Models
##### 1. Enterprise Warehouse
> * Centralized data warehouse for entire organization
> * Store all subject areas (sales, HR, finance)

##### 2. Data Mart
> * Subset of enterprise warehouse
> * For specific group of users or department (sales, HR, finance)
> * Faster and cheaper to build than enterprise warehouse
> 
> **Dependent Data Mart:** Get all data from central warehouse
> **Independent Data Mart:** Build seperately, with its own sources and ETL processes

##### 3. Virtual Warehouse
> * A set of views over OLTP databases
> * No physical warehouse: data is not stored, only queried on demand
> * Lower cost, but slower

### Extraction, Transformation & Loading (ETL)
##### 1. Data Extraction
> Pull data from multiple sources (database, files, web API)
##### 2. Cleaning
> Detect and fix errors in data
##### 3. Transformation
> Convert data to common warehouse format
##### 4. Loading
> Move cleaned and transformed data into data warehouse
##### Refresh
> Update warehouse to keep up-to-date

### What is metadata in Data Warehouse?
> Data about data. Tells you what is in the warehouse, where it came from, how to use it.

### What is data cube?
> Smart way to look at lots of data from different angles (dimensions).
> Instead of tables, organize like cubes.
> 
> **Example:**
> How much was sold?
> When?
> What item?
> 
### Why use cube?
> Get answer fast

### What is fact table?
> Measurable data (like numbers) you want to analyze like total sales amount.

### What is dimension table?
> Details (provide context) you want to filter or group by, like product name, product category


### Conceptual Modeling of Data Warehouses (fancy way to say types of warehouse design)
##### Star Schema
> 1 fact table in the middle, many dimension tables around it
> ![[img_c3_a.png|400]]
##### Snowflake Schema
> Same as star schema, but dimension tables are normalized (like SQL normalization, breaking down table to smaller tables)
> ![[img_c3_b.png|400]]
##### Fact Constellation / Galaxy Schema
> Many fact tables, many dimension tables, all sharing.
> ![[img_c3_c.png|400]]

### 4 view in data warehouse design
##### 1. Top-down view
> Focus on selecting what data the warehouse need to include
##### 2. Data source view
> Look at info captured and stored in OLTP (source) system.
##### 3. Data warehouse view
> Show warehouse structure, mainly **fact tables** (metrics) and **dimension tables** (context)
##### 4. Business query view
> Perspective of end users querying and analyzing data from the warehouse.

### Data warehouse design approach
##### 1. Top-down approach
> Start from big picture — overall design and planning before building (more mature, structured).
##### 2. Bottom-up approach
> Start with small experiments, then expand (faster, repetitive)
##### 3. Hybrid approach
> Combine both methods

### Software engineering perspectives of designing data warehouse
##### 1. Waterfall model
> Step-by-step structured process, analyze fully before moving on to the next step
##### 2. Spiral mode
> Repetitive, quick cycles of development with quick feedback.

### Typical design process step (IMPORTANT PAST YEAR)
##### 1. Choose business process to model (orders, shipments)
##### 2. Choose grain (level of detail): what 1 row represent?
##### 3. Choose dimensions: time, products etc. (dimension tables)
##### 4. Choose measures (facts): sales amount, cost etc. (fact tables)

### What data warehouse is used for?
##### 1. Information processing
> Query data, basic statistics, create reports
##### 2. Analytical processing
> Multidimensional analysis
##### 3. Data mining
> discover hidden patterns from data (Chapter 1's definition of data mining)

