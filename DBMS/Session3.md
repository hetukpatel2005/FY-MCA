SQL> select * from student;

   ROLL_NO NAME                                               G        AGE EMAIL                                              COURSE                                                                    
---------- -------------------------------------------------- - ---------- -------------------------------------------------- --------------------------------------------------                        
         1 Hetuk                                              M         20 hetuk@gmail.com                                    MCA                                                                       
         2 Hello                                              M                                                                                                                                         
         3 World                                              M         20 world@gmail.com                                    MBA                                                                       
         4 Rupal                                              F         20 rupal@gmail.com                                    MCA Second Year                                                           
         5 Rupesh                                             M         20 rupesh@gmail.com                                   MBA Second Year                                                           
         6 Light                                              m         20 light@gmail.com                                    mca                                                                       
         7 Mohit                                              M         20 m@gmail.com                                        MCA                                                                       
         9 Ram                                                M         20 r@gmail.com                                        MCA                                                                       
        10 Ravan                                              M         20 ra@gmail.com                                       MBA                                                                       

9 rows selected.

SQL> alter table student
  2  add phone_number varchar2(50);

Table altered.  

SQL> select * from student;

   ROLL_NO NAME                                               G        AGE EMAIL                                              COURSE                                                                    
---------- -------------------------------------------------- - ---------- -------------------------------------------------- --------------------------------------------------                        
PHONE_NUMBER                                                                                                                                                                                            
--------------------------------------------------                                                                                                                                                      
         1 Hetuk                                              M         20 hetuk@gmail.com                                    MCA                                                                       
                                                                                                                                                                                                        
         2 Hello                                              M                                                                                                                                         
                                                                                                                                                                                                        
         3 World                                              M         20 world@gmail.com                                    MBA                                                                       
                                                                                                                                                                                                        
         4 Rupal                                              F         20 rupal@gmail.com                                    MCA Second Year                                                           
                                                                                                                                                                                                        
         5 Rupesh                                             M         20 rupesh@gmail.com                                   MBA Second Year                                                           
                                                                                                                                                                                                        
         6 Light                                              m         20 light@gmail.com                                    mca                                                                       
                                                                                                                                                                                                        
         7 Mohit                                              M         20 m@gmail.com                                        MCA                                                                       
                                                                                                                                                                                                        
         9 Ram                                                M         20 r@gmail.com                                        MCA                                                                       
                                                                                                                                                                             
        10 Ravan                                              M         20 ra@gmail.com                                       MBA                                                                       

9 rows selected.

SQL> desc student
 Name                                                                                                              Null?    Type
 ----------------------------------------------------------------------------------------------------------------- -------- ----------------------------------------------------------------------------
 ROLL_NO                                                                                                                    NUMBER(4)
 NAME                                                                                                                       VARCHAR2(50)
 GENDER                                                                                                                     CHAR(1)
 AGE                                                                                                                        NUMBER(3)
 EMAIL                                                                                                                      VARCHAR2(50)
 COURSE                                                                                                                     VARCHAR2(50)
 PHONE_NUMBER                                                                                                               VARCHAR2(50)

SQL> set pagesize 100
SQL> set linesize 200
SQL> select * from student;

   ROLL_NO NAME                                               G        AGE EMAIL                                              COURSE                                                                    
