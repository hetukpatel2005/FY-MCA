SQL> create table doctor(
  2  doctor_id number(5) primary key,
  3  doctor_name varchar2(40) not null,
  4  specilization varchar2(40) not null,
  5  email varchar2(30) unique,
  6  contact_number varchar2(10)
  7  );

Table created.

SQL> alter table doctor
  2  modify contact_number varchar2(10) unique;

Table altered.

SQL> desc doctor;
 Name                                      Null?    Type
 ----------------------------------------- -------- ----------------------------
 DOCTOR_ID                                 NOT NULL NUMBER(5)
 DOCTOR_NAME                               NOT NULL VARCHAR2(40)
 SPECILIZATION                             NOT NULL VARCHAR2(40)
 EMAIL                                              VARCHAR2(30)
 CONTACT_NUMBER                                     VARCHAR2(10)

SQL> insert into doctor
  2  values('&doctor_id', '&doctor_name', '&specilization', 'email', 'contact_number')
  3  ;
Enter value for doctor_id: 401
Enter value for doctor_name: harsh
Enter value for specilization: 
old   2: values('&doctor_id', '&doctor_name', '&specilization', 'email', 'contact_number')
new   2: values('401', 'harsh', '', 'email', 'contact_number')
values('401', 'harsh', '', 'email', 'contact_number')
                       *
ERROR at line 2:
ORA-01400: cannot insert NULL into ("C##MBA53"."DOCTOR"."SPECILIZATION") 


SQL> /
Enter value for doctor_id: 401
Enter value for doctor_name: harsh
Enter value for specilization: dermatology
old   2: values('&doctor_id', '&doctor_name', '&specilization', 'email', 'contact_number')
new   2: values('401', 'harsh', 'dermatology', 'email', 'contact_number')
values('401', 'harsh', 'dermatology', 'email', 'contact_number')
                                               *
ERROR at line 2:
ORA-12899: value too large for column "C##MBA53"."DOCTOR"."CONTACT_NUMBER" 
(actual: 14, maximum: 10) 


SQL> /
Enter value for doctor_id: 402
Enter value for doctor_name: shrikant
Enter value for specilization: urology
old   2: values('&doctor_id', '&doctor_name', '&specilization', 'email', 'contact_number')
new   2: values('402', 'shrikant', 'urology', 'email', 'contact_number')
values('402', 'shrikant', 'urology', 'email', 'contact_number')
                                              *
ERROR at line 2:
ORA-12899: value too large for column "C##MBA53"."DOCTOR"."CONTACT_NUMBER" 
(actual: 14, maximum: 10) 


SQL> desc doctor
 Name                                      Null?    Type
 ----------------------------------------- -------- ----------------------------
 DOCTOR_ID                                 NOT NULL NUMBER(5)
 DOCTOR_NAME                               NOT NULL VARCHAR2(40)
 SPECILIZATION                             NOT NULL VARCHAR2(40)
 EMAIL                                              VARCHAR2(30)
 CONTACT_NUMBER                                     VARCHAR2(10)

SQL> values('&doctor_id', '&doctor_name', '&specilization', '&email', '&contact_number');
SP2-0734: unknown command beginning "values('&d..." - rest of line ignored.
SQL> insert into doctor
  2  values('&doctor_id', '&doctor_name', '&specilization', '&email', '&contact_number');
Enter value for doctor_id: 501
Enter value for doctor_name: Dr. ananya rao
Enter value for specilization: cardiology
Enter value for email: ananya@hospital.com
Enter value for contact_number: 9768484121
old   2: values('&doctor_id', '&doctor_name', '&specilization', '&email', '&contact_number')
new   2: values('501', 'Dr. ananya rao', 'cardiology', 'ananya@hospital.com', '9768484121')

1 row created.

SQL> /
Enter value for doctor_id: 502
Enter value for doctor_name: Dr.rohan mehta
Enter value for specilization: neurology
Enter value for email: rohan@hospital.com
Enter value for contact_number: 65416584785
old   2: values('&doctor_id', '&doctor_name', '&specilization', '&email', '&contact_number')
new   2: values('502', 'Dr.rohan mehta', 'neurology', 'rohan@hospital.com', '65416584785')
values('502', 'Dr.rohan mehta', 'neurology', 'rohan@hospital.com', '65416584785')
                                                                   *
ERROR at line 2:
ORA-12899: value too large for column "C##MBA53"."DOCTOR"."CONTACT_NUMBER" 
(actual: 11, maximum: 10) 


SQL> /
Enter value for doctor_id: 502
Enter value for doctor_name: Dr.rohan mehta
Enter value for specilization: neurology
Enter value for email: rohan@hospital.com
Enter value for contact_number: 6541658478
old   2: values('&doctor_id', '&doctor_name', '&specilization', '&email', '&contact_number')
new   2: values('502', 'Dr.rohan mehta', 'neurology', 'rohan@hospital.com', '6541658478')

