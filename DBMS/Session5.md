SQL> select * from student;

 ROLL_CALL NAME                                               GENDER                      AGE EMAIL                                              COURSE                                                 
---------- -------------------------------------------------- -------------------- ---------- -------------------------------------------------- --------------------------------------------------     
MOBILE_NUMBER                                      GRADING                                                                                                                                              
-------------------------------------------------- --------------------------------------------------                                                                                                   
         1 Hetuk                                              M                            20 hetuk@gmail.com                                    MCA                                                    
12315641534                                                                                                                                                                                             
                                                                                                                                                                                                        
         2 Aryan                                              M                            22 aryan@gmail.com                                    MCA                                                    
123156415345                                                                                                                                                                                            
                                                                                                                                                                                                        
         4 Rupal                                              F                            24 rupal@gmail.com                                    MCA Second Year                                        
123156415346                                                                                                                                                                                            
                                                                                                                                                                                                        
         5 Rupesh                                             M                            26 rupesh@gmail.com                                   MBA Second Year                                        
123156415347                                                                                                                                                                                            
                                                                                                                                                                                                        
         6 Light                                              M                            28 light@gmail.com                                    MCA                                                    
123156415348                                                                                                                                                                                            
                                                                                                                                                                                                        
         7 Mohit                                              M                            29 m@gmail.com                                        MCA                                                    
123156415349                                                                                                                                                                                            
                                                                                                                                                                                                        
         8 Ram                                                M                            27 r@gmail.com                                        MCA                                                    
123156415340                                                                                                                                                                                            
                                                                                                                                                                                                        
         9 Ravan                                              M                            25 ra@gmail.com                                       MBA                                                    
123156415341                                                                                                                                                                                            
                                                                                                                                                                                                        
        10 Sita                                               F                            21 s@gmail.com                                        MCA                                                    
9876543210                                                                                                                                                                                              
                                                                                                                                                                                                        

9 rows selected.

SQL> CREATE TABLE student_copy as select * from student
  2  
SQL> CREATE TABLE student_copy as select * from student;

Table created.

SQL> select * from student_copy;

 ROLL_CALL NAME                                               GENDER                      AGE EMAIL                                              COURSE                                                 
---------- -------------------------------------------------- -------------------- ---------- -------------------------------------------------- --------------------------------------------------     
MOBILE_NUMBER                                      GRADING                                                                                                                                              
-------------------------------------------------- --------------------------------------------------                                                                                                   
         1 Hetuk                                              M                            20 hetuk@gmail.com                                    MCA                                                    
12315641534                                                                                                                                                                                             
                                                                                                                                                                                                        
         2 Aryan                                              M                            22 aryan@gmail.com                                    MCA                                                    
123156415345                                                                                                                                                                                            
                                                                                                                                                                                                        
         4 Rupal                                              F                            24 rupal@gmail.com                                    MCA Second Year                                        
123156415346                                                                                                                                                                                            
                                                                                                                                                                                                        
         5 Rupesh                                             M                            26 rupesh@gmail.com                                   MBA Second Year                                        
123156415347                                                                                                                                                                                            
                                                                                                                                                                                                        
         6 Light                                              M                            28 light@gmail.com                                    MCA                                                    
123156415348                                                                                                                                                                                            
                                                                                                                                                                                                        
         7 Mohit                                              M                            29 m@gmail.com                                        MCA                                                    
123156415349                                                                                                                                                                                            
                                                                                                                                                                                                        
         8 Ram                                                M                            27 r@gmail.com                                        MCA                                                    
123156415340                                                                                                                                                                                            
                                                                                                                                                                                                        
         9 Ravan                                              M                            25 ra@gmail.com                                       MBA                                                    
123156415341                                                                                                                                                                                            
                                                                                                                                                                                                        
        10 Sita                                               F                            21 s@gmail.com                                        MCA                                                    
9876543210                                                                                                                                                                                              
                                                                                                                                                                                                        

9 rows selected.