---------- -------------------------------------------------- - ---------- -------------------------------------------------- --------------------------------------------------                        
PHONE_NUMBER                                                                                                                                                                                            
--------------------------------------------------                                                                                                                                                      
         1 Hetuk                                              M         20 hetuk@gmail.com                                    MCA                                                                       
                                                                                                                                                                                                        
                                                                                                                                                                                                        
         2 Hello                                              M                                                                                                                                         
                                                                                                                                                                                                        
                                                                                                                                                                                                        
         3 World                                              M         20 world@gmail.com                                    MBA                                                                       
                                                                                                                                                                                                        
                                                                                                                                                                                                        
         4 Rupal                                              F         20 rupal@gmail.com                                    MCA Second Year                                                           
                                                                                                                                                                                                        
                                                                                                                                                                                                        
         5 Rupesh                                             M         20 rupesh@gmail.com                                   MBA Second Year                                                           
                                                                                                                                                                                                        
                                                                                                                                                                                                        
         6 Light                                              m         20 light@gmail.com                                    mca                                                                       
                                                                                                                                                                                                        
                                                                                                                                                                                                        
         7 Mohit                                              M         20 m@gmail.com                                        MCA                                                                       
                                                                                                                                                                                                        
                                                                                                                                                                                                        
         9 Ram                                                M         20 r@gmail.com                                        MCA                                                                       
                                                                                                                                                                                                        
                                                                                                                                                                                                        
        10 Ravan                                              M         20 ra@gmail.com                                       MBA                                                                       
                                                                                                                                                                                                        
                                                                                                                                                                                                        

9 rows selected.

SQL> alter table student
  2  modify gender varchar2(20);

Table altered.

SQL> insert into student
  2  values('&roll_no','&name','&gender','&age','&email','&course','&phone_number');
Enter value for roll_no: 11
Enter value for name: Sita
Enter value for gender: Female
Enter value for age: 20
Enter value for email: s@gmail.com
Enter value for course: MCA
Enter value for phone_number: 9876543210
old   2: values('&roll_no','&name','&gender','&age','&email','&course','&phone_number')
new   2: values('11','Sita','Female','20','s@gmail.com','MCA','9876543210')

1 row created.

SQL> select * from student;

   ROLL_NO NAME                                               GENDER                      AGE EMAIL                                              COURSE                                                 
---------- -------------------------------------------------- -------------------- ---------- -------------------------------------------------- --------------------------------------------------     
MOBILE_NUMBER                                                                                                                                                                                            
--------------------------------------------------                                                                                                                                                      
         1 Hetuk                                              M                            20 hetuk@gmail.com                                    MCA                                                    
                                                                                                                                                                                                        
         2 Hello                                              M                                                                                                                                         
                                                                                                                                                                                                        
         3 World                                              M                            20 world@gmail.com                                    MBA                                                    
                                                                                                                                                                                                        
         4 Rupal                                              F                            20 rupal@gmail.com                                    MCA Second Year                                        
                                                                                                                                                                                                        
         5 Rupesh                                             M                            20 rupesh@gmail.com                                   MBA Second Year                                        
                                                                                                                                                                                                        
         6 Light                                              m                            20 light@gmail.com                                    mca                                                    
                                                                                                                                                                                                        
         7 Mohit                                              M                            20 m@gmail.com                                        MCA                                                    
                                                                                                                                                                                                        
         9 Ram                                                M                            20 r@gmail.com                                        MCA                                                    
                                                                                                                                                                                                        
        10 Ravan                                              M                            20 ra@gmail.com                                       MBA                                                    
                                                                                                                                                                                                        
        11 Sita                                               Female                       20 s@gmail.com                                        MCA                                                    
9876543210                                                                                                                                                                                              
                                    
10 rows selected.

SQL> alter table student
  2  rename column phone_number to mobile_number;

Table altered.

SQL> select * from student;

   ROLL_NO NAME                                               GENDER                      AGE EMAIL                                              COURSE                                                 
