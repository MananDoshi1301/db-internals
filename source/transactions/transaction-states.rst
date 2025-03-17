.. Transaction States
.. ====================

.. Transactions as explained earlier, can be considered as one indivisible unit of work, which makes the operations within prone to failures. In fact if the system is more optimistic in terms of failure handling in concurrent transactions, there are high chances of failures (which is way more common than it sounds).

.. However, several steps need to be taken to ``rollback`` operations that have been executed taking the database to earlier consistent state. Before operating on these operations to recover to older consistency, the transaction needs to identify its current state. Therefore, these are the five possible states in which a database can exist into irrespective of the transactional success or failure:

.. Active 
.. ----------------
.. Transaction is in a state where it is executing. (Initial State)

.. Partially committed
.. ----------------
.. This is a state in which the last operation of the transaction has executed and completed

.. Failed
.. ----------------
.. Here the normal operation execution has failed and cannot move any further

.. Aborted
.. ----------------
.. Here the transaction fails and rollbacks to the older (prior) safe or consistent state before beginning the transaction.

.. Committed
.. ----------------
.. Successful execution and completion of transaction


Transaction States
====================

Transactions, as explained earlier, are considered as one indivisible unit of work, which makes the operations within them prone to failures. In fact, if the system is more optimistic in terms of failure handling in concurrent transactions, the chances of failure increase significantly (which is more common than it sounds).

To handle failures gracefully, the system needs to take several steps to **rollback** operations that have already been executed, restoring the database to a previous consistent state. Before initiating recovery, the transaction needs to identify its current state.

The five possible states of a transaction, irrespective of success or failure, are:

.. image:: /_static/transaction-states.png
   :alt: Transaction States Diagram
   :width: 400px
   :align: center

**1. Active**  
- The transaction is in an executing state.  
- This is the **initial state** of the transaction.  

.. ---

**2. Partially Committed**  
- The last operation of the transaction has executed and completed.  
- The system has not yet made the changes permanent.  

.. ---

**3. Failed**  
- The transaction has encountered an error during execution.  
- The system cannot proceed further with this transaction.  

.. ---

**4. Aborted**  
- The transaction has failed and is rolling back to the previous **consistent state**.  
- The database state is restored to the state before the transaction began.  

.. ---

**5. Committed**  
- The transaction has successfully executed all operations.  
- Changes have been made permanent in the database.  

.. ---

A transaction progresses through these states during its lifecycle, depending on the success or failure of operations. Handling these states correctly ensures the system maintains **data consistency** and **integrity**.  

.. ---