SQL> desc student_copy
 Name                                                                                                              Null?    Type
 ----------------------------------------------------------------------------------------------------------------- -------- ----------------------------------------------------------------------------
 ROLL_CALL                                                                                                                  NUMBER(4)
 NAME                                                                                                                       VARCHAR2(50)
 GENDER                                                                                                                     VARCHAR2(20)
 AGE                                                                                                                        NUMBER(3)
 EMAIL                                                                                                                      VARCHAR2(50)
 COURSE                                                                                                                     VARCHAR2(50)
 MOBILE_NUMBER                                                                                                              VARCHAR2(50)
 GRADING                                                                                                                    VARCHAR2(50)

SQL> set pagesize 100
SQL> set linesize 100
SQL> desc student_copy
 Name                                                  Null?    Type
 ----------------------------------------------------- -------- ------------------------------------
 ROLL_CALL                                                      NUMBER(4)
 NAME                                                           VARCHAR2(50)
 GENDER                                                         VARCHAR2(20)
 AGE                                                            NUMBER(3)
 EMAIL                                                          VARCHAR2(50)
 COURSE                                                         VARCHAR2(50)
 MOBILE_NUMBER                                                  VARCHAR2(50)
 GRADING                                                        VARCHAR2(50)

SQL> select * from student_copy;

 ROLL_CALL NAME                                               GENDER                      AGE       
---------- -------------------------------------------------- -------------------- ----------       
EMAIL                                                                                               
--------------------------------------------------                                                  
COURSE                                                                                              
--------------------------------------------------                                                  
MOBILE_NUMBER                                                                                       
--------------------------------------------------                                                  
GRADING                                                                                             
--------------------------------------------------                                                  
         1 Hetuk                                              M                            20       
hetuk@gmail.com                                                                                     
MCA                                                                                                 
12315641534                                                                                         
                                                                                                    
                                                                                                    
         2 Aryan                                              M                            22       
aryan@gmail.com                                                                                     
MCA                                                                                                 
123156415345                                                                                        
                                                                                                    
                                                                                                    
         4 Rupal                                              F                            24       
rupal@gmail.com                                                                                     
MCA Second Year                                                                                     
123156415346                                                                                        
                                                                                                    
                                                                                                    
         5 Rupesh                                             M                            26       
rupesh@gmail.com                                                                                    
MBA Second Year                                                                                     
123156415347                                                                                        
                                                                                                    
                                                                                                    
         6 Light                                              M                            28       
light@gmail.com                                                                                     
MCA                                                                                                 
123156415348                                                                                        
                                                                                                    
                                                                                                    
         7 Mohit                                              M                            29       
m@gmail.com                                                                                         
MCA                                                                                                 
123156415349                                                                                        
                                                                                                    
                                                                                                    
         8 Ram                                                M                            27       
r@gmail.com                                                                                         
MCA                                                                                                 
123156415340                                                                                        
                                                                                                    
                                                                                                    
         9 Ravan                                              M                            25       
ra@gmail.com                                                                                        
MBA                                                                                                 
123156415341                                                                                        
                                                                                                    
                                                                                                    
        10 Sita                                               F                            21       
s@gmail.com                                                                                         
MCA                                                                                                 
9876543210                                                                                          
                                                                                                    
                                                                                                    

9 rows selected.

SQL> set linesize 200
SQL> select * from student_copy;

 ROLL_CALL NAME                                               GENDER                      AGE EMAIL                                              COURSE                                                 
---------- -------------------------------------------------- -------------------- ---------- -------------------------------------------------- --------------------------------------------------     
MOBILE_NUMBER                                      GRADING                                                                                                                                              
-------------------------------------------------- --------------------------------------------------                                                                                                   
         1 Hetuk                                              M                            20 hetuk@gmail.com                                    MCA                                                    
12315641534                                                                                                                                                                                             
                                                                                                                                                                                                        
         2 Aryan                                              M                            22 aryan@gmail.com                                    MCA                                                    
123156415345                                                                                                                                                                                            
                                                                                                                                                                                                        
         4 Rupal                                              F                            24 rupal@gmail.com                                    MCA Second Year                                        