---------- -------------------------------------------------- -------------------- ---------- -------------------------------------------------- --------------------------------------------------     
MOBILE_NUMBER                                                                                                                                                                                           
--------------------------------------------------                                                                                                                                                      
         1 Hetuk                                              M                            20 hetuk@gmail.com                                    MCA                                                    
                                                                                                                                                                                                        
         2 Hello                                              M                                                                                                                                         
                                                                                                                                                                                                        
         3 World                                              M                            20 world@gmail.com                                    MBA                                                    
                                                                                                                                                                                                        
         4 Rupal                                              F                            20 rupal@gmail.com                                    MCA Second Year                                        
                                                                                                                                                                                                        
         5 Rupesh                                                                                                                                                                                       
                                                                                                                                                                                                        
         6 Light                                              m                            20 light@gmail.com                                    mca                                                    
                                                                                                                                                                                                        
         7 Mohit                                              M                            20 m@gmail.com                                        MCA                                                    
                                                                                                                                                                                                        
         9 Ram                                                M                            20 r@gmail.com                                        MCA                                                    
                                                                                                                                                                                                        
        10 Ravan                                              M                            20 ra@gmail.com                                       MBA                                                    
                                                                                                                                                                                                        
        11 Sita                                               Female                       20 s@gmail.com                                        MCA                                                    
9876543210                                                                                                                                                                                              
                          
10 rows selected.

SQL> alter table student
  2  rename column roll_no to roll_call;

Table altered.

SQL> select * from student;

 ROLL_CALL NAME                                               GENDER                      AGE EMAIL                                              COURSE                                                 
---------- -------------------------------------------------- -------------------- ---------- -------------------------------------------------- --------------------------------------------------     
MOBILE_NUMBER                                                                                                                                                                                           
--------------------------------------------------                                                                                                                                                      
         1 Hetuk                                              M                            20 hetuk@gmail.com                                    MCA                                                    
                                                                                                                                                                                                        
                                                                                                                                                                                                        
         2 Hello                                              M                                                                                                                                         
                                                                                                                                                                                                        
                                                                                                                                                                                                        
         3 World                                              M                            20 world@gmail.com                                    MBA                                                    
                                                                                                                                                                                                        
                                                                                                                                                                                                        
         4 Rupal                                              F                            20 rupal@gmail.com                                    MCA Second Year                                        
                                                                                                                                                                                                        
                                                                                                                                                                                                        
         5 Rupesh                                             M                            20 rupesh@gmail.com                                   MBA Second Year                                        
                                                                                                                                                                                                        
                                                                                                                                                                                                        
         6 Light                                              m                            20 light@gmail.com                                    mca                                                    
                                                                                                                                                                                                        
                                                                                                                                                                                                        
         7 Mohit                                              M                            20 m@gmail.com                                        MCA                                                    
                                                                                                                                                                                                        
                                                                                                                                                                                                        
         9 Ram                                                M                            20 r@gmail.com                                        MCA                                                    
                                                                                                                                                                                                        
                                                                                                                                                                                                        
        10 Ravan                                              M                            20 ra@gmail.com                                       MBA                                                    
                                                                                                                                                                                                        
                                                                                                                                                                                                        
        11 Sita                                               Female                       20 s@gmail.com                                        MCA                                                    
9876543210                                                                                                                                                                                              
                                                                                                                                                                                                        

10 rows selected.

SQL> desc student
 Name                                                                                                              Null?    Type
 ----------------------------------------------------------------------------------------------------------------- -------- ----------------------------------------------------------------------------
 ROLL_CALL                                                                                                                  NUMBER(4)
 NAME                                                                                                                       VARCHAR2(50)
 GENDER                                                                                                                     VARCHAR2(20)
 AGE                                                                                                                        NUMBER(3)
 EMAIL                                                                                                                      VARCHAR2(50)
 COURSE                                                                                                                     VARCHAR2(50)
 MOBILE_NUMBER                                                                                                              VARCHAR2(50)

SQL> update student
  2  set mobile_number = '1234567890'
  3  where roll_call='3';

1 row updated.

SQL> select * from student;

 ROLL_CALL NAME                                               GENDER                      AGE EMAIL                                              COURSE                                                 
---------- -------------------------------------------------- -------------------- ---------- -------------------------------------------------- --------------------------------------------------     
MOBILE_NUMBER                                                                                                                                                                                           
--------------------------------------------------                                                                                                                                                      
         1 Hetuk                                              M                            20 hetuk@gmail.com                                    MCA                                                    
                                                                                                                                                                                                        
                                                                                                                                                                                                        
         2 Hello                                              M                                                                                                                                         
                                                                                                                                                                                                        
                                                                                                                                                                                                        
         3 World                                              M                            20 world@gmail.com                                    MBA                                                    
