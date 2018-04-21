1.1 TRANSACTIONS
-----

Concurrency control is the activity of coordinating the actions of processes that operate in parallel, 
access shared data, and therefore potentially interfere with each other. Recovery is the activity of ensuring
that software and hardware failures do not corrupt persistent data. Concurrency control and recovery problem
arise in the design of hardware, operating systems, real time systems, communications systems, and database 
systems, among others. In this book, We will explore concurrency control and recovery problems in database systems.

We will study these problems using a model of database systems. This model is abstraction of many types of data
handling systems, such as database management systems of data processing applications, transaction processing system
for airline reservations or banking, and file systems for a general purpose computing environment. Our study of
concurrency control and recovery applies to any such systems that conforms to our model.

The main component of this model is *transaction*. Infomally, a transaction is an execution of a program that accesses
a shared database.