1 row created.

SQL> /
Enter value for doctor_id: 503
Enter value for doctor_name: Dr.aman mehra
Enter value for specilization: orthopedic
Enter value for email: aman@hospital.com
Enter value for contact_number: 5484544647
old   2: values('&doctor_id', '&doctor_name', '&specilization', '&email', '&contact_number')
new   2: values('503', 'Dr.aman mehra', 'orthopedic', 'aman@hospital.com', '5484544647')

1 row created.

SQL> /
Enter value for doctor_id: 504
Enter value for doctor_name: Dr.sheetal
Enter value for specilization: plastic surgeon
Enter value for email: sheetal@hospital.com
Enter value for contact_number: 1544545441
old   2: values('&doctor_id', '&doctor_name', '&specilization', '&email', '&contact_number')
new   2: values('504', 'Dr.sheetal', 'plastic surgeon', 'sheetal@hospital.com', '1544545441')

1 row created.

SQL> /
Enter value for doctor_id: 505
Enter value for doctor_name: Dr.amit ghole
Enter value for specilization: urology
Enter value for email: amit@hospital.com
Enter value for contact_number: 1285441485
old   2: values('&doctor_id', '&doctor_name', '&specilization', '&email', '&contact_number')
new   2: values('505', 'Dr.amit ghole', 'urology', 'amit@hospital.com', '1285441485')

1 row created.

SQL> select * from doctor
  2  ;

 DOCTOR_ID DOCTOR_NAME                                                          
---------- ----------------------------------------                             
SPECILIZATION                            EMAIL                                  
---------------------------------------- ------------------------------         
CONTACT_NU                                                                      
----------                                                                      
       501 Dr. ananya rao                                                       
cardiology                               ananya@hospital.com                    
9768484121                                                                      
                                                                                
       502 Dr.rohan mehta                                                       
neurology                                rohan@hospital.com                     
6541658478                                                                      

 DOCTOR_ID DOCTOR_NAME                                                          
---------- ----------------------------------------                             
SPECILIZATION                            EMAIL                                  
---------------------------------------- ------------------------------         
CONTACT_NU                                                                      
----------                                                                      
                                                                                
       503 Dr.aman mehra                                                        
orthopedic                               aman@hospital.com                      
5484544647                                                                      
                                                                                
       504 Dr.sheetal                                                           
plastic surgeon                          sheetal@hospital.com                   

 DOCTOR_ID DOCTOR_NAME                                                          
---------- ----------------------------------------                             
SPECILIZATION                            EMAIL                                  
---------------------------------------- ------------------------------         
CONTACT_NU                                                                      
----------                                                                      
1544545441                                                                      
                                                                                
       505 Dr.amit ghole                                                        
urology                                  amit@hospital.com                      
1285441485                                                                      
                                                                                

SQL> set pagesize 200
SQL> set limitsize 100
SP2-0158: unknown SET option "limitsize"
SQL> set linesize 100
SQL> select * from doctor;

 DOCTOR_ID DOCTOR_NAME                              SPECILIZATION                                   
---------- ---------------------------------------- ----------------------------------------        
EMAIL                          CONTACT_NU                                                           
------------------------------ ----------                                                           
       501 Dr. ananya rao                           cardiology                                      
ananya@hospital.com            9768484121                                                           
                                                                                                    
       502 Dr.rohan mehta                           neurology                                       
rohan@hospital.com             6541658478                                                           
                                                                                                    
       503 Dr.aman mehra                            orthopedic                                      
aman@hospital.com              5484544647                                                           
                                                                                                    
       504 Dr.sheetal                               plastic surgeon                                 
sheetal@hospital.com           1544545441                                                           
                                                                                                    
       505 Dr.amit ghole                            urology                                         
amit@hospital.com              1285441485                                                           
                                                                                                    

SQL> set linesize 50
SQL> select * from doctor;

 DOCTOR_ID                                        
----------                                        
DOCTOR_NAME                                       
----------------------------------------          
SPECILIZATION                                     
----------------------------------------          
EMAIL                          CONTACT_NU         
------------------------------ ----------         
       501                                        
Dr. ananya rao                                    
cardiology                                        
ananya@hospital.com            9768484121         
                                                  
       502                                        
Dr.rohan mehta                                    
neurology                                         
rohan@hospital.com             6541658478         
                                                  
       503                                        
Dr.aman mehra                                     
orthopedic                                        
aman@hospital.com              5484544647         
                                                  
       504                                        
Dr.sheetal                                        
plastic surgeon                                   
sheetal@hospital.com           1544545441         
                                                  
       505                                        
