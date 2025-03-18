Transactions
========================

.. toctree::
   :maxdepth: 3

   acid
   transaction-states
   transaction_isolation/transaction_isolation
   .. parallel-transactions
   .. distributed-transactions


**Transactions** is a fundamental concept within databases to perform some operations on multiple databases and tables as one unit of work! 

Transactions are very widely used in relational databases (SQL) to adhere and guarantee ACID properties (mostly importantly atomicity).

Mostly all databases that allow users to write transactions use the keywords **begin transaction** and **end transaction**. The operations within this start and end are executed as part of transaction demonstrating one unit of indivisible work.