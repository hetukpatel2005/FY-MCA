SQL> select c.customer_name, a.account_type, a.balance
  2  from customer as c
  3  join account a
  4  on c.customer_id = a.customer_id;
from customer as c
              *
ERROR at line 2:
ORA-00933: SQL command not properly ended 


SQL> select c.customer_name, a.account_type, a.balance
  2  from customer c
  3  join account a
  4  on c.customer_id = a.customer_id;

CUSTOMER_NAME                            ACCOUNT_TYPE       BALANCE                                                                                                                                     
---------------------------------------- --------------- ----------                                                                                                                                     
Riya Sharma                              savings              50000                                                                                                                                     
Amit Patel                               current              85000                                                                                                                                     
Neha Verma                               savings              35000                                                                                                                                     
Rahul Mehta                              current             120000                                                                                                                                     
Sneha Joshi                              savings              45000                                                                                                                                     
Arjun Singh                              savings              75000                                                                                                                                     
Priya Nair                               current              95000                                                                                                                                     
Karan Shah                               savings              28000                                                                                                                                     
Pooja Gupta                              current             150000                                                                                                                                     
Vikram Rao                               savings              62000                                                                                                                                     

10 rows selected.

SQL> select c.customer_name, a.account_id, a.account_type, a.branch_id
  2  from customer c
  3  join account a
  4  on c.customer_id = a.customer_id;

CUSTOMER_NAME                            ACCOUNT_ID ACCOUNT_TYPE     BRANCH_ID                                                                                                                          
---------------------------------------- ---------- --------------- ----------                                                                                                                          
Riya Sharma                                  200001 savings               1001                                                                                                                          
Amit Patel                                   200002 current               1002                                                                                                                          
Neha Verma                                   200003 savings               1003                                                                                                                          
Rahul Mehta                                  200004 current               1004                                                                                                                          
Sneha Joshi                                  200005 savings               1005                                                                                                                          
Arjun Singh                                  200006 savings               1006                                                                                                                          
Priya Nair                                   200007 current               1007                                                                                                                          
Karan Shah                                   200008 savings               1008                                                                                                                          
Pooja Gupta                                  200009 current               1009                                                                                                                          
Vikram Rao                                   200010 savings               1010                                                                                                                          

10 rows selected.

SQL> select c.customer_name, a.account_id, a.account_type, b.branch_name
  2  from customer c
  3  join account a
  4  on c.customer_id = a.customer_id
  5  join branch b
  6  on a.branch_id = b.branch_id;

CUSTOMER_NAME                            ACCOUNT_ID ACCOUNT_TYPE    BRANCH_NAME                                                                                                                         
---------------------------------------- ---------- --------------- ----------------------------------------                                                                                            
Riya Sharma                                  200001 savings         Andheri                                                                                                                             
Amit Patel                                   200002 current         Pune Camp                                                                                                                           
Neha Verma                                   200003 savings         Delhi Central                                                                                                                       
Rahul Mehta                                  200004 current         Ahemdabad Branch                                                                                                                    
Sneha Joshi                                  200005 savings         Nashik Branch                                                                                                                       
Arjun Singh                                  200006 savings         Bangalore Branch                                                                                                                    
Priya Nair                                   200007 current         Kochi Branch                                                                                                                        
Karan Shah                                   200008 savings         Surat Branch                                                                                                                        
Pooja Gupta                                  200009 current         Jaipur Branch                                                                                                                       
Vikram Rao                                   200010 savings         Hyderabad Branch                                                                                                                    

10 rows selected.

SQL> select c.customer_name, a.account_id, t.transaction_type, f.amount
  2  from customer c
  3  join account a
  4  on c.customer_id = a.customer_id
  5  
SQL> select c.customer_name, a.account_id, a.account_type, b.branch_name
  2  
SQL> 
SQL> select c.customer_name, a.account_id, t.transaction_type, t.amount
  2  from customer c
  3  join account a
  4  on c.customer_id = a.customer_id
  5  join bank_transaction t
  6  on a.account_id = t.account_id;

