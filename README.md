# High Level System Design | ETL - multiple clients
High level description of system design which involves ETL process from multiple clients with different data systems


## Goal
Having some statistic model that performs behaviour analysis or some data mining tasks on client's data there is a need
in some ETL mechanism that allows gathering this data and make it more structurized for analyzing purposes.
Since different clients (enterprises) have different IT systems and APIs the ETL tool has to be highly configurable, applicable to any data source and generic as much as possible in order to preserve ан ease of maintenance. Client's data might change and our solution should be addapted to this changes as well.

## Solution
In the following diagram there is a description of how the ETL flow mentioned above can look like. As you can see there are three main layers where one layer is decoupled from another, selfcontained, replacable and also can be scaled if needed: 

![ETL diagram](https://user-images.githubusercontent.com/33380175/71544124-c9201900-2983-11ea-8af1-d46202fdc20d.png)


### Client integration layer
Different clients have different APIs to interact with our ETL. Clients want to send us their data without integrating with our system or developing additional integration mechanisms. The most popular way for client to share his data with external services is via some __SFTP__ that temporary stores his data to be taken by some file tranfer service (Extract phase). Another way is to expose our __API__ to our clients so they could send us their data by using it (i.e API for our file transfer service). Simillar way is some __web interface__ that makes the same but has some UI for customer convenience. There is also an option for client to send the data to some cloud storage (Amazon S3, Microsoft Simple Storage etc.) <br />
The final stage of the extract phase is __Data Lake__ - this is a storage for all customer's data (files). It has all file history per customer. Data lake stores the files as is - the same format as client sends to us. There can be csv, json, text, excel and many other formats stored in there.