123156415346                                                                                                                                                                                            
                                                                                                                                                                                                        
         5 Rupesh                                             M                            26 rupesh@gmail.com                                   MBA Second Year                                        
123156415347                                                                                                                                                                                            
                                                                                                                                                                                                        
         6 Light                                              M                            28 light@gmail.com                                    MCA                                                    
123156415348                                                                                                                                                                                            
                                                                                                                                                                                                        
         7 Mohit                                              M                            29 m@gmail.com                                        MCA                                                    
123156415349                                                                                                                                                                                            
                                                                                                                                                                                                        
         8 Ram                                                M                            27 r@gmail.com                                        MCA                                                    
123156415340                                                                                                                                                                                            
                                                                                                                                                                                                        
         9 Ravan                                              M                            25 ra@gmail.com                                       MBA                                                    
123156415341                                                                                                                                                                                            
                                                                                                                                                                                                        
        10 Sita                                               F                            21 s@gmail.com                                        MCA                                                    
9876543210                                                                                                                                                                                              
                                                                                                                                                                                                        

9 rows selected.

SQL> create table student_basic as
  2  select roll_call, name, gender,course from student;

Table created.

SQL> select * from student_basic;

 ROLL_CALL NAME                                               GENDER               COURSE                                                                                                               
---------- -------------------------------------------------- -------------------- --------------------------------------------------                                                                   
         1 Hetuk                                              M                    MCA                                                                                                                  
         2 Aryan                                              M                    MCA                                                                                                                  
         4 Rupal                                              F                    MCA Second Year                                                                                                      
         5 Rupesh                                             M                    MBA Second Year                                                                                                      
         6 Light                                              M                    MCA                                                                                                                  
         7 Mohit                                              M                    MCA                                                                                                                  
         8 Ram                                                M                    MCA                                                                                                                  
         9 Ravan                                              M                    MBA                                                                                                                  
        10 Sita                                               F                    MCA                                                                                                                  

9 rows selected.

SQL> select * from student
  2  as where course = ""
  3  
SQL> create table mca_students as
  2  select * from students
  3  where course = 'MCA';
select * from students
              *
ERROR at line 2:
ORA-00942: table or view does not exist 


SQL> create table mca_students as
  2  select * from student
  3  where course = 'MCA';

Table created.

SQL> select * from mca_student
  2  
SQL> select * from mca_student;
select * from mca_student
              *
ERROR at line 1:
ORA-00942: table or view does not exist 


SQL> select * from mca_students;

 ROLL_CALL NAME                                               GENDER                      AGE EMAIL                                              COURSE                                                 
---------- -------------------------------------------------- -------------------- ---------- -------------------------------------------------- --------------------------------------------------     
MOBILE_NUMBER                                      GRADING                                                                                                                                              
-------------------------------------------------- --------------------------------------------------                                                                                                   
         1 Hetuk                                              M                            20 hetuk@gmail.com                                    MCA                                                    
12315641534                                                                                                                                                                                             
                                                                                                                                                                                                        
         2 Aryan                                              M                            22 aryan@gmail.com                                    MCA                                                    
123156415345                                                                                                                                                                                            
                                                                                                                                                                                                        
         6 Light                                              M                            28 light@gmail.com                                    MCA                                                    
123156415348                                                                                                                                                                                            
                                                                                                                                                                                                        
         7 Mohit                                              M                            29 m@gmail.com                                        MCA                                                    
123156415349                                                                                                                                                                                            
                                                                                                                                                                                                        
         8 Ram                                                M                            27 r@gmail.com                                        MCA                                                    
123156415340                                                                                                                                                                                            
                                                                                                                                                                                                        
        10 Sita                                               F                            21 s@gmail.com                                        MCA                                                    
9876543210                                                                                                                                                                                              
                                                                                                                                                                                                        

6 rows selected.

SQL> create table male_students as
  2  select roll_call, name, age, gender, course from student
  3  where gender = 'Male';

Table created.

SQL> select * from male_students
  2  
SQL> select * from male_students;

no rows selected