1234567890                                                                                                                                                                                              
                                                                                                                                                                                                        
         4 Rupal                                              F                            20 rupal@gmail.com                                    MCA Second Year                                        
                                                                                                                                                                                                        
                                                                                                                                                                                                        
         5 Rupesh                                             M                            20 rupesh@gmail.com                                   MBA Second Year                                        
                                                                                                                                                                                                        
                                                                                                                                                                                                        
         6 Light                                              m                            20 light@gmail.com                                    mca                                                    
                                                                                                                                                                                                        
                                                                                                                                                                                                        
         7 Mohit                                              M                            20 m@gmail.com                                        MCA                                                    
                                                                                                                                                                                                        
                                                                                                                                                                                                        
         9 Ram                                                M                            20 r@gmail.com                                        MCA                                                    
                                                                                                                                                                                                        
                                                                                                                                                                                                        
        10 Ravan                                              M                            20 ra@gmail.com                                       MBA                                                    
                                                                                                                                                                                                        
                                                                                                                                                                                                        
        11 Sita                                               Female                       20 s@gmail.com                                        MCA                                                    
9876543210                                                                                                                                                                                              
                                                                                                                                                                                                        

10 rows selected.

SQL> update student
  2  set name ='Aryan'
  3  where roll_call='2';

1 row updated.

SQL> select * from student;

 ROLL_CALL NAME                                               GENDER                      AGE EMAIL                                              COURSE                                                 
---------- -------------------------------------------------- -------------------- ---------- -------------------------------------------------- --------------------------------------------------     
MOBILE_NUMBER                                                                                                                                                                                           
--------------------------------------------------                                                                                                                                                      
         1 Hetuk                                              M                            20 hetuk@gmail.com                                    MCA                                                    
                                                                                                                                                                                                        
                                                                                                                                                                                                        
         2 Aryan                                              M                                                                                                                                         
                                                                                                                                                                                                        
                                                                                                                                                                                                        
         3 World                                              M                            20 world@gmail.com                                    MBA                                                    
1234567890                                                                                                                                                                                              
                                                                                                                                                                                                        
         4 Rupal                                              F                            20 rupal@gmail.com                                    MCA Second Year                                        
                                                                                                                                                                                                        
                                                                                                                                                                                                        
         5 Rupesh                                             M                            20 rupesh@gmail.com                                   MBA Second Year                                        
                                                                                                                                                                                                        
                                                                                                                                                                                                        
         6 Light                                              m                            20 light@gmail.com                                    mca                                                    
                                                                                                                                                                                                        
                                                                                                                                                                                                        
         7 Mohit                                              M                            20 m@gmail.com                                        MCA                                                    
                                                                                                                                                                                                        
                                                                                                                                                                                                        
         9 Ram                                                M                            20 r@gmail.com                                        MCA                                                    
                                                                                                                                                                                                        
                                                                                                                                                                                                        
        10 Ravan                                              M                            20 ra@gmail.com                                       MBA                                                    
                                                                                                                                                                                                        
                                                                                                                                                                                                        
        11 Sita                                               Female                       20 s@gmail.com                                        MCA                                                    
9876543210                                                                                                                                                                                              
                                                                                                                                                                                                        

10 rows selected.

SQL> update student
  2  set age = '20'
  3  set email='aryan@gmail.com'
  4  set course='MCA'
  5  where roll_no='2'
  6  where roll_no='2';
set email='aryan@gmail.com'
*
ERROR at line 3:
ORA-00933: SQL command not properly ended 


SQL> update student
  2  set age = '20'
  3  where roll_no='2';
where roll_no='2'
      *
ERROR at line 3:
ORA-00904: "ROLL_NO": invalid identifier 


