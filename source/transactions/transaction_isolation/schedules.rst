.. Schedules
.. ========================


.. Schedule represents the chronological order of operations or instructions. This execution sequence captures the order of instructions within and between transactions.

.. Consider these transactions executing independently,

.. .. code-block:: text
   
..    T₁₂₁:
..        read(Annas_account)
..        Annas_account := Annas_account - 50
..        write(Annas_account)
..        read(Bens_account)
..        Bens_account := Bens_account + 50
..        write(Bens_account)
..        commit

..    T₂₂₁:
..        read(Annas_account)
..        temp := Annas_account * 0.15
..        Annas_account := Annas_account - temp
..        write(Annas_account)
..        read(Bens_account)
..        Bens_account := Bens_account + temp
..        write(Bens_account)
..        commit

.. By the principles of isolation, either T₁, is followed by T₂ or vice versa. This ordering is nothing but called as schedule, where schedule₁ has T₁ execute before T₂ and schedule₂ executing T₂ followed by T₁. 

Schedules
========================

A **schedule** represents the chronological order of operations or instructions. This execution sequence captures the order of instructions **within** and **between** transactions.

Consider the following transactions executing independently:

.. list-table::
   :header-rows: 1
   :widths: 50 50

   * - **T₁₂₁**
     - **T₂₂₁**
   * - .. code-block:: text

          read(Annas_account)
          Annas_account := Annas_account - 50
          write(Annas_account)
          read(Bens_account)
          Bens_account := Bens_account + 50
          write(Bens_account)
          commit

     - .. code-block:: text

          read(Annas_account)
          temp := Annas_account * 0.15
          Annas_account := Annas_account - temp
          write(Annas_account)
          read(Bens_account)
          Bens_account := Bens_account + temp
          write(Bens_account)
          commit




Order of Execution
~~~~~~~~~~~~
By the principles of **isolation**, either **T₁₂₁** is followed by **T₂₂₁** or vice versa. This ordering is called a **schedule**:

- **Schedule₁** – T₁₂₁ executes before T₂₂₁.  
- **Schedule₂** – T₂₂₁ executes before T₁₂₁.  


A well-defined schedule ensures transactional consistency and prevents conflicts between concurrent transactions.
