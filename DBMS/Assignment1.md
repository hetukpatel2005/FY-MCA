SQL> select patient_id, patient_name, disease, doctor_name, fees from patient_details;

PATIENT_ID PATIENT_NAME                   DISEASE                        DOCTOR_NAME                                    FEES                                                                                                                              
---------- ------------------------------ ------------------------------ ---------------------------------------- ----------                                                                                                                              
       101 Rahul Sharma                   Fever                          Dr. Amit Patel                                  500                                                                                                                              
       102 Priya Shah                     Diabetes                       Dr. Neha Mehta                                  800                                                                                                                              
       103 Arjun Verma                    Heart Disease                  Dr. Raj Malhotra                               1500                                                                                                                              
       104 Sneha Joshi                    Asthma                         Dr. Kavita Rao                                  700                                                                                                                              
       105 Vikram Singh                   Arthritis                      Dr. Rakesh Gupta                               1000                                                                                                                              
       106 Anjali Desai                   Migraine                       Dr. Pooja Shah                                  900                                                                                                                              
       107 Karan Mehta                    Cold and Cough                 Dr. Sanjay Kumar                                400                                                                                                                              
       108 Riya Kapoor                    Skin Allergy                   Dr. Nisha Kapoor                                650                                                                                                                              
       109 Mohit Agarwal                  Kidney Stone                   Dr. Manish Jain                                1200                                                                                                                              
       110 Meera Iyer                     Blood Pressure                 Dr. Sunita Rao                                  750                                                                                                                              

10 rows selected.

SQL> update patient_details
  2  set fees = 15000
  3  where patient_id = 103;

1 row updated.

SQL> select * from patient_details;

PATIENT_ID PATIENT_NAME                   GENDER             AGE DISEASE                        DOCTOR_NAME                              DEPARTMENT                     LOCATION                             FEES ADMISSION_DATE                          
---------- ------------------------------ ----------- ---------- ------------------------------ ---------------------------------------- ------------------------------ ------------------------------ ---------- ----------------------------------------
CONTACT_NO                                                                                                                                                                                                                                                
----------                                                                                                                                                                                                                                                
       101 Rahul Sharma                   Male                25 Fever                          Dr. Amit Patel                           General Medicine               Mumbai                                500 01-09-2026                              
9876543210                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       102 Priya Shah                     Female              32 Diabetes                       Dr. Neha Mehta                           Endocrinology                  Ahmedabad                             800 02-09-2026                              
9876543211                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       103 Arjun Verma                    Male                45 Heart Disease                  Dr. Raj Malhotra                         Cardiology                     Delhi                               15000 03-09-2026                              
9876543212                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       104 Sneha Joshi                    Female              19 Asthma                         Dr. Kavita Rao                           Pulmonology                    Pune                                  700 03-09-2026                              
9876543213                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       105 Vikram Singh                   Male                67 Arthritis                      Dr. Rakesh Gupta                         Orthopedics                    Jaipur                               1000 04-09-2026                              
9876543214                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       106 Anjali Desai                   Female              54 Migraine                       Dr. Pooja Shah                           Neurology                      Surat                                 900 05-09-2026                              
9876543215                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       107 Karan Mehta                    Male                 8 Cold and Cough                 Dr. Sanjay Kumar                         Pediatrics                     Bangalore                             400 05-09-2026                              
9876543216                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       108 Riya Kapoor                    Female              29 Skin Allergy                   Dr. Nisha Kapoor                         Dermatology                    Kolkata                               650 06-09-2026                              
9876543217                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       109 Mohit Agarwal                  Male                38 Kidney Stone                   Dr. Manish Jain                          Urology                        Hyderabad                            1200 07-09-2026                              
9876543218                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       110 Meera Iyer                     Female              72 Blood Pressure                 Dr. Sunita Rao                           General Medicine               Chennai                               750 08-09-2026                              
9876543219                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          

10 rows selected.

SQL> delete from patient_details where 110;
delete from patient_details where 110
                                    *
ERROR at line 1:
ORA-00920: invalid relational operator 