SQL> update student
  2  set age = '20'
  3  set email='aryan@gmail.com'
  4  set course='MCA'
  5  where roll_call='2';
set email='aryan@gmail.com'
*
ERROR at line 3:
ORA-00933: SQL command not properly ended 


SQL> update student
  2  set age = '20'
  3  where roll_call='2';

1 row updated.

SQL> update student
  2  set course='MCA'
  3  where roll_call='2';

1 row updated.

SQL> update student
  2  set email='aryan@gmail.com'
  3  where roll_call='2';

1 row updated.

SQL> select * from student
  2  
SQL> select * from student;

 ROLL_CALL NAME                                               GENDER                      AGE EMAIL                                              COURSE                                                 
---------- -------------------------------------------------- -------------------- ---------- -------------------------------------------------- --------------------------------------------------     
MOBILE_NUMBER                                                                                                                                                                                           
--------------------------------------------------                                                                                                                                                      
         1 Hetuk                                              M                            20 hetuk@gmail.com                                    MCA                                                    
                                                                                                                                                                                                        
                                                                                                                                                                                                        
         2 Aryan                                              M                            20 aryan@gmail.com                                    MCA                                                    
                                                                                                                                                                                                        
                                                                                                                                                                                                        
         3 World                                              M                            20 world@gmail.com                                    MBA                                                    
1234567890                                                                                                                                                                                              
                                                                                                                                                                                                        
         4 Rupal                                              F                            20 rupal@gmail.com                                    MCA Second Year                                        
                                                                                                                                                                                                        
                                                                                                                                                                                                        
         5 Rupesh                                             M                            20 rupesh@gmail.com                                   MBA Second Year                                        
                                                                                                                                                                                                        
                                                                                                                                                                                                        
         6 Light                                              m                            20 light@gmail.com                                    mca                                                    
                                                                                                                                                                                                        
                                                                                                                                                                                                        
         7 Mohit                                              M                            20 m@gmail.com                                        MCA                                                    
                                                                                                                                                                                                        
                                                                                                                                                                                                        
         9 Ram                                                M                            20 r@gmail.com                                        MCA                                                    
                                                                                                                                                                                                        
                                                                                                                                                                                                        
        10 Ravan                                              M                            20 ra@gmail.com                                       MBA                                                    
                                                                                                                                                                                                        
                                                                                                                                                                                                        
        11 Sita                                               Female                       20 s@gmail.com                                        MCA                                                    
9876543210                                                                                                                                                                                              
                                                                                                                                                                                                        

10 rows selected.

SQL> update all
  2  into student values()
  3  
SQL> update student
  2  set mobile_number='12315641534'
  3  where roll_call='1';

1 row updated.

SQL> update student
  2  set mobile_number='123156415345'
  3  where roll_call='2';

1 row updated.

SQL> update student
  2  set mobile_number='123156415346'
  3  where roll_call='4';

1 row updated.

SQL> update student
  2  set mobile_number='123156415347'
  3  where roll_call='5';

1 row updated.

SQL> update student
  2  set mobile_number='123156415348'
  3  where roll_call='6';

1 row updated.

SQL> update student
  2  set mobile_number='123156415349'
  3  where roll_call='7';

1 row updated.

SQL> update student
  2  set mobile_number='123156415340'
  3  where roll_call='9';

1 row updated.

SQL> update student
  2  set mobile_number='123156415341'
  3  where roll_call='10';

1 row updated.

SQL> update student
  2  set mobile_number='123156415342'
  3  
SQL> update student
  2  set roll_call='8'
  3  where roll_call='9';

1 row updated.

SQL> update student
  2  set roll_call='9'
  3  where roll_call='10';

1 row updated.

SQL> update student
  2  set roll_call='10'
  3  where roll_call='11';

1 row updated.

SQL> clear screen

SQL> select * from student
  2  
SQL> select * from student;

 ROLL_CALL NAME                                               GENDER                      AGE EMAIL                                              COURSE                                                 