CUSTOMER_NAME                            ACCOUNT_ID TRANSACTION_TYP     AMOUNT                                                                                                                          
---------------------------------------- ---------- --------------- ----------                                                                                                                          
Riya Sharma                                  200001 deposit              10000                                                                                                                          
Amit Patel                                   200002 withdrawal            5000                                                                                                                          
Neha Verma                                   200003 deposit              15000                                                                                                                          
Rahul Mehta                                  200004 withdrawal           12000                                                                                                                          
Sneha Joshi                                  200005 deposit               8000                                                                                                                          
Arjun Singh                                  200006 withdrawal            7000                                                                                                                          
Priya Nair                                   200007 deposit              20000                                                                                                                          
Karan Shah                                   200008 withdrawal            4000                                                                                                                          
Pooja Gupta                                  200009 deposit              25000                                                                                                                          
Vikram Rao                                   200010 withdrawal            6000                                                                                                                          

10 rows selected.

SQL> select a.account_id, a.balance, t.amount
  2  from account a
  3  join bank_transaction t
  4  on a.account_id = t.account_id
  5  where a.balance > t.amount;

ACCOUNT_ID    BALANCE     AMOUNT                                                                                                                                                                        
---------- ---------- ----------                                                                                                                                                                        
    200001      50000      10000                                                                                                                                                                        
    200002      85000       5000                                                                                                                                                                        
    200003      35000      15000                                                                                                                                                                        
    200004     120000      12000                                                                                                                                                                        
    200005      45000       8000                                                                                                                                                                        
    200006      75000       7000                                                                                                                                                                        
    200007      95000      20000                                                                                                                                                                        
    200008      28000       4000                                                                                                                                                                        
    200009     150000      25000                                                                                                                                                                        
    200010      62000       6000                                                                                                                                                                        

10 rows selected.

SQL> select a.account_id, a.balance, t.amount
  2  from account a
  3  join bank_transaction t
  4  on a.balance > t.amount;

ACCOUNT_ID    BALANCE     AMOUNT                                                                                                                                                                        
---------- ---------- ----------                                                                                                                                                                        
    200009     150000      25000                                                                                                                                                                        
    200009     150000      20000                                                                                                                                                                        
    200009     150000      15000                                                                                                                                                                        
    200009     150000      12000                                                                                                                                                                        
    200009     150000      10000                                                                                                                                                                        
    200009     150000       8000                                                                                                                                                                        
    200009     150000       7000                                                                                                                                                                        
    200009     150000       6000                                                                                                                                                                        
    200009     150000       5000                                                                                                                                                                        
    200009     150000       4000                                                                                                                                                                        
    200004     120000      25000                                                                                                                                                                        
    200004     120000      20000                                                                                                                                                                        
    200004     120000      15000                                                                                                                                                                        
    200004     120000      12000                                                                                                                                                                        
    200004     120000      10000                                                                                                                                                                        
    200004     120000       8000                                                                                                                                                                        
    200004     120000       7000                                                                                                                                                                        
    200004     120000       6000                                                                                                                                                                        
    200004     120000       5000                                                                                                                                                                        
    200004     120000       4000                                                                                                                                                                        
    200007      95000      25000                                                                                                                                                                        
    200007      95000      20000                                                                                                                                                                        
    200007      95000      15000                                                                                                                                                                        
    200007      95000      12000                                                                                                                                                                        
    200007      95000      10000                                                                                                                                                                        
    200007      95000       8000                                                                                                                                                                        
    200007      95000       7000                                                                                                                                                                        
    200007      95000       6000                                                                                                                                                                        
    200007      95000       5000                                                                                                                                                                        
    200007      95000       4000                                                                                                                                                                        
    200002      85000      25000                                                                                                                                                                        
    200002      85000      20000                                                                                                                                                                        
    200002      85000      15000                                                                                                                                                                        
    200002      85000      12000                                                                                                                                                                        
    200002      85000      10000                                                                                                                                                                        
    200002      85000       8000                                                                                                                                                                        
    200002      85000       7000                                                                                                                                                                        
    200002      85000       6000                                                                                                                                                                        
    200002      85000       5000                                                                                                                                                                        
    200002      85000       4000                                                                                                                                                                        
    200006      75000      25000                                                                                                                                                                        
    200006      75000      20000                                                                                                                                                                        
    200006      75000      15000                                                                                                                                                                        
    200006      75000      12000                                                                                                                                                                        
    200006      75000      10000                                                                                                                                                                        
    200006      75000       8000                                                                                                                                                                        
    200006      75000       7000                                                                                                                                                                        