SQL> delete from patient_details where patient_id = 110;

1 row deleted.

SQL> select * from patient_details;

PATIENT_ID PATIENT_NAME                   GENDER             AGE DISEASE                        DOCTOR_NAME                              DEPARTMENT                     LOCATION                             FEES ADMISSION_DATE                          
---------- ------------------------------ ----------- ---------- ------------------------------ ---------------------------------------- ------------------------------ ------------------------------ ---------- ----------------------------------------
CONTACT_NO                                                                                                                                                                                                                                                
----------                                                                                                                                                                                                                                                
       101 Rahul Sharma                   Male                25 Fever                          Dr. Amit Patel                           General Medicine               Mumbai                                500 01-09-2026                              
9876543210                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       102 Priya Shah                     Female              32 Diabetes                       Dr. Neha Mehta                           Endocrinology                  Ahmedabad                             800 02-09-2026                              
9876543211                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       103 Arjun Verma                    Male                45 Heart Disease                  Dr. Raj Malhotra                         Cardiology                     Delhi                               15000 03-09-2026                              
9876543212                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       104 Sneha Joshi                    Female              19 Asthma                         Dr. Kavita Rao                           Pulmonology                    Pune                                  700 03-09-2026                              
9876543213                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       105 Vikram Singh                   Male                67 Arthritis                      Dr. Rakesh Gupta                         Orthopedics                    Jaipur                               1000 04-09-2026                              
9876543214                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       106 Anjali Desai                   Female              54 Migraine                       Dr. Pooja Shah                           Neurology                      Surat                                 900 05-09-2026                              
9876543215                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       107 Karan Mehta                    Male                 8 Cold and Cough                 Dr. Sanjay Kumar                         Pediatrics                     Bangalore                             400 05-09-2026                              
9876543216                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       108 Riya Kapoor                    Female              29 Skin Allergy                   Dr. Nisha Kapoor                         Dermatology                    Kolkata                               650 06-09-2026                              
9876543217                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       109 Mohit Agarwal                  Male                38 Kidney Stone                   Dr. Manish Jain                          Urology                        Hyderabad                            1200 07-09-2026                              
9876543218                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          

9 rows selected.

SQL> CREATE TABLE PATIENT_COPY AS
  2  SELECT * FROM PATIENT_DETAILS;

Table created.

SQL> select * from patient_copy;

PATIENT_ID PATIENT_NAME                   GENDER             AGE DISEASE                        DOCTOR_NAME                              DEPARTMENT                     LOCATION                             FEES ADMISSION_DATE                          
---------- ------------------------------ ----------- ---------- ------------------------------ ---------------------------------------- ------------------------------ ------------------------------ ---------- ----------------------------------------
CONTACT_NO                                                                                                                                                                                                                                                
----------                                                                                                                                                                                                                                                
       101 Rahul Sharma                   Male                25 Fever                          Dr. Amit Patel                           General Medicine               Mumbai                                500 01-09-2026                              
9876543210                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       102 Priya Shah                     Female              32 Diabetes                       Dr. Neha Mehta                           Endocrinology                  Ahmedabad                             800 02-09-2026                              
9876543211                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       103 Arjun Verma                    Male                45 Heart Disease                  Dr. Raj Malhotra                         Cardiology                     Delhi                               15000 03-09-2026                              
9876543212                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       104 Sneha Joshi                    Female              19 Asthma                         Dr. Kavita Rao                           Pulmonology                    Pune                                  700 03-09-2026                              
9876543213                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       105 Vikram Singh                   Male                67 Arthritis                      Dr. Rakesh Gupta                         Orthopedics                    Jaipur                               1000 04-09-2026                              
9876543214                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       106 Anjali Desai                   Female              54 Migraine                       Dr. Pooja Shah                           Neurology                      Surat                                 900 05-09-2026                              
9876543215                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       107 Karan Mehta                    Male                 8 Cold and Cough                 Dr. Sanjay Kumar                         Pediatrics                     Bangalore                             400 05-09-2026                              
9876543216                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       108 Riya Kapoor                    Female              29 Skin Allergy                   Dr. Nisha Kapoor                         Dermatology                    Kolkata                               650 06-09-2026                              
9876543217                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       109 Mohit Agarwal                  Male                38 Kidney Stone                   Dr. Manish Jain                          Urology                        Hyderabad                            1200 07-09-2026                              
9876543218                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          