---------- -------------------------------------------------- -------------------- ---------- -------------------------------------------------- --------------------------------------------------     
MOBILE_NUMBER                                                                                                                                                                                           
--------------------------------------------------                                                                                                                                                      
         1 Hetuk                                              M                            20 hetuk@gmail.com                                    MCA                                                    
12315641534                                                                                                                                                                                             
                                                                                                                                                                                                        
         2 Aryan                                              M                            20 aryan@gmail.com                                    MCA                                                    
123156415345                                                                                                                                                                                            
                                                                                                                                                                                                        
         3 World                                              M                            20 world@gmail.com                                    MBA                                                    
1234567890                                                                                                                                                                                              
                                                                                                                                                                                                        
         4 Rupal                                              F                            20 rupal@gmail.com                                    MCA Second Year                                        
123156415346                                                                                                                                                                                            
                                                                                                                                                                                                        
         5 Rupesh                                             M                            20 rupesh@gmail.com                                   MBA Second Year                                        
123156415347                                                                                                                                                                                            
                                                                                                                                                                                                        
         6 Light                                              m                            20 light@gmail.com                                    mca                                                    
123156415348                                                                                                                                                                                            
                                                                                                                                                                                                        
         7 Mohit                                              M                            20 m@gmail.com                                        MCA                                                    
123156415349                                                                                                                                                                                            
                                                                                                                                                                                                        
         8 Ram                                                M                            20 r@gmail.com                                        MCA                                                    
123156415340                                                                                                                                                                                            
                                                                                                                                                                                                        
         9 Ravan                                              M                            20 ra@gmail.com                                       MBA                                                    
123156415341                                                                                                                                                                                            
                                                                                                                                                                                                        
        10 Sita                                               Female                       20 s@gmail.com                                        MCA                                                    
9876543210                                                                                                                                                                                              
                                                                                                                                                                                                        

10 rows selected.

SQL> update student
  2  set gender='M'
  3  where roll_call='6';

1 row updated.

SQL> update student
  2  set course='MCA'
  3  where roll_call='6';

1 row updated.

SQL> select * from student;

 ROLL_CALL NAME                                               GENDER                      AGE EMAIL                                              COURSE                                                 
---------- -------------------------------------------------- -------------------- ---------- -------------------------------------------------- --------------------------------------------------     
MOBILE_NUMBER                                                                                                                                                                                           
--------------------------------------------------                                                                                                                                                      
         1 Hetuk                                              M                            20 hetuk@gmail.com                                    MCA                                                    
12315641534                                                                                                                                                                                             
                                                                                                                                                                                                        
         2 Aryan                                              M                            20 aryan@gmail.com                                    MCA                                                    
123156415345                                                                                                                                                                                            
                                                                                                                                                                                                        
         3 World                                              M                            20 world@gmail.com                                    MBA                                                    
1234567890                                                                                                                                                                                              
                                                                                                                                                                                                        
         4 Rupal                                              F                            20 rupal@gmail.com                                    MCA Second Year                                        
123156415346                                                                                                                                                                                            
                                                                                                                                                                                                        
         5 Rupesh                                             M                            20 rupesh@gmail.com                                   MBA Second Year                                        
123156415347                                                                                                                                                                                            
                                                                                                                                                                                                        
         6 Light                                              M                            20 light@gmail.com                                    MCA                                                    
123156415348                                                                                                                                                                                            
                                                                                                                                                                                                        
         7 Mohit                                              M                            20 m@gmail.com                                        MCA                                                    
123156415349                                                                                                                                                                                            
                                                                                                                                                                                                        
         8 Ram                                                M                            20 r@gmail.com                                        MCA                                                    
123156415340                                                                                                                                                                                            
                                                                                                                                                                                                        
         9 Ravan                                              M                            20 ra@gmail.com                                       MBA                                                    
123156415341                                                                                                                                                                                            
                                                                                                                                                                                                        
        10 Sita                                               Female                       20 s@gmail.com                                        MCA                                                    