SQL> create table male_student as
  2  select roll_call, name, age, gender, course from student
  3  where gender = 'M';

Table created.

SQL> select * from male_student;

 ROLL_CALL NAME                                                      AGE GENDER               COURSE                                                                                                    
---------- -------------------------------------------------- ---------- -------------------- --------------------------------------------------                                                        
         1 Hetuk                                                      20 M                    MCA                                                                                                       
         2 Aryan                                                      22 M                    MCA                                                                                                       
         5 Rupesh                                                     26 M                    MBA Second Year                                                                                           
         6 Light                                                      28 M                    MCA                                                                                                       
         7 Mohit                                                      29 M                    MCA                                                                                                       
         8 Ram                                                        27 M                    MCA                                                                                                       
         9 Ravan                                                      25 M                    MBA                                                                                                       

7 rows selected.

SQL> select * from student;

 ROLL_CALL NAME                                               GENDER                      AGE EMAIL                                              COURSE                                                 
---------- -------------------------------------------------- -------------------- ---------- -------------------------------------------------- --------------------------------------------------     
MOBILE_NUMBER                                      GRADING                                                                                                                                              
-------------------------------------------------- --------------------------------------------------                                                                                                   
         1 Hetuk                                              M                            20 hetuk@gmail.com                                    MCA                                                    
12315641534                                                                                                                                                                                             
                                                                                                                                                                                                        
         2 Aryan                                              M                            22 aryan@gmail.com                                    MCA                                                    
123156415345                                                                                                                                                                                            
                                                                                                                                                                                                        
         4 Rupal                                              F                            24 rupal@gmail.com                                    MCA Second Year                                        
123156415346                                                                                                                                                                                            
                                                                                                                                                                                                        
         5 Rupesh                                             M                            26 rupesh@gmail.com                                   MBA Second Year                                        
123156415347                                                                                                                                                                                            
                                                                                                                                                                                                        
         6 Light                                              M                            28 light@gmail.com                                    MCA                                                    
123156415348                                                                                                                                                                                            
                                                                                                                                                                                                        
         7 Mohit                                              M                            29 m@gmail.com                                        MCA                                                    
123156415349                                                                                                                                                                                            
                                                                                                                                                                                                        
         8 Ram                                                M                            27 r@gmail.com                                        MCA                                                    
123156415340                                                                                                                                                                                            
                                                                                                                                                                                                        
         9 Ravan                                              M                            25 ra@gmail.com                                       MBA                                                    
123156415341                                                                                                                                                                                            
                                                                                                                                                                                                        
        10 Sita                                               F                            21 s@gmail.com                                        MCA                                                    
9876543210                                                                                                                                                                                              
                                                                                                                                                                                                        

9 rows selected.

SQL> create table senior_students as
  2  select * from student where age > 22
  3  ;

Table created.

SQL> select * from senior_students
  2  ;

 ROLL_CALL NAME                                               GENDER                      AGE EMAIL                                              COURSE                                                 
---------- -------------------------------------------------- -------------------- ---------- -------------------------------------------------- --------------------------------------------------     
MOBILE_NUMBER                                      GRADING                                                                                                                                              
-------------------------------------------------- --------------------------------------------------                                                                                                   
         4 Rupal                                              F                            24 rupal@gmail.com                                    MCA Second Year                                        
123156415346                                                                                                                                                                                            
                                                                                                                                                                                                        
         5 Rupesh                                             M                            26 rupesh@gmail.com                                   MBA Second Year                                        
123156415347                                                                                                                                                                                            
                                                                                                                                                                                                        
         6 Light                                              M                            28 light@gmail.com                                    MCA                                                    
123156415348                                                                                                                                                                                            
                                                                                                                                                                                                        
         7 Mohit                                              M                            29 m@gmail.com                                        MCA                                                    
123156415349                                                                                                                                                                                            
                                                                                                                                                                                                        
         8 Ram                                                M                            27 r@gmail.com                                        MCA                                                    
123156415340                                                                                                                                                                                            
                                                                                                                                                                                                        
         9 Ravan                                              M                            25 ra@gmail.com                                       MBA                                                    