9 rows selected.

SQL> desc patient_copy;
 Name                                                                                                                                            Null?    Type
 ----------------------------------------------------------------------------------------------------------------------------------------------- -------- ------------------------------------------------------------------------------------------------
 PATIENT_ID                                                                                                                                               NUMBER
 PATIENT_NAME                                                                                                                                             VARCHAR2(30)
 GENDER                                                                                                                                                   VARCHAR2(11)
 AGE                                                                                                                                                      NUMBER
 DISEASE                                                                                                                                                  VARCHAR2(30)
 DOCTOR_NAME                                                                                                                                              VARCHAR2(40)
 DEPARTMENT                                                                                                                                               VARCHAR2(30)
 LOCATION                                                                                                                                                 VARCHAR2(30)
 FEES                                                                                                                                                     NUMBER
 ADMISSION_DATE                                                                                                                                           VARCHAR2(40)
 CONTACT_NO                                                                                                                                               NUMBER

SQL> TRUNCATE TABLE PATIENT_COPY;

Table truncated.

SQL> SELECT * FROM PATIENT_COPY;

no rows selected

SQL> desc patient_copy;
 Name                                                                                                                                            Null?    Type
 ----------------------------------------------------------------------------------------------------------------------------------------------- -------- ------------------------------------------------------------------------------------------------
 PATIENT_ID                                                                                                                                               NUMBER
 PATIENT_NAME                                                                                                                                             VARCHAR2(30)
 GENDER                                                                                                                                                   VARCHAR2(11)
 AGE                                                                                                                                                      NUMBER
 DISEASE                                                                                                                                                  VARCHAR2(30)
 DOCTOR_NAME                                                                                                                                              VARCHAR2(40)
 DEPARTMENT                                                                                                                                               VARCHAR2(30)
 LOCATION                                                                                                                                                 VARCHAR2(30)
 FEES                                                                                                                                                     NUMBER
 ADMISSION_DATE                                                                                                                                           VARCHAR2(40)
 CONTACT_NO                                                                                                                                               NUMBER

SQL> select * from patient_details
  2  where department = 'Cardiology';

PATIENT_ID PATIENT_NAME                   GENDER             AGE DISEASE                        DOCTOR_NAME                              DEPARTMENT                     LOCATION                             FEES ADMISSION_DATE                          
---------- ------------------------------ ----------- ---------- ------------------------------ ---------------------------------------- ------------------------------ ------------------------------ ---------- ----------------------------------------
CONTACT_NO                                                                                                                                                                                                                                                
----------                                                                                                                                                                                                                                                
       103 Arjun Verma                    Male                45 Heart Disease                  Dr. Raj Malhotra                         Cardiology                     Delhi                               15000 03-09-2026                              
9876543212                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          

SQL> select * from patient_details
  2  where age > 40;

PATIENT_ID PATIENT_NAME                   GENDER             AGE DISEASE                        DOCTOR_NAME                              DEPARTMENT                     LOCATION                             FEES ADMISSION_DATE                          
---------- ------------------------------ ----------- ---------- ------------------------------ ---------------------------------------- ------------------------------ ------------------------------ ---------- ----------------------------------------
CONTACT_NO                                                                                                                                                                                                                                                
----------                                                                                                                                                                                                                                                
       103 Arjun Verma                    Male                45 Heart Disease                  Dr. Raj Malhotra                         Cardiology                     Delhi                               15000 03-09-2026                              
9876543212                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       105 Vikram Singh                   Male                67 Arthritis                      Dr. Rakesh Gupta                         Orthopedics                    Jaipur                               1000 04-09-2026                              
9876543214                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       106 Anjali Desai                   Female              54 Migraine                       Dr. Pooja Shah                           Neurology                      Surat                                 900 05-09-2026                              
9876543215                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          

