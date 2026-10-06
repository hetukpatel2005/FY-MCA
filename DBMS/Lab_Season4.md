SQL> create table customer(
  2  customer_id number(5) primary key,
  3  customer_name varchar2(40) not null,
  4  city varchar2(30),
  5  phone varchar2(10) unique,
  6  email varchar2(50) unique);

Table created.
SQL> desc customer;
 Name                                                                                                              Null?    Type
 ----------------------------------------------------------------------------------------------------------------- -------- ----------------------------------------------------------------------------
 CUSTOMER_ID                                                                                                       NOT NULL NUMBER(5)
 CUSTOMER_NAME                                                                                                     NOT NULL VARCHAR2(40)
 CITY                                                                                                                       VARCHAR2(30)
 PHONE                                                                                                                      VARCHAR2(10)
 EMAIL                                                                                                                      VARCHAR2(50)

SQL> set pagesize 50
SQL> set linesize 200

SQL> create table account(
  2  account_id number(6) primary key,
  3  customer_id number(5) references customer(customer_id),
  4  \
  5  
SQL> create table branch(
  2  branch_id number(4) primary_key,
  3  branch_id number(4) primary_key,
  4  
SQL> create table branch(
  2  branch_id number(4) primary key,
  3  branch_name varchar2(40) not null,
  4  city varchar2(30),
  5  manager_id number(5));

Table created.

SQL> desc branch;
 Name                                                                                                              Null?    Type
 ----------------------------------------------------------------------------------------------------------------- -------- ----------------------------------------------------------------------------
 BRANCH_ID                                                                                                         NOT NULL NUMBER(4)
 BRANCH_NAME                                                                                                       NOT NULL VARCHAR2(40)
 CITY                                                                                                                       VARCHAR2(30)
 MANAGER_ID                                                                                                                 NUMBER(5)

SQL> create table account(
  2  account_id number(6) primary key,
  3  customer_id number(5) references customer(customer_id),
  4  branch_id number(4) references branch(branch_id),
  5  account_type varchar2(15) check(savings, current),
  6  balance number(12,2) check(balance >= 0),
  7  open_date date not null,
  8  status varchar2(15) check(active, closed));
account_type varchar2(15) check(savings, current),
                                       *
ERROR at line 5:
ORA-00920: invalid relational operator 


SQL> create table account(
  2  account_id number(6) primary key,
  3  customer_id number(5) references customer(customer_id),
  4  branch_id number(4) references branch(branch_id),
  5  account_type varchar2(15) check(status IN('savings', 'current')),
  6  balance number(12,2) check(balance >= 0),
  7  open_date date not null,
  8  status varchar2(15) check(status IN('active', 'closed')));
account_type varchar2(15) check(status IN('savings', 'current')),
                                                                *
ERROR at line 5:
ORA-02438: Column check constraint cannot reference other columns 


SQL> create table account(
  2  account_id number(6) primary key,
  3  customer_id number(5) references customer(customer_id),
  4  branch_id number(4) references branch(branch_id),
  5  account_type varchar2(15) check(account_type IN('savings', 'current')),
  6  balance number(12,2) check(balance >= 0),
  7  open_date date not null,
  8  status varchar2(15) check(status IN('active', 'closed')));

Table created.

SQL> desc account;
 Name                                                                                                              Null?    Type
 ----------------------------------------------------------------------------------------------------------------- -------- ----------------------------------------------------------------------------
 ACCOUNT_ID                                                                                                        NOT NULL NUMBER(6)
 CUSTOMER_ID                                                                                                                NUMBER(5)
 BRANCH_ID                                                                                                                  NUMBER(4)
 ACCOUNT_TYPE                                                                                                               VARCHAR2(15)
 BALANCE                                                                                                                    NUMBER(12,2)
 OPEN_DATE                                                                                                         NOT NULL DATE
 STATUS                                                                                                                     VARCHAR2(15)

SQL> create table bank_transaction(
  2  transaction_id number(7) primary key,
  3  account_id number(6) references account(account_id),
  4  transaction_type varchar2(15) check(transaction_type IN ('deposit','withdrawal')),
  5  amount number(10,2) references check(amount > 0),
  6  transaction_date date not null);
amount number(10,2) references check(amount > 0),
                               *
ERROR at line 5:
ORA-00903: invalid table name 


SQL> create table bank_transaction(
  2  transaction_id number(7) primary key,
  3  account_id number(6) references account(account_id),
  4  transaction_type varchar2(15) check(transaction_type IN ('deposit','withdrawal')),
  5  amount number(10,2) check(amount > 0),
  6  amount number(10,2) references check(amount > 0),
  7  transaction_date date not null);
amount number(10,2) references check(amount > 0),
*
ERROR at line 6:
ORA-00957: duplicate column name 


SQL> create table bank_transaction(
  2  transaction_id number(7) primary key,
  3  account_id number(6) references account(account_id),
  4  transaction_type varchar2(15) check(transaction_type IN ('deposit','withdrawal')),
  5  amount number(10,2) check(amount > 0),
  6  transaction_date date not null);

Table created.

SQL> desc transaction;
ERROR:
ORA-04043: object transaction does not exist 

SQL> desc bank_transaction;
 Name                                                                                                              Null?    Type
 ----------------------------------------------------------------------------------------------------------------- -------- ----------------------------------------------------------------------------
 TRANSACTION_ID                                                                                                    NOT NULL NUMBER(7)
 ACCOUNT_ID                                                                                                                 NUMBER(6)
 TRANSACTION_TYPE                                                                                                           VARCHAR2(15)
 AMOUNT                                                                                                                     NUMBER(10,2)
 TRANSACTION_DATE                                                                                                  NOT NULL DATE

SQL> commit;

Commit complete.

SQL> clear screen

SQL> insert into customer(
  2  
SQL> insert into customer values('&customer_id','&customer_name','&city');
Enter value for customer_id: 101
Enter value for customer_name: Riya Sharma
Enter value for city: Mumbai
old   1: insert into customer values('&customer_id','&customer_name','&city')
new   1: insert into customer values('101','Riya Sharma','Mumbai')
insert into customer values('101','Riya Sharma','Mumbai')
            *
ERROR at line 1:
ORA-00947: not enough values 


SQL> desc customer;
 Name                                                                                                              Null?    Type
 ----------------------------------------------------------------------------------------------------------------- -------- ----------------------------------------------------------------------------
 CUSTOMER_ID                                                                                                       NOT NULL NUMBER(5)
 CUSTOMER_NAME                                                                                                     NOT NULL VARCHAR2(40)
 CITY                                                                                                                       VARCHAR2(30)
 PHONE                                                                                                                      VARCHAR2(10)
 EMAIL                                                                                                                      VARCHAR2(50)

SQL> desc bank_transaction;
 Name                                                                                                              Null?    Type
 ----------------------------------------------------------------------------------------------------------------- -------- ----------------------------------------------------------------------------
 TRANSACTION_ID                                                                                                    NOT NULL NUMBER(7)
 ACCOUNT_ID                                                                                                                 NUMBER(6)
 TRANSACTION_TYPE                                                                                                           VARCHAR2(15)
 AMOUNT                                                                                                                     NUMBER(10,2)
 TRANSACTION_DATE                                                                                                  NOT NULL DATE

SQL> desc branch;
 Name                                                                                                              Null?    Type
 ----------------------------------------------------------------------------------------------------------------- -------- ----------------------------------------------------------------------------
 BRANCH_ID                                                                                                         NOT NULL NUMBER(4)
 BRANCH_NAME                                                                                                       NOT NULL VARCHAR2(40)
 CITY                                                                                                                       VARCHAR2(30)
 MANAGER_ID                                                                                                                 NUMBER(5)

SQL> clear screen

SQL> insert into customer values('&customer_id','&customer_name','&city','&phone','&email');
Enter value for customer_id: 101
Enter value for customer_name: Riya Sharma
Enter value for city: Mumbai
Enter value for phone: 9876543210
Enter value for email: riya@gmail.com
old   1: insert into customer values('&customer_id','&customer_name','&city','&phone','&email')
new   1: insert into customer values('101','Riya Sharma','Mumbai','9876543210','riya@gmail.com')

1 row created.

SQL> \
SP2-0042: unknown command "\" - rest of line ignored.
SQL> /
Enter value for customer_id: 102
Enter value for customer_name: Amit Patel
Enter value for city: Pune
Enter value for phone: 9876543211
Enter value for email: amit@gmail.com
old   1: insert into customer values('&customer_id','&customer_name','&city','&phone','&email')
new   1: insert into customer values('102','Amit Patel','Pune','9876543211','amit@gmail.com')

1 row created.

SQL> /
Enter value for customer_id: 103
Enter value for customer_name: Neha Verma
Enter value for city: Delhi
Enter value for phone: 9876543212
Enter value for email: neha@gmail.com
old   1: insert into customer values('&customer_id','&customer_name','&city','&phone','&email')
new   1: insert into customer values('103','Neha Verma','Delhi','9876543212','neha@gmail.com')

1 row created.

SQL> /
Enter value for customer_id: 104
Enter value for customer_name: Rahul Mehta
Enter value for city: Ahemdabad
Enter value for phone: 9876543213
Enter value for email: neha@gmail.com
old   1: insert into customer values('&customer_id','&customer_name','&city','&phone','&email')
new   1: insert into customer values('104','Rahul Mehta','Ahemdabad','9876543213','neha@gmail.com')
insert into customer values('104','Rahul Mehta','Ahemdabad','9876543213','neha@gmail.com')
*
ERROR at line 1:
ORA-00001: unique constraint (C##MBA53.SYS_C0058942) violated 


SQL> select * from customer;

CUSTOMER_ID CUSTOMER_NAME                            CITY                           PHONE      EMAIL                                                                                                    
----------- ---------------------------------------- ------------------------------ ---------- --------------------------------------------------                                                       
        101 Riya Sharma                              Mumbai                         9876543210 riya@gmail.com                                                                                           
        102 Amit Patel                               Pune                           9876543211 amit@gmail.com                                                                                           
        103 Neha Verma                               Delhi                          9876543212 neha@gmail.com                                                                                           

SQL> /

CUSTOMER_ID CUSTOMER_NAME                            CITY                           PHONE      EMAIL                                                                                                    
----------- ---------------------------------------- ------------------------------ ---------- --------------------------------------------------                                                       
        101 Riya Sharma                              Mumbai                         9876543210 riya@gmail.com                                                                                           
        102 Amit Patel                               Pune                           9876543211 amit@gmail.com                                                                                           
        103 Neha Verma                               Delhi                          9876543212 neha@gmail.com                                                                                           

SQL> insert into customer values('&customer_id','&customer_name','&city','&phone','&email');
Enter value for customer_id: 104
Enter value for customer_name: Rahul Mehta
Enter value for city: Ahemdabad
Enter value for phone: 9876543213
Enter value for email: rahul@gmail.com
old   1: insert into customer values('&customer_id','&customer_name','&city','&phone','&email')
new   1: insert into customer values('104','Rahul Mehta','Ahemdabad','9876543213','rahul@gmail.com')

1 row created.

SQL> /
Enter value for customer_id: 105
Enter value for customer_name: Sneha Joshi
Enter value for city: Nashik
Enter value for phone: 9876543214
Enter value for email: sneha@gmail.com
old   1: insert into customer values('&customer_id','&customer_name','&city','&phone','&email')
new   1: insert into customer values('105','Sneha Joshi','Nashik','9876543214','sneha@gmail.com')

1 row created.

SQL> /
Enter value for customer_id: 105
Enter value for customer_name: Arjun Singh
Enter value for city: Bangalore
Enter value for phone: 9876543215
Enter value for email: arjun@gmail.com
old   1: insert into customer values('&customer_id','&customer_name','&city','&phone','&email')
new   1: insert into customer values('105','Arjun Singh','Bangalore','9876543215','arjun@gmail.com')
insert into customer values('105','Arjun Singh','Bangalore','9876543215','arjun@gmail.com')
*
ERROR at line 1:
ORA-00001: unique constraint (C##MBA53.SYS_C0058940) violated 


SQL> INSERT INTO customer (customer_id, customer_name, city, phone, email)
  2  VALUES (106, 'Arjun Singh', 'Bangalore', '9876543215', 'arjun@gmail.com');

1 row created.

SQL> INSERT INTO customer (customer_id, customer_name, city, phone, email)
  2  VALUES (107, 'Priya Nair', 'Kochi', '9876543216', 'priya@gmail.com');

1 row created.

SQL> INSERT INTO customer (customer_id, customer_name, city, phone, email)
  2  VALUES (108, 'Karan Shah', 'Surat', '9876543217', 'karan@gmail.com');

1 row created.

SQL> INSERT INTO customer (customer_id, customer_name, city, phone, email)
  2  VALUES (109, 'Pooja Gupta', 'Jaipur', '9876543218', 'pooja@gmail.com');

1 row created.

SQL> INSERT INTO customer (customer_id, customer_name, city, phone, email)
  2  VALUES (110, 'Vikram Rao', 'Hyderabad', '9876543219', 'vikram@gmail.com');

1 row created.

SQL> select * from customer;

CUSTOMER_ID CUSTOMER_NAME                            CITY                           PHONE      EMAIL                                                                                                    
----------- ---------------------------------------- ------------------------------ ---------- --------------------------------------------------                                                       
        101 Riya Sharma                              Mumbai                         9876543210 riya@gmail.com                                                                                           
        102 Amit Patel                               Pune                           9876543211 amit@gmail.com                                                                                           
        103 Neha Verma                               Delhi                          9876543212 neha@gmail.com                                                                                           
        104 Rahul Mehta                              Ahemdabad                      9876543213 rahul@gmail.com                                                                                          
        105 Sneha Joshi                              Nashik                         9876543214 sneha@gmail.com                                                                                          
        106 Arjun Singh                              Bangalore                      9876543215 arjun@gmail.com                                                                                          
        107 Priya Nair                               Kochi                          9876543216 priya@gmail.com                                                                                          
        108 Karan Shah                               Surat                          9876543217 karan@gmail.com                                                                                          
        109 Pooja Gupta                              Jaipur                         9876543218 pooja@gmail.com                                                                                          
        110 Vikram Rao                               Hyderabad                      9876543219 vikram@gmail.com                                                                                         

10 rows selected.

SQL> clear screen;

SQL> insert into branch values('&branch_id','&branch_name','&city','&manager_id');
Enter value for branch_id: 1001
Enter value for branch_name: Andheri
Enter value for city: Mumbai
Enter value for manager_id: 501
old   1: insert into branch values('&branch_id','&branch_name','&city','&manager_id')
new   1: insert into branch values('1001','Andheri','Mumbai','501')

1 row created.

SQL> /
Enter value for branch_id: 1002
Enter value for branch_name: Pune Camp
Enter value for city: Pune
Enter value for manager_id: 502
old   1: insert into branch values('&branch_id','&branch_name','&city','&manager_id')
new   1: insert into branch values('1002','Pune Camp','Pune','502')

1 row created.

SQL> /
Enter value for branch_id: 1003
Enter value for branch_name: Delhi Central
Enter value for city: Delhi
Enter value for manager_id: 503
old   1: insert into branch values('&branch_id','&branch_name','&city','&manager_id')
new   1: insert into branch values('1003','Delhi Central','Delhi','503')

1 row created.

SQL> /
Enter value for branch_id: 1004
Enter value for branch_name: Ahemdabad Branch
Enter value for city: Ahemdabad
Enter value for manager_id: 504
old   1: insert into branch values('&branch_id','&branch_name','&city','&manager_id')
new   1: insert into branch values('1004','Ahemdabad Branch','Ahemdabad','504')

1 row created.

SQL> /
Enter value for branch_id: 1005
Enter value for branch_name: Nashik Branch
Enter value for city: Nashik
Enter value for manager_id: 505
old   1: insert into branch values('&branch_id','&branch_name','&city','&manager_id')
new   1: insert into branch values('1005','Nashik Branch','Nashik','505')

1 row created.

SQL> /
Enter value for branch_id: 1006
Enter value for branch_name: Bangalore Branch
Enter value for city: Bangalore
Enter value for manager_id: 506
old   1: insert into branch values('&branch_id','&branch_name','&city','&manager_id')
new   1: insert into branch values('1006','Bangalore Branch','Bangalore','506')

1 row created.

SQL> /
Enter value for branch_id: 1007
Enter value for branch_name: Kochi Branch
Enter value for city: Kochi
Enter value for manager_id: 507
old   1: insert into branch values('&branch_id','&branch_name','&city','&manager_id')
new   1: insert into branch values('1007','Kochi Branch','Kochi','507')

1 row created.

SQL> /
Enter value for branch_id: 1008
Enter value for branch_name: Surat Branch
Enter value for city: Surat
Enter value for manager_id: 508
old   1: insert into branch values('&branch_id','&branch_name','&city','&manager_id')
new   1: insert into branch values('1008','Surat Branch','Surat','508')

1 row created.

SQL> /
Enter value for branch_id: 1009
Enter value for branch_name: Jaipur Branch
Enter value for city: Jaipur
Enter value for manager_id: 509
old   1: insert into branch values('&branch_id','&branch_name','&city','&manager_id')
new   1: insert into branch values('1009','Jaipur Branch','Jaipur','509')

1 row created.

SQL> /
Enter value for branch_id: 1010
Enter value for branch_name: Hyderabad Branch
Enter value for city: Hyderabad
Enter value for manager_id: 510
old   1: insert into branch values('&branch_id','&branch_name','&city','&manager_id')
new   1: insert into branch values('1010','Hyderabad Branch','Hyderabad','510')

1 row created.

SQL> select * from branch;

 BRANCH_ID BRANCH_NAME                              CITY                           MANAGER_ID                                                                                                           
---------- ---------------------------------------- ------------------------------ ----------                                                                                                           
      1001 Andheri                                  Mumbai                                501                                                                                                           
      1002 Pune Camp                                Pune                                  502                                                                                                           
      1003 Delhi Central                            Delhi                                 503                                                                                                           
      1004 Ahemdabad Branch                         Ahemdabad                             504                                                                                                           
      1005 Nashik Branch                            Nashik                                505                                                                                                           
      1006 Bangalore Branch                         Bangalore                             506                                                                                                           
      1007 Kochi Branch                             Kochi                                 507                                                                                                           
      1008 Surat Branch                             Surat                                 508                                                                                                           
      1009 Jaipur Branch                            Jaipur                                509                                                                                                           
      1010 Hyderabad Branch                         Hyderabad                             510                                                                                                           

10 rows selected.

SQL> clear screen

SQL> insert into account values('&account_id','&customer_id','&branch_id','&account_type','&balance','&open_date','&status');
Enter value for account_id: 200001
Enter value for customer_id: 
Enter value for branch_id: 
Enter value for account_type: 
Enter value for balance: 
Enter value for open_date: 
Enter value for status: 
old   1: insert into account values('&account_id','&customer_id','&branch_id','&account_type','&balance','&open_date','&status')
new   1: insert into account values('200001','','','','','','')
insert into account values('200001','','','','','','')
                                                *
ERROR at line 1:
ORA-01400: cannot insert NULL into ("C##MBA53"."ACCOUNT"."OPEN_DATE") 


SQL> INSERT INTO account
  2  (account_id, customer_id, branch_id, account_type, balance, open_date, status)
  3  VALUES
  4  (200001, 101, 1001, 'savings', 50000.00, TO_DATE('10-01-2025','DD-MM-YYYY'), 'active');

1 row created.

SQL> 
SQL> INSERT INTO account
  2  (account_id, customer_id, branch_id, account_type, balance, open_date, status)
  3  VALUES
  4  (200002, 102, 1002, 'current', 85000.00, TO_DATE('15-02-2025','DD-MM-YYYY'), 'active');

1 row created.

SQL> 
SQL> INSERT INTO account
  2  (account_id, customer_id, branch_id, account_type, balance, open_date, status)
  3  VALUES
  4  (200003, 103, 1003, 'savings', 35000.00, TO_DATE('20-03-2025','DD-MM-YYYY'), 'active');

1 row created.

SQL> 
SQL> INSERT INTO account
  2  (account_id, customer_id, branch_id, account_type, balance, open_date, status)
  3  VALUES
  4  (200004, 104, 1004, 'current', 120000.00, TO_DATE('05-04-2025','DD-MM-YYYY'), 'active');

1 row created.

SQL> 
SQL> INSERT INTO account
  2  (account_id, customer_id, branch_id, account_type, balance, open_date, status)
  3  VALUES
  4  (200005, 105, 1005, 'savings', 45000.00, TO_DATE('12-05-2025','DD-MM-YYYY'), 'active');

1 row created.

SQL> 
SQL> INSERT INTO account
  2  (account_id, customer_id, branch_id, account_type, balance, open_date, status)
  3  VALUES
  4  (200006, 106, 1006, 'savings', 75000.00, TO_DATE('18-06-2025','DD-MM-YYYY'), 'active');

1 row created.

SQL> 
SQL> INSERT INTO account
  2  (account_id, customer_id, branch_id, account_type, balance, open_date, status)
  3  VALUES
  4  (200007, 107, 1007, 'current', 95000.00, TO_DATE('25-07-2025','DD-MM-YYYY'), 'active');

1 row created.

SQL> 
SQL> INSERT INTO account
  2  (account_id, customer_id, branch_id, account_type, balance, open_date, status)
  3  VALUES
  4  (200008, 108, 1008, 'savings', 28000.00, TO_DATE('10-08-2025','DD-MM-YYYY'), 'active');

1 row created.

SQL> 
SQL> INSERT INTO account
  2  (account_id, customer_id, branch_id, account_type, balance, open_date, status)
  3  VALUES
  4  (200009, 109, 1009, 'current', 150000.00, TO_DATE('15-09-2025','DD-MM-YYYY'), 'active');

1 row created.

SQL> 
SQL> INSERT INTO account
  2  (account_id, customer_id, branch_id, account_type, balance, open_date, status)
  3  VALUES
  4  (200010, 110, 1010, 'savings', 62000.00, TO_DATE('20-10-2025','DD-MM-YYYY'), 'active');

1 row created.

SQL> select * from account;

ACCOUNT_ID CUSTOMER_ID  BRANCH_ID ACCOUNT_TYPE       BALANCE OPEN_DATE STATUS                                                                                                                           
---------- ----------- ---------- --------------- ---------- --------- ---------------                                                                                                                  
    200001         101       1001 savings              50000 10-JAN-25 active                                                                                                                           
    200002         102       1002 current              85000 15-FEB-25 active                                                                                                                           
    200003         103       1003 savings              35000 20-MAR-25 active                                                                                                                           
    200004         104       1004 current             120000 05-APR-25 active                                                                                                                           
    200005         105       1005 savings              45000 12-MAY-25 active                                                                                                                           
    200006         106       1006 savings              75000 18-JUN-25 active                                                                                                                           
    200007         107       1007 current              95000 25-JUL-25 active                                                                                                                           
    200008         108       1008 savings              28000 10-AUG-25 active                                                                                                                           
    200009         109       1009 current             150000 15-SEP-25 active                                                                                                                           
    200010         110       1010 savings              62000 20-OCT-25 active                                                                                                                           

10 rows selected.

SQL> INSERT INTO bank_transaction
  2  (transaction_id, account_id, transaction_type, amount, transaction_date)
  3  VALUES
  4  (3000001, 200001, 'deposit', 10000.00, TO_DATE('01-01-2026','DD-MM-YYYY'));

1 row created.

SQL> 
SQL> INSERT INTO bank_transaction
  2  (transaction_id, account_id, transaction_type, amount, transaction_date)
  3  VALUES
  4  (3000002, 200002, 'withdrawal', 5000.00, TO_DATE('03-01-2026','DD-MM-YYYY'));

1 row created.

SQL> 
SQL> INSERT INTO bank_transaction
  2  (transaction_id, account_id, transaction_type, amount, transaction_date)
  3  VALUES
  4  (3000003, 200003, 'deposit', 15000.00, TO_DATE('05-01-2026','DD-MM-YYYY'));

1 row created.

SQL> 
SQL> INSERT INTO bank_transaction
  2  (transaction_id, account_id, transaction_type, amount, transaction_date)
  3  VALUES
  4  (3000004, 200004, 'withdrawal', 12000.00, TO_DATE('07-01-2026','DD-MM-YYYY'));

1 row created.

SQL> 
SQL> INSERT INTO bank_transaction
  2  (transaction_id, account_id, transaction_type, amount, transaction_date)
  3  VALUES
  4  (3000005, 200005, 'deposit', 8000.00, TO_DATE('10-01-2026','DD-MM-YYYY'));

1 row created.

SQL> 
SQL> INSERT INTO bank_transaction
  2  (transaction_id, account_id, transaction_type, amount, transaction_date)
  3  VALUES
  4  (3000006, 200006, 'withdrawal', 7000.00, TO_DATE('12-01-2026','DD-MM-YYYY'));

1 row created.

SQL> 
SQL> INSERT INTO bank_transaction
  2  (transaction_id, account_id, transaction_type, amount, transaction_date)
  3  VALUES
  4  (3000007, 200007, 'deposit', 20000.00, TO_DATE('15-01-2026','DD-MM-YYYY'));

1 row created.

SQL> 
SQL> INSERT INTO bank_transaction
  2  (transaction_id, account_id, transaction_type, amount, transaction_date)
  3  VALUES
  4  (3000008, 200008, 'withdrawal', 4000.00, TO_DATE('18-01-2026','DD-MM-YYYY'));

1 row created.

SQL> 
SQL> INSERT INTO bank_transaction
  2  (transaction_id, account_id, transaction_type, amount, transaction_date)
  3  VALUES
  4  (3000009, 200009, 'deposit', 25000.00, TO_DATE('20-01-2026','DD-MM-YYYY'));

1 row created.

SQL> 
SQL> INSERT INTO bank_transaction
  2  (transaction_id, account_id, transaction_type, amount, transaction_date)
  3  VALUES
  4  (3000010, 200010, 'withdrawal', 6000.00, TO_DATE('22-01-2026','DD-MM-YYYY'));

1 row created.

SQL> select * from bank_transaction;

TRANSACTION_ID ACCOUNT_ID TRANSACTION_TYP     AMOUNT TRANSACTI                                                                                                                                          
-------------- ---------- --------------- ---------- ---------                                                                                                                                          
       3000001     200001 deposit              10000 01-JAN-26                                                                                                                                          
       3000002     200002 withdrawal            5000 03-JAN-26                                                                                                                                          
       3000003     200003 deposit              15000 05-JAN-26                                                                                                                                          
       3000004     200004 withdrawal           12000 07-JAN-26                                                                                                                                          
       3000005     200005 deposit               8000 10-JAN-26                                                                                                                                          
       3000006     200006 withdrawal            7000 12-JAN-26                                                                                                                                          
       3000007     200007 deposit              20000 15-JAN-26                                                                                                                                          
       3000008     200008 withdrawal            4000 18-JAN-26                                                                                                                                          
       3000009     200009 deposit              25000 20-JAN-26                                                                                                                                          
       3000010     200010 withdrawal            6000 22-JAN-26                                                                                                                                          

10 rows selected.

SQL> clear screen

SQL> select * from customer;

CUSTOMER_ID CUSTOMER_NAME                            CITY                           PHONE      EMAIL                                                                                                    
----------- ---------------------------------------- ------------------------------ ---------- --------------------------------------------------                                                       
        101 Riya Sharma                              Mumbai                         9876543210 riya@gmail.com                                                                                           
        102 Amit Patel                               Pune                           9876543211 amit@gmail.com                                                                                           
        103 Neha Verma                               Delhi                          9876543212 neha@gmail.com                                                                                           
        104 Rahul Mehta                              Ahemdabad                      9876543213 rahul@gmail.com                                                                                          
        105 Sneha Joshi                              Nashik                         9876543214 sneha@gmail.com                                                                                          
        106 Arjun Singh                              Bangalore                      9876543215 arjun@gmail.com                                                                                          
        107 Priya Nair                               Kochi                          9876543216 priya@gmail.com                                                                                          
        108 Karan Shah                               Surat                          9876543217 karan@gmail.com                                                                                          
        109 Pooja Gupta                              Jaipur                         9876543218 pooja@gmail.com                                                                                          
        110 Vikram Rao                               Hyderabad                      9876543219 vikram@gmail.com                                                                                         

10 rows selected.

SQL> select * from branch;

 BRANCH_ID BRANCH_NAME                              CITY                           MANAGER_ID                                                                                                           
---------- ---------------------------------------- ------------------------------ ----------                                                                                                           
      1001 Andheri                                  Mumbai                                501                                                                                                           
      1002 Pune Camp                                Pune                                  502                                                                                                           
      1003 Delhi Central                            Delhi                                 503                                                                                                           
      1004 Ahemdabad Branch                         Ahemdabad                             504                                                                                                           
      1005 Nashik Branch                            Nashik                                505                                                                                                           
      1006 Bangalore Branch                         Bangalore                             506                                                                                                           
      1007 Kochi Branch                             Kochi                                 507                                                                                                           
      1008 Surat Branch                             Surat                                 508                                                                                                           
      1009 Jaipur Branch                            Jaipur                                509                                                                                                           
      1010 Hyderabad Branch                         Hyderabad                             510                                                                                                           

10 rows selected.

SQL> select * from account;

ACCOUNT_ID CUSTOMER_ID  BRANCH_ID ACCOUNT_TYPE       BALANCE OPEN_DATE STATUS                                                                                                                           
---------- ----------- ---------- --------------- ---------- --------- ---------------                                                                                                                  
    200001         101       1001 savings              50000 10-JAN-25 active                                                                                                                           
    200002         102       1002 current              85000 15-FEB-25 active                                                                                                                           
    200003         103       1003 savings              35000 20-MAR-25 active                                                                                                                           
    200004         104       1004 current             120000 05-APR-25 active                                                                                                                           
    200005         105       1005 savings              45000 12-MAY-25 active                                                                                                                           
    200006         106       1006 savings              75000 18-JUN-25 active                                                                                                                           
    200007         107       1007 current              95000 25-JUL-25 active                                                                                                                           
    200008         108       1008 savings              28000 10-AUG-25 active                                                                                                                           
    200009         109       1009 current             150000 15-SEP-25 active                                                                                                                           
    200010         110       1010 savings              62000 20-OCT-25 active                                                                                                                           

10 rows selected.

SQL> select * from bank_transaction;

TRANSACTION_ID ACCOUNT_ID TRANSACTION_TYP     AMOUNT TRANSACTI                                                                                                                                          
-------------- ---------- --------------- ---------- ---------                                                                                                                                          
       3000001     200001 deposit              10000 01-JAN-26                                                                                                                                          
       3000002     200002 withdrawal            5000 03-JAN-26                                                                                                                                          
       3000003     200003 deposit              15000 05-JAN-26                                                                                                                                          
       3000004     200004 withdrawal           12000 07-JAN-26                                                                                                                                          
       3000005     200005 deposit               8000 10-JAN-26                                                                                                                                          
       3000006     200006 withdrawal            7000 12-JAN-26                                                                                                                                          
       3000007     200007 deposit              20000 15-JAN-26                                                                                                                                          
       3000008     200008 withdrawal            4000 18-JAN-26                                                                                                                                          
       3000009     200009 deposit              25000 20-JAN-26                                                                                                                                          
       3000010     200010 withdrawal            6000 22-JAN-26                                                                                                                                          

10 rows selected.

SQL> commit;

Commit complete.

SQL> spool off;