ACCOUNT_ID    BALANCE     AMOUNT                                                                                                                                                                        
---------- ---------- ----------                                                                                                                                                                        
    200006      75000       6000                                                                                                                                                                        
    200006      75000       5000                                                                                                                                                                        
    200006      75000       4000                                                                                                                                                                        
    200010      62000      25000                                                                                                                                                                        
    200010      62000      20000                                                                                                                                                                        
    200010      62000      15000                                                                                                                                                                        
    200010      62000      12000                                                                                                                                                                        
    200010      62000      10000                                                                                                                                                                        
    200010      62000       8000                                                                                                                                                                        
    200010      62000       7000                                                                                                                                                                        
    200010      62000       6000                                                                                                                                                                        
    200010      62000       5000                                                                                                                                                                        
    200010      62000       4000                                                                                                                                                                        
    200001      50000      25000                                                                                                                                                                        
    200001      50000      20000                                                                                                                                                                        
    200001      50000      15000                                                                                                                                                                        
    200001      50000      12000                                                                                                                                                                        
    200001      50000      10000                                                                                                                                                                        
    200001      50000       8000                                                                                                                                                                        
    200001      50000       7000                                                                                                                                                                        
    200001      50000       6000                                                                                                                                                                        
    200001      50000       5000                                                                                                                                                                        
    200001      50000       4000                                                                                                                                                                        
    200005      45000      25000                                                                                                                                                                        
    200005      45000      20000                                                                                                                                                                        
    200005      45000      15000                                                                                                                                                                        
    200005      45000      12000                                                                                                                                                                        
    200005      45000      10000                                                                                                                                                                        
    200005      45000       8000                                                                                                                                                                        
    200005      45000       7000                                                                                                                                                                        
    200005      45000       6000                                                                                                                                                                        
    200005      45000       5000                                                                                                                                                                        
    200005      45000       4000                                                                                                                                                                        
    200003      35000      25000                                                                                                                                                                        
    200003      35000      20000                                                                                                                                                                        
    200003      35000      15000                                                                                                                                                                        
    200003      35000      12000                                                                                                                                                                        
    200003      35000      10000                                                                                                                                                                        
    200003      35000       8000                                                                                                                                                                        
    200003      35000       7000                                                                                                                                                                        
    200003      35000       6000                                                                                                                                                                        
    200003      35000       5000                                                                                                                                                                        
    200003      35000       4000                                                                                                                                                                        
    200008      28000      25000                                                                                                                                                                        
    200008      28000      20000                                                                                                                                                                        
    200008      28000      15000                                                                                                                                                                        
    200008      28000      12000                                                                                                                                                                        

ACCOUNT_ID    BALANCE     AMOUNT                                                                                                                                                                        
---------- ---------- ----------                                                                                                                                                                        
    200008      28000      10000                                                                                                                                                                        
    200008      28000       8000                                                                                                                                                                        
    200008      28000       7000                                                                                                                                                                        
    200008      28000       6000                                                                                                                                                                        
    200008      28000       5000                                                                                                                                                                        
    200008      28000       4000                                                                                                                                                                        

100 rows selected.

SQL> select a.account_id, a.open_date, t.transaction_id, t.transaction_date
  2  from account a
  3  join bank_transaction t
  4  on t.transaction_date > a.open_date;

