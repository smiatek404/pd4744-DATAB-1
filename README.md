# pd4744-DATAB-1
**Schema (MySQL v5.7)**

    CREATE TABLE patients (
        id INT PRIMARY KEY,
        name VARCHAR(255),
      	date_of_birth DATETIME,
      	email VARCHAR(255),
      	phone_number BIGINT,
      	weight DOUBLE (5,2),
      	height INT
    );

---

**Query #1**

    INSERT INTO patients (id, name, date_of_birth, email, phone_number, weight, height)
    VALUES 
    (1, 'John Doe', '1985-06-15', 'john.doe@gmail.com', 1234567890, 72.50, 180),
    (2, 'Jane Smith', '1990-03-20', 'jane.smith@gmail.com', 987654321, 60.00, 165),
    (3, 'Maria Garcia', '1978-12-05', NULL, 1122334455, 68.00, 170),
    (4, 'James Brown', '2000-07-15', 'james.brown@yahoo.com', 5566778899, 80.25, 175),
    (5, 'Emily Davis', '1995-02-10', 'emily.davis@outlook.com', 6677889900, 55.50, 160);

There are no results to be displayed.

---
**Query #2**

    
    
    select * from patients;

| id  | name         | date_of_birth | email                   | phone_number | weight | height |
| --- | ------------ | ------------- | ----------------------- | ------------ | ------ | ------ |
| 1   | John Doe     | 1985-06-15    | john.doe@gmail.com      | 1234567890   | 72.5   | 180    |
| 2   | Jane Smith   | 1990-03-20    | jane.smith@gmail.com    | 987654321    | 60     | 165    |
| 3   | Maria Garcia | 1978-12-05    |                         | 1122334455   | 68     | 170    |
| 4   | James Brown  | 2000-07-15    | james.brown@yahoo.com   | 5566778899   | 80.25  | 175    |
| 5   | Emily Davis  | 1995-02-10    | emily.davis@outlook.com | 6677889900   | 55.5   | 160    |

---
**Query #3**

    
    select * from patients where weight < 65.00;

| id  | name        | date_of_birth | email                   | phone_number | weight | height |
| --- | ----------- | ------------- | ----------------------- | ------------ | ------ | ------ |
| 2   | Jane Smith  | 1990-03-20    | jane.smith@gmail.com    | 987654321    | 60     | 165    |
| 5   | Emily Davis | 1995-02-10    | emily.davis@outlook.com | 6677889900   | 55.5   | 160    |

---
**Query #4**

    
    select * from patients order by height DESC;

| id  | name         | date_of_birth | email                   | phone_number | weight | height |
| --- | ------------ | ------------- | ----------------------- | ------------ | ------ | ------ |
| 1   | John Doe     | 1985-06-15    | john.doe@gmail.com      | 1234567890   | 72.5   | 180    |
| 4   | James Brown  | 2000-07-15    | james.brown@yahoo.com   | 5566778899   | 80.25  | 175    |
| 3   | Maria Garcia | 1978-12-05    |                         | 1122334455   | 68     | 170    |
| 2   | Jane Smith   | 1990-03-20    | jane.smith@gmail.com    | 987654321    | 60     | 165    |
| 5   | Emily Davis  | 1995-02-10    | emily.davis@outlook.com | 6677889900   | 55.5   | 160    |

---

[View on DB Fiddle](https://www.db-fiddle.com/)


**Schema (MySQL v5.7)**

    CREATE TABLE patients (
        id INT PRIMARY KEY,
        name VARCHAR(255),
      	date_of_birth DATETIME,
      	email VARCHAR(255),
      	phone_number BIGINT,
      	weight DOUBLE (5,2),
      	height INT
    );
    
    INSERT INTO patients (id, name, date_of_birth, email, phone_number, weight, height)
        VALUES 
        (1, 'John Doe', '1985-06-15', 'john.doe@gmail.com', 1234567890, 72.50, 180),
        (2, 'Jane Smith', '1990-03-20', 'jane.smith@gmail.com', 987654321, 60.00, 165),
        (3, 'Maria Garcia', '1978-12-05', NULL, 1122334455, 68.00, 170),
        (4, 'James Brown', '2000-07-15', 'james.brown@yahoo.com', 5566778899, 80.25, 175),
        (5, 'Emily Davis', '1995-02-10', 'emily.davis@outlook.com', 6677889900, 55.50, 160);

---

**Query #1**

    update patients set email = 'john.updated@gmail.com' where name = 'John Doe';

There are no results to be displayed.

---
**Query #2**

    
    delete from patients where id = 3;

There are no results to be displayed.

---
**Query #3**

    
    alter table patients add blood_type CHAR(3);

There are no results to be displayed.

---
**Query #4**

    
    UPDATE patients
    SET blood_type = '0+'
    WHERE name = 'John Doe';

There are no results to be displayed.

---
**Query #5**

    
    
    UPDATE patients
    SET blood_type = 'AB+'
    WHERE name = 'Jane Smith';

There are no results to be displayed.

---
**Query #6**

    
    
    UPDATE patients
    SET blood_type = 'A-'
    WHERE name = 'James Brown';

There are no results to be displayed.

---
**Query #7**

    
    
    UPDATE patients
    SET blood_type = 'B+'
    WHERE name = 'Emily Davis';

There are no results to be displayed.

---
**Query #8**

    
    
    SELECT * FROM patients
    LIMIT 2 OFFSET 2;

| id  | name        | date_of_birth | email                   | phone_number | weight | height | blood_type |
| --- | ----------- | ------------- | ----------------------- | ------------ | ------ | ------ | ---------- |
| 4   | James Brown | 2000-07-15    | james.brown@yahoo.com   | 5566778899   | 80.25  | 175    | A-         |
| 5   | Emily Davis | 1995-02-10    | emily.davis@outlook.com | 6677889900   | 55.5   | 160    | B+         |

---

[View on DB Fiddle](https://www.db-fiddle.com/)