SQL> select * from patient_details
  2  where fees > 5000;

PATIENT_ID PATIENT_NAME                   GENDER             AGE DISEASE                        DOCTOR_NAME                              DEPARTMENT                     LOCATION                             FEES ADMISSION_DATE                          
---------- ------------------------------ ----------- ---------- ------------------------------ ---------------------------------------- ------------------------------ ------------------------------ ---------- ----------------------------------------
CONTACT_NO                                                                                                                                                                                                                                                
----------                                                                                                                                                                                                                                                
       103 Arjun Verma                    Male                45 Heart Disease                  Dr. Raj Malhotra                         Cardiology                     Delhi                               15000 03-09-2026                              
9876543212                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          

SQL> select * from patient_details
  2  where disease = 'Diabetes';

PATIENT_ID PATIENT_NAME                   GENDER             AGE DISEASE                        DOCTOR_NAME                              DEPARTMENT                     LOCATION                             FEES ADMISSION_DATE                          
---------- ------------------------------ ----------- ---------- ------------------------------ ---------------------------------------- ------------------------------ ------------------------------ ---------- ----------------------------------------
CONTACT_NO                                                                                                                                                                                                                                                
----------                                                                                                                                                                                                                                                
       102 Priya Shah                     Female              32 Diabetes                       Dr. Neha Mehta                           Endocrinology                  Ahmedabad                             800 02-09-2026                              
9876543211                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          

SQL> select * from patient_details
  2  where gender = 'Female';

PATIENT_ID PATIENT_NAME                   GENDER             AGE DISEASE                        DOCTOR_NAME                              DEPARTMENT                     LOCATION                             FEES ADMISSION_DATE                          
---------- ------------------------------ ----------- ---------- ------------------------------ ---------------------------------------- ------------------------------ ------------------------------ ---------- ----------------------------------------
CONTACT_NO                                                                                                                                                                                                                                                
----------                                                                                                                                                                                                                                                
       102 Priya Shah                     Female              32 Diabetes                       Dr. Neha Mehta                           Endocrinology                  Ahmedabad                             800 02-09-2026                              
9876543211                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       104 Sneha Joshi                    Female              19 Asthma                         Dr. Kavita Rao                           Pulmonology                    Pune                                  700 03-09-2026                              
9876543213                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       106 Anjali Desai                   Female              54 Migraine                       Dr. Pooja Shah                           Neurology                      Surat                                 900 05-09-2026                              
9876543215                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       108 Riya Kapoor                    Female              29 Skin Allergy                   Dr. Nisha Kapoor                         Dermatology                    Kolkata                               650 06-09-2026                              
9876543217                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          

SQL> select * from patient_details
  2  where location = 'Mumbai';

PATIENT_ID PATIENT_NAME                   GENDER             AGE DISEASE                        DOCTOR_NAME                              DEPARTMENT                     LOCATION                             FEES ADMISSION_DATE                          
---------- ------------------------------ ----------- ---------- ------------------------------ ---------------------------------------- ------------------------------ ------------------------------ ---------- ----------------------------------------
CONTACT_NO                                                                                                                                                                                                                                                
----------                                                                                                                                                                                                                                                
       101 Rahul Sharma                   Male                25 Fever                          Dr. Amit Patel                           General Medicine               Mumbai                                500 01-09-2026                              
9876543210                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          

SQL> select * from patient_details
  2  where department = 'Cardiology' and fees > 5000;

PATIENT_ID PATIENT_NAME                   GENDER             AGE DISEASE                        DOCTOR_NAME                              DEPARTMENT                     LOCATION                             FEES ADMISSION_DATE                          
---------- ------------------------------ ----------- ---------- ------------------------------ ---------------------------------------- ------------------------------ ------------------------------ ---------- ----------------------------------------
CONTACT_NO                                                                                                                                                                                                                                                
----------                                                                                                                                                                                                                                                
       103 Arjun Verma                    Male                45 Heart Disease                  Dr. Raj Malhotra                         Cardiology                     Delhi                               15000 03-09-2026                              