9876543210                                                                                                                                                                                              

10 rows selected.

SQL> update student
  2  set gender='F'
  3  where roll_call='10';

1 row updated.

SQL> select * from student;

 ROLL_CALL NAME                                               GENDER                      AGE EMAIL                                              COURSE                                                 
---------- -------------------------------------------------- -------------------- ---------- -------------------------------------------------- --------------------------------------------------     
MOBILE_NUMBER                                                                                                                                                                                           
--------------------------------------------------                                                                                                                                                      
         1 Hetuk                                              M                            20 hetuk@gmail.com                                    MCA                                                    
12315641534                                                                                                                                                                                             
                                                                                                                                                                                                        
         2 Aryan                                              M                            20 aryan@gmail.com                                    MCA                                                    
123156415345                                                                                                                                                                                            
                                                                                                                                                                                                        
         3 World                                              M                            20 world@gmail.com                                    MBA                                                    
1234567890                                                                                                                                                                                              
                                                                                                                                                                                                        
         4 Rupal                                              F                            20 rupal@gmail.com                                    MCA Second Year                                        
123156415346                                                                                                                                                                                            
                                                                                                                                                                                                        
         5 Rupesh                                             M                            20 rupesh@gmail.com                                   MBA Second Year                                        
123156415347                                                                                                                                                                                            
                                                                                                                                                                                                        
         6 Light                                              M                            20 light@gmail.com                                    MCA                                                    
123156415348                                                                                                                                                                                            
                                                                                                                                                                                                        
         7 Mohit                                              M                            20 m@gmail.com                                        MCA                                                    
123156415349                                                                                                                                                                                            
                                                                                                                                                                                                        
         8 Ram                                                M                            20 r@gmail.com                                        MCA                                                    
123156415340                                                                                                                                                                                            
                                                                                                                                                                                                        
         9 Ravan                                              M                            20 ra@gmail.com                                       MBA                                                    
123156415341                                                                                                                                                                                            
                                                                                                                                                                                                        
        10 Sita                                               F                            20 s@gmail.com                                        MCA                                                    
9876543210                                                                                                                                                                                              
                                                                                                                                                                                                        

10 rows selected.

SQL> delete from student
  2  where roll_call='3';

1 row deleted.

SQL> select * from student;

 ROLL_CALL NAME                                               GENDER                      AGE EMAIL                                              COURSE                                                 
---------- -------------------------------------------------- -------------------- ---------- -------------------------------------------------- --------------------------------------------------     
MOBILE_NUMBER                                                                                                                                                                                           
--------------------------------------------------                                                                                                                                                      
         1 Hetuk                                              M                            20 hetuk@gmail.com                                    MCA                                                    
12315641534                                                                                                                                                                                             
                                                                                                                                                                                                        
         2 Aryan                                              M                            20 aryan@gmail.com                                    MCA                                                    
123156415345                                                                                                                                                                                            
                                                                                                                                                                                                        
         4 Rupal                                              F                            20 rupal@gmail.com                                    MCA Second Year                                        
123156415346                                                                                                                                                                                            
                                                                                                                                                                                                        
         5 Rupesh                                             M                            20 rupesh@gmail.com                                   MBA Second Year                                        
123156415347                                                                                                                                                                                            
                                                                                                                                                                                                        
         6 Light                                              M                            20 light@gmail.com                                    MCA                                                    
123156415348                                                                                                                                                                                            
                                                                                                                                                                                                        
         7 Mohit                                              M                            20 m@gmail.com                                        MCA                                                    
123156415349                                                                                                                                                                                            
                                                                                                                                                                                                        
         8 Ram                                                M                            20 r@gmail.com                                        MCA                                                    
123156415340                                                                                                                                                                                            
                                                                                                                                                                                                        
         9 Ravan                                              M                            20 ra@gmail.com                                       MBA                                                    
