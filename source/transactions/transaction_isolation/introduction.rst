Introduction
========================

**Isolation** refers to the property of a database that ensures transactional independence, such that two concurrently running transactions appear independent, preventing data inconsistencies.

**Semantics**:  
If transaction T₁ and T₂ are executing concurrently, the system should behave as if either T₁ executes before T₂ or T₂ executes before T₁ — but never interleave their operations in a way that causes inconsistency.


Simplified Transactions Example
-------------------------------

Below is a simplified pseudo-transaction example that demonstrates sequential operations within transactions. This example is free from specific syntax, or programming language barriers.

Some of the most important transaction primitives are:

- **read** – To read data from the database.  
- **write** – To update data in the database.  
- **lock** – To lock a resource for exclusive access.  
- **unlock** – To release the locked resource.  

Example:
~~~~~~~~

Consider two transactions:

1. **T₁** – Transfers $50 from Anna's account (`Annas_account`) to Ben's account (`Bens_account`).  
2. **T₂** – Transfers 15% of Anna's balance to Ben's account.  

.. code-block:: text
   
   T₁:
       read(Annas_account)
       Annas_account := Annas_account - 50
       write(Annas_account)
       read(Bens_account)
       Bens_account := Bens_account + 50
       write(Bens_account)

   T₂:
       read(Annas_account)
       temp := Annas_account * 0.15
       Annas_account := Annas_account - temp
       write(Annas_account)
       read(Bens_account)
       Bens_account := Bens_account + temp
       write(Bens_account)

This is one of the examples where we read and write data in our system