ACCOUNT_ID OPEN_DATE TRANSACTION_ID TRANSACTI                                                                                                                                                           
---------- --------- -------------- ---------                                                                                                                                                           
    200001 10-JAN-25        3000001 01-JAN-26                                                                                                                                                           
    200001 10-JAN-25        3000002 03-JAN-26                                                                                                                                                           
    200001 10-JAN-25        3000003 05-JAN-26                                                                                                                                                           
    200001 10-JAN-25        3000004 07-JAN-26                                                                                                                                                           
    200001 10-JAN-25        3000005 10-JAN-26                                                                                                                                                           
    200001 10-JAN-25        3000006 12-JAN-26                                                                                                                                                           
    200001 10-JAN-25        3000007 15-JAN-26                                                                                                                                                           
    200001 10-JAN-25        3000008 18-JAN-26                                                                                                                                                           
    200001 10-JAN-25        3000009 20-JAN-26                                                                                                                                                           
    200001 10-JAN-25        3000010 22-JAN-26                                                                                                                                                           
    200002 15-FEB-25        3000001 01-JAN-26                                                                                                                                                           
    200002 15-FEB-25        3000002 03-JAN-26                                                                                                                                                           
    200002 15-FEB-25        3000003 05-JAN-26                                                                                                                                                           
    200002 15-FEB-25        3000004 07-JAN-26                                                                                                                                                           
    200002 15-FEB-25        3000005 10-JAN-26                                                                                                                                                           
    200002 15-FEB-25        3000006 12-JAN-26                                                                                                                                                           
    200002 15-FEB-25        3000007 15-JAN-26                                                                                                                                                           
    200002 15-FEB-25        3000008 18-JAN-26                                                                                                                                                           
    200002 15-FEB-25        3000009 20-JAN-26                                                                                                                                                           
    200002 15-FEB-25        3000010 22-JAN-26                                                                                                                                                           
    200003 20-MAR-25        3000001 01-JAN-26                                                                                                                                                           
    200003 20-MAR-25        3000002 03-JAN-26                                                                                                                                                           
    200003 20-MAR-25        3000003 05-JAN-26                                                                                                                                                           
    200003 20-MAR-25        3000004 07-JAN-26                                                                                                                                                           
    200003 20-MAR-25        3000005 10-JAN-26                                                                                                                                                           
    200003 20-MAR-25        3000006 12-JAN-26                                                                                                                                                           
    200003 20-MAR-25        3000007 15-JAN-26                                                                                                                                                           
    200003 20-MAR-25        3000008 18-JAN-26                                                                                                                                                           
    200003 20-MAR-25        3000009 20-JAN-26                                                                                                                                                           
    200003 20-MAR-25        3000010 22-JAN-26                                                                                                                                                           
    200004 05-APR-25        3000001 01-JAN-26                                                                                                                                                           
    200004 05-APR-25        3000002 03-JAN-26                                                                                                                                                           
    200004 05-APR-25        3000003 05-JAN-26                                                                                                                                                           
    200004 05-APR-25        3000004 07-JAN-26                                                                                                                                                           
    200004 05-APR-25        3000005 10-JAN-26                                                                                                                                                           
    200004 05-APR-25        3000006 12-JAN-26                                                                                                                                                           
    200004 05-APR-25        3000007 15-JAN-26                                                                                                                                                           
    200004 05-APR-25        3000008 18-JAN-26                                                                                                                                                           
    200004 05-APR-25        3000009 20-JAN-26                                                                                                                                                           
    200004 05-APR-25        3000010 22-JAN-26                                                                                                                                                           
    200005 12-MAY-25        3000001 01-JAN-26                                                                                                                                                           
    200005 12-MAY-25        3000002 03-JAN-26                                                                                                                                                           
    200005 12-MAY-25        3000003 05-JAN-26                                                                                                                                                           
    200005 12-MAY-25        3000004 07-JAN-26                                                                                                                                                           
    200005 12-MAY-25        3000005 10-JAN-26                                                                                                                                                           
    200005 12-MAY-25        3000006 12-JAN-26                                                                                                                                                           
    200005 12-MAY-25        3000007 15-JAN-26                                                                                                                                                           

