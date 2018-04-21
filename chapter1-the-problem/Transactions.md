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
a shared database. The goal of concurrency control and recovery is to ensure that transactions execute atomically
meaning that

1. each transaction accesses shared data without interfering with other transactions, and 
2. if a transaction terminates normally, then all of its effects are made permanent; otherwise it has no effect at all.

The purpose of this chapter is to make this model precise.

In this section we present a user-oriented model of the system, Which consists of a database that a user can access
by executing transactions.