Dr.amit ghole                                     
urology                                           
amit@hospital.com              1285441485         
                                                  

SQL> set linesize 200
SQL> set pagesize 50
SQL> select * from doctor;

 DOCTOR_ID DOCTOR_NAME                              SPECILIZATION                            EMAIL                          CONTACT_NU                                                                  
---------- ---------------------------------------- ---------------------------------------- ------------------------------ ----------                                                                  
       501 Dr. ananya rao                           cardiology                               ananya@hospital.com            9768484121                                                                  
       502 Dr.rohan mehta                           neurology                                rohan@hospital.com             6541658478                                                                  
       503 Dr.aman mehra                            orthopedic                               aman@hospital.com              5484544647                                                                  
       504 Dr.sheetal                               plastic surgeon                          sheetal@hospital.com           1544545441                                                                  
       505 Dr.amit ghole                            urology                                  amit@hospital.com              1285441485                                                                  

SQL> commit;

Commit complete.

SQL> clear screen;

SQL> create table appointment
  2  (
  3  a_id number(6) primary key,
  4  patient_name varchar2(40) not null,
  5  patient_phone_number varchar2(10) not null,
  6  doctor_id number(5) references doctor(doctor_id),
  7  fees number(8,2) check(fees>50),
  8  status varchar2(20) check(status IN('booked','completed','cancelled');
status varchar2(20) check(status IN('booked','completed','cancelled')
                                                                    *
ERROR at line 8:
ORA-00907: missing right parenthesis 


SQL> create table appointment
  2  (
  3  a_id number(6) primary key,
  4  patient_name varchar2(40) not null,
  5  patient_phone_number varchar2(10) not null,
  6  doctor_id number(5) references doctor(doctor_id),
  7  fees number(8,2) check(fees>50),
  8  status varchar2(20) check(status IN('booked','completed','cancelled'));
status varchar2(20) check(status IN('booked','completed','cancelled'))
                                                                     *
ERROR at line 8:
ORA-00907: missing right parenthesis 


SQL> create table appointment
  2  (
  3  a_id number(6) primary key,
  4  patient_name varchar2(40) not null,
  5  patient_phone_number varchar2(10) not null,
  6  doctor_id number(5) references doctor(doctor_id),
  7  fees number(8,2) check(fees>50),
  8  status varchar2(20) check(status IN('booked','completed','cancelled')));

Table created.

SQL> select * from appionment;
select * from appionment
              *
ERROR at line 1:
ORA-00942: table or view does not exist 


SQL> select * from appiontment;
select * from appiontment
              *
ERROR at line 1:
ORA-00942: table or view does not exist 


SQL> select * from appointment;

no rows selected

SQL> desc appointment;
 Name                                                                                                              Null?    Type
 ----------------------------------------------------------------------------------------------------------------- -------- ----------------------------------------------------------------------------
 A_ID                                                                                                              NOT NULL NUMBER(6)
 PATIENT_NAME                                                                                                      NOT NULL VARCHAR2(40)
 PATIENT_PHONE_NUMBER                                                                                              NOT NULL VARCHAR2(10)
 DOCTOR_ID                                                                                                                  NUMBER(5)
 FEES                                                                                                                       NUMBER(8,2)
 STATUS                                                                                                                     VARCHAR2(20)

SQL> commit;

Commit complete.

SQL> alter table appointment
  2  add a_date date not null;

Table altered.

SQL> desc appointment;
 Name                                                                                                              Null?    Type
 ----------------------------------------------------------------------------------------------------------------- -------- ----------------------------------------------------------------------------
 A_ID                                                                                                              NOT NULL NUMBER(6)
 PATIENT_NAME                                                                                                      NOT NULL VARCHAR2(40)
 PATIENT_PHONE_NUMBER                                                                                              NOT NULL VARCHAR2(10)
 DOCTOR_ID                                                                                                                  NUMBER(5)
 FEES                                                                                                                       NUMBER(8,2)
 STATUS                                                                                                                     VARCHAR2(20)
 A_DATE                                                                                                            NOT NULL DATE

SQL> commit;

Commit complete.

SQL> cls
SP2-0042: unknown command "cls" - rest of line ignored.
SQL> clear screen

SQL> insert into appointment
  2  values('&a_id','&patient_name','&patient_phone_number','&doctor_id','&fees','&status','&status');
Enter value for a_id: 101
Enter value for patient_name: aarav jhoshi
Enter value for patient_phone_number: 7894561230
Enter value for doctor_id: 501
Enter value for fees: 500
Enter value for status: booked
Enter value for status: 22-sept-2026
old   2: values('&a_id','&patient_name','&patient_phone_number','&doctor_id','&fees','&status','&status')
new   2: values('101','aarav jhoshi','7894561230','501','500','booked','22-sept-2026')
values('101','aarav jhoshi','7894561230','501','500','booked','22-sept-2026')
                                                              *
ERROR at line 2:
ORA-01861: literal does not match format string 


SQL> alter table appointment
  2  modify a_date
  3  
SQL> 
SQL> insert into appointment
  2  values('&a_id','&patient_name','&patient_phone_number','&doctor_id','&fees','&status','&status');
Enter value for a_id: 101
Enter value for patient_name: aarav jhoshi
Enter value for patient_phone_number: 7894561230
Enter value for doctor_id: 501
Enter value for fees: 500
Enter value for status: booked
Enter value for status: 22-sep-2026
old   2: values('&a_id','&patient_name','&patient_phone_number','&doctor_id','&fees','&status','&status')
new   2: values('101','aarav jhoshi','7894561230','501','500','booked','22-sep-2026')

1 row created.

SQL> /
Enter value for a_id: 102
Enter value for patient_name: meera nair
Enter value for patient_phone_number: 1545485414
Enter value for doctor_id: 510
Enter value for fees: 700
Enter value for status: booked
Enter value for status: 22-sep-2026
old   2: values('&a_id','&patient_name','&patient_phone_number','&doctor_id','&fees','&status','&status')
new   2: values('102','meera nair','1545485414','510','700','booked','22-sep-2026')
insert into appointment
*
ERROR at line 1:
ORA-02291: integrity constraint (C##MBA53.SYS_C0058267) violated - parent key not found 


SQL> /
Enter value for a_id: 102
Enter value for patient_name: meera nair
Enter value for patient_phone_number: 1545485414
Enter value for doctor_id: 503
Enter value for fees: 700
Enter value for status: booked
Enter value for status: booked
old   2: values('&a_id','&patient_name','&patient_phone_number','&doctor_id','&fees','&status','&status')
new   2: values('102','meera nair','1545485414','503','700','booked','booked')
values('102','meera nair','1545485414','503','700','booked','booked')
                                                            *
ERROR at line 2:
ORA-01858: a non-numeric character was found where a numeric was expected 


SQL> /
Enter value for a_id: 102
Enter value for patient_name: meera nair
Enter value for patient_phone_number: 1545485414
Enter value for doctor_id: 503
Enter value for fees: 700
Enter value for status: booked
Enter value for status: 20-mar-2026
old   2: values('&a_id','&patient_name','&patient_phone_number','&doctor_id','&fees','&status','&status')
new   2: values('102','meera nair','1545485414','503','700','booked','20-mar-2026')

1 row created.

SQL> /
Enter value for a_id: 103
Enter value for patient_name: abhishek shah
Enter value for patient_phone_number: 7414755211
Enter value for doctor_id: 502
Enter value for fees: 1000
Enter value for status: completed
Enter value for status: 11-sep-2026
old   2: values('&a_id','&patient_name','&patient_phone_number','&doctor_id','&fees','&status','&status')
new   2: values('103','abhishek shah','7414755211','502','1000','completed','11-sep-2026')

1 row created.

SQL> /
Enter value for a_id: 104
Enter value for patient_name: dev mehra
Enter value for patient_phone_number: 7845961231
Enter value for doctor_id: 505
Enter value for fees: 1200
Enter value for status: cancelled
Enter value for status: 13-sep-2026
old   2: values('&a_id','&patient_name','&patient_phone_number','&doctor_id','&fees','&status','&status')
new   2: values('104','dev mehra','7845961231','505','1200','cancelled','13-sep-2026')

1 row created.

SQL> /
Enter value for a_id: 105
Enter value for patient_name: harsh kadam
Enter value for patient_phone_number: 1234567890
Enter value for doctor_id: 504
Enter value for fees: 1500
Enter value for status: completed
Enter value for status: 22-oct-2026
old   2: values('&a_id','&patient_name','&patient_phone_number','&doctor_id','&fees','&status','&status')
new   2: values('105','harsh kadam','1234567890','504','1500','completed','22-oct-2026')

1 row created.

SQL> select * from appointment;

      A_ID PATIENT_NAME                             PATIENT_PH  DOCTOR_ID       FEES STATUS               A_DATE                                                                                        
---------- ---------------------------------------- ---------- ---------- ---------- -------------------- ---------                                                                                     
       101 aarav jhoshi                             7894561230        501        500 booked               22-SEP-26                                                                                     
       102 meera nair                               1545485414        503        700 booked               20-MAR-26                                                                                     
       103 abhishek shah                            7414755211        502       1000 completed            11-SEP-26                                                                                     
       104 dev mehra                                7845961231        505       1200 cancelled            13-SEP-26                                                                                     
       105 harsh kadam                              1234567890        504       1500 completed            22-OCT-26                                                                                     

SQL> spool off;
