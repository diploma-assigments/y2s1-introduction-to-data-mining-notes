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
> Basically, OLTP is DB for normal users, applications. 
> OLAP is DB specialized only for data mining, storing results and decision making.

### Why seperate data warehouse (OLAP)

| OLTP                               | OLAP                                             |
| ---------------------------------- | ------------------------------------------------ |
| constant read and write            | optimized for complex queries (read)             |
| store current data (username, DOB) | store historical data (trend of number of users) |