9876543212                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          

SQL> select * from patient_details
  2  where department = 'Cardiology' or department = 'Neurology';

PATIENT_ID PATIENT_NAME                   GENDER             AGE DISEASE                        DOCTOR_NAME                              DEPARTMENT                     LOCATION                             FEES ADMISSION_DATE                          
---------- ------------------------------ ----------- ---------- ------------------------------ ---------------------------------------- ------------------------------ ------------------------------ ---------- ----------------------------------------
CONTACT_NO                                                                                                                                                                                                                                                
----------                                                                                                                                                                                                                                                
       103 Arjun Verma                    Male                45 Heart Disease                  Dr. Raj Malhotra                         Cardiology                     Delhi                               15000 03-09-2026                              
9876543212                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       106 Anjali Desai                   Female              54 Migraine                       Dr. Pooja Shah                           Neurology                      Surat                                 900 05-09-2026                              
9876543215                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          

SQL> select * from patient_details
  2  where department = 'Cardiology' and age > 50;

no rows selected

SQL> select * from patient_details
  2  where department != 'Pediatrics';

PATIENT_ID PATIENT_NAME                   GENDER             AGE DISEASE                        DOCTOR_NAME                              DEPARTMENT                     LOCATION                             FEES ADMISSION_DATE                          
---------- ------------------------------ ----------- ---------- ------------------------------ ---------------------------------------- ------------------------------ ------------------------------ ---------- ----------------------------------------
CONTACT_NO                                                                                                                                                                                                                                                
----------                                                                                                                                                                                                                                                
       101 Rahul Sharma                   Male                25 Fever                          Dr. Amit Patel                           General Medicine               Mumbai                                500 01-09-2026                              
9876543210                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       102 Priya Shah                     Female              32 Diabetes                       Dr. Neha Mehta                           Endocrinology                  Ahmedabad                             800 02-09-2026                              
9876543211                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       103 Arjun Verma                    Male                45 Heart Disease                  Dr. Raj Malhotra                         Cardiology                     Delhi                               15000 03-09-2026                              
9876543212                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       104 Sneha Joshi                    Female              19 Asthma                         Dr. Kavita Rao                           Pulmonology                    Pune                                  700 03-09-2026                              
9876543213                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       105 Vikram Singh                   Male                67 Arthritis                      Dr. Rakesh Gupta                         Orthopedics                    Jaipur                               1000 04-09-2026                              
9876543214                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       106 Anjali Desai                   Female              54 Migraine                       Dr. Pooja Shah                           Neurology                      Surat                                 900 05-09-2026                              
9876543215                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       108 Riya Kapoor                    Female              29 Skin Allergy                   Dr. Nisha Kapoor                         Dermatology                    Kolkata                               650 06-09-2026                              
9876543217                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          
       109 Mohit Agarwal                  Male                38 Kidney Stone                   Dr. Manish Jain                          Urology                        Hyderabad                            1200 07-09-2026                              
9876543218                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          

8 rows selected.

SQL> select * from patient_details
  2  where department = 'Cardiology' and age > 40 and fees > 4000;

PATIENT_ID PATIENT_NAME                   GENDER             AGE DISEASE                        DOCTOR_NAME                              DEPARTMENT                     LOCATION                             FEES ADMISSION_DATE                          
---------- ------------------------------ ----------- ---------- ------------------------------ ---------------------------------------- ------------------------------ ------------------------------ ---------- ----------------------------------------
CONTACT_NO                                                                                                                                                                                                                                                
----------                                                                                                                                                                                                                                                
       103 Arjun Verma                    Male                45 Heart Disease                  Dr. Raj Malhotra                         Cardiology                     Delhi                               15000 03-09-2026                              
9876543212                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                          

SQL> select * from patient_details
  2  where department = 'Neurology' and fees > 3000
  3  order by fees desc;

no rows selected

SQL> spool off;