ACCOUNT_ID OPEN_DATE TRANSACTION_ID TRANSACTI                                                                                                                                                           
---------- --------- -------------- ---------                                                                                                                                                           
    200005 12-MAY-25        3000008 18-JAN-26                                                                                                                                                           
    200005 12-MAY-25        3000009 20-JAN-26                                                                                                                                                           
    200005 12-MAY-25        3000010 22-JAN-26                                                                                                                                                           
    200006 18-JUN-25        3000001 01-JAN-26                                                                                                                                                           
    200006 18-JUN-25        3000002 03-JAN-26                                                                                                                                                           
    200006 18-JUN-25        3000003 05-JAN-26                                                                                                                                                           
    200006 18-JUN-25        3000004 07-JAN-26                                                                                                                                                           
    200006 18-JUN-25        3000005 10-JAN-26                                                                                                                                                           
    200006 18-JUN-25        3000006 12-JAN-26                                                                                                                                                           
    200006 18-JUN-25        3000007 15-JAN-26                                                                                                                                                           
    200006 18-JUN-25        3000008 18-JAN-26                                                                                                                                                           
    200006 18-JUN-25        3000009 20-JAN-26                                                                                                                                                           
    200006 18-JUN-25        3000010 22-JAN-26                                                                                                                                                           
    200007 25-JUL-25        3000001 01-JAN-26                                                                                                                                                           
    200007 25-JUL-25        3000002 03-JAN-26                                                                                                                                                           
    200007 25-JUL-25        3000003 05-JAN-26                                                                                                                                                           
    200007 25-JUL-25        3000004 07-JAN-26                                                                                                                                                           
    200007 25-JUL-25        3000005 10-JAN-26                                                                                                                                                           
    200007 25-JUL-25        3000006 12-JAN-26                                                                                                                                                           
    200007 25-JUL-25        3000007 15-JAN-26                                                                                                                                                           
    200007 25-JUL-25        3000008 18-JAN-26                                                                                                                                                           
    200007 25-JUL-25        3000009 20-JAN-26                                                                                                                                                           
    200007 25-JUL-25        3000010 22-JAN-26                                                                                                                                                           
    200008 10-AUG-25        3000001 01-JAN-26                                                                                                                                                           
    200008 10-AUG-25        3000002 03-JAN-26                                                                                                                                                           
    200008 10-AUG-25        3000003 05-JAN-26                                                                                                                                                           
    200008 10-AUG-25        3000004 07-JAN-26                                                                                                                                                           
    200008 10-AUG-25        3000005 10-JAN-26                                                                                                                                                           
    200008 10-AUG-25        3000006 12-JAN-26                                                                                                                                                           
    200008 10-AUG-25        3000007 15-JAN-26                                                                                                                                                           
    200008 10-AUG-25        3000008 18-JAN-26                                                                                                                                                           
    200008 10-AUG-25        3000009 20-JAN-26                                                                                                                                                           
    200008 10-AUG-25        3000010 22-JAN-26                                                                                                                                                           
    200009 15-SEP-25        3000001 01-JAN-26                                                                                                                                                           
    200009 15-SEP-25        3000002 03-JAN-26                                                                                                                                                           
    200009 15-SEP-25        3000003 05-JAN-26                                                                                                                                                           
    200009 15-SEP-25        3000004 07-JAN-26                                                                                                                                                           
    200009 15-SEP-25        3000005 10-JAN-26                                                                                                                                                           
    200009 15-SEP-25        3000006 12-JAN-26                                                                                                                                                           
    200009 15-SEP-25        3000007 15-JAN-26                                                                                                                                                           
    200009 15-SEP-25        3000008 18-JAN-26                                                                                                                                                           
    200009 15-SEP-25        3000009 20-JAN-26                                                                                                                                                           
    200009 15-SEP-25        3000010 22-JAN-26                                                                                                                                                           
    200010 20-OCT-25        3000001 01-JAN-26                                                                                                                                                           
    200010 20-OCT-25        3000002 03-JAN-26                                                                                                                                                           
    200010 20-OCT-25        3000003 05-JAN-26                                                                                                                                                           
    200010 20-OCT-25        3000004 07-JAN-26                                                                                                                                                           

ACCOUNT_ID OPEN_DATE TRANSACTION_ID TRANSACTI                                                                                                                                                           
---------- --------- -------------- ---------                                                                                                                                                           
    200010 20-OCT-25        3000005 10-JAN-26                                                                                                                                                           
    200010 20-OCT-25        3000006 12-JAN-26                                                                                                                                                           
    200010 20-OCT-25        3000007 15-JAN-26                                                                                                                                                           
    200010 20-OCT-25        3000008 18-JAN-26                                                                                                                                                           
    200010 20-OCT-25        3000009 20-JAN-26                                                                                                                                                           
    200010 20-OCT-25        3000010 22-JAN-26                                                                                                                                                           

100 rows selected.

SQL> commit;

Commit complete.

SQL> spool off;
