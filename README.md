# Hadoop Notes

## What is BigData?
Big Data is a collection of data that is huge in volume, yet growing exponentially with time. 
It is a data with so large size and complexity that none of traditional data management tools can store it or process it efficiently.

<img width="1028" alt="image" src="https://github.com/user-attachments/assets/beb15d7f-c81a-445c-a8a8-5be35539f776" />

### 5 V's of BigData
- **Volume:** This refers to the sheer quantity of data, which is typically enormous. It can range from terabytes to 
  petabytes and even exabytes of data
- **Velocity:** This refers to the speed at which new data is generated and the speed at which data moves around. With 
  the growth of the internet and smart devices, data is being generated continuously, in real time, from various 
  sources
- **Variety:** This refers to the different types of data that are now available. Big Data can include structured data 
  (SQL databases), semi-structured data (XML, JSON), unstructured data (Word documents, JPEG images), and even 
  complex structured data (from ERP systems or websites).
- **Veracity:** This refers to the quality of the data, which can vary greatly. Veracity allows us to deal with 
  uncertainty or imprecision, which is often an issue with many forms of big data.
- **Value:** This is the ability to turn data into value. This is becoming the most important V of Big Data because it's 
  important that business make a return in their investment in big data and data analytics.

### Type of data
- **Structured data:** This type fo data that adheres to a model and is easily searchable. Examples include data 
  stored in relational databases and spreadsheets.
- **Unstructured data:** This type of data does not have a predefined model or is not organized in a pre-defined 
  manner. Example include text files, images, videos, emails, web pages, and social medial posts.
- **SemiStructured data:** This is a hybrid of structured and unstructured data. While it does not conform to the 
  formal structure of data models, it contains tags or other markers to enforce hierarchy and order. Examples 
  include JSON, XML, and email messages with both defined fields and free-form text.

### What is cluster?
A cluster, in the context of computing, refers to a group of computers or servers that work together and can
be viewed as a single system. These computers, known as nodes, interact with each other to accomplish a
common goal. This setup is used to improve performance and availability over that provided by a single
computer, while typically being much more cost-effective and scalable than a single computer of comparable
speed or availability.

<img width="735" alt="image" src="https://github.com/user-attachments/assets/96ee93fe-fcbe-495c-9781-35ba76f6eacb" />


### Vertical Vs Horizontal Scaling
- **Vertical Scaling:** Increasing the capacity of single server such as using a more powerful CPU, adding more RAM, or 
  increasing disk space. Is called vertical scaling. This is know as scaling up.
- **Horizontal Scaling:** Adding more server to system and distributing load across the servers known as Horizontal 
  scaling. which is know as scaling out.

<img width="735" alt="image" src="https://github.com/user-attachments/assets/5fc8b535-f443-4617-b9bf-f2d468467678" />

## Hadoop
Hadoop is an open-source software framework for storing and processing big data in a distributed fashion on large
cluster of commodity hardware. Essentially, it accomplishes two tasks: massive data storage and faster processing.

There are three main components.

- **Hadoop Distributed File System (HDFS)**: This is storage component of Hadoop, designed to hold large amounts of data 
  potentially in the range of petabytes or even exabytes. The data is distributed across multiple nodes in the 
  cluster, providing high availability and fault tolerance.
- **Map-Reduce:** This is the processing component of Hadoop, which provides a software framework for writing 
  applications that process large amounts of data in parallel. MapReduce operations are divided into two stages: the 
  **Map stage**, which sorts and filters the data and the **Reduce stage** which summarizes the data
- **Yet Another Resource Negotiator (YARN)**: This is the resource management layer in Hadoop. Introduced in Hadoop 2.0, 
  YARN decouples the programming model from the resource management infrastructure, and it oversees and manages the 
  compute resources in the cluster.

  <img width="1408" alt="image" src="https://github.com/user-attachments/assets/dfb74ab3-9e45-4a60-b132-d02273dba03e" />


### HDFS
Hadoop database file system follows a master-slave architecture. The two main components HDFS are the NameNode (the 
master) and the Data Node(the slave)

**NameNode:** The NameNode is the centerpiece of the HDFS file system. It keeps the directory tree of all files in the 
file system, and tracks where across the cluster the file data is kept. It does not store the data of these files 
itself.

- The NameNode manages the file system namespace. It maintains the file system tree and the metadata for all the 
  files and directories in the tree.
- The NameNode also knows the DataNodes on which all the blocks for a given file are located.

**DataNode:** The DataNode are responsible for serving read and write requests from the file system's clients. They 
also perform block creation, and replication upon instruction from the NameNode.
- The DataNodes manage the storage attached to the nodes that they run on.
- DataNodes regularly report back to the NameNode with lists of blocks that they are storing.

<img width="1049" alt="image" src="https://github.com/user-attachments/assets/eb75215d-6459-4ad3-bfaf-581a4f352162" />


