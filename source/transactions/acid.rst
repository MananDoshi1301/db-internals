.. ACID
.. =====================


.. **ACID** forms one of the most foundational properties, when dealing with large-scale data infrastructures and millions of requests to maintain transactional consistency.

.. ACID properties are as follows:

.. 1. Atomicity: The transaction (or any operation) either completes or rollbacks to the initial state is nothing but atomicity. Atomicity make sure no torn writes happen for torn reads to happen within the system.

.. Eg: For a bank transfer from Anna's account to Ben's account, if money is withdrawn from Anna's account, then it should be deposited to Ben's account. There shouldn't be a possibility where withdrawing or depositing money executes with the other operation failing or not executing due to any reason.

.. 2. Consistency: For a certain transaction, operations are processed such that no other operation or transaction happen on the same data to leave the state of data inconsistent. Therefore, the state of a consistent database after a transaction or transactional operation must render it consistent.

.. Eg: If Anna's bank account consists of 50$ and two transactions(withdrawing 50$ and 20$) execute at the same time, then only one operation, should go through (assuming bank balance cannot be negative) where the deduction is either 50$ or 20$ and not both leaving the database inconsistent.

.. 3. Isolation: Here transactions should be unaware of other transactions executing such that no two transactions interfere between their intermediate state.

.. Eg: If Transactions T1 and T2 are trying to execute concurrently, then system should pair both transactions such that T1 happens-before T2 executes, or T2 executes before T1 making it look sequential.

.. 4. Durability: In case of a failure, power-outage, catastrophic event, natural disaster, the system should never lose data after a transaction commits. It should persist data once the transaction commits.


ACID
=====================

**ACID** forms one of the most foundational properties when dealing with large-scale data infrastructures and millions of requests to maintain transactional consistency.

ACID stands for **Atomicity**, **Consistency**, **Isolation**, and **Durability** — key principles that ensure the reliability of database transactions.

---

Atomicity  
----------------
A transaction (or any operation) either **completes fully** or **rolls back** to the initial state — there is no partial execution. Atomicity ensures that no partial writes or torn reads occur within the system.

**Example:**  
For a bank transfer from Anna's account to Ben's account, if money is withdrawn from Anna's account, it must also be deposited into Ben's account. If either operation fails, the entire transaction should be rolled back to prevent inconsistencies.

---

Consistency  
----------------
A transaction should take the database from one **valid state** to another, ensuring that no other transaction can leave the database in an inconsistent state. After a transaction, the database should always satisfy its integrity constraints.

**Example:**  
If Anna's bank account has $50 and two transactions (withdrawing $50 and $20) are initiated simultaneously, the system should allow only one transaction to succeed (assuming the balance cannot go negative), ensuring a consistent state.

---

Isolation  
----------------
Each transaction should be **executed independently** without interference from other transactions. The final outcome should appear as if transactions were executed sequentially, even if they run concurrently.

**Example:**  
If two transactions, T1 and T2, are executed concurrently, the system should ensure that either T1 appears to happen before T2 or T2 before T1 — making it look like a sequential execution.

---

Durability  
----------------
Once a transaction is **committed**, its changes should persist even in the event of a system failure (e.g., power outage, hardware crash, or natural disaster).

**Example:**  
If a bank transfer is confirmed, the system should retain the record even if the server crashes immediately after.

---

This ensures that transactions in a database are reliable and consistent even under high load or failure scenarios.  