123156415341                                                                                                                                                                                            
                                                                                                                                                                                                        

6 rows selected.

SQL> create table student_template as
  2  select * from student where age < 1;

Table created.

SQL> select * from student_template
  2  ;

no rows selected

SQL> desc student_template
 Name                                                                                                              Null?    Type
 ----------------------------------------------------------------------------------------------------------------- -------- ----------------------------------------------------------------------------
 ROLL_CALL                                                                                                                  NUMBER(4)
 NAME                                                                                                                       VARCHAR2(50)
 GENDER                                                                                                                     VARCHAR2(20)
 AGE                                                                                                                        NUMBER(3)
 EMAIL                                                                                                                      VARCHAR2(50)
 COURSE                                                                                                                     VARCHAR2(50)
 MOBILE_NUMBER                                                                                                              VARCHAR2(50)
 GRADING                                                                                                                    VARCHAR2(50)

SQL> create table student_age_details as
  2  select roll_call, name, age, age+1 as next_year_age from student;

Table created.

SQL> desc student_age_details
 Name                                                                                                              Null?    Type
 ----------------------------------------------------------------------------------------------------------------- -------- ----------------------------------------------------------------------------
 ROLL_CALL                                                                                                                  NUMBER(4)
 NAME                                                                                                                       VARCHAR2(50)
 AGE                                                                                                                        NUMBER(3)
 NEXT_YEAR_AGE                                                                                                              NUMBER

SQL> select * from student_age_details
  2  ;

 ROLL_CALL NAME                                                      AGE NEXT_YEAR_AGE                                                                                                                  
---------- -------------------------------------------------- ---------- -------------                                                                                                                  
         1 Hetuk                                                      20            21                                                                                                                  
         2 Aryan                                                      22            23                                                                                                                  
         4 Rupal                                                      24            25                                                                                                                  
         5 Rupesh                                                     26            27                                                                                                                  
         6 Light                                                      28            29                                                                                                                  
         7 Mohit                                                      29            30                                                                                                                  
         8 Ram                                                        27            28                                                                                                                  
         9 Ravan                                                      25            26                                                                                                                  
        10 Sita                                                       21            22                                                                                                                  

9 rows selected.

SQL> commit
  2  
SQL> commit;

Commit complete.

SQL> create table student_info as
  2  select roll_call as roll_no, name as student_name, course as program, mobile_number as contact_number from student;

Table created.

SQL> select * from student_info;

   ROLL_NO STUDENT_NAME                                       PROGRAM                                            CONTACT_NUMBER                                                                         
---------- -------------------------------------------------- -------------------------------------------------- --------------------------------------------------                                     
         1 Hetuk                                              MCA                                                12315641534                                                                            
         2 Aryan                                              MCA                                                123156415345                                                                           
         4 Rupal                                              MCA Second Year                                    123156415346                                                                           
         5 Rupesh                                             MBA Second Year                                    123156415347                                                                           
         6 Light                                              MCA                                                123156415348                                                                           
         7 Mohit                                              MCA                                                123156415349                                                                           
         8 Ram                                                MCA                                                123156415340                                                                           
         9 Ravan                                              MBA                                                123156415341                                                                           
        10 Sita                                               MCA                                                9876543210                                                                             

9 rows selected.

SQL> create table student_contact as
  2  select roll_call || '-' || name as student_details, gender from student;

Table created.

SQL> select * from student_contact;

STUDENT_DETAILS                                                                             GENDER                                                                                                      
------------------------------------------------------------------------------------------- --------------------                                                                                        
1-Hetuk                                                                                     M                                                                                                           
2-Aryan                                                                                     M                                                                                                           
4-Rupal                                                                                     F                                                                                                           
5-Rupesh                                                                                    M                                                                                                           
6-Light                                                                                     M                                                                                                           
7-Mohit                                                                                     M                                                                                                           
8-Ram                                                                                       M                                                                                                           
9-Ravan                                                                                     M                                                                                                           
10-Sita                                                                                     F                                                                                                           

9 rows selected.

SQL> spool off
