# High Level System Design | ETL - multiple clients
High level description of system design which involves ETL process from multiple clients with different data systems


## Goal
Having some statistic model that performs behaviour analysis or some data mining tasks on client's data there is a need
in some ETL mechanism that allows gathering this data and make it more structurized for analyzing purposes.
Since different clients (enterprises) have different IT systems and APIs the ETL tool has to be highly configurable, applicable to any data source and generic as much as possible in order to preserve ан ease of maintenance. Client's data might change and our solution should be addapted to this changes as well.

## Solution
In the following diagram there is a description of how the ETL flow mentioned above can look like. As you can see there are three main layers where one layer is decoupled from another, selfcontained, replacable and also can be scaled if needed: 

![ETL diagram](https://user-images.githubusercontent.com/33380175/71544124-c9201900-2983-11ea-8af1-d46202fdc20d.png)
