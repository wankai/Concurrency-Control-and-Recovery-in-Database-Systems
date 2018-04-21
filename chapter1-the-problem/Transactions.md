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
by executing transactions. In Section 1.2, we explain what is means for a transaction to execute atomically in the presence
failures. In Section 1.3, We explain what it means for a transaction to execute atomically in an environment where its
database access can be interleaved with those of other transactions. Section 1.4 presents a model of database system's
concurrency control and recovery components, whose goal is to realize transaction atomicity.

#### Database System

A database consists of a set of named data items. Each data item has a value. The values of data items at any one time
comprise the *state* of the database.

In practice, a data item could be a word of main memory, a page of disk, a record of a file, or a field of a record. The
size of data item contained in a data item is call granualarity of the data item. Granualarity will usually be unimportant
to our study and we will therefore leave it unspecified. When we leave granualarity unspecified, we denote data items by
lower case letters, typically x, y, and z.

A database system (DBS) is collection of hardware and software modules that support commands to access the database, called
database operations (or simply operations). The most important operations we will consider are Read and Write. Read(x)
return the value of data item x. Write(x, val) changes the value of x to val. We will use other operations from time to time.

The DBS executes each operation atomically. This means that the DBS behaves as if it executes operations sequentially, that
is, one at a time.