123156415341                                                                                                                                                                                            
                                                                                                                                                                                                        
        10 Sita                                               F                            20 s@gmail.com                                        MCA                                                    
9876543210                                                                                                                                                                                              
                                                                                                                                                                                                        

9 rows selected.

SQL> commit;

Commit complete.

SQL> select * from student
  2  where course='mca';

no rows selected

SQL> select * from student
  2  where course='MCA';

 ROLL_CALL NAME                                               GENDER                      AGE EMAIL                                              COURSE                                                 
---------- -------------------------------------------------- -------------------- ---------- -------------------------------------------------- --------------------------------------------------     
MOBILE_NUMBER                                                                                                                                                                                           
--------------------------------------------------                                                                                                                                                      
         1 Hetuk                                              M                            20 hetuk@gmail.com                                    MCA                                                    
12315641534                                                                                                                                                                                             
                                                                                                                                                                                                        
         2 Aryan                                              M                            20 aryan@gmail.com                                    MCA                                                    
123156415345                                                                                                                                                                                            
                                                                                                                                                                                                        
         6 Light                                              M                            20 light@gmail.com                                    MCA                                                    
123156415348                                                                                                                                                                                            
                                                                                                                                                                                                        
         7 Mohit                                              M                            20 m@gmail.com                                        MCA                                                    
123156415349                                                                                                                                                                                            
                                                                                                                                                                                                        
         8 Ram                                                M                            20 r@gmail.com                                        MCA                                                    
123156415340                                                                                                                                                                                            
                                                                                                                                                                                                        
        10 Sita                                               F                            20 s@gmail.com                                        MCA                                                    
9876543210                                                                                                                                                                                              
                                                                                                                                                                                                        

6 rows selected.

SQL> select * from student
  2  where roll_call=10 AND gender='F';

 ROLL_CALL NAME                                               GENDER                      AGE EMAIL                                              COURSE                                                 
---------- -------------------------------------------------- -------------------- ---------- -------------------------------------------------- --------------------------------------------------     
MOBILE_NUMBER                                                                                                                                                                                           
--------------------------------------------------                                                                                                                                                      
        10 Sita                                               F                            20 s@gmail.com                                        MCA                                                    
9876543210                                                                                                                                                                                              
                                                                                                                                                                                                        

SQL> select * from student
  2  where roll_call=2 OR gender='F';

 ROLL_CALL NAME                                               GENDER                      AGE EMAIL                                              COURSE                                                 
---------- -------------------------------------------------- -------------------- ---------- -------------------------------------------------- --------------------------------------------------     
MOBILE_NUMBER                                                                                                                                                                                           
--------------------------------------------------                                                                                                                                                      
         2 Aryan                                              M                            20 aryan@gmail.com                                    MCA                                                    
123156415345                                                                                                                                                                                            
                                                                                                                                                                                                        
         4 Rupal                                              F                            20 rupal@gmail.com                                    MCA Second Year                                        
123156415346                                                                                                                                                                                            
                                                                                                                                                                                                        
        10 Sita                                               F                            20 s@gmail.com                                        MCA                                                    
9876543210                                                                                                                                                                                              
                                                                                                                                                                                                        

SQL> select * from student
  2  where course='MBA';

 ROLL_CALL NAME                                               GENDER                      AGE EMAIL                                              COURSE                                                 
---------- -------------------------------------------------- -------------------- ---------- -------------------------------------------------- --------------------------------------------------     
MOBILE_NUMBER                                                                                                                                                                                           
--------------------------------------------------                                                                                                                                                      
         9 Ravan                                              M                            20 ra@gmail.com                                       MBA                                                    
123156415341                                                                                                                                                                                            
                                                                                                                                                                                                        

SQL> commit
  2  
SQL> commit;

Commit complete.

SQL> pull off;
SP2-0042: unknown command "pull off" - rest of line ignored.
SQL> spoll off
SP2-0042: unknown command "spoll off" - rest of line ignored.
SQL> spool off